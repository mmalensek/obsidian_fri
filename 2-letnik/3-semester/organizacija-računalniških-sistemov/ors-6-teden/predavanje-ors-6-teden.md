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

Če pride prekinitvena zahtev

---
