### [[ors]], 6.teden, 07-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #ors-flashcards 

---

### Vsebina:

[[izjeme pri ARM Cortex]];

### Kako CPE ve, kdo zahteva prekinitev?

![[predavanje-ors-6-teden 2024-11-07 11.30.42.excalidraw]]

CPE preko DATA BUS-a dobi prekinitveni vektor od prekinitvenega krmilnika. Najbolj pogosta rešitev: če se proži $IRQ_i \rightarrow$ na vodilo se zapiše i + offset

### Prekinitveni krmilnik NVIC v Cortex ARM procesorjih

$NVIC$ - nested vectored interrupt controller

![[predavanje-ors-6-teden 2024-11-07 11.40.05.excalidraw]]

Če pride prekinitvena zahteva na:
- $IRQ_0 \rightarrow 0x0000\ 0040$   
- $IRQ_1 \rightarrow 0x0000\ 0044$   
- $IRQ_2 \rightarrow 0x0000\ 0048$
- ...
- $IRQ_{40} \rightarrow 0x0000\ 00c4$
- $IRQ_{41} \rightarrow 0x0000\ 00c8$
- ...

Če pride na $i$, torej pride na $i + 40$, pri tem danem offset-u, ker nižje od $40$ pripadajo pastem v tem primeru.

Vsaka $V/I$ naprava v sistemu je vezana na en $IRQ_i$ vhod. Običajno so iste naprave npr. nek serijski komunikacijski vmesnik, se da vedno na isti $IRQ$ vhod pri vseh procesorjih Cortex, ne glede na različico.

### Poleg V/I enot, ki so vgrajene v čip, bi radi na IRQ vhode vezali tudi GPIO pine

![[predavanje-ors-6-teden 2024-11-07 12.24.56.excalidraw]]

Ampak: GPIO pinov je npr. v našem sistemu $11 \cdot 16 = 176$, kar je preveč za takšen primer kot je na sliki.

Želimo si, da bi lahko programsko izbral neko manjšo podmnožico GPIO pinov, ki bodo vezani na prekinitve krmilnik (NVIC).

![[predavanje-ors-6-teden 2024-11-07 12.31.07.excalidraw]]

$MUX_i$ izbira, kateri izmed GPIO pinov z indeksom $i$ gre na $EXTI_i$.

---
