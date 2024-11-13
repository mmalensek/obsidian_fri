[[predavanje-vs-6-teden]]; #vs-flashcards 

Naprava za delo s časom, ki ga vsebujejo vsi računalniški sistemi. V našem STM-u je okoli 15 različnih časovnikov, ki so zgrajeni iz enakih jeder - <font color="#92cddc">časovna baza</font>.

Poznamo osnovne, splošno-namenske in napredne časovnike.

![[Časovniki 2024-11-06 10.27.39.excalidraw]]

- $TIMx\_PSC$ je delilnik ure, ki urin signal na vodilu $APB1$ deli z vrednostjo v $TIMx\_PSC$: $f_{TIM_CLK} = \frac{f_{APB1_CLK}}{TIMx\_PSC + 1}$ 
- $TIMx\_CNT$ je prostotekoči števec, ki teče se frekvenco ure $TIM\_CLK$.
- $TIMx\_ARR$ (Auto Reload Register) je register s katerim se primerja vrednost prostotekočega števca, ko $TIM\_CNT$ doseže vrednost zapisano v $TIM\_ARR$ registru, se proži <font color="#92cddc">dogodek</font> $UEV$ (update event).
- ta dogodek pomeni, da se postavi zastavica in lahko se proži prekinitev, če jo omogočimo in $TIM\_CNT$ se resetira.

- npr. da v $TIM\_ARR$ vpišemo $99$, potem bo $TIM\_CNT$ štel od $0-99$, tako bo njegova perioda štetja $100$, to pomeni da $TIM\_ARR$ določa periodo štetja.

- lahko merimo absolutni čas, tako da beremo $TIM\_CNT$, pri čemer je natančnost določena s $f_{TIM\_CLK}$ 
- lahko pa periodično prožimo dogodke na vsake $ARR$ časa, kjer je: $$t_{periode} = (TIDx\_ARR + 1) \cdot \frac{1}{f_{TIM\_CLK}}$$
Časovniki so, kot vse ostale periferne naprave, pomnilniško preslikani, torej so CPE vidni kot 32-bitne pomnilniške besede, čeprav se uporablja samo spodnjih 16.

Poleg omenjenih treh registrov imajo še množico drugih kontrolnih in statusnih registrov, ki so prav tako pomnilniško preslikani, npr:
- $TIMx\_CR1$ (control register 1, jih je lahko več, odvisno od zahtevnosti časovnika), v katerem nastavljamo osnovne lastnosti posameznega časovnika
- $TIMx\_SR$ (status register, ki je samo en), iz njega razberemo trenutni status časovnika (npr. ali se je prožil UEV - zastavica)
- $TIMx\_DIER$ (interrupt enable register), omogočamo ali onemogočamo s posameznimi biti, prožanje različnih prekinitev iz časovnika

Za primer vzamemo $TIM3$:

1) $TIM3\_CRA$

![[Časovniki 2024-11-06 11.28.11.excalidraw]]

Imamo dva načina spreminjanja $ARR$-ja:
1) $CPE$ piše neposredno v $TIMx\_ARR$, kar pomeni, da se nova perioda štetja upošteva takoj
2) $CPE$ piše v $SHADOW \ TIMx\_ARR$ in se ob $UEV$ prepiše v $TIMx\_ARR$. 


-  $TIM3\_DIER$ - kjer nam zadnji bit pove ali ob $UEV$ proži prekinitev (gleda se samo zadnji bit)
-  $TIM3\_SR$ - zadnji bit predstavlja zastavico, ki se postavi ob $UEV$

---

Postopek inicializacije časovnika npr. $TIM3$:
0) vklopi uro za časovnik $TIM3$
1) v $ARR$ in $PSC$ vpišemo željene vrednosti
2) nastavim bite v $CR1$, omogočim časovnik
3) po potrebi omogočim tudi prekinitve