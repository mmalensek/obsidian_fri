[[predavanje-vs-1-teden]];
[[izjeme pri ARM Cortex]];
[[predavanje-ors-3-teden]]; #ors-flashcards

Posledica nekega zunanjega vhoda, ne samega procesorja.

![[Prekinitve 2024-10-17 10.42.33.excalidraw]]

<font color="#d83931">Interrupt request:</font> V/I zahteva od CPE da prekine izvajanje trenutnega programa.

Če kdorkoli postavi <font color="#92cddc">IRQ</font> signal v obratno stanje, CPE preneha zajemati ukaze in začne s <font color="#92cddc">prekinitveno-servisnim ciklom</font>. V PC ne gre tako PC + 4, ampak neka nova vrednost.

Zgled: RISC-V ![[Prekinitve 2024-10-17 10.51.51.excalidraw]]
Imamo 5 registrov, ki v RISC-V omogočajo implementacijo izjem.

-  <font color="#92cddc">epc register: exception PC</font>;; vanj se shrani naslov, ki ga ob prekinitveni zahtevi hrani PC in ki kaže na ne prevzeti ukaz prekinjenega programa
		-> hrani nekakšen "povratni naslov" (ni enako povratnim naslovom v podprogramih)

1) <font color="#92cddc">IRQ</font> prekine izvajanje programa pri ukazi na naslovu v PC
2) epc <- PC
3) PC <- naslov programa "interrupt handlerja"
4) ko zaključimo izvajanje <font color="#92cddc">ISR</font> (interrupt service routine) v PC <- epc, da se znamo <font color="#92cddc">vrnit v prekinjeni program</font>

Celoten ta proces je transparenten, pomeni, da ustavljen program, ne ve, da je bil ustavljen.

- 
