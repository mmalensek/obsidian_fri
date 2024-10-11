[[predavanje-opb-1-teden]]; #opb-flashcards 

Je <font color="#92cddc">nepostopkovni</font> ali <font color="#92cddc">deklarativni</font> jezik, je pa prav tako formalni poizvedovalni jezik.

[[relacijski_račun.pdf]];

Sintaksa predikatnega računa:
- če predikat vsebuje spremenljivko, mora za $x$ obstajati <font color="#92cddc">domena vrednosti</font>.
- če je $P$ predikat, potem lahko zapišemo množico vseh $x$, za katere je $P$ resničen: $\{x \mid P(x)\}$

Poznamo dve vrsti relacijskega računa:
- <font color="#92cddc">n-terični</font>,
	- temelji na uporabi n-teričnih spremenljivk
	- npr. poišči vsi artikli, ki imajo zalogo manjšo od tri: $$\{A \mid Artikel(A) \land A.zaloga < 3\}$$
	- če pa nas zanima samo določen atribut pa namesto prvega $A$, zapišemo $A.ime$ (projekcija).
	- npr. izpiši nazive hotelov, ki se nahajajo v Ljubljani $$\{H.hotelName \mid Hotel(H \land H.address = \ 'Ljubljana'\}$$
	- v relacijskem računu je možno zapisati stavke, ki vračajo neskončne množice.
	- primer nevarnega izraza: $$\{A \mid \neg(Artikel(A))\}$$
- <font color="#92cddc">domenski</font>.
	- imamo enaka pravila, kot pri n-teričnem računu.
	- npr. izpiši nazive hotelov v Ljubljani (enak primer kot prej) $$\{hName \mid \exists (hNo, hAddress) (Hotel(hNo, hName, hAddress) \land hAddress = \ 'Ljubljana')\}$$