[[osnovni-matematični-pojmi-irz]];

[[irz_prosojnice.pdf#page=29&selection=6,0,47,1|irz_prosojnice, page 29]]

> Neusmerjen graph G = (V, E) sestavljata množica V točk (oz. vozlišč) in množica E parov točk, imenovanih povezave.

![[Pasted image 20241007133454.png]]

> Pot v grafu je zaporedje točk $vl, v2, …, vk, k ≥1$, kjer je $\{v_i,v_{i+1}\}$ za vsak $i, 1≤ i < k$ povezava v grafu. Dolžina poti je $k -1$, če je $v_l = v_K$, je pot cikel.

npr: Zaporedje 1, 3, 4 je pot dolžine 2, zaporedje 5 pa je trivialna pot dolžine 0.

> Usmerjen graf $G = (V, A)$ sestavljata množica točk $V$ in množica $A$ urejenih parov točk, imenovanih usmerjene povezave. Usmerjeno povezavo $(u,v)$ označimo tudi z $u ➝ v$.

![[Pasted image 20241007133825.png]]

> Pot v usmerjenem grafu je zaporedje točk vl, v2, …, vk, k ≥1, kjer je vi ➝ vi+1 za vsak i, 1≤i<k, usmerjena povezava grafa. Rečemo, da gre ta pot iz v1 v uk. Če je u ➝ v, je u neposredni prednik točke v (oz. v neposredni naslednik točke u).

npr: $1 \rightarrow 2 \rightarrow 3 \rightarrow 4$ je pot iz $1$ v $4$. Tu je $3$ predhodnik $4$.

> Drevo je usmerjen graf z (dodatnimi) lastnostmi:
> 	1) Obstaja natanko ena točka, imenovana koren, ki nima prednikov in iz katerega obstaja pot do vsake točke. 
> 	2) Vsaka točka, ki ni koren, ima natanko enega prednika. 
> 	3) Če ima točka naslednike, so ti urejeni (običajno od leve proti desni).

> Neposrednemu nasledniku točke rečemo tudi sin, neposrednemu predniku pa oče. Če obstaja pot iz $v_i$ v $v_j$, rečemo, da je $v_i$ prednik točke $v_j$ (oz. $v_j$ potomec točke $v_i$ ). Če točka nima sinov, ji rečemo list, sicer pa notranja točka drevesa.

![[Pasted image 20241007134245.png]]

---

#irz-flashcards 

Kdaj je točka grafa list?;; Ko nima sinov.
<!--SR:!2024-10-16,4,270-->
Kaj je koren grafa?;; To je natanko ena točka grafa, ki nima prednikov in iz katere obstaja pot do vsake točke grafa.
<!--SR:!2024-10-15,3,250-->

---
