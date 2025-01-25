### Napredno urejanje

1. <font color="#4bacc6">merge sort: </font>razdeli elemente seznama na prvo in drugo polovico, rekurzivno uredi vsako polovico na enak način, nato pa združi dva urejena seznama v skupen urejen seznam. Globina rekurzije je $O(\log n)$, ker sezba vsakič razdelimo na pol, za posamezen nivo pa potrebujemo $O(n)$ časa za združevanje. <font color="#4bacc6">Časovna zahtevnost</font> je zato vedno $O(n \log n)$. Da zmanjšamo prostorsko zahtevnost lahko uporabimo le pomožno tabelo za indekse in ne delamo kopij tabele.
2. <font color="#4bacc6">quick sort: </font>ta razdeli elemente seznama na majhne in velike, majhne da na začetek seznama, velike pa na konec, za število po katerem ločujemo izberemo naključen $pivot$, npr. prvi element seznama. Nato gremo čez seznam in delimo elemente seznama v tri skupine: manjše, večje in enake pivotu. V najslabšem primeru pridemo tako do $O(n^2)$ <font color="#4bacc6">časovne zahtevnosti</font>, a je še vedno v povprečju ta enaka $O(\log n)$. Prostorska zahtevnost pa je odvisna od implementacije od $O(\log n)$ do $O(n)$.
3. <font color="#4bacc6">heap sort: </font> ... izboljšava navadnega urejanja z izbiranjem, le da vedno znova iščeš najmanjši element samo med neurejenimi, ... (heap)
4. <font color="#4bacc6">counting sort: </font>ko imaš nabor različnih možnosti, ki ni velik (npr. poštne številke), kjer za vsako vrednost preštejemo kolikokrat se uporabi in jo na koncu temu primerno večkrat vnesemo v urejen seznam. Časovna zahtevnost je linearna ozr. $O(n + m)$, kjer je $m$ največja možna vrednost, neugodna pa je prostorska zahtevnost.
5. <font color="#4bacc6">bucket/bin sort</font> (mi pogledamo <font color="#4bacc6">radix sort</font>): osnovna ideja je, da razdeliš elemente seznama v koše glede na njihovo vrednost in rekurzivno dobimo nekaj podobnega $quicksortu$. Pogledamo si $radix \ sort$ ozr. <font color="#4bacc6">korensko urejanje</font>, kjer razporejamo elemente v koše glede na števke v primeru števil (in črke v primeru nizov). Nize lahko razdelimo v koše glede na njihovo prvo črko, nato pa posamezen koš uredimo po enakem postopku, samo da sedaj delimo v koše glede na drugo črko itd. Ko so koši urejeni, rezultate enostavno zložimo nazaj skupaj (poglej si animacijo). Časovna zahtevnost je tako $O(nd)$, če je $d$ dolžina največjega niza, enako pa velja za prostorsko zahtevnost (v resnici, je zraven še faktor $a$ - velikost abecede, samo da je ta konstanten v večini primerov).

Zakaj to delamo? Da lahko implementiramo, <font color="#4bacc6">binary search</font> (dvojiško iskanje - <font color="#4bacc6">bisekcija</font>) seveda: s časovno zahtevnostjo $O(\log n)$. 

### Abstraktni podatkovni tipi

1. <font color="#4bacc6">polje (array): </font>hrani urejen nabor elementov, do katerih dostopamo s celoštevilskimi indeksi, hrani podatke enakega tipa/velikosti zaporedno enega za drugim v strnjenem kosu pomnilnika.
2. <font color="#4bacc6">sklad (stack):</font> hrani elemente organizirane tako, da lahko dodamo nov element, dostopamo pa lahko samo do tistega, ki je bil dodan nazadnje, za njegovo implementacijo se uporabi povezan seznam, s katerim dosežemi konstantno časovno zahtevnost operacij.
3. <font color="#4bacc6">seznam (list):</font> podobno kot array, samo da lahko hrani različne tipe podatkov.
4. <font color="#4bacc6">povezani seznam (linked list):</font> omogoča učinkovito vsavljanje in brisanje preko kazalcev na elemente.
5. <font color="#4bacc6">dinamično polje (dynamic/resizeable array):</font> je "nadgradnja" osnovnega array-a, ki omogoča dodajanje novih elementov, kjer zaradi časovne zahtevnosti, ki bi jo prinesel array velikosti $n$ vsakič ko bi dodali nov element, se ustvari array z velikostjo (npr.) $2n$, kjer glede na določene faktorje potem malokrat dejansko kopiramo elemente polja v večjega (ali manjšega).
6. <font color="#4bacc6">vrsta (queue):</font> hrani elemente organizirane tako, da lahko dodamo nov element na konec vrste, dostopamo pa lahko do tistega, ki se nahaja na začetku vrste, torej FIFO (first in, first out). Lahko imamo tudi različico z dvema koncema, kjer lahko dodajamo in odstranjujemo z obeh strani. Lahko jo implementiramo s povezanim seznamom, vse operacije imajo tako konstantno časovno zahtevnost, prostorska zahtevnost pa je linearna.
7. <font color="#4bacc6">vrsta s prednostjo (priority queue):</font> podobna navadni vrsti, le da ima vsak element prirejeno tudi prioriteto, ko odstranjujemo elemente iz vrste, prejmemo najprej tistega z največjo (ali najmanjšo) prioiriteto in ne prvega, ki je bil vstavljen. 
8. <font color="#4bacc6">kopica (heap):</font> tipična učinkovita implementacija prioritetne vrste. Obstaj več vrst, mi obravnavamo le dvojiško kopico, za katero velja, da je zgrajena iz poravnanega dvojiškega drevesa, vsako vozlišče pa mora biti manjše ali enako od svojih otrok (oziroma obratno v primeru max-heap). Najmanjši element se tako nahaja v korenu drevesa, višina drevesa pa je $O(\log n)$. Zaradi svoje strukture jo lahko predstavimo kar s tabelo (kjer zaradi enostavnosti začnemo z indeksom 1 in ne 0), kjer velja da ima vozlišče $i$ na indeksu $2i$ in $2i+1$ svoja otroka in obratno svojega starša na indeksu $i / 2$ (zaokroženo navzdol). Nov element vstavimo na prvo prosto mesto, s čimer smo pokvarili urejenost, ki pa jo popravimo, tako delamo menjave s starši, dokler ne pride na ustrezno mesto, ali pa ne pride do korena. Prostorska zahtevnost je linearna, časovna zahtevnost obeh operacij pa sorazmerna z višino kopice, torej $O(\log n)$. S Floydovim algoritmom lahko kopico zgradimo v $O(n)$ času.
9. <font color="#4bacc6">preskočni seznam (skip list):</font> vsako vozlišče ima svojo "višino", ki je izbrana naključno. Vsak nov nivo pa je dodan z verjetnostjo $p$, ki je običajno $0.5$. Pričakovana prostorska zahtevnost je linearna $O(n)$, časovna zahtevnost vstavljanja ali iskanja posameznega elementa pa $O(\log n)$. 
10. <font color="#4bacc6">množica (set):</font> hrani množico elementov, ki ne predpisuje vrstnega reda elementov.
11. <font color="#4bacc6">slovar (map):</font> hrani pare - ključ, vrednost - pri tem pa se vsak ključ lahko pojavi največ enkrat, vsakemu ključu pa je prirejena neka vrednost.
12. <font color="#4bacc6">zgoščena/razpršena tabela (hash map):</font> temelji na zgoščevalni funkciji, ki preslika ključ kot indeks v tabelo določene velikosti, preslikavi različnih elementov v enako vrednost pravimo $trk$, katerih želimo čim manj, a vseeno jih potrebujemo obvladovati z veriženjem. Običajno merimo zasedenost tabele kot razmerje med številom vnesenih elementov in kapaciteto tabele, $\alpha = \frac{n}{H}$, ko ta faktor preseže določeno vrednost (če bi bilo to ena, bi pomenilo, da vedno pride do trka) lahko izvedemo ponovno zgoščevanje, kjer alociramo npr. dvakrat večjo tabelo in izračunamo nove vrednosti. V primeru da iščemo element, ki ne obstaja je pričakovana časovna zahtevnost enaka pričakovani dolžini seznama, torej $\alpha$, če poskrbimo da bo ta faktor neka konstantna vrednost, bo torej pričakovana časovna zahtevnost $O(1)$.

### Drevesne strukture

1. <font color="#4bacc6">vrste dreves: </font>
	1. dvojiška, kjer ima vsako vozlišče dva otroka, bolj splošno je $k$-tiško drevo,
	2. polno, ima v vsakem vozlišču maksimalno število otrok ali nobenega, npr. v dvojiškem drevesu ni vozlišča z le enim otrokom.
	3. popolno, so polna drevesa in vsebujejo maksimalno število vozlišč glede na višino drevesa
	4. urejena in neurejena
	5. iskalna, ki so urejena drevesa, v katerih velja, da vsebuje prvi otrok v svojem poddrevesu najmanjše vrednosti, drugi malo večje itd.
	6. črkovna/znakovna drevesa (trie)
2. <font color="#4bacc6">predstavitev dreves:</font> povezave do otrok in do starša ponavadi hranimo kot kazalce do njih, elemente vstavljamo rekurzivno, izbrišemo pa jih, če nima otrok ga preprosto odstranimo, če ima samo enega otroka, ga preprosto zamenjamo z njim, če ima pa oba otroka, pa ga zamenjamo z naslednjim večjim vozliščem (to je vozlišče, ki je najbolj levo v desnem poddrevesu, tega pa le preprosto odstranimo, saj zagotovo nima otroka), včasih lahko tudi pogoljufamo in se delamo da tega vozlišča preprosto ni.
3. <font color="#4bacc6">poizvedba na območjih (na statičnih drevesih):</font>
	1. vsota: pripravimo si tabelo kumulativnih vsot od začetka tabele in ju za poljubna elementa samo odštejemo.
	2. minimum: s statičnim drevesom, kjer imamo v vsakem korenu poddrevesa najmanjšo vrednost tega poddrevesa.
4. <font color="#4bacc6">uravnotežena drevesa:</font>
	1. AVL drevo: v vsakem vozlišču se višina levefga in desnega poddrevesa razlikuje kvečjemu za 1, to pomeni, da je višina drevesa $O(\log n)$. 
	2. rdeče-črno drevo: uporablja barvanje vozlišč z rdečo in črno barvo, s pravili kot so: prazna vozlišča so črna, rdeča vozlišče nima rdečih otrok, poti od vsakega vozlišča do praznih potomcev vključujejo enako število črnih vozlišč
	3. 2-3 drevo: vsako vozlišče ima dva ali tri otroke
	4. B-drevo: posplošitev 2-3 drevesa. V B-drevesu reda $m$ imajo vozlišča največ $m$ otrok, notranja vozlišča pa vsaj $m/2$. Vsi list pa se nahajajo na enaki globini.


### Požrešni algoritmi 

Pri požrešnem pristopu reševanja se na vsakem koraku odločimo za izbiro, ki v tistem trenutku zgleda najbolj obetavno, vendar takšni algoritmi ne delujejo pri vseh problemih, le pri "enostavnejših". Dokazovanje pravilnosti požrešnih algoritmov s prednostjo - dokažemo, da je po vsakem koraku rešitev vsaj tako dobra kot katerakoli druga, - zamenjava, dokažemo, da lahko z določenimi spremembami pretvorimo predpostavljeno boljšo rešitev v tako, ki bi jo našla tudi požrešna metoda, -struktura, dokažemo, da neko strukturno lastnost optimalne rešitve, ki predstavlja mejo in dokažemo, da jo požrešna rešitev res doseže.


### Grafi

1. <font color="#4bacc6">grafi glede na lastnosti:</font>
	1. neusmerjeni in usmerjeni
	2. neuteženi in uteženi
	3. enostavni - taki, ki ne vsebujejo zank, ki povezujejo vozlišče s samim seboj in vzporednih povezav med istimi pari vozlišč.
	4. gosti - katerih število vozlišč je velikostnega reda, ki je blizu maksimalnemu številu možnih povezav in redki - katerih število povezav je linearno odvisno od števila vozlišč
2. <font color="#4bacc6">drugi termini v povezavi z grafi:</font>
	1. stopnja vozlišča, predstavlja število povezav, ki vključujejo to vozlišče, v usmerjenih grafih ločimo vzhodni in izhodno stopnjo
	2. dve dvozlišči sta sosednji, če ju povezuje katera izmed povezav v grafu
3. <font color="#4bacc6">ločimo:</font>
	1. drevesa, ki so v resnici aciklični povezani neusmerjeni grafi
	2. polne grafe, ki vsebujejo vse možne povezave
	3. regularne grafe, v katerih imajo vsa vozlišča enako stopnjo
	4. dvodelne grafe, ki so sestavljeni iz dveh skupin vozlišč, povezave pa potekajo samo med obema skupinama
4. <font color="#4bacc6">premiki med sosednjimi vozlišči:</font>
	1. sprehod - poljubno zaporedje vozlišč, rečemo da če obstaja sprehod med dvema vozliščema, da sta povezani
	2. obhod - sprehod, ki se začne in konča v istem vozlišču
	4. steza - sprehod brez ponovljenih povezav
	5. pot - sprehod brez ponovljeniv vozlišč
	6. cikel - obhod brez ponovljenih vmesnih vozlišč (z izjemo začetnega in končnega, ki sta enaka)
5. <font color="#4bacc6">implementacija:</font> imamo tri pogoste implementacije grafov, glede na funkcionalnost, ki jo potrebujemo:
	1. edge list - najbolj enostavna predstavitev, kjer vse povezave shranimo v seznam
	2. adjacency list - za vsako vozlišče hrani seznam njegovih sosedov, uporabno kadar se premikamo po grafih od enega vozlišča k drugemu
	3. adjacency matrix - namenjena učinkovitemu preverjanju sosednosti dveh vozlišč, sestavimo matriko $M$, kjer na mestu $M_{x,y}$ hranimo informacijo o prisotnosti ali teži povezave med vozliščema $x$ in $y$.
6. <font color="#4bacc6">preiskovanje grafov:</font>
	1. v širino (breadth-first search), najprej obiščemo začetno vozlišče, nato njegove sosede, njihove sosede itd.
	2. v globino (depth-first search), najprej obišče zaćetno vozlišče, nato izvede preiskovanje v globino na prvem otroku, ko se to zaključi in če drugi otrok še ni bil obiskan, izvede preiskovanje v globino še iz drugega otroka itd.
7. <font color="#4bacc6">topološko urejanje:</font> topološki vrstni red vozlišč v usmerjenem grafu je tak vrstni red, da vse povezave v frafu kažejo od zgodnejšega proti kasnejšemu vozlišču v topološkem vrstnem redu.
8. <font color="#4bacc6">kritična pot:</font> najdaljša pot v uteženem usmerjenem acikličnem grafu


### Najkrajše poti

1. <font color="#4bacc6">neuteženi grafi:</font> tukaj nimamo problema, saj že poznamo metodo iskanja v širino (BFS), ki potrebuje le malenkostni dodatek.
2. <font color="#4bacc6">dijkstrov algoritem:</font> poglej visualizacijo, prostorska zahtevnost algoritma je $O(\log n)$, časovna pa je odvisna od iskanja najmanjše potencialne razdalje $O(n^2)$ in posodabljanja sosedov $O(e)$, ker je $e = O(n^2)$, je časovna zahtevnost  implementacije algoritma (če uporabimo prioritetno vrsto, drugače pa je $O(n^2)$) $O(e\log n)$. A to se uporabi, samo če je graf dovolj redek, če je graf gost in vsebuje skoraj vse možne povezave ($e = n^2$), je časovna zahtevnost še slabša.
3. <font color="#4bacc6">negativne uteži:</font> imajo smisel samo na usmerjenih grafih.


### Vpeta drevesa

Začnemo najprej z <font color="#4bacc6">disjunktnimi množicami</font> (disjoint-set), ki hranijo množico disjunktnih množic, kjer je časovna zahtevnost, potem ko uporabimo združevanje po velikosti in stiskanje poti, operacije $O(m \times \log n)$.

<font color="#4bacc6">Minimalno vpeto drevo:</font> (vpeto drevo grafa, je takšno da vključuje vsa vozlišča grafa in podmnožico njegovih povezav, ta je minimalen, ki ima najmanjšo vsoto uteži povezav). Prerez grafa je razbitje vozlišč grafa na dve disjunktni množici, povezavam pa prerezne povezave. Prerezna lastnost pravi, da je najmanjša prerezna povezava vedno del nekega minimalnega vpetega drevesa.

<font color="#4bacc6">Primov algoritem:</font> je požrešen algoritem, ki gradi vpeto drevo s širjenjem od izhodiščnega vozlišča navzven proti sosedom. Za izhodišče uporabimo poljubno vozlišče, saj morajo biti vsa del minimalnega vpetega drevesa, ko si ogledamo prerez grafa A (ki vključuje vsa vozlišča do sedaj zgrajenega drevesa) in B (ki vsebuje preostala), iz prerezne lastnosti sledi, da je najmanjša povezava med A in B del nekega minimalnega vpetega drevesa, zato jo lahko dodamo v drevo in ponovimo z razmislekom.

V tem primeru bi bila časovna zahtevnosti $O(nm)$, kjer je $m$ število povezav in $n$ število vozlišč.

Jo pa izboljšamo tako, da za vsako še nedodano vozlišče vzdržujemo njegovo razdaljo do že zgrajenega drevesa, te so vse na začetku enake $\infty$ (razen za začetno vozlišče), ki ima razdaljo $0$. Na vsakem koraku poiščemo vozlišče z najmanjšo razdaljo, ga dodamo v drevo in posodobimo radalje do drevesa vseh njegovih sosedov. To lahko hranimo v prioritetni vrsti, tako kot pri Dijkstri in je na koncu časovna zahtevnost $O(m\log n)$. - tega uporabiš, če je graf gost.

<font color="#4bacc6">Kruskalov algoitem:</font> je prav tako požrešni algoritem, ki začne z množico vozlišč in dodaja povezave od manjših proti večjim povezavam glede na uteži. Pravzaprav postopoma pretvarja gozd z več manjšimi drevesi v eno veliko drevo. Doda vsako povezavo $(x,y)$, če njena vključitev ne ustvari cikla. - tega uporabiš, če je graf redek. Zahtevnost: $O(m \log n)$.

<font color="#4bacc6">Steinerjevo drevo v grafu:</font> Problem minimalnega vpetega drevesa posplošimo tako, da zahtevamo, da je med seboj povezana samo neka izbrama podmnožica vozlišč (ki jim rečemo terminali $t$), če velja: 
1. $t = n$ imamo opravka s problemom minimalnega vpetega drevesa
2. $t = 2$ imamo vpravka s problemom najkrajše poti


### Deli in vladaj

Gre za idejo, da problem razdelimo na več manjših podproblemov, te pa rešimo rekurzivno po enakem postopku, nato pa združimo dobljene rezultate manjših problemov v rešitve večjega problema.

Krovni izrek: nam poda rešitve rekurzivne enačbe $T(n) = aT(n/b) + f(n)$ pri konstantah $a \geq 1, b > 1$ za tri skupin enačb glede na razmerje med $c = \log_b a$ in funkcijo $f(n)$, kjer velikostni red funkcije $f(n)$ primerjamo z $n^c$ in ločimo tri primere:
1. $f(n) = O(n^{c-\varepsilon}) \Rightarrow T(n) = \Theta(n^c)$, torej je čas za združevanje manjši od $n^c$ in je velikost rekurzivnega drevesa $n^c$ prevladujoča vrednost.
2. $f(n) = O(n^{c}) \Rightarrow T(n) = \Theta(n^c \log n)$, funkciji sta "enaki",
3. $f(n) = O(n^{c+\varepsilon}) \Rightarrow T(n) = \Theta(f(n))$, če je čas za združevanje večji, potem je to prevladujoča vrednost.

Pogosto so odločitveni problemi lažji od optimizacijskih, npr. ali je neka konkretna meja $v$ sprejemljiva, ...? 


### Dinamično programirane

Je algoritmični pristop, ki je podobno deli in vladaj, le da velja:
- posamezen podproblem lahko rešujemo neodvisno od drugih podproblemob
- optimalna rešitev problema vsebuje optimalne rešitve podproblemov
- podproblemi se ponavljajo in prekrivajo (npr. fibonaccijevo zaporedje)

Pogosto uporabimo memoizacijo, torej funkcija za vsak možen argument funkcije izvledna največ enkrat.



### Računska geometrija

To je področje algoritmov in podatkovnih struktur, ki se ukvarja z učinkovitim reševanjem geometrijskih problemov.



