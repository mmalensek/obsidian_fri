### [[irz]], 9.teden, 27-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #irz-flashcards 

---

### Vsebina:

Kdaj je SA determinističen? Če za vsak $\delta$, ta obstaja in je manjši ali enak 1 (torej mora obstajati natanko en prehod, ki preprečuje tihe poteze).
Tega označimo z $DSA$ - <font color="#00b050">deterministični skladovni avtomat</font>.

Sprejemanje s praznim skladom ali končnim stanjem <font color="#4bacc6">je ekvivalentno</font>, če je jezik sprejet s praznim skladom potem obstaja skladovni avtomat, ki sprejme ta jezik tudi s končnim stanjem in obratno.

Razred vseh jezikov, sprejetih s $SA$, je enak razredu vseh $KNJ$.

Le, da tu velja, da je $DSA$ po sposobnosti sprejemanja <font color="#4bacc6">šibkejši</font> od $SA$.

### Lastnosti kontekstno-neodvisnih jezikov

Lema o napihovanju za $KNJ$ pravi, da vsaka zadosti dolga beseda iz $KNJ$ jezika $L$ vsebuje dve kratki podbesedi, ki sta si blizu in ki ju lahko končno mnogokrat ponovimo (obe enako mnogokrat)m a bo nova beseda še vedno v jeziku $L$.

S tem lahko dokažemo, da obstaja formalni jezik, ki ni $KNJ$.

Razred kontekstno-neodvisnih jezikov je <font color="#4bacc6">zaprt</font> za operacije:
- unija,
- stik,
- Kleeneovo zaprtje,
- substitucija (in homomorfizem) in
- inverzni homomorfizem

<font color="#8064a2">Ni zaprt</font> za operaciji:
- presek,
- komplement.

Toda KNJ <font color="#4bacc6">je zaprt</font> za presek z regularnim jezikom.

<font color="#4bacc6">Obstajata</font> odločitvena algoritma za ugotavljanje, ali je KNJ - prazen in končen.



---
