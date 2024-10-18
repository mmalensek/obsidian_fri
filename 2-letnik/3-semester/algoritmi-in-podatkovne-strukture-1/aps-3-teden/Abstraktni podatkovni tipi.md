[[predavanje-aps1-3-teden]]; #aps1-flashcards 

ta nam definira funkcionalnost.



<font color="#92cddc">Polje (Array):</font>
- implementacija: s preprosto tabelo

![[Pasted image 20241018131610.png]]
- 
- inicializacija(n)
- set(i, x) - nastaviti i-ti element na x
- get(i)
- ... 
- size

<font color="#92cddc">Sklad (Stack) - po principu LIFO:</font>
- implementacija: z linked listom

![[Pasted image 20241018131628.png]]

- push(x) - dati nekaj na vrh
- pop() - vrne vrh
- ...
- size
- top() / peak() - pogledat, kaj je na vrhu, ne da bi zbrisal

<font color="#92cddc">Seznam (List):</font>
- hrani končno število elementov, spremenljive velikosti
- implementacija: linked list ali resizable array

![[Pasted image 20241018131710.png]]
- ali

![[Pasted image 20241018131735.png|450]]

- kjer dodamo tudi nekaj "rezerve", da ni potrebno, tako pogosto kopirati vseh elementov, (neki neki amortizirana časovna zahtevnost?).

- add(x)
- remove(x)
- size() - pomembnejši kot pri Array, zaradi spremenljivosti
- traverse
- ...
- contains(x)
- empty()

<font color="#92cddc">Vrsta (Queue):</font>
- imamo nek začetek in konec, kjer dodajamo na koncu, vzemamo na začetku, torej FIFO.
- implementacija: povezan seznam, lahko pa tudi z dvema skladoma 
 
![[Pasted image 20241018133118.png]]
- ali

![[Pasted image 20241018134032.png]]

- push(x)
- pop()

<font color="#92cddc">Dinamično polje (Dynamic Array):</font>

![[Pasted image 20241018131735.png|450]]

- ko količina elementov, pade pod četrtino, se ustvari novo pol manjše polje in obratno, zato da vedno ostane nekaj "bufferja".


<font color="#92cddc">Prioritetna vrsta (Priority Queue):</font>
- hranimo neko zaporedje elementov, kjer ma vsak element neko svojo prioriteto.
- v c++, višja je številka, večja je pomembnost.

- implementacija: 
	1) najlažje kot seznam parov, a velja, da je push $O(1)$ in pop $O(n)$
	2) kot urejen seznam, velja, da je push $O(n)$ in pop $O(1)$

![[Pasted image 20241018135134.png]]

- push(x, p) - element x in prioriteta p, lahko tudi implicitno
- pop()


<font color="#92cddc">Dvojiška kopica (Heap):</font>
- poravnano dvojiško drevo
- $\forall (vozlišče \leq otrok)$ 

![[Pasted image 20241018141842.png|400]]

- višina je $O(\log n)$, prostorska zahtevnost je $O(n)$.

- kako bi naredil pri min heap npr. push(35)? dodamo na prvo prazno mesto ozr. nov list na dnu (kjer paziš na poravnanost), in tja vpisal 35 in bi delal zamenjaval s starši, dokler ne bi bilo pravilno poravnano

- kako bi naredil pri min heap pop()? Zamenjaš koren in najnižji (najbolj desni (zaradi poravnanosti)) list in nato menjavaš zamenjani list, dokler ni spet poravnano.

- implementacija: lahko preprosto v array-u, kjer so relacije implicitne $$[10, 15, 30, 40, 50, 100, 40]$$
- starš od vozlišča $x$ je $\frac{x}{2}$
- levi in desni otrok od $x$ pa je $2x$ in $2x + 1$

