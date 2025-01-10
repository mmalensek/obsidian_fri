### [[ors]], 13. teden, 09-01-2025
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #ors-flashcards 

---

### Vsebina:

### Navidezno naslavljanje
Videli smo, da programi (CPE) ne uporabljajo naslovov pomnilniških besed v <font color="#7030a0">fizičnem</font> pomnilniku, ampak nasloe pomnilniških besed v <font color="#7030a0">navideznem</font> pomnilniku. - ta ne obstaja, samo program misli da obstaja

Pri navideznem pomnilniku je vsak program prepričan, da je edini izvajajoči se program v sistemu in da je <font color="#4bacc6">ves</font> (celotni naslovni prostor) pomnilnik le njegov. - pri 64-bitnih naslovih je to od 0x0000000000000000 do 0xFFFFFFFFFFFFFFFF.

Programi nič ne vedo o tem, koliko je dejansko fizičnega pomnilnika v sistemu, niti kje se ta nahaja. Programi so zato pozicijsko neodvisni.

Programi se lahko izvajajo ne glede na količino fizičnega pomnilnika.

<font color="#4bacc6">Navidezne naslove moramo preslikovati v fizične.</font>

S tem upravlja - <font color="#8064a2">Memory Management Unit</font> - ki mora biti blizu ozr. del procesorja, zato da lahko dela z enako hitrostjo kot CPE.

<font color="#4bacc6">Programi na Linuxu</font>

Polovica naslovov je rezervirana za externe linkane kode, npr. ko uporabiš -lm, da se doda matematična knjižnica, 

<font color="#4bacc6">Kako preslikujemo navidezne v fizične naslove?</font>
1. preslikavo dela MMU: dobi navidezni naslov od CPE in 
2. potrebuje preslikovalno tabelo: za njo skrbi OS
3. ta bo v RAM-u, začetni naslov preslikovalne tabele se za vsak program na arhitekturah Intel hrani v registru $cr3$
4. kako velika naj bo ta tabela? Ne more hraniti vseh $2^{64}$ naslovov. Bolje je da ena preslikava za en blok naslovov, ki imajo skupnih npr. zgornjih n bitov (takemu bloku pravimo stran - page)

Zgled: Intel Architecture - 32

Preslikovanje (odstranjevanje, paging)


