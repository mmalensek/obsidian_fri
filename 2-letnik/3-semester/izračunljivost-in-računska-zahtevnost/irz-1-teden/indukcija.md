[[Metode dokazovanja]];

Princip indukcije:
	naj bo $P(n)$ trditev o naravnih številih $n$. Tedaj, če $P(0)$ velja in če velja $P(k-1) \rightarrow P(k)$ za poljuben $k \geq 1$, potem $P(n)$ velja za vsak naravni $n$ (0 štejemo za naravno število).

$P(0)$ je <font color="#92cddc">osnova indukcije</font>.
$P(k-1)$ je <font color="#92cddc">induktivna hipoteza</font>.
$P(k-1) \rightarrow P(k)$ pa je <font color="#92cddc">induktivni korak</font>.

Primer:

![[Pasted image 20241007135559.png]]

### Induktivni razredi
1. <font color="#92cddc">Baza</font>
2. <font color="#92cddc">Pravila</font>, npr: $a\in I \rightarrow f(a) \in I$

> Primer: $\mathbb{N}$
	Baza: 1
	Pravilo: $n\in \mathbb{N} \rightarrow n+1 \in \mathbb{N}$ 

> Primer: Zid, ali je katerikoli zid rdeč?
> Baza: $opeka \in Zid$
> Pravilo: $z\in Zid \rightarrow z + opeka \in Zid$

> Primer: Drevo z $n$ vozlišči ima $n - 1$ povezav
> Baza: $Vozlišče$
> Pravilo: Dodamo vozlišče in ga povežemo s katerimkoli prejšnjim
> 
> $n = 1$ povezav je $0$, baza drži.
> imamo drevo $T$, ki ima $n$ vozlišč in $n-1$ povezav $\rightarrow$ $T': n + 1$ in $n$ povezav.  

---

#irz-flashcards 

$P(0)$;; Je <font color="#92cddc">osnova indukcije</font>.
<!--SR:!2024-10-17,3,250-->
$P(k-1)$;; Je <font color="#92cddc">induktivna hipoteza</font>.
<!--SR:!2024-10-17,3,250-->
$P(k-1) \rightarrow P(k)$;; Je <font color="#92cddc">induktivni korak</font>.
<!--SR:!2024-10-16,4,270-->

---
