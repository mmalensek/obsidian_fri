[[predavanje-opb-9-teden]], [[načrtovanje_podatkovnih_baz.pdf]]; #opb-flashcards 

Dva osnovna pristopa k načrtovanju PB:
- od <font color="#4bacc6">spodaj navzgor </font>in
	- začne z atributi ter jih združuje v skupine
	- primeren za enostavne PB
	- tak pristop predstavlja normalizacija
- iz <font color="#4bacc6">vrha navzdol</font>.
	- na začetku modeli z le nekaj osnovnih entitetnih tipov in razmerij
	- to predstavlja uporaba tehnike "Entiteta - Razmerje (E-R)"

Za kompleksne domene pristop <font color="#4bacc6">"po delih"</font>.

Trije nivoji podatkovnega modeliranje:
- konceptualni,
- logični in
- fizični.

### Konceptualno načrtovanje
Je neodvisno od tehnologije, kjer je cilj razumeti domeno, ter identificirati koncepte, ki jih želimo hraniti v bazi.

Za izdelavo konceptualnega načrta/modela lahko uporabimo različne tehnike, ena najbolj uporabljenih je tehnika <font color="#4bacc6">entiteta-razmerje</font> (ER).

Delamo <font color="#4bacc6">abstrakcijo</font> - izberemo le lastnosti, ki nas glede entitet nekega tipa zanimajo, tem izbranim lastnostim pravimo atributi.

Vrste atributov:
- <font color="#4bacc6">totalni</font>; ki mora imeti vredno vrednost
- <font color="#4bacc6">več-vrednostna</font>; lahko jih je več
- <font color="#4bacc6">parcialni</font>; ni nujno, da ima vrednost
- <font color="#4bacc6">eno-vrednostni</font>; ima lahko le eno vrednost

Med entitetami/tipi lahko obstjajo različna razmerja, ki izhajajo iz dejanskih povezav med njimi, ki jih prikažemo s črto.

Za števnost razmerja na vsaki strani označimo <font color="#4bacc6">minimalno in maksimalno</font> števnost.

Med opazovanim parom entitet/tipov je <font color="#4bacc6">lahko več razmerij</font>. Npr. študent je izbral nič ali več predmetov in študent je opravil nič ali več predmetov.

Kdaj je entitetni tip <font color="#4bacc6">močan ali šibek</font>?
Je močen, ko ima dovolj svojih atributov, da ga je možno enolično identificirati in šibek če velja obratno.

Razširjena ER notacija:
- <font color="#4bacc6">specializacija</font>; entitetni tip je posebna vrsta drugega entitetnega tipa
- <font color="#4bacc6">generalizacija</font>; entitetni tip je posplošitev več podobnih entitetnih tipov
- <font color="#4bacc6">agregacija</font>; predstavlja razmerje, v katerem je en entitetni tip neka celota, drugi pa njen del
- <font color="#4bacc6">kompozicija</font>; kadar je povezava tako močna, da entitetni tip, ki predstavlja del, ne more obstajati brez entitetnega tipa

Metoda konceptualnega načrtovanja:
-  <font color="#76923c">identificiraj entitetne tipe</font>
- <font color="#76923c"> indentificiraj povezave</font>
-  <font color="#76923c">identificiraj in z entitetne tipe poveži atribute</font>
	-  atribute delimo na:
		- sestavljene,
		- več-vrednostne,
		- izpeljane.
-  <font color="#76923c">atributom določi domene:</font>
	- določi množico možnih vrednosti
-  <font color="#76923c">določi kandidate za ključe, izberi primarni ključ:</font>
	- če je kandidatov več, kaj potem?
		- tisti za katerega je najmanj verjetno, da se bodo njegove vrednosti spreminjale
		- tisti z najmanjšo dolžino znakov (za alfanumerične kandidate)
		- tisti z najmanjšo maksimalno vrednostjo (za numerične kandidate)
-  <font color="#76923c">po potrebi uporabi elemente razširjenega diagrama entiteta-razmerje</font>
-  <font color="#76923c">preveri, če obstajajo odvečni elementi</font>
	- gledamo samo povezave $1-1$, kar je že tako redko
- <font color="#76923c"> preveri če model zdrži transakcije</font>
	- npr. na prosojnicah je primer za drugo transakcijo, da jo ne zdrži, ker lahko pogledamo na katero smer je vpisan študent, samo če je že opravljal kakšen izpit, torej moramo dodati neko novo direktno povezavo do predmeta ali smeri, ...
-  <font color="#76923c">preveri model z uporabnikom</font>

### Logično načrtovanje podatkovnih baz

V logičnem modelu bojo v atribute vključeni tudi tuji ključi, da vemo kateri je tuji ključ je relacija predstavljena s puščico, kjer glava puščice kaže izkod izhaja tuji ključ.



---


