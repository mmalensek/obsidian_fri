[[predavanje-aps1-2-teden]]; #aps1-flashcards 

Zanima nas časovna in prostorska zahtevnost, zanima nas asimptotična zgornja meja v najslabšem primeru.

Pravtako za $najboljši, povprečen \ in \ najslabši \ primer$. Ukvarjali se bomo samo z velikimi problemi.

<font color="#92cddc">Big O notation</font>, nam predstavlja;; zgornjo mejo asimptotične računske zahtevnosti.

V primeru, da je $O(g(n))$, $\exists k > 0, \exists n_0, \forall n >= n_0 \ : \ f(n) <= kg(n)$.

Primer: $f(n) = \frac{1}{2}(n-1)(n+2)log(n) + \sqrt{n}$ kakšen je $O$?;; če to poenostavimo je to $\frac{1}{2}n²log(n)-log(n)+\sqrt{n}$, neka prva zgornja meja je $O(n^3)$, boljše je $O(n^2log(n))$.

- konstant ni potrebno pisati,
- pri vsoti - vzamemo max člen.

- $O(1)$, pomeni da vedno potrebujem največ 10 operacij,
- $O(\log{n})$, npr. bisekcija,
- $O(\sqrt{n})$, iščemo delitelje npr,
- $O(n)$, gremo npr. 10-krat čez podatke,
- $O(n\log n)$, npr. n krat delam bisekcijo,
- $O(n²)$, polinomske zahtevnosti $n^x$.
- $O(2^n)$, eksponentna

Kako velike probleme lahko rešujemo z vsemi od teh algoritmov?

Upoštevamo, da računalnik zmore $10^{8...9}op/sek$. 
- $O(1)$, poljubno velik problem
- $O(n²)$, $n \approx 10⁴$
- $O(2^n)$, $n \approx 25$

npr. 
- $1+n\log n + n^{1,5} = O(n^{1,5})$, ker je $n^{1,5} = n\sqrt{n}$, kar hitreje narašča kot $n\log n$.
- $\sum_{k = 1}^n = \frac{n}{k} = O(n\log n)$, (harmonična vrsta)
- $f(n) = n + f(n/2) = O(n)$,
- $f(m,n) = an² + n\sqrt{m} + b\log n = O(n² + n\sqrt{m})$


npr. 

```c++
for(x = 1; x <= n; n*=2){          // <= log n
	for(i = 0; i < x; i++){        // <= n
		for(y = 0; y < n; y += 2){ // <= n
		for(y = 1; y < n; y *= 2){ // <= log n
			}	
			}
		}
}
```

$O(n²)$.

