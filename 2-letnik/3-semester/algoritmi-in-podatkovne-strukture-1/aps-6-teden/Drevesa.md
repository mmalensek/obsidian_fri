[[Abstraktni podatkovni tipi]], [[predavanje-aps-6-teden]]; #aps1-flashcards 

Vrste dreves:

glede strukture:
- dvojiško / k-tiško - [[dvojiško iskalno drevo]]
- polno (full)
- poravnano (complete)
- popolno (perfect)

- urejena
- neurejena
- iskalno

- črkovna/znakovna (trie - https://en.wikipedia.org/wiki/Trie)

Kako predstaviti?


![[Drevesa 2024-11-08 12.36.14.excalidraw]]

Uravnoteženo drevo je takrat ko je višina enaka $O(\log n)$.
Nasprotje je izrojeno drevo.

Obhodi:

![[Drevesa 2024-11-08 12.54.28.excalidraw|200]]

- vmesni (in-order) - $A, B, C, D, E, F, G, H, I$
- premi (pre-order) - $F, B, A, D, C, E, G, I, H$
- obratni (post-order) - $A, C, E, D, B, H, I, G, F$
- nivojski (level) - $F, B, G, A, D, I, C, E, H$ 