ali direct memory access.

[[predavanje-ors-8-teden]], [[predavanje-vs-9-teden]]; #ors-flashcards #vs-flashcards 

Prenaša podatke $MEM$ to $MEM$ (RAM - delovni spomin) ali pa tudi $MEM$ to $I/O$ brez vpletanja $CPE$.

$DMA$ krmilnik mora znati:
- naslavljati,
- računati z naslovi,
- imeti dostop do pomnilnika preko $ADDR$ in $DATA$ vodila

![[DMA krmilniki 2024-11-21 12.19.39.excalidraw|500]]

- vsaka naprava, ki je povezana z $DMA$ krmilnikom ima svojo $DREQ$ žico - $DMA$ kanal.

### ORS del:
Ko pride nov podatek na $DATAR$, je potrebno vsebino registra prebrati in shraniti. Namesto da CPE, vsakič prebere ukaz iz RAM-a, prebere podatek, ... uporabimo samo $DMA$ krmilnik, ki ima load in store operacijo, hard code-ano v samemu sebi. 