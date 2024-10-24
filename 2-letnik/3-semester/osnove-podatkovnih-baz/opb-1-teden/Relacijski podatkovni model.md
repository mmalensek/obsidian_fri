[[predavanje-opb-1-teden]];

---

<font color="#92cddc">Relacija</font>;; dvodimenzionalna tabela s stolpci in vrsticami, je <font color="#92cddc">logična struktura</font> podatkovne baze in ne fizična.
<!--SR:!2024-11-12,20,250-->

<font color="#92cddc">Atribut</font>;; poimenovan stolpec relacije
<!--SR:!2024-11-03,15,290-->

<font color="#92cddc">Domena</font>;; množica dovoljenih vrednosti enega ali več atributov npr. domena za EMŠO je število (13 cifer)
<!--SR:!2024-10-26,11,270-->

<font color="#92cddc">N-terica</font>;; je ena vrstica v relaciji
<!--SR:!2024-11-03,15,290-->

<font color="#92cddc">Števnost relacije</font>;; število n-teric relacije
<!--SR:!2024-10-30,11,270-->

<font color="#92cddc">Stopnja relacije</font>;; število atributov v relaciji
<!--SR:!2024-10-29,10,250-->

<font color="#92cddc">Relacijska podatkovna baza</font>;; množica normaliziranih relacij z enoličnimi imeni
<!--SR:!2024-10-24,1,130-->

Zakaj pravimo da je relacija <font color="#92cddc">podmnožica</font> kartezičnega produkta vseh atributov? ($r \subset x_1 \times x_2 \times ...$);; Ker s kartezičnim produktom vseh atributov, generiramo veliko več variacij relacij, kot jih pa je npr. v neki podatkovni bazi.
<!--SR:!2024-10-26,11,270-->

| <font color="#92cddc">Ime</font> | <font color="#92cddc">Starost (leta)</font> | <font color="#92cddc">Teža (kg)</font> |
| -------------------------------- | ------------------------------------------- | -------------------------------------- |
| Bojan                            | 20                                          | 75                                     |
| Vid                              | 14                                          | 43                                     |
| Smeh                             | 29                                          | 69                                     |

<font color="#92cddc">Relacijska shema:</font>
?
	- predstavlja semantiko ali pomen relacije
	- del konceptualnih ali zunanjih shem,
	- semantika ni bogata, zato tudi besedni opisi
	- R(A1:D1, A2:D2, ..., An:Dn)
	^ <font color="#92cddc">oznaka sheme</font>          ^ <font color="#92cddc">oznaka domene</font>, ...
	- npr. Študent(VpŠt: number(8), Ime: char(20), ...)


<font color="#92cddc">Lastnosti relacij:</font>
?
	- ime relacije je enolično (znotraj sheme),
	- celica tabele vsebuje natančno eno atomarno vrednost,
	- ime atributa relacije je enolično (znotraj relacije),
	- vrednosti atributa so iz iste domene,
	- n-terica je enolična (znotraj relacije),
	- vrstni red atributov v relaciji je nepomemben,
	- vrstni red n-teric v relaciji je nepomemben.


<font color="#92cddc">Funkcionalne odvisnosti:</font>
?
	- predpostavimo, da obstaja relacijska shema $R$ z množico atributov, katere podmnožici sta $X$ in $Y$,
	- v relacijski shemi $R$ velja $X\rightarrow Y$ ($X$ funkcionalno določa $Y$ oziroma je funkcionalno odvisen od $X$),
	- množico funkcionalnih odvisnosti označimo s $F$
	- npr. Izpit(VpŠt, Priimek, Ime, ŠifraPredmeta, ...)
	V tem primeru VpŠt določa Priimek in Ime; VpŠt skupaj z ŠifraPredmeta in DatumIzpita pa določa OcenaPisno in OcenaUstno.

<font color="#92cddc">Ključ relacije</font>;; je najmanjši nabor atributov, ki funkcionalno določa ostale atribute
<!--SR:!2024-10-24,5,230-->

Poznamo več <font color="#92cddc">konceptov</font>, ki jih poimenujemo ključ:
?
	- kandidat za ključ - npr. EMŠO in vpisna številka, mi izberemo enega
	- primarni ključ
	- superključ / nadključ
	- tuji ključ - ključ iz neke druge relacije



---

#opb-flashcards 

---
