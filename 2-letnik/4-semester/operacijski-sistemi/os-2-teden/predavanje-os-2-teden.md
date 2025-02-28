[[predavanje-os-1-teden]];

### Operacijski sistemi
Kaj sploh je? Nabor programske opreme, ki nadzoruje izvajanje programov, povezuje uporabnika s strojno opremo in deluje kot vmesnik med programi in strojno opremo.

Za uporabnika ima cilj, da čim bolj olajša uporabo računalnika.

### Koncepti operacijskih sistemov
1. abstrakcija
2. virtualizacija - ne skrije podrobnosti tako kot abstrakcija
3. varnost - npr. zaščita pomnilnika, izolacija procesov, ...
4. sočasnost - občutek hkratnega izvajanja večih procesov - concurrency
5. persistenca - učinkovitost hrambe, dolgoročni obstoj podatkov in informacij, ...

### Jedro operacijskega sistema
Programska koda, ki vsebuje bistveni del OS, npr. upravljanje s procesi in pomnilnikom. Izvaja se v privilegiranem načinu delovanja procesorja (medtem ko sistemska in aplikacijska programska oprema tečeta v zaščitenem načinu).

Procesorski nivoji zaščite:
Vsak OS potrebuje najmanj dva nivoja. To sta <font color="#4bacc6">zaščiteni</font> način, ki omejuje uporabo procesorja in katerega napačna uporaba povzroči izjemo. <font color="#4bacc6">Privilegirani</font> način pa omogoča neomejen dostop do pomnilnika in naprav, nekateru ukazi se lahko izvajajo samo v tem načinu.

Mnoge arhitekture pa omogočajo še tretji način - <font color="#4bacc6">hipervizorski</font> način, ki omogoča virtualizacijo.

### Komunikacija med jedrom in programsko opremo
Vmesnik jedra nam predstavljajo sistemski klici.

### Arhitektura jedra
Kakšna je struktura in način povezovanje med posameznimi deli jedra, to je arhitektura jedra. 

Poznamo več vrst:
- <font color="#4bacc6">monolitno jedro:</font>
	- (en) velik kos strojne kode, ki vsebuje celotni OS
	- <font color="#92d050">omogoča hitro komunikacijo med posameznimi deli OS</font>
	- <font color="#ff0000">a napaka v enem delu OS lahko povzroči sesutje celotnega OS</font>
	- <font color="#ff0000">prav tako je zelo težko obvladljiva celotna koda</font>
	- npr. Windows 95

- <font color="#4bacc6">monolitno modularno jedro:</font>
	- omogoča modularno zasnovo jedra, torej lahko delčke jedra (predvsem gonilnike), prevajamo posebej in vložiti in izločiti iz jedra tekom samega izvajanja
	- <font color="#ff0000">še vedno napaka dela OS lahko povzroči sesutje celotnega OS</font>
	- npr. Linux

- <font color="#4bacc6">mikro jedro:</font>
	- vsebuje samo osnovne funkcionalnosti
	- ostale funkcionalnosi pa so izvedene preko procesov (v uporabniškem načinu, <font color="#ff0000">medsebojni klici pa so časovno zahtevnejši</font>)
	- <font color="#92d050">omogoča pa boljšo prilagodljivost, porazdeljenost, varnost in enostavnejšo implementacije</font>
	- npr. Mach