[[predavanje-ors-11-teden]]; #ors-flashcards 

Informacija se hrani v obliki naboja na parazitni kapacitivnosti tranzistorja, kar predstavlja <font color="#92d050">prednost</font> zaradi majhnosti pomnilniške celice, pomeni da bo kapaciteta pomnilnika lahko velika. 

A ima nekaj <font color="#c0504d">slabosti</font>:
- tega naboja je zelo malo in 
- ga je težko zaznati tako majhno spremembo napetosti, 
- ta naboj izginja s čimer se informacija izgublja (dandanes je to okoli 64ms),
- vsako branje je destruktivno.

(DRAM polje na skici iz [[predavanje-ors-10-teden]])

Ta DRAM polja lahko vzporedno zložim in dobim DRAM banko. 
Kako izgleda dostop (ozr. branje zelo podobno):
- naslovimo vrstico, tako da aktiviramo njen word line (wl)
- naslovimo stolpec, ki ga želimo prebrati in ga na izhodu iz tipalnega ojačevalnika preberemo (1 bit iz enega DRAM polja)

Če pa želimo z enim naslovom vrstice in stolpca prebrati več bitov naenkrat ($N$) potem dostopamo do $N$ vzporednih polj (banka).

Ideja: vzdolž banke ($z$ os) tvorimo $N$-bitne pomnilniške besede.

Predpostavimo polje $4\times 4$ celic:
![[DRAM 2024-12-12 10.54.59.excalidraw]]

Ko aktivirmo en WL (= aktiviramo vrstico, odpremo vrstico) preberemo v tipalnem ojačevalniku vse bite v tej vrstici in jih hranimo v tipalnih ojačevalnikih (register vrstice). Dostop do podatkov v registru vrstice je hitreje kot dostop iz vrstice DRAM polja, kar nas sili, da do podatkov shranjenih v DRAM-ih dostopoamo po zaporednih besedah (64, ker se ob zgrešitvi v L3 pomnilniku prenese cel 64 bajtov dolg blok).

### Časovni potek branja

![[DRAM 2024-12-12 12.23.38.excalidraw]]

---

Ne smemo takoj spet odpreti nove vrstice, ker potrebujemo najprej spet zapisati nazaj. Vse skupaj to traja okoli $100ns$ medtem ko procesor dela s $\frac{1}{3}ns$, torej je še vedno veliko počasnejši in potrebujemo predpomnilnik.

---

### Izboljšave tega DRAM-a
1. vpeljemo CLK v DRAM
2. vpeljemo eksplozijske prenose - z enim naslovom stolpca prenesemo več zaporednih stolpcev
3. več bank - zato, da ko iz ene berem iz druge lahko že odpiram novo vrstico in nekako prikrijem zamike in skrajšam čas dostopa

Temu rečemo sinhroni dinamični RAM ([[SDRAM]]).

---