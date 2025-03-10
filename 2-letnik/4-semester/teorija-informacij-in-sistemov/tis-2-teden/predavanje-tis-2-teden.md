ponovi še entropijo
### Kviz 1, 7. naloga:
![[predavanje-tis-2-teden 2025-02-26 11.22.18.excalidraw]]

### Kodi
Imamo abecedo vira (izvorna abeceda) npr. $A = \{a_1, ..., a_n\}$
Abecede koda $B = \{b_1, ..., b_r\}$, tipično je to $\{0, 1\}$

Kod je preslikava iz abecede vira v abecedo koda: $a_i \rightarrow b_jb_n$, ker imamo manj znakov abecede koda. Zaporedju znakov abecede koda imenujemo <font color="#4bacc6">kodna abeseda</font> (zamenjava). 
### Npr. morsejeva abeceda, morsejev kod.

![[predavanje-tis-2-teden 2025-02-26 11.35.58.excalidraw|200]]
Bolj pogosto uporabljene črke, imajo krajšo kodo, ...

### ASCII kod
$A \rightarrow 1000001$
$a \rightarrow 1100001$
$0 \rightarrow 0110000$
...

### Lastnosti kodov
Upoštevamo povprečno dolžino kodne besede, ki jo izračunamo če imamo:
- $A = \{a_1, ..., a_n\}$
- $P_A = \{p_1, ..., p_n\}$
- $L_A = \{l_1, ..., l_n\}$

$L = \Sigma p_i \cdot l_i$, kjer je pogoj da je $\Sigma p_i = 1$.  

Kaj je <font color="#4bacc6">idealni</font> kod? če je $L = H(A)$, če je povprečna dolžina enaka entropiji.
Kaj pa <font color="#4bacc6">optimalni</font> kod? najboljši možni, ima povprečno dolžino tako, da se najbolj približa entropiji

Idealni kod lahko obstaja, samo če so verjetnosti enake potencam števila dva (torej $2^{-1}, 2^{-2}, ...$)

### Razvrstitev kodov
$A = \{a_1, a_2, a_3\}$
$P_A = \{p_1, p_2, p_3\}$
$B = \{0, 1\}$

![[predavanje-tis-2-teden 2025-02-26 11.50.55.excalidraw]]

Kod 5?
Če gledamo samo povprečno dolžino je kod 5 najboljši, a je sevedno neuporaben, zaradi <font color="#4bacc6">singularnosti</font> (dvoumnosti). Mi se bomo ukvarjali samo z <font color="#4bacc6">nesingularnimi</font> kodi.

Kaj pa kod 2?
Spet je nedvoumen, v tem primeru <font color="#4bacc6">neenoznačen</font> kod, nas zanimajo le <font color="#4bacc6">enoznačni</font> kodi.

Kaj pa kod 3?
Slabost tega koda, je to da je potrebno prebrati vedno en znak več, da zagotovo vemo kateri znak je zapisan, torej je <font color="#4bacc6">netrenutni</font> kod. Nasprotje tega je <font color="#4bacc6">trenutni</font> kod, s katerimi se bomo ukvarjali tudi mi, torej takrat ko nobena kodna beseda ni predpona, katere druge kodne besede.

Kod 1?
Je <font color="#4bacc6">enakomerni</font>, vsi znaki so sestavljeni iz enake dolžine, nasprotje pa so neenakomerni, načeloma bodo ti s krajšo povprečno dolžino, zato izberemo samo tistega s krajšo povprečno dolžino, ni pomembne razlike za nas.

![[predavanje-tis-2-teden 2025-02-26 12.25.23.excalidraw|200]]

Tisti kodi, ki ustrezajo našim zahtevam, imajo vse kodne simbole v listih (npr. kod 1).

### Kraftova neenakost
$A = \{a_1, ..., a_n\}$
$B = \{b_1, ..., b_r\}$
$L_A = \{l_1, ..., l_n\}$

Če velja $\Sigma \ r^{-li} \leq 1$, potem obstaja trenutni kod, s podanimi dolžinami vhodnih besed.

![[predavanje-tis-2-teden 2025-02-26 12.33.01.excalidraw]]

### l. Shannonov teorem
Ogledamo si povprečno dolžino kodnih besed ($L$) in entropijo
 $A = \{a_1, ..., a_n\}$
 $P = \{p_1, ..., p_n\}$
$B = \{b_1, ..., b_r\}$
$L_A = \{l_1, ..., l_n\}$

$H_r(A) \leq L$ 

sledi: $\frac{H(A)}{log \ r} \leq L$ 

Kdaj pa sploh velja ta enakost? Če za verjetnosti velja $p_i = r^{-li}$.

V splošnem je $li = -log \ r \cdot p_i$ zaokroženo navzgor

$H_r(A) \leq L < H_r(A) + 1$ (to vse velja le za trenutne kode)

Zakaj to velja?
![[predavanje-tis-2-teden 2025-02-26 12.45.02.excalidraw]]

Mera za to koliko blizu minimalne dolžine ..., je učinkovitost koda $\eta = \frac{H_r(A)}{L}$. 

Če imamo blok znakov $A^m = y$, velja da je $H_r(A^m) = m \cdot H_r(A)$.

Ko gre $m$ proti <font color="#4bacc6">neskončnosti</font> velja: $$\lim_{m\rightarrow\infty} \frac{L_m}{m}= H_r(A)$$
Več kot bomo znakov pakirali skupej, bližje bomo prišli entropiji, to je <font color="#4bacc6">prvi Shannonov zakon</font>.


Praktične vidike, tega teorema sledi v poglavju:
### Stiskanje
### 1. Shannonov kod
- znake razvrstimo po padajočih verjetnostih,
- izračunamo povprečne dolžine $l_i$ in $P_i$
- $P_i$ pretvorimo v bazo $r$
- kodno besede predstavlja prvih $l_i$ znakov za decimalnim ločilom

![[predavanje-tis-2-teden 2025-02-26 13.38.04.excalidraw]]

### 2. (Shannon) Fanojev kod
- znake razvrstimo po padajočih verjetnostih,
- znake razdelimo v $r$ skupin, katere so čimbolj uravnotežene po verjetnostih,
- vsaki skupini dodelimo en znak abecede koda,
- postopek ponovimo za vsako skupino če je potrebno

![[predavanje-tis-2-teden 2025-02-26 13.54.43.excalidraw]]

### 3. Huffmanov kod
- združevanje: 
	- vzamemo $r$ najmanj verjetnih znakov in jih združimo v nov znak
	- postopek ponavljamo dokler ne ostane en sam sestavljeni znak (katerega verjetnost je $1$)
- razdruževanje: 
	- sestavljeni znak razstavimo na $r$ znakov in vsakemu priredimo en znak kodne abecede
	- postopek ponavljamo, dokler imamo sestavljene znake
	- kodne besede - preberemo oznake vej od korena proti listom
