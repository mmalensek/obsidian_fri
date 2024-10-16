[[predavanje-vs-1-teden]]; #vs-flashcards

```cardlink
url: https://en.wikipedia.org/wiki/ARM_Cortex-M
title: "ARM Cortex-M - Wikipedia"
host: en.wikipedia.org
favicon: https://en.wikipedia.org/static/favicon/wikipedia.ico
image: https://upload.wikimedia.org/wikipedia/commons/thumb/6/67/STM32F100C4T6B-HD.jpg/1200px-STM32F100C4T6B-HD.jpg
```

![[Registri-ARM-Cortex-M.png]]

Se razlikuje od RISC procesorja s tem, da <font color="#92cddc">ima ukaze za sklad</font> (push in pop).

<font color="#92cddc">Programski model</font> pomeni, kako kot programer vidiš procesor.

ARM ima;; <font color="#92cddc">16</font> - 32 bitnih splošno namenskih registrov, kjer je $R15$ <font color="#92cddc">programski števec</font>, $R14$ je <font color="#92cddc">link-register</font>, za vračanje pri skokih, $R13$ je <font color="#92cddc">stack-pointer</font>. To je samo dogovor (ABI - application binary interface), ARM omogoča, da lahko uporabljaš tudi druge, a je dobro da se uporablja dogovor ABI, zaradi univerzalnosti, in premostljivosti na druge naprave.
<!--SR:!2024-10-16,2,230-->

$R13$ je nekakšen "virtualni" register, poglej si [[control register]].

Prvi štirje registri se uporabljajo;; <font color="#92cddc">za prenašanje argumentov</font>, če jih je več kot štiri, se to dela preko skladu.
<!--SR:!2024-10-17,3,250-->

Od $R4$ do $R11$ so;; "pure general purpose" registers.
<!--SR:!2024-10-16,4,270-->

Za delovanje samega procesorja mora ta imeti tudi nekaj <font color="#92cddc">kontrolnih registrov</font>:
- [[program status register]],
- [[base priority mask register]],
- [[control register]],
- interrupt mask register,
- fault mask register.

Za vse zadnje štiri registre velja, da jih pri prekinjanju programov ne shranjujemo.

Te <font color="#92cddc">ne morejo</font> biti operandi za AL, Load/Store in branch ukaze. Ampak se za <font color="#92cddc">dostop do njih</font> uporabljajo posebni ukazi (vsi so 32 bitni).

---
Katere registre ima procesor poleg prvih šestnajst (general-purpose)?;; Ima tudi 5 drugih posebnih kontrolnih registrov, ki določajo kontekst programa.
<!--SR:!2024-10-23,8,250-->