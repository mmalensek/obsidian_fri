### [[vis]], 4.teden, 24-10-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #vis-flashcards 

---

### Vsebina:

<font color="#92cddc">Slučajne spremenljivke</font> označujemo z velikimi tiskanimi črkami iz konca abecede, vrednosti spremenljivke pa z enakimi malimi črkami. Tako je npr. $X = x_i$ dogodek, da slučajna spremenljivka $X$ zavzame vrednost $x_i$. 

<font color="#92cddc">Porazdelitveni zakon</font> $X$ je poznan;; če je mogoče za vsako realno število $x$ določiti verjetnost, torej: $F(x) = P(X \leq x)$, kjer je $F(x)$ <font color="#92cddc">porazdelitevena funkcija</font>.

To se uporablja pri dveh določenih vrstah slučajnih spremenljivk:
1) <font color="#92cddc">diskretna</font> slučajna spremenljivka, katere zaloga vrednost je neka števna diskretna množica
2) <font color="#92cddc">zvezna</font> slučajna spremenljivka, ki lahko zavzame vsako realno število znotraj določenega intervala

<font color="#92cddc">Binomska porazdelitev</font>:

Pričakovana vrednost $E(X)$ je posplošitev povprečne vrednosti diskretne spremenljivke $X$ in je: $$E(X) = \sum_{i = 1}^mx_ip_i = \sum_{k = 0}^n \binom{n}{k}p^kq^{n-k} = n \cdot p$$  
Velja: $$E(X+Y) = E(X) + E(Y)$$
<font color="#92cddc">Poissonova porazdelitev</font>;; izraža verjetnost števila dogodkov, ki se zgodijo v danem časovnem intervalu, če vemo, da se ti dogodki pojavijo s poznano povprečno frekvenco in neodvisno od časa, ko se je zgodil zadnji dogodek.

	Primer: Kakšna je verjetnost, da zapelje v danem časovnem intervalu skozi križišče npr. 100 avtomobilov, kjer definiramo slučajno spremenljivko $X$, ki je enaka številu avtomobilov, ki pridejo v križišče na uro
	Imamo dve predpostavki:
	 1) vsaka ura je enaka kot vsaka druga ura
	 2) število avtov v eni uri je neodvisno v drugi, npr. da imamo veliko avtov eno uro, še ne pomeni, da bo veliko avtov drugo uro
	 3) enoto zmanjšamo na sekundo in kasneje množimo z 3600, ker nočemo več avtov hkrati


Poissonov obrazec: za velike $n$ in majhne verjetnosti $p$ (blizu 0): $$vstavi \ manjkajoče!$$
<font color="#92cddc">Pascalova ali negativna binomska porazdelitev</font>:
- npr. kolikokrat moramo vreči kocko, da z verjetnostjo $99\%$ vržemo $6$ pik na kocki.
- ima zalogo vrednosti $m, m+1, m+2,...$ in je enak: $p_k = \binom{k-1}{m-1}p^mq^{k-m}$ za $k >= m$,
- opisuje porazdelitev potrebnega števila poskusov, da se dogodek $A$ zgodi $m$-krat.
- če je $m = 1$, potem je to $geometrijska$ porazdelitev $G(p)$.
- npr 2. število obratov do muhe iz začetnega vozlišča pajka, ker ima vsak korak $\frac{1}{3}$ možnosti, da pride do muhe

<font color="#92cddc">Hipergeometrijska porazdelitev</font>:

---
