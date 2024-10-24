### [[vs]], 1.teden, 02-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano  #vs-flashcards

---

### Vsebina:

Dva načina programiranja embedded sistemov:
	1) nek <font color="#92cddc">"super" loop</font>
		bolj počasno
	2) se uporablja nek <font color="#92cddc">osnovni operacijski sistem</font>
		občutek delovanje "real-time"

Arhitektura procesorja <font color="#92cddc">določa vrste ukazov in vrste podatkov</font>, ki jih uporablja/pozna procesor in tudi <font color="#92cddc">koliko registrov</font> ima procesor in tudi to, ali zna delati s <font color="#92cddc">skladom</font> (first-in/last-out), kar prinese veliko težav pri delovanje [[Cevovod|cevovoda]].

Procesor tudi mora imeti definirano, kaj naredi, kaj se zgodi, ko dobi nek <font color="#92cddc">neveljavni ukaz</font> (npr. neznan ukaz, neveljavni vhodni podatki, neveljavni naslov) in izvede <font color="#92cddc">izjemo</font> - [[Past|PASTI]]. Prebere-izvede poseben ukaz, spremeni programski števec na nek predpisan način, kjer se nahaja prvi ukaz, kateri se izvede, ko je nekaj narobe.

Kako lahko računalnik <font color="#92cddc">hkrati</font> upravlja motor in hkrati bere vhod iz touch zaslona?
	Prvi proces rabimo prekiniti, s tem da imamo <font color="#92cddc">"interrupt request"</font> vodilo, katero procesor ob vsaki urini periodi preveri in je nekakšna "<font color="#92cddc">zunanja" izjema</font> - [[Prekinitve|PREKINITVE]].

### [[Programski model ARM Cortex-M]]
	![[Programski model ARM Cortex-M]]

---

<font color="#92cddc">Flashcards:</font>

Katera dva načina programiranja embedded sistemov poznamo?;; "super" loop in RTOS
<!--SR:!2024-11-03,15,290-->
Na kaj vpliva arhitektura procesorja?;; Na vrste ukazov, tipe podatkov, s katerimi dela in ali zna delati s skladom (problematično glede cevovoda).
<!--SR:!2024-11-03,15,290-->
Kaj je past?;; Poseben ukaz, ki spremeni PC na vrednost "trap handlerja" in se izvede v primeru neveljavnega ukaza.
<!--SR:!2024-10-27,8,250-->
Kaj je prekinitev?;; Povzroči jo nek zunanji dogodek (npr. signal miške), ki omogoča delovanje "interrupt handlerja" in s tem branje iz V/I naprav npr.
<!--SR:!2024-11-20,28,270-->

---
