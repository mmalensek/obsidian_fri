### [[ors]], 4.teden, 20-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano #ors-flashcards

---

### Vsebina:

Načini za delo z naslovi v C-ju:
1) Grd način: 
```C
uint32_t *p = ((uint32_t *) 0x10012008);
*p = *p | (1 << 19);
```
2) Malo lepše z uporabo konstant: 
```C
#define GPIO_OUTPUT_EN ((uint32_t *) 0x10012008)
uint32_t *p = GPIO_OUTPUT_EN;
*p = *p | (1 << 19);
```
3) Ali pa še lepše: 
```C
#define GPIO_OUTPUT_EN ((uint32_t *) 0x10012008)
*GPIO_OUTPUT_EN = *GPIO_OUTPUT_EN | (1 << 19);
```

Rezervirana beseda <font color="#92cddc">volatile</font>?;; Ta prevajalniku pove, da naj ne optimizira te spremenljivke, saj se lahko med izvajanjem programa <font color="#92cddc">spreminja</font>, ker je npr. register pomnilniško preslikane vzhodno-izhodne naprave, globalne spremenljivke, do katerih dostopa več niti.
<!--SR:!2024-10-24,3,250-->

```C
volatile uint32_t *p = (volatile uint32_t *) REG_A;
```

[[GPIO]] + STM vaja 4.

---
