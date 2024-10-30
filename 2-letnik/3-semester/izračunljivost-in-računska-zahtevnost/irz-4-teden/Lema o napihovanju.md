[[Lastnosti regularnih jezikov]]; #irz-flashcards 

Je koristna, če hočemo dokazati, da dani jezik ni regularen, da nekateri regularni jeziki so / niso končni, torej da jih lahko definiramo s končnim avtomatom.

![[Lema o napihovanju 2024-10-29 07.49.52.excalidraw]]

Kjer mora biti dolžina "cikla" $y$ najmanj 1. ($uvw = xyz$ na vajah smo pisal $xyz$). Torej velja $xy^{i}z$, kjer je $\forall i >= 0$ (lahko sploh ne gremo v cikel, lahko pa je cikel poljubno dolg)

Definicija:
Naj bo $L$ regularni jezik. Potem obstaja konstanta $n$ (odvisna samo od $L$), da velja naslednje:
- če je $z$ poljubna beseda z lastnostjo $z \in L \land |z| >= n$, potem obstajajo besede $u, v, w$, da velja $z = uvw \land |uv| <= n \land |w| >= 1 \land \forall i >= 0: uv^{i}w \in L$. ![[Pasted image 20241023145557.png|inv|400]]
- kjer $uv^{i}w$ predstavlja "napihnjenko" in ne glede na eksponent $i$, bo ta beseda še vedno vsebovana v $L$, tudi če je $0$.

Formalno: $$L \ regular \rightarrow (\exists n)(\forall z)[z\in L \land|z| >= n \rightarrow (\exists u,v,w)[z = uvw \land|uv|<=n \land |v| >= 1 \land(\exists i >= 0)uv^{i}w \in L]]$$
O dokazu:
Če avtomat sprejme besedo $w$, za katero velja $|w| > n$, kjer je $n$ najmanjša beseda, ki jo avtomat sprejme oziroma, število stanj avtomata, pomeni, da se $w$ v nekem delu cikla, kjer je cikel dolg najmanj $1$, besedo zato lahko razdelimo na tri dele $w = xyz$, kjer $x$ predstavlja del besede pred ciklom, $y$ predstavlja sam cikel in $z$ zadnji del besede po ciklu do končnega stanja.

---

V praksi: [[vaje-irz-5-teden]].

