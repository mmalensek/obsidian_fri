[[Lastnosti regularnih jezikov]]; #irz-flashcards 

Je koristna, če hočemo dokazati, da dani jezik ni regularen, da nekateri regularni jeziki so / niso končni.

Definicija:
Naj bo $L$ regularni jezik. Potem obstaja konstanta $n$ (odvisna samo od $L$), da velja naslednje:
- če je $z$ poljubna beseda z lastnostjo $z \in L \land |z| >= n$, potem obstajajo besede $u, v, w$, da velja $z = uvw \land |uv| <= n \land |w| >= 1 \land \forall i >= 0: uv^{i}w \in L$. ![[Pasted image 20241023145557.png|inv|400]]
- kjer $uv^{i}w$ predstavlja "napihnjenko" in ne glede na eksponent $i$, bo ta beseda še vedno vsebovana v $L$, tudi če je $0$.

Formalno: $$L \ regular \rightarrow (\exists n)(\forall z)[z\in L \land|z| >= n \rightarrow (\exists u,v,w)[z = uvw \land|uv|<=n \land |v| >= 1 \land(\exists i >= 0)uv^{i}w \in L]]$$
O dokazu:


