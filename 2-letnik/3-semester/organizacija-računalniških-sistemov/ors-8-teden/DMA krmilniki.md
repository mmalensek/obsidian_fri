ali direct memory access.

[[predavanje-ors-8-teden]]; #ors-flashcards 

Prenaša podatke $MEM$ to $MEM$ (RAM - delovni spomin) ali pa tudi $MEM$ to $I/O$ brez vpletanja $CPE$.

$DMA$ krmilnik mora znati:
- naslavljati,
- računati z naslovi,
- imeti dostop do pomnilnika preko $ADDR$ in $DATA$ vodila

![[DMA krmilniki 2024-11-21 12.19.39.excalidraw]]

- vsaka naprava, ki je povezana z $DMA$ krmilnikom ima svojo $DREQ$ žico - $DMA$ kanal.