### [[opb]],  11. teden, 13-12-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #opb-flashcards 

---

### Vsebina:

### Načrtovanje fizične podatkovne baze
Proces, s katerim izdelamo opis implementacije PB na sekundarnem pomnilnem mediju.

1. <font color="#9bbb59">pretvorba v jezik za SUPB</font>
	- iz logičnega modela izdelati podatkovno shemo za ciljni SUPB in moramo poznati funkcionalnost danega SUPB zelo dobro
	- izdelava osnovnih relacij
	- predstavitev izpeljanih atributov - navesti moramo kako se bodo taki atributi izračunali ali jih bomo sploh hranili, kjer gledamo na "strošek" shranjevanja ali računanja, npr. starost je nesmiselno shranjevati, saj bi jo morali vsako leto ponovno računati
	- načrt splošnih omejitev - npr. da v bazo ne moremo vpisati ne veljavne EMŠO številke
2. <font color="#9bbb59">datotečna organizacija in indeksi</font>
	- analiza transakcij (primer matrike:)
	![[Screenshot 2024-12-13 at 09.58.27.png|400]]
	- izbira datotečne organizacije, npr MySQL ponuja različne vrste shramb podatkov imenovani <font color="#6425d0">storage engine</font>, npr.
		- avtomatsko prevzeti InnoDB,
		- MyISAM,
		- ...
	- izbira indeksa
	- ocena velikosti podatkovne baze
3. <font color="#92d050">načrt uporabniških pogledov</font>
4. <font color="#92d050">načrt varnostnih mehanizmov</font>


---
