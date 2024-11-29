[[predavanje-aps-9-teden]]; #aps1-flashcards 

<font color="#4bacc6">Imamo:</font>
- vozlišča: $1\Rightarrow N$
- povezave: $E(M)$

![[Grafi 2024-11-29 12.21.32.excalidraw]]

<font color="#4bacc6">Operacije:</font>
- velikost
- pot
- dodaj/izbriši vozlišče/povezavo
- ugotavljamo/nastavljamo lastnosti vozlišč/povezav
- sosednost

<font color="#4bacc6">Lastnosti:</font>
- (ne)usmerjene povezave
- (ne)uteženi grafi
- enostavni - so grafi brez zank in vzporednih povezav
- (a)ciklični
- gosti/redki - redki, ko imamo $N$ povezav, gosti pa $N^2$ povezav

<font color="#4bacc6">Termini:</font>
- stopnja - število povezav iz nekega vozlišča - kjer je stopnja grafa max od vseh vozlišč označena z $(d)$, če pa imamo usmerjene povezave pa ličimo stopnjo vzhodnih in izhodnih
- soseda in soseščina

<font color="#4bacc6">Tipi grafov:</font>
- [[Drevesa]]
- polni grafi - vsa vozlišča imajo max stopnjo
- dvodelni
- regularni - vsa vozlišča imajo isto stopnjo
- ...

<font color="#4bacc6">Premiki:</font>
- sprehod - $A,B$ ... povezani
- obhod
- steza - je sprehod, ki nima ponovljenih povezav, lahko pa isto vozlišče
- pot - je steza brez ponovljenih vozlišč
- cikel - obhod brez ponavljajočih vozlišč

<font color="#4bacc6">Predstavitve:</font>
primer: 
![[seznam povezav 2024-11-29 12.47.42.excalidraw]]
- seznam povezav:
	- tabela vseh povezav
	- [(1, 3), (1, 2), (3, 4), (4, 5), (2, 4), (2, 5)]
- seznam sosedov:
	- 1: [2, 3], 2: [1, 4, 5], 3: [1, 4], 4: [2, 3, 5], 5: [2, 4]
- matrika sosednosti:

|     | **1** | **2** | **3** | **4** | **5** |
| --- | ----- | ----- | ----- | ----- | ----- |
| **1**   |       | 1     |       |       |       |
| **2**   | 1     |       |       | 1     |       |
| **3**   |       |       |       | 1     |       |
| **4**   |       | 1     | 1     |       | 1     |
| **5**   |       |       |       | 1     |       |

|                        | seznam povezav | seznam sosedov | matrika sosednosti  |
| ---------------------- | -------------- | -------------- | ------------------- |
| prostorska zahtevnosti | $O(E)$         | $O(N + E)$     | $O(N^2)$            |
| dodajanje povezav      | $O(1)$         | $O(1)$         | $O(1)$              |
| brisanje povezav       | $O(E)$         | $O(N)$         | $O(1)$              |
| dodajanje vozlišča     | $O(1)$         | $O(1)$         | $O(N^2)$            |
| brisanje vozlišča      | $O(E)$         | $O(N + E)$     | $O(N)$ ali $O(N^2)$ |
| sosednost              | $O(E)$         | $O(E)$         | $O(1)$              |


### Preiskovanje
<font color="#4bacc6">1. preiskovanje v širino (BFS)</font>

primer: 
![[Grafi 2024-11-29 13.40.14.excalidraw]]
1) 0
2) 4 1 
3) 5 3 7
4) 2 6 

<font color="#4bacc6">2) presikovanje v globino (DFS)</font>

0 1 5 2 3 4 7 6 (ni važen vrstni red, važno da je dolžina prava)

