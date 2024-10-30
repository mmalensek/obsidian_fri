[[Lastnosti regularnih jezikov]]; #irz-flashcards 

Je koristna, če hočemo dokazati, da dani jezik ni regularen, da nekateri regularni jeziki so / niso končni, torej da jih lahko definiramo s končnim avtomatom.

![[Lema o napihovanju 2024-10-29 07.49.52.excalidraw]]

Kjer mora biti dolžina "cikla" $y$ najmanj 1. ($uvw = xyz$ na vajah smo pisal $xyz$). Torej velja $xy^{i}z$, kjer je $\forall i >= 0$ (lahko sploh ne gremo v cikel, lahko pa je cikel poljubno dolg)

Definicija:
Naj bo $L$ regularni jezik. Potem obstaja konstanta $n$ (odvisna samo od $L$), da velja naslednje:
- če je $z$ poljubna beseda z lastnostjo $z \in L \land |z| >= n$, potem obstajajo besede $u, v, w$, da velja $z = uvw \land |uv| <= n \land |w| >= 1 \land \forall i >= 0: uv^{i}w \in L$. ![[Pasted image 20241023145557.png|inv|400]]
- kjer $uv^{i}w$ predstavlja "napihnjenko" in ne glede na eksponent $i$, bo ta beseda še vedno vsebovana v $L$, tudi če je $0$.

Formalno: $$L \ regular \rightarrow (\exists n)(\forall z)[z\in L \land|z| >= n \rightarrow (\exists u,v,w)[z = uvw \land|uv|<=n \land |v| >= 1 \land(\exists i >= 0)uv^{i}w \in L]]$$
če rečemo da so $n, z, u, w$ "dobri", potem lahko lemo skrajšamo na: $$L \ regular \Longrightarrow (\forall z)(\exists u, v, w)(\forall i \geq 0)uv^{i}w\in L$$
Tako se hitro poenostavi, da če za dani $L$ dokažemo da obstaja $z = uvw$, kjer ne velja $uv^{i}w \notin L$, da jezik ni regularen.

O dokazu:
Če avtomat sprejme besedo $w$, za katero velja $|w| > n$, kjer je $n$ najmanjša beseda, ki jo avtomat sprejme oziroma, število stanj avtomata, pomeni, da se $w$ v nekem delu cikla, kjer je cikel dolg najmanj $1$, besedo zato lahko razdelimo na tri dele $w = xyz$, kjer $x$ predstavlja del besede pred ciklom, $y$ predstavlja sam cikel in $z$ zadnji del besede po ciklu do končnega stanja.

---

V praksi: [[vaje-irz-5-teden]]. 

---

Primer: naj bo $L = \{0^{i^{2}}\mid i \in \mathbb{N}\}$  
- Naj bo $n$ konstanta iz leme o napihovanju.
- vzemimo besedo $z = 0^{n²}$ - je dobra, je vsebovana v jeziku in je daljša od $n$
- obstaja več možnih razdelitev besede $z$ na 'dobre' $u,v,w$
- naj bo $u,v,w$ poljubna 'dobra' razdelitev besede $z$. Dokazali bomo, da $uv²w \notin L$
	- računamo: $|uv²w|= |u| + 2|v| + |w| = |z| + |v| = |n²| + |v|$
	- vemo da je: $1 \leq|v| \leq n$
	- če prištejemo $n²$, dobimo $n²+1 \leq |uv²w| \leq n² + n$
	- torej je $n² < |uv²w| < (n+1)²$, to pomeni da $|uv²w|$ ni popolni kvadrat
- tako smo dokazali da za poljubne 'dobre' $u,v,w$ obstaja $i (=2)$, da $uv^{i}w \notin L$ 

Torej tega jezika ne sprejme noben končni avtomat, ni regularen izraz.

---
