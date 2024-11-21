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

### Kaskadne vezave
- Za dodajanje prekinjajočih naprav so predvideli možnost kaskadne vezave (kjer je en master, drugi slave, kjer je samo master dejansko prekinjal $CPE$, ampak sta oba bila vezana na podatkovno vodilo $CPE$), kar je namesto 8 omogočilo 15 naprav (ena povezava je namenjena kaskadni povezavi $IRQ$-jev), v teoriji bi lahko kaskadno vezali neomejeno število naprav, v praksi pa največ dva.

- zgled: prekinitvena zahteva pride na $slave$ $IRQ5$ in $IRQ3$, ki ima višjo prioriteto.
	1) $slave$ aktivira svoj $int$ in s tem odda prekinitven zahtevo na $master$ $IRQ2$
	2) $master$ aktivira svoj $int$
	3) $CPE$ zaključi izvajanje trenutno izvajajočega se ukaza in aktivira $inta$ za čas 1 urine periode ($inta$ pulz), s tem sporoči obema, da je videl prekinitveno zahtevo
	4) po 4 u.p. $CPE$ drugič aktivira $inta$ pulz
	5) $master$ je bil programiran tako, da je vedel, da ima na $IRQ2$ kaskano vezan še en $8259A$ zato $master$ ignorira 2. $inta$ pulz, $slave$ pa ob 2. $inta$ pulzu na podatkovno vodilo zapiše: $offset | ivn$ (offset in interrupt vector number)
	6) $CPE$ v $PC\leftarrow M[(offset|ivn) \times 4]$, zato morata biti offset-a pri $master$ in $slave$ različna


### APIC - advanced programmable interrupt controller
Pojavi se potreba o več jedrnih $CPE$ v sistemu.

Ideja: Prekinitveni krmilnik ni en sam čip, temveč je par dveh:
- $IOAPIC$ - input/output ($APIC$), pobira prekinitvene zatheve V/I naprav, in jih kot sporočila na vodilu, pošilja v $LAPIC$.
- $LAPIC$ - local ($APIC$), se nahaja v $CPE$

![[predavanje-ors-7-teden 2024-11-21 10.56.08.excalidraw]]

Potem so sredi 90-tih let vpeljali novo vodilo v računalniški sistem $\rightarrow PCI$. V $PCI$ kompatibilne naprave so vgradili funkcionalnost pošiljanja sporočil v $LAPIC$-e, ki jih imenujemo $MSI$ (message signaled interrupt).

---
