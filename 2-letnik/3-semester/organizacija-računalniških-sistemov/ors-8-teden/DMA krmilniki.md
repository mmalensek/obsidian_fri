ali direct memory access.

[[predavanje-ors-8-teden]], [[predavanje-vs-9-teden]]; #ors-flashcards #vs-flashcards 

Prenaša podatke $MEM$ to $MEM$ (RAM - delovni spomin) ali pa tudi $MEM$ to $I/O$ brez vpletanja $CPE$ in jih ne potrebujemo več, ter lahko samo enega vežemo na več kanalov ($DREQ$ - $DMA$ request), kjer mu sami nastavimo katera naprava je na katerem kanalu.

$DMA$ krmilnik <font color="#8064a2">mora znati:</font>
- <font color="#4bacc6">naslavljati</font> 
	- katera beseda je izvorna in ponorna,
	- kar ve programer, to pomeni, da mora imeti vsak $DMA$ krmilnik imeti dva naslovna registra, v katera zapišemo ta dva naslova.
- <font color="#4bacc6">računati z naslovi,</font>
	- oziroma popravljati naslove, ali jih inkrementirati, ali ostanejo enaki, ...
	- zato ima $DMA$ še en kontrolni register 
- <font color="#4bacc6">imeti dostop do pomnilnika preko</font> $ADDR$ <font color="#4bacc6">in</font> $DATA$ <font color="#4bacc6">vodila</font>
- <font color="#4bacc6">vedeti koliko podatkov mora prenesti</font>
	- za kar ima še en register: $NDR$ - number of data (to transfer)

![[DMA krmilniki 2024-11-21 12.19.39.excalidraw|500]]

- vsaka naprava, ki je povezana z $DMA$ krmilnikom ima svojo $DREQ$ žico - $DMA$ kanal.

### VS del:
Ko pride nov podatek na $DATAR$, je potrebno vsebino registra prebrati in shraniti. Namesto da CPE, vsakič prebere ukaz iz RAM-a, prebere podatek, ... uporabimo samo $DMA$ krmilnik, ki ima load in store operacijo, hard code-ano v samemu sebi. 

CPE ne bo ves čas čakala na DMA krmilnik, ker bo ta uporabljala podatkovno vodilo, zato ker CPE v $98\%$ uporablja predpomnilnik.

Zato ker imamo več kanalov $DREQ$, se jih lahko proži več naenkrat, torej moramo imeti možnost <font color="#8064a2">nastavljanja prioritet</font>.

### DMA krmilnika v STM32H7:
Imamo $DMA1$ in $DMA2$, ki sta popolnoma enaka, le da drugi zna tudi prenašati $MEM$ to $MEM$. Oba tudi omogočata do 8 hkratnih aktivnih prenosov (ne v isti urini periodi seveda, ampak imamo 8 množic inicializiranih prenosov), katerim se reče <font color="#00b050">stream</font>.

![[DMA krmilniki 2024-11-27 11.28.51.excalidraw]]

Kako povezati kanale (naprave) na stream-e?
- programer lahko nastavi, kateri kanal gre na kateri stream.
- imamo 8 - 128/1 MUX-ov, za vsak stream en MUX