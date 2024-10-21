[[Končni avtomat]]; #irz-flashcards 

ima končno množico stanj in končno množico prehodov med stanji, ki se zgodijo po branju simbolov iz vhodne abecede.

Pri tem velja:
- za vsak vhodni simbol in vsako stanje obstaja <font color="#92cddc">natanko en prehod</font>,
- eno stanje, označeno s $q_0$, je <font color="#92cddc">začetno stanje</font>, kjer DKA začne delovanje.
- nekatera stanja so končna.

![[Pasted image 20241009133029.png]]

- Točke predstavljajo stanja DKA
- usmerjene povezave pa prehode

V tem primeru je začetno stanje tudi končno (črn krogec).

Kdaj povezava $\frac{q_i \rightarrow q_j}{a}$ obstaja?;; če DKA lahko preide iz stanja $q_i$ v $q_j$ pri prebranem $a$.
<!--SR:!2024-11-03,15,290-->

<font color="#92cddc">Definicija</font>: DKA je peterka, kjer so:
- $Q$ končna množica stanj,
- $\Sigma$ vhodna abeceda,
- $q_0 \in Q$ začetno stanje,
- $F \subseteq Q$ množica končnih stanj,
- $\delta$ funkcija prehodov, $\delta : Q \times \Sigma \rightarrow Q$. (stanje v katerega DKA, preide iz stanja $q$ če prebere $a$).

$\delta$ je (definiran za?);; <font color="#92cddc">totalna</font>, pomeni da mora biti definirana za čisto vsak par.
<!--SR:!2024-10-22,1,210-->

Če je $\delta(q,a)$ končno stanje, pravimo, da je DKA <font color="#92cddc">sprejel</font> predpono vhodne besede vključno do prebranega $a$. Lahko sprejme več predpon vhodne besede.

$\delta$ razširimo, da je lahko njen drugi argument <font color="#92cddc">niz simbolov</font> (ne le en simbol). 

![[Pasted image 20241009135029.png]]

Primer za $\delta(q, wa)$.

- DKA $M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo x, če je $\delta(q_0, x) = p$ za neki $p \in F$ (množici končnih stanj). Torej sprejme besedo, če beseda iz začetnega stanja pride po koncu branja v končno stanje.
- jezik, sprejet z DKA $M$ je množica $L(M)$ vseh besed, ki jih sprejme $M$: $$L(M) = \{x \in \Sigma^* \mid \delta(q_0, x)\in F\}$$ tukaj je [[Formalni jezik|$\Sigma^*$]].
- jezik $L'$ je regularen (oz. je regularna množica), če $L'$ sprejme kak DKA (tj. če $\exists$ DKA $M : L'  = L(M)$)

---
Kako označimo končno stanje končnih avtomatov?;; S črnim krogcem
<!--SR:!2024-11-03,15,290-->
Kaj velja za DKA?;; Ima končno množico stanj in končno množico prehodov med stanji. Za vsak vhodni simbol in vsako stanje obstaja <font color="#92cddc">natanko en prehod</font>, eno stanje, označeno s $q_0$, je <font color="#92cddc">začetno stanje</font>, kjer DKA začne delovanje. Nekatera stanja so končna. Točke predstavljajo stanja DKA in usmerjene povezave pa prehode.
<!--SR:!2024-10-24,5,230-->
Kaj je $Q$?;; Končna množica stanj.
<!--SR:!2024-11-03,15,290-->
Kaj je $\Sigma$?;; Vhodna abeceda.
<!--SR:!2024-10-22,3,210-->
Kaj je $q_0$?;; Začetno stanje.
<!--SR:!2024-11-03,15,290-->
Kaj je $F$ in kaj zanj velja?;; Je množica končnih stanj in je podmnožica $Q$.
<!--SR:!2024-10-26,11,270-->
Kaj je $\delta$? Je funkcija prehodov. 
Kaj je jezik, sprejet z DKA? je množica vseh besed, ki jih sprejme nek DKA.
Kaj pomeni da je jezik regularen?;; Je jezik, ki ga lahko prepoznamo s končnim avtomatom.
<!--SR:!2024-10-25,6,250-->