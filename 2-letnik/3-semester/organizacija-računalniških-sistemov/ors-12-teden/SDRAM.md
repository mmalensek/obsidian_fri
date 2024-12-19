[[predavanje-ors-12-teden]], [[DRAM]]; #ors-flashcards 

---
### Izboljšave  DRAM-a
1. vpeljemo CLK v DRAM,
2. vpeljemo eksplozijske prenose - z enim naslovom stolpca prenesemo več zaporednih stolpcev,
3. več bank - zato, da ko iz ene berem iz druge lahko že odpiram novo vrstico in nekako prikrijem zamike in skrajšam čas dostopa.

Temu rečemo sinhroni dinamični RAM ([[SDRAM]]).

---

Zato vpeljemo novo <font color="#7030a0">kontrolno logiko</font>, ki sprejema <font color="#7030a0">navodila</font> za delovanje SDRAM. Navodila kot so npr. <font color="#7030a0">ACTIVE</font> - odpri vrstico, <font color="#7030a0">READ</font>, <font color="#7030a0">WRITE</font>, <font color="#7030a0">PRECHARGE</font> - zapri vrstico, <font color="#7030a0">AUTO REFRESH</font> - ker nimamo perfektnega izolatorja (ta čas je danes 64 ms), rabimo obnavljati stanje, ...

1. MC (- memory controller) izstavi ukaz za odpiranje vrstice v banki.
2. MC počaka predpisano število urinih period (3)
3. po preteku n (3) urinih period MC izstavi ukaz za branje iz odprte vrstice
4. MC počaka predpisan čas (CL = 2) in začne ob vsaki pozitivni fronti brati eno besedo (v našem primeru 4 zaporedne besede)

Tako efektivno hitrost branja lahko praktično zmanjšamo za faktor $n$ prebranih besed naenkrat (če vrstica ni odprta).

Kaj pa če je vrstica odprta? ...

<font color="#7030a0">DDR SDRAM</font> - Double Data Rate SDRAM - prenesemo dve besedi znotraj ene urine periode enkrat na pozitivno drugič pa na negativno urino fronto.



---