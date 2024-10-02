### [[vs]], 1.teden, 02-10-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #flashcard

---

### Vsebina:

Dva načina programiranja embedded sistemov:
	1) nek <font color="#92cddc">"super" loop</font>
		bolj počasno
	2) se uporablja nek <font color="#92cddc">osnovni operacijski sistem</font>
		občutek delovanje "real-time"

Arhitektura procesorja <font color="#92cddc">določa vrste ukazov in vrste podatkov</font>, ki jih uporablja/pozna procesor in tudi <font color="#92cddc">koliko registrov</font> ima procesor in tudi to, ali zna delati s <font color="#92cddc">skladom</font> (first-in/last-out), kar prinese veliko težav pri delovanje <font color="#92cddc">cevovoda</font>.

Procesor tudi mora imeti definirano, kaj naredi, kaj se zgodi, ko dobi nek <font color="#92cddc">neveljavni ukaz</font> (npr. neznan ukaz, neveljavni vhodni podatki, neveljavni naslov) in izvede <font color="#92cddc">izjemo</font>. Prebere-izvede poseben ukaz, spremeni programski števec na nek predpisan način, kjer se nahaja prvi ukaz, kateri se izvede, ko je nekaj narobe.

Kako lahko računalnik <font color="#92cddc">hkrati</font> upravlja motor in hkrati bere vhod iz touch zaslona?
	

---

<font color="#92cddc">Flashcards:</font>

vprasanje;; odgovor

---
