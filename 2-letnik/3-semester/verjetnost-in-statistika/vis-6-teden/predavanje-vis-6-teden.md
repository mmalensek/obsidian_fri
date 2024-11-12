### [[vis]], 6.teden, 07-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #vis-flashcards 

---

### Vsebina:

Enakomerna porazdelitev;
- predstavlja pravokotnik nad osjo grafa
- kjer je $P(x) = 0, \ x > a, \ x < b$
- vsi izidi na intervalu $[a,b]$ so enako verjetni
- gostota verjetnosti $p_X(x)=\frac{1}{b-1}$
- porazdelitvena funkcija $F_X(x)=\frac{x-a}{b-a}$
- pričakovana vrednost $E(X) = \frac{a+b}{2}$
- disperzija $D(X) = \frac{(b-1)^2}{12}$

![[Screenshot 2024-11-09 at 20.38.03.png|300]]

Normalna porazdelitev;
![[Screenshot 2024-11-09 at 20.35.39.png|300]]
Oznaka: $X \sim N(\gamma, \sigma^2)$ in 
Enačba: $f(x) = \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{1}{2\sigma^2}(x-\gamma)^2}$

Eksponentna porazdelitev;
- slučajna spremenljivka $X$ - čas med zaporednima dogodkoma, pri čemer so dogodki neodvisni in se pojavijo s konstantno stopnjo $\lambda$.
- $\lambda$ je povprečno število dogodkov na izbrano časovno enoto
- gostota verjetnosti $p_X(x)=\lambda e^{-\lambda x}, x ≥ 0$
- porazdelitvena funkcija $F_X(x)  =1 - e^{-\lambda x}$
- pričakovana vrednost $E(X) = \frac{1}{\lambda}$
- disperzija $D(X) = \frac{1}{\lambda^2}$


![[Screenshot 2024-11-09 at 20.38.54.png|300]]

Funkcija napake; 
- je liha, zvezno odvedljiva, strogo naraščajoča funkcija.

Laplaceov točkovni obrazec; 
- izhaja, da za $p$ blizu $\frac{1}{2}$ in velike $n$ velja: $$B(n, P) \approx N(np,\sqrt{npq})$$
Laplaceov intervalski obrazec;
- zanima nas, kolikšna je verjetnost, da se v Bernoullijevem zaporedju neodvisnih poskusov v $n$ zaporednih poskusih zgodi dogodek $A$, vsaj $k_1$ krat in manj kot $k_2$ krat. 
- za velike $n$ zamenjamo vsoto z integralom

Bernoullijev zakon velikih števil;
- več poskusov - bolj natančno: osnova
- ...

Gamma funkcija;
- pomaga nam predstaviti npr. $(\frac{3}{2})!$
[![Graph of the absolute value of the complex gamma function (factorial  extension), hand-drawn : r/math|inv|300](https://i.imgur.com/JlcwSuq.png)

---
