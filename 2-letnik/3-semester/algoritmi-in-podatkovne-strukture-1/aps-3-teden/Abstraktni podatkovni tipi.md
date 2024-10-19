[[predavanje-aps1-3-teden]]; #aps1-flashcards 

ta nam definira funkcionalnost.

- [[Array|Polje (Array)]],
- [[Stack|Sklad (stack) - po principu LIFO]],
- [[List|Seznam (List)]],
- [[Queue|Vrsta (Queue)]],
- [[Dynamic Array|Dinamično polje (Dynamic Array)]],
- [[Priority Queue|Prioritetna vrsta (Priority Queue)]],
- [[Heap|Dvojiška kopica (Heap)]].

---

#aps1-flashcards 

Kako implementiramo array?;; S preprosto tabelo
Kako implementiramo sklad?;; Z linked listom
Kaj pove funkcija peak() ozr. top() v skladu?;; Vrne vrednost vrha skladu, ne da bi ga pobrisal
Kako implementiramo list?;; Ali kot linked list ali kot resizable array
Na katera dva načina lahko implementiramo queue?;; Ali z linked listom ali pa dvema skladoma
Kakšen princip dostopa podatkov imamo v queue?;; FIFO
Kako deluje buffer v dynamic arrayu?;; Če število podatkov preseže velikost arraya, se velikost naslednjega arraya podvoji, če se število podatkov zmanjša na eno četrtino velikosti arraya, se njegova naslednja velikost razpolovi
Kaj je in kako implementiramo priority queue?;; Zaporedje elementov, kjer ima vsak določeno vrednost prioritete. To lahko implementiramo ali z urejenim seznamom ali seznamom parov.
Kako implementiramo heap?;; Kot preprosto tabelo, kjer so relacije med vozlišči implicitne, npr. starš od indeksa $x$ je na $\frac{x}{2}$ in obratno.

---
