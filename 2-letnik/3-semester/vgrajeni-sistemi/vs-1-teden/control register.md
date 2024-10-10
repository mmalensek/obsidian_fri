[[Programski model ARM Cortex-M]];

Pomembna sta bita 1 -> <font color="#92cddc">SPSEL</font> in bit 0 -> <font color="#92cddc">nPRIV</font>.

Hočemo onemogočiti dostop do skladovnega kazalca operacijskega sistema. Procesor tako lahko ve kateri skladovni kazalec uporablja, ali od operacijskega sistema ali od kode programerja

<font color="#92cddc">nPRIV</font>;; Določa priviligirano ali ne-priviligirano stanje. To omogoča <font color="#92cddc">nPriv</font> in ne sme biti dosegljiv programerju.

<font color="#92cddc">SPSEL</font>;; Pove kateri skladovni kazalec se uporablja.

Kako sploh obstajata <font color="#92cddc">dva skladovna kazalca</font>?;; Tako, da uporabimo en multiplekser, ki deli na ===Main stack pointer=== in ===Program stack pointer===. 

Hočemo pa ločiti sklada že zaradi stabilnosti operacijskega sistema, tako da ga ne more "slab" program skreširat.

Določa kontekst programa, zato skrbi procesor.

---

#vs-flashcards 

---
