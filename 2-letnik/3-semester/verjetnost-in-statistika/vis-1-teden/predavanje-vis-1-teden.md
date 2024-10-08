### [[vis]], 1.teden, 03-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano  #vis-flashcards 

---

[[vis_prosojnice.pdf]];
### Vsebina:

<font color="#92cddc">Populacija</font>, so vsi objekti, ki jih opazujemo, njena velikost je enaka $N$.
<font color="#92cddc">Vzorec</font>, pa je podmnožica populacije.

POPULACIJA $\rightarrow$ <font color="#92cddc">VERJETNOST</font> $\rightarrow$ VZOREC $\rightarrow$ <font color="#92cddc">INFERENČNA STATISTIKA</font> $\rightarrow$ POPULACIJA $\rightarrow$ .. 

Poznamo dva tipa podatkov:
- <font color="#92cddc">kvantitativni</font>: 
	- (numerični) predstavljajo količino nečesa
	- npr. intervali, razmerja, ...
- <font color="#92cddc">kvalitativni</font>:
	- (kategorije) nimajo kvantitativnih interpretacij
	- npr. nominalni (brez neke urejenosti) in ordinalni (kategorije z urejenostjo)

Pri grafih določimo <font color="#92cddc">razrede</font>: npr. točke pri testu spremenimo v ocene

<font color="#92cddc">Oznake</font>: 
- števila označimo z $x_1, x_2, ..., x_n$,
- razrede pa z $X_1, X_2, ..., X_r$,
in običajno velja, da $n >> r$.

<font color="#92cddc">Modus</font> - $M_0$ - je tisti podatek, ki se največkrat pojavi. 

<font color="#92cddc">Mediana</font> - $M_e$ - je "srednji" podatek, to pomeni, če pa imamo sodo število podatkov, je to povprečje "sredinskih" dveh podatkov.

<font color="#92cddc">Centili</font> - (procenti) - 25-ti <font color="#92cddc">centil</font> lahko poimenujemo prvi <font color="#92cddc">kvartil</font>, 50-ti centil, kot drugi kvartil ali <font color="#92cddc">mediana</font>, 75-ti centil pa tretji kvartil.

<font color="#92cddc">Škatla z brki</font> - predstavlja obseg prvega in tretjega kvartila.

---

<font color="#92cddc">Povprečje</font>:
$$\frac{\sum_{i = 1}^{N}x_i}{N} = \overline{x}$$

---

<font color="#92cddc">Mere razpršenosti</font>:
- [[varianca]] je kvadrat [[pričakovani odklon|pričakovanega odklona]] populacije:
	$$\sigma² = \frac{\sum_{i = 1}^{N}(x_i - \mu)²}{N}$$
	- kjer je $\mu$ povprečje in $\sigma$ standardni odklon.
- <font color="#92cddc">standardni odklon</font> je pozitivno predznačen kvadratni koren variance

---

<font color="#92cddc">Sredine</font>:
- [[aritmetična sredina]];; $A_n = \frac{a_1, a_2, ..., a_n}{n}$ ; primerna za podatke, ki so enakomerno porazdeljeni, saj je zelo občutljiva na ekstremne primere.

- [[geometrična sredina]];; $G_n = \sqrt[n]{a_1\cdot ... \cdot a_n}$ ; bolj uporabna, ko so vrednosti odvisna druga od druge in ko je treba poudariti multiplikativne spremembe.

- [[harmonična sredina]];; $H_n = \frac{n}{\frac{1}{a_1}+...+\frac{1}{a_n}}$ ; nanjo bolj vplivajo manjše vrednosti, je najboljša za razmerja.

- [[kvadratna sredina]];; $K_n = \sqrt{\frac{a_1²+ ... + a_n²}{n}}$ ; nanjo bolj vplivajo, večje spremembe in dobro prikazuje odklone.

- npr. za $n = 2$ velja: $H_2 \leq G_2 \leq A_2 \leq K_2$

- [[potenčna sredina]];; $P_{n, k} = \sqrt[k]{\frac{a_1^k + ... + a_n^k}{n}}$

---

Če ima podatkovna množica porazdelitev <font color="#92cddc">približno zvonaste oblike</font>, potem velja približno:
- $68\%$ podatkov leži na razdalji $\pm1\sigma$,
- $96\%$ - $\pm2\sigma$,
- $99,5\%$ - $\pm3\sigma$

---

<font color="#92cddc">Standardizacija</font> - vsaki vrednosti $x_i$ odštejemo povprečje $\mu$ in delimo z njenim standardnim odklonom $\sigma$.
$$z_i = \frac{x_i - \mu}{\sigma}$$
Velja, da je $\overline{z} = 0$ in da je $\sigma_z = 1$. 

---

<font color="#92cddc">Flashcards:</font>

Katera dva tipa podatkov poznamo?;; Kvantitativni in kvalitativni.
Kaj je modus?;; To je podatek, ki se največkrat pojavi.
Kaj je mediana?;; To je "srednji" podatek, če so vsi razvrščeni po vrstnem redu
Kaj je varianca + enačba;; Varianca je kvadrat pričakovanega odklona populacije $\sigma² = \frac{\sum_{i = 1}^{N}(x_i - \mu)²}{N}$.
Kaj je standardni odklon?;; Je pozitivno predznačen koren variance.

---
