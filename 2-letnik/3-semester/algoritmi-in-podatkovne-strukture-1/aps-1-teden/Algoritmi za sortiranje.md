[[predavanje-aps1-1-teden]];
[[primer-latex]];
### Urejanje:
Iskanje neke permutacije, da bo za zaporedne objekte veljalo <= ali >=. Algoritem je <font color="#92cddc">stabilen</font>, če se vrstni red enakih vrednosti ohranja (katerikoli algoritem, lahko narediš stabilen, če poleg nekih $x_1, x_2, ...$, hraniš tudi, njihov originalen indeks $(x_1, 3), (x_2, 5), ...$).

Kr ena:
1. [[Permutation sort]]
	- v najslabšem primeru je to $n!$, najboljšem $1$, v povprečju $\frac{n!}{2}$
2. [[Random sort]]
	- v najslabšem primeru $\infty$, najboljšem $1$, v povprečju $n!$
---

Osnovni:
1. [[Selection sort]]
	- v vseh primerih je $O(n²)$
2. [[Insertion sort]]
	- v najslabšem primeru $O(n²)$, najboljšem $O(n)$, v povprečju $O(n²)$
3. [[Bubble sort]]
	- v najslabšem primeru $O(n²)$, najboljšem $O(n)$, v povprečju $O(n²)$

---
Nekoliko jačejši:
1) [[Merge sort]]
2) [[Quick sort]]
 
 Če se zanašamo samo na primerjanje med elementi je $O(n\log n)$, najboljše kar lahko dosežemo. 

3) [[Heap sort]]
4) [[Counting sort]]
5) [[Bucket ali Bin sort (radix)]]

 ---

#aps1-flashcards 

Kdaj je algoritem stabilen?;; Če se vrstni red enakih vrednosti ohranja.

---
