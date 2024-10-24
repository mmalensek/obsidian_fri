[[predavanje-vs-1-teden]];
[[izjeme pri ARM Cortex]];
[[predavanje-ors-3-teden]]; #ors-flashcards

Posledica nekega zunanjega vhoda, ne samega procesorja.

![[Prekinitve 2024-10-17 10.42.33.excalidraw]]

<font color="#d83931">Interrupt request</font>;; V/I zahteva od CPE da prekine izvajanje trenutnega programa.
<!--SR:!2024-10-25,2,210-->

Če kdorkoli postavi <font color="#92cddc">IRQ</font> signal v obratno stanje, CPE preneha zajemati ukaze in začne s <font color="#92cddc">prekinitveno-servisnim ciklom</font>. V PC ne gre tako PC + 4, ampak neka nova vrednost.

[[Izjeme pri RISC-V]] in [[izjeme pri ARM Cortex]].

---

Kaj pomeni da je proces transparenten in podaj en primer?;; To pomeni, da proces ne ve, da je bil ustavljen, npr. interrupt service routine
<!--SR:!2024-11-07,15,290-->

Kaj se zgodi, ko se CPE odzove na izjemo?;; 1) epc <- pc 2) pie <- ie (zapomnimo, ali so pred izjemo prekinitve bile onemogočene) 3) ie <- 0 in status\[3] <- 0, s tem onemogočimo nadaljnje prekinitve 4) prevzem naslova prekinitveno servisnega podprograma	4A) <font color="#92cddc">DIREKTNO</font>, kjer se v $PC \leftarrow\emptyset$ . Preprosta a omejujoča rešitev. V RISC-V "dodali še en register" - tvec: ki v zgornjih 30-ih bitih shranjuje poljuben naslov za PSP, po reset-u je ta naslov 0x0 in direktno: $PC \leftarrow base$. PSP nato iz registra $cause$ ugotovi, kdo je vzrok izjeme, temu se reče <font color="#92cddc">"programsko izpraševanje"</font>. 4B) <font color="#92cddc">VEKTORSKO</font> (kot je danes zaželjeno), kjer $PC \leftarrow BASE+4\times cause[9:0]$. $cause$ ; odvisno ali je software (3), timer (7) ali IRQ (11) kjer je ukaz na temu naslovu ukaz $jump$, ki se nahaja v vektorski tabeli. 5) ko se zaključi izvajanje PSP-ja, se vrnemo v pravkar prekinjeni program - z ukazom $mret$, ki v $ie \leftarrow pie$ in v $pc \leftarrow epc$
<!--SR:!2024-10-24,1,190-->

---


