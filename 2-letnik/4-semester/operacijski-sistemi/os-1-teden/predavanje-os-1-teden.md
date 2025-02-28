### Procesorska arhitektura
- Intel 80x86, AMD
	- CISC
- ARM
	- RISC
- RISC-V
	- RISC

Torej ima RISC instruction set več prihodnosti, ...

### Terminal
Naprava s tipkovnico in zaslonom, ki je še "neumnejša" od računalnika, saj le znake prikazuje na zaslon in jih posreduje do "mainframe"-a preko neke povezave.

- standardni vhod - deskriptor 0
- standardni izhod - deskriptor 1
- standardni izhod za napake - deskriptor 2

Danes se uporablja emulator terminala, ki je program, ki oponaša tekstovni terminal in se izvaja v oknu, ki je v grafičnem okolju.

Najdemo tudi v imeniku `/dev/pts/0` kjer "pts" pomeni pseudoterminal.
### Lupina
Program, ki uporabniku nudi osnovni uporabniški vmesnik za uporabo in delo z operacijskim sistemom.

### Upravljanje oken (pri grafičnih lupinah)
- skladovni - navadni windows
- tiling - npr. PopOS
- hibridni - je rekel, da je nepotrebno definiran
- kompozitni - npr. starejši macOS

### Ukazna lupina
Je tekstovna in omogoča napredno uporabo, kot je programiranje, preusmerjanje vhoda in zajem izhoda ukazov, ...

Postopek dela: REPL - read, evaluate, print, loop (loopanje zadnjih treh faz)

Delimo na vgrajene in zunanje ukaze, kjer so zunanji shranjeni v izvršljivih datotekah nekje v datotečnem sistemu, katere se poišče na lokaciji $PATH, imajo pa vgrajeni ukazi prednost pred zunanjimi (če obstajata dva enaka).

Da zaženeš program npr. $tetris$, moraš v linux dodati še ./$tetris$ in v $PATH dodati še "." in se lahko zažene, a to ni priporočljivo iz varnostnih razlogov.



