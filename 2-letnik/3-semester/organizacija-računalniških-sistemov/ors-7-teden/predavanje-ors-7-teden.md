### [[ors]], 7.teden, 14-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #ors-flashcards 

---

### Vsebina:
[[predavanje-ors-6-teden]]; 

### Intel 8259A prekinitveni krmilnik
- enak princip vektorskih prekinitev

![[predavanje-ors-7-teden 2024-11-14 12.34.19.excalidraw|200]]

- časovni potek:
	1) aktiviramo $INT$ (in s tem zahtevamo prekinitev)
	2) $CPE$ se odzove in shrani stanje na sklad
	3) $CPE$ prvič aktivira $INTA$ v trajanju $1$ urine periode, kar imenujemo $INTA$ pulz
	4) nato po 4 urinih periodah aktivira še drugi $INTA$ pulz, s tem je od tisteha, ki ga prekinja zahteval prekinitveni vektor na podatkovnem vodilu
- ta specifičen krmilnik je omogočal do 8 prekinjajočih naprav:

![[predavanje-ors-7-teden 2024-11-14 12.42.09.excalidraw|200]]

- je programabilen $\Rightarrow$ $CPE$ je s pisanjem v njegove registre nastavljal način delovanja
- potek:
	1) npr. aktivira se $IRQ2$ na $8259A$ krmilniku
	2) $8259A$ aktivira $INT$
	3) $CPE$ shrani stanje in aktivira $INTA$ (1.pulz)
	4) $CPE$ čez 4. urine periode aktivira 2.pulz
	5) $8259A$ na podatkovno vodilo postavi $OFFSET \ | \ IVN$ (kar je skupaj 8 bitov)
	6) $CPE$ v $PC \leftarrow [4\cdot IVN+ OFFSET|000]$   
- za dodajanje prekinjajočih naprav so predvideli možnost kaskadne vezave (kjer je en master, drugi slave, kjer je samo master dejansko prekinjal $CPE$, ampak sta oba bila vezana na podatkovno vodilo $CPE$), kar je namesto 8 omogočilo 15 naprav (ena povezava je namenjena kaskadni povezavi $IRQ$-jev).

---
