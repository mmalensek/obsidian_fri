[[predavanje-opb-8-teden]], [[organizacija_datotek_in_indeksi.pdf|pdf o tej temi]];

### Organizacija datotek
- uporabnik zahteva nek zapis od SUPB:
	- SUPB naredi preslikavo logičnega zapisa v fizični
	- in ga na to prepiše v primarni pomnilnik oziroma medpomnilnik.

<font color="#6425d0">Datotečna organizacija:</font>
- <font color="#245bdb">kopica</font> (ali neurejena datoteka)
	- zelo učinkovita za <font color="#92d050">dodajanje zapisov</font>
		- zapisi so v takem vrstnem redu, kot so bili dodani,
		- če ni dovolj prostora, se doda nova stran
	- a je <font color="#8064a2">iskanje</font> zelo neučinkovito,
	- prav tako pa predstavlja težavo <font color="#8064a2">neizkoriščenost prostora</font>, ki ga puščajo brisani zapisi

- <font color="#245bdb">zaporedno urejena datoteka</font>
	- zapisi so urejeni po enem ali več poljih
	- omogoča <font color="#92d050">binarno iskanje</font> (bisekcijo)
	- a ta vrstni red <font color="#8064a2">rabimo vzdrževati</font>, ko dodajamo in brisamo zapise
	- <font color="#8064a2">dodajanje zapisa na začetek</font> velike datoteke je posebej problematično, kar rešujemo <font color="#8064a2">z dodatno neurejeno podatko</font> (nekim heap-om), kamor pogledamo če z bisekcijo nismo našli zapisa

- <font color="#245bdb">razpršena</font> (ali hash) <font color="#245bdb">datoteka</font>
	- zapisi so razpršeni v skladu s hash funkcijo
	- input output take datoteke <font color="#92d050">je najhitrejša</font> od vseh ostalih
	- a ima določene <font color="#8064a2">omejitve</font> pri iskanju
	- imamo tudi <font color="#f79646">tehnike za reševanje kolizije</font>:
		- <font color="#4bacc6">odprto naslavljanje:</font>
			- zapisovanje: kolizija $\rightarrow$ poiščemo prvo stran, ki ima še kakšno prosto mesto
			- iskanje: se podaljša, ker rabimo poiskati vse do prvega prostega mesta če na hash funkciji ni iskanega elementa
		- <font color="#4bacc6">nepovezane dodatne strani:</font>
			- vzdržujemo seznam dodatnih strani
		- <font color="#4bacc6">povezane dodatne strani (najbolj učinkovit):</font>
			- ko pride do kolizije, ga damo potem v prvo prosto stran, ki si jo tudi zapišemo kot dodatni podatek tiste polne strani
		- <font color="#4bacc6">večkratno razprševanje:</font>
			- v primeru kolizije se uporabi dodatna hash funkcija, ki vrača drugačen naslov, ki razvršča v dodatni prostor


<font color="#8064a2">Dinamične razpršene datoteke:</font>
- razširljivo razprševanje (extendible hashing)
- primer: ![[Screenshot 2024-11-22 at 10.39.34.png|300]]

### Indeksi in indeksiranje

...

<font color="#8064a2">Drevesno indeksiranje:</font>
- ISAM (indexed sequential access method)
- B+ drevesna struktura (kle velik manjka)

<font color="#8064a2">Stiskanje ključev:</font>
- npr. imamo atribut "priimek" rezervirano 500 char, a redko bomo uporabili več kot 10 char

<font color="#8064a2">Bitni indeks:</font>
- uporabimo takrat ko ni veliko možnosti za vrednost nekega atributa npr. pozicija v službi.

<font color="#8064a2">Stični indeks:</font>
- uporablja se za tabele, ki imajo skupna polja

<font color="#8064a2">Gruče:</font>
- označuje skupino relacij, ki so fizično shranjene skupaj, imajo nekatere stolpce enake in se pogosto uporabljajo skupaj