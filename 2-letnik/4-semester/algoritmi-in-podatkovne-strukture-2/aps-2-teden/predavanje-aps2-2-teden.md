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