### [[vs]], 12. teden, 18-12-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #vs-flashcards 

---

### Vsebina:

### Analogno digitalni konverterji - ADC
Pretvori neko analogno količino (ponavadi napetost) pretvori v digitalno vrednost, kjer si omejen s številom bitov, medtem ko je analogna količina seveda zvezna (z neskončno možnimi vrednostmi, odvisno od natančnosti merjenja).

Npr. 8-bitov, kjer je zvezna količin od $0$ do $x$, bitne vrednosti pa zasedajo od $0{...}2^8-1$ 

<font color="#7030a0">Osnovni princip delovanja</font>, predpostavka : 4-biti na voljo
$V_{sense}$ - napetost, ki jo tipamo. Zanjo želimo da je med pretvarjanjem konstantna, zato ima vsak konverter stikalo in kondenzator, zato da se ta kondenzator najprej napolni in se potem stikalo stakne in lahko v miru preberemo napetost na kondenzatorju.

<font color="#7030a0">Pretvorba:</font> (ko mine dovolj časa da se kondenzator napolni)
Dobljeno napetost peljemo v komparator, kjer jo primerjamo z $V_{ref}$ in vrne $1$, če je večji in $0$ če velja obratno, kjer potem z bisekcijo probavaš aproksimirati vrednost na kondenzatorju.
Visoko zmogljiv ADC (kot npr. ta v našem STM ima 16 bitov za aproksimacijo)

### ADC v STM32H7
Vsebuje 3 $ADC$ pretvornike: $ADC1, ADC2, ADC3$ in so vsi 16 bitni, a je število bitov za aproksimacijo nastavljivo (16, 12, 10, 8).

So 20 kanalni, torej lahko en $ADC$, preko multiplekserja lahko tip 20 različnih veličin, seveda ne naenkrat, saj npr. merjenje temperature ne bomo izvajali konstantno, ampak npr. samo enkrat na minuto, zato je brezveze cel $ADC$ rezervirati samo za eno redko merjenje.

Lahko zajamejo več kanalov zaporedoma v izbranem vrstnem redu.

Kanale praviloma vežem na enega od GPIO pinov, vendar imajo nekateri kanali fiksno vezane naprave, npr. $ADC3$ - kanal 18 meri temperaturo v jedru čipa.

---
