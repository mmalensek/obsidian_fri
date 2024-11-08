[[predavanje-aps1-3-teden]], [[predavanje-aps-4-teden]]; #aps1-flashcards 

ta nam definira funkcionalnost.

- [[Array|Polje (Array)]],
	- [[Dynamic Array|Dinamično polje (Dynamic Array)]].
- [[Stack|Sklad (stack) - po principu LIFO]],
- [[List|Seznam (List)]],
	- [[Urejen seznam]],
	- [[Preskočni seznam (Skip list)]].
- [[Queue|Vrsta (Queue)]],
	- [[Priority Queue|Prioritetna vrsta (Priority Queue)]].
- [[Heap|Dvojiška kopica (Heap)]],
- [[Množica (Set)]],
- [[Slovar (Map)]],
	- [[Zgoščena-Razpršena tabela (Hash table)]],

---

- [[Drevesa]]

---

#aps1-flashcards 

Kako implementiramo array?;; S preprosto tabelo
<!--SR:!2024-11-07,15,290-->
Kako implementiramo sklad?;; Z linked listom
<!--SR:!2024-11-03,11,270-->
Kaj pove funkcija peak() ozr. top() v skladu?;; Vrne vrednost vrha skladu, ne da bi ga pobrisal
<!--SR:!2024-11-07,15,290-->
Kako implementiramo list?;; Ali kot linked list ali kot resizable array
<!--SR:!2024-11-03,11,270-->
Na katera dva načina lahko implementiramo queue?;; Ali z linked listom ali pa dvema skladoma
<!--SR:!2024-11-03,11,270-->
Kakšen princip dostopa podatkov imamo v queue?;; FIFO
<!--SR:!2024-11-07,15,290-->
Kako deluje buffer v dynamic arrayu?;; Če število podatkov preseže velikost arraya, se velikost naslednjega arraya podvoji, če se število podatkov zmanjša na eno četrtino velikosti arraya, se njegova naslednja velikost razpolovi
<!--SR:!2024-11-07,15,290-->
Kaj je in kako implementiramo priority queue?;; Zaporedje elementov, kjer ima vsak določeno vrednost prioritete. To lahko implementiramo ali z urejenim seznamom ali seznamom parov.
<!--SR:!2024-10-29,6,250-->
Kako implementiramo heap?;; Kot preprosto tabelo, kjer so relacije med vozlišči implicitne, npr. starš od indeksa $x$ je na $\frac{x}{2}$ in obratno.
<!--SR:!2024-11-03,11,270-->

---
