[[predavanje-vs-1-teden]];
[[izjeme pri ARM Cortex]];
[[predavanje-ors-3-teden]]; #ors-flashcards

Posledica nekega zunanjega vhoda, ne samega procesorja.

![[Prekinitve 2024-10-17 10.42.33.excalidraw]]

<font color="#d83931">Interrupt request</font>;; V/I zahteva od CPE da prekine izvajanje trenutnega programa.
<!--SR:!2024-10-25,2,210-->

Če kdorkoli postavi <font color="#92cddc">IRQ</font> signal v obratno stanje, CPE preneha zajemati ukaze in začne s <font color="#92cddc">prekinitveno-servisnim ciklom</font>. V PC ne gre tako PC + 4, ampak neka nova vrednost.

## Zgled: RISC-V 

![[Prekinitve 2024-10-17 10.51.51.excalidraw]]
Imamo 5 registrov, ki v RISC-V omogočajo implementacijo izjem.

-  <font color="#92cddc">epc register: exception PC</font>;; vanj se shrani naslov, ki ga ob prekinitveni zahtevi hrani PC in ki kaže na ne prevzeti ukaz prekinjenega programa
<!--SR:!2024-10-25,2,230-->
		-> hrani nekakšen "povratni naslov" (ni enako povratnim naslovom v podprogramih)

1) <font color="#92cddc">IRQ</font> prekine izvajanje programa pri ukazu na naslovu v PC
2) epc <- PC
3) PC <- naslov programa "interrupt handlerja"
4) ko zaključimo izvajanje <font color="#92cddc">ISR</font> (interrupt service routine) v PC <- epc, da se znamo <font color="#92cddc">vrnit v prekinjeni program</font>

Celoten ta proces je <font color="#92cddc">transparenten</font>, pomeni, da ustavljen program, ne ve, da je bil ustavljen.

- <font color="#92cddc">ie register: interrupt enable</font>;; omogoča in onemogoča odziv CPE na prekinitvene zahteve in <font color="#c00000">ne</font> vpliva na <font color="#c00000">pasti</font>. ![[Prekinitve 2024-10-17 11.20.05.excalidraw]]
<!--SR:!2024-10-25,2,230-->

RISC-V ima <font color="#92cddc">tri</font> prekinitvene zahteve;; preko <font color="#92cddc">IRQ</font> (od zunaj) - interrupt, <font color="#92cddc">software interrupt</font> (npr. tako prevajalnik najde naslov funkcije malloc) in <font color="#92cddc">časovnik</font> (prosto tekoči števec).
<!--SR:!2024-10-24,1,210-->

- <font color="#92cddc">ip register: interrupt pending</font>;; ![[Prekinitve 2024-10-17 11.59.35.excalidraw]]
<!--SR:!2024-10-24,1,210-->
- <font color="#92cddc">cause register</font>;; hrani vzrok izjeme ![[Prekinitve 2024-10-17 12.01.59.excalidraw]]
<!--SR:!2024-10-24,1,190-->
- <font color="#92cddc">status register</font>;; ![[Prekinitve 2024-10-17 12.25.29.excalidraw]]
<!--SR:!2024-10-24,1,190-->
Kaj se zgodi, ko se CPE odzove na izjemo?
1) epc <- pc
2) pie <- ie (zapomnimo, ali so pred izjemo prekinitve bile onemogočene)
3) ie <- 0 in status\[3] <- 0, s tem onemogočimo nadaljnje prekinitve
4) prevzem naslova prekinitveno servisnega podprograma
	1) <font color="#92cddc">DIREKTNO</font>, kjer se v $PC \leftarrow\emptyset$ . Preprosta a omejujoča rešitev.
		- v RISC-V "dodali še en register" - tvec: ki v zgornjih 30-ih bitih shranjuje poljuben naslov za PSP, po reset-u je ta naslov 0x0 in direktno: $PC \leftarrow base$.

		- PSP nato iz registra $cause$ ugotovi, kdo je vzrok izjeme, temu se reče <font color="#92cddc">"programsko izpraševanje"</font>.
	
	2) <font color="#92cddc">VEKTORSKO</font> (kot je danes zaželjeno), kjer $PC \leftarrow BASE+4\times cause[9:0]$.
		- $cause$ ; odvisno ali je software (3), timer (7) ali IRQ (11) 
		- kjer je ukaz na temu naslovu ukaz $jump$, ki se nahaja v vektorski tabeli.
5) ko se zaključi izvajanje PSP-ja, se vrnemo v pravkar prekinjeni program - z ukazom $mret$, ki v $ie \leftarrow pie$ in v $pc \leftarrow epc$


---

#ors-flashcards

Kaj pomeni da je proces transparenten in podaj en primer?;; To pomeni, da proces ne ve, da je bil ustavljen, npr. interrupt service routine
<!--SR:!2024-11-07,15,290-->

Kaj se zgodi, ko se CPE odzove na izjemo?;; 1) epc <- pc 2) pie <- ie (zapomnimo, ali so pred izjemo prekinitve bile onemogočene) 3) ie <- 0 in status\[3] <- 0, s tem onemogočimo nadaljnje prekinitve 4) prevzem naslova prekinitveno servisnega podprograma	4A) <font color="#92cddc">DIREKTNO</font>, kjer se v $PC \leftarrow\emptyset$ . Preprosta a omejujoča rešitev. V RISC-V "dodali še en register" - tvec: ki v zgornjih 30-ih bitih shranjuje poljuben naslov za PSP, po reset-u je ta naslov 0x0 in direktno: $PC \leftarrow base$. PSP nato iz registra $cause$ ugotovi, kdo je vzrok izjeme, temu se reče <font color="#92cddc">"programsko izpraševanje"</font>. 4B) <font color="#92cddc">VEKTORSKO</font> (kot je danes zaželjeno), kjer $PC \leftarrow BASE+4\times cause[9:0]$. $cause$ ; odvisno ali je software (3), timer (7) ali IRQ (11) kjer je ukaz na temu naslovu ukaz $jump$, ki se nahaja v vektorski tabeli. 5) ko se zaključi izvajanje PSP-ja, se vrnemo v pravkar prekinjeni program - z ukazom $mret$, ki v $ie \leftarrow pie$ in v $pc \leftarrow epc$
<!--SR:!2024-10-24,1,190-->

---


