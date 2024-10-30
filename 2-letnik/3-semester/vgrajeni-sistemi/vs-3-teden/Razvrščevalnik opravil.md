[[predavanje-vs-4-teden]]; #vs-flashcards 

Oziroma "scheduler".

<font color="#92cddc">Vsako</font> opravilo ima svoj <font color="#92cddc">sklad</font>. 

Opravilo se samo po sebi ne sme zaključiti, zato tudi ničesar ne vrača (void), prav tako pa se jih ne da poklicati.

npr. imamo 4 opravila
- ko se prekine prvo opravilo in se začne prekinitveno servisni program, se ne želimo vrniti nazaj na prvo opravilo ampak na drugo.
- zato naredi hardware destacking iz skladu drugega opravila.
- zato imamo rezervirano prostora v pomnilniku, da bo zadoščal za sklad vsakega od štirih opravil - $stackRegion$, ki ga navidezno razdelimo na štiri in imamo tako štiri kazalce, ki je dodeljen ustreznemu opravilu.

Imamo tudi $Task Control Block$, ki ima dva kazalca, enega za naslov opravila in eno za naslov njegovega sklada.

In funkcijo $TaskCreate$, ki napolni TaskControlBlock posameznega opravila. 

Opravila se vrtijo v neskončni zanki, ves čas.

```C
void task1(){
	while(1){
		}
}
```

Morajo imeti tudi že <font color="#92cddc">inicializiran sklad</font> - napolniti sklad, najmanj tistih 8 registrov, ki so potrebne za hardware destacking, ker tudi ko opravilo prvič "pokličem", se izvede HD. Od registra $R0$ do $R3$ in $R12$ ter $LR$ je čisto vseeno, kaj dam notri (za $LR$, tudi, ker opravilo nikoli ne vračam). V $PC$ pa se da naslov opravila.

```C
pHWStackFrame->r0 = 0;
pHWStackFrame->r1 = 0;
pHWStackFrame->r2 = 0;
pHWStackFrame->r3 = 0;
pHWStackFrame->r12 = 0;
pHWStackFrame->lr = 0xFFFFFFFF;
pHWStackFrame->pc = pTCB->pTaskFunction;
pHWStackFrame->psr = 0x01000000;
```

Kjer je $pHWStackFrame$ kazalec, ki kaže na skladovni kazalec, na katerega kaže $TCB$ in odštejemo velikost od $HWSF\_Type$.

Na podoben način kot je struktura za dostopanje do registrov, ki so obvezni pri HD. Dodamo še eno strukturo $SWSF\_Type$ (ali software stack frame).

Main bo poklical "Task 0", zato v funkciji $InitScheduler$, kjer inicializiramo scheduler, postavili sklad samo za opravila $(1, 2, ..., n)$ in ne $(0, 1, ..., n)$.

Za Task 0, pa ne, ker ga pokličemo iz main-a in bo prvi prekinjen.

V $TaskFunctions$ tabeli imamo naslove vsakega od opravil, na predavanjih je bilo npr. opravilo na naslovu $0x800060f$, a dejanski naslov je $0x800060e$, saj tista zadnja enica predstavlja samo to, da naj $CPE$ uporablja 16-bitne in ne 32-bitne ukaze.

Če imamo $1kb$ blok za eno opravilo, moramo sami nastaviti skladovni kazalec opravila nastaviti na;; "vrh" tega bloka, ker nam sklad narašča v smeri padajočih naslovov.

Delovanje razvrščevalnika za menjavanje opravil:
1) set context - $\_\_SAVE\_CONTEXT$
2) temp - s funkcijo $ContextSwitch$
3) temp - s funkcijo $ContextSwitch$
4) load psp - s funkcijo $ContextSwitch$
5) restore context - $\_\_RESTORE\_CONTEXT$

Prekinitev z višjo prioriteto lahko prekini prekinitev z nižjo prekinitev (imamo 16 nivojev, kjer je najvišji $reset$ in $hardFault$). Kaj potem če prekinitev prekini drugo prekinitev? Zato obstaja prekinitev z najnižjo prioriteto in se je ne da povečati, to je software-ska prekinitev. Imamo nek SVC - supervisor call.

---

Kolikokrat je poklican $taskInit$, če imamo $n$ opravil?;; $n-1$
<!--SR:!2024-10-27,4,270-->
Kaj vsebuje $TaskControlBlock$?;; Vsebuje dva kazalca, en ki kaže na naslov opravila in drugi na naslov njegovega sklada.
<!--SR:!2024-10-26,3,250-->
Zakaj kaže da je opravilo na naslovu, ki se konča z enico, čeprav se ne konča tako?;; Zato, ker to procesorju pove, da uporablja 16-bitne in ne 32-bitne ukaze.

---



