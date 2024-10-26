[[Abstraktni podatkovni tipi]]; #aps1-flashcards 

A)
![[Preskočni seznam (Skip list) 2024-10-25 12.52.14.excalidraw]]

Find - najprej pogledamo za skok največje dolžino, potem podobno kot z bisekcijo nadaljujemo.
Insert - vse povezave, bi moral na novo povezati


B)
![[Preskočni seznam (Skip list) 2024-10-25 12.58.27.excalidraw]]

Nivoje dodajam naključno, tako da je najmanj 1 in vsak naslednji nastane z $\frac{1}{2}$, torej če je uspel še drugi nivo, je spet $\frac{1}{2}$ možnosti, da nastane še tretji.
Find - $O(\log n)$
Insert - $O(\log n)$ 

Ampak je to le pričakovana vrednost, medtem ko kopica je vedno $O(\log n)$. 
