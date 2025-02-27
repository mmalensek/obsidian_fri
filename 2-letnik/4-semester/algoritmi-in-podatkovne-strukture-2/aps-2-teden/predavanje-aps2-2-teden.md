### Heap sort
- sestavljanje začetne kopice:
	- gremo od spodaj navzgor, od prvega očeta (ta se nahaja na indeksu $n / 2$) do korena (zadnjega očeta) in pri vsakem urediš poddrevo v kopico (vedno samo preveriš ali je koren poddrevesa za prestavit ali ne, saj so ostali deli poddrevesa že kopica), to zahteva časovno zahtevnost $O(n)$.
- izločanje korena in prestavljanje lista:
	- zamenjamo prvo in $n$-to komponento, zabeležimo da prvih $n-1$ komponent opsiuje drevo, $n$-ta komponenta pa že izločeni koren.
- popravljanje drevesa v kopico:
	- list se pogrezne tja, kjer je večji ali enak od sinov
- časovne zahtevnosti:
	- časovna zahtevnost gradnje kopice je $O(n)$
	- sam algoritem pa $O(n \log n)$ 

### Metode razvoja algoritmov
Želimo si splošnih pristopov k razvoju algoritmov, tj. metod, ki nas bodo sistematično usmerjale pri naših poskusih, da bi razvili algoritem za dani problem. 
Obravnavamo naslednje metode:
- deli in vladaj
- dinamično programiranje
- požrešnošt (greedy)
- sestopanje (backtracking)
- gola sila (brute force)
- naravna inteligenca

### Deli in vladaj:
### Quicksort - hitro urejanje
Določi eno komponento kot pivot $p$ in vse ostale komponente razdeli v tri tabele, te manjše od $p$, enake kot $p$ in večje od $p$.

Izbira delilnega elementa:
Lahko določimo, da je $p$ prvi ali zadnji element, element, ki leži na sredi tabele. Lahko je $p$ naključno izbran

Lahko pa ga tudi izračunamo iz večih komponent tabele $t$ npr. $p = \frac{1}{2}(t[0] + t[n])$ ali pa $p = mediana \ t$. V tem primeru je možno ta je tabela $t_2$ prazna.

Dve različici, pri prvi je $t_2$ samo en element, pri drugi pa je $t_2$ tabela vseh elementov enakih $p$

Časovna zahtevnost:

