[[predavanje-opb-7-teden]]; #opb-flashcards 

SUPB je sestavljen iz:
- stroja za evaluacijo poizvedb,
- enote za nadzor sočasnosti,
- upravljalca obnove podatkov,

ti so medseboj povezani z:
- datotekami in metodami dostopa,
- upravljalcem medpomnilnika in
- upravljalcem prostora na disku.

Kjer je upravljalec prostora na disku <font color="#92cddc">povezan</font> z podatkovno bazo.

Komponente SUPB za delo s podatki:
- upravljalec prostora na disku,
- upravljalec z datotekami - posreduje zahteve za zaseganje/sproščanje prostora v straneh (enota v SUPB)
- upravljalec medpomnilnika

Hierarhija pomnilnika:
- CPU
- Medpomnilnik - <font color="#92cddc">primarni</font>
- Glavni pomnilnik - <font color="#92cddc">primarni</font>
- (Magnetni) disk - <font color="#92cddc">sekundarni</font>
- Magnetni trak - <font color="#92cddc">terciarni</font>

Kaj so razlogi za obstoj sekundarnih in terciarnih pomnilnikov?
- obstojnost podatkov,
- cena na enoto
- (včasih tudi) omejenost naslovnega prostora na 32-bitnih računalnikih

Magnetni disk:
- povprečni dostopni čas nam predstavlja:
	1) iskalni čas, 
	2) rotacijska zakasnitev in 
	3) čas prenosa
- organizacija podatkov na disku vpliva na povprečni dostopni čas (zato danes skrbi OS),
- dostopni čas RAM : disk $\approx$ 1 : 1000.

HDD in SSD diski:
- veliko hitrejši, a dražji, ...

Polje diskov:
- disk predstavlja potencialno ozko grlo za učinkovitost SUPB, ... vpliva na zanesljivost delovanja sistema.
- zato povežemo več diskov, z namenom:
	- povečanja učinkovitosti in/ali - porazdelitev podatkov
	- izboljšanja zanesljivosti. - podvajanje podatkov (redundanca)

<font color="#6425d0">RAID</font> (Redundant Arrays of Independent Disks):
- implementacija diskovnih polj, ki vključujejo porazdelitev in podvajanje podatkov
- več vrst

- uporabniku se kaže kot velik disk,
- podatki se razdelijo na enake enote (striping units), ki se zapišejo na več diskov, vsaka enota na en disk
- v praksi je ena enota en blok.

RAID z <font color="#6425d0">redundanco podatkov</font>
- ker je MTTF (mean-time-to-failure) enega diska okoli 6 let, pomeni da je pri 100-ih diskih MTTF enak 21 dni,
- za večjo zanesljivost je potrebna redundanca
- npr. če polju 100-ih diskov dodamo 10 diskov z redundantnimi podatki se MTTF poveča na 250 let.

- večinoma redundanten disk na podlagi paritetni bit, kjer če en disk odpove lahko na podlagi paritet se novo vstavljeni disk postavi.

- RAID 0 - porazdeljen in brez redundancem, MTTF pada linearno s številom diskov v polju,
- RAID 1 - zrcaljenje - kar se piše na en disk se kopira na drugega (izraba prostora samo 50%),
- RAID 4 in 5, na 4 so vsi paritetni biti na enem disku, v 5 pa so porazdeljeni,
- ... RAID 5 in 6 sta največkrat uporabljena v praksi (6 je neobčutljiv na odpoved dveh diskov).