### [[irz]], 4.teden, 23-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano #irz-flashcards 

---

### Vsebina:

Razred jezikov, sprejetih s končnimi avtomati, je <font color="#92cddc">identičen</font> razredu jezikov, predstavljivih z regularnimi izrazi.

1) Za vsak $r.i.$ obstaja $NKA_\varepsilon$, ki sprejme jezik $L(r)$.
2) Za vsak $DKA \ \ M$ obstaja $r.i.$, ki predstavlja jezik $L(M)$.

Dokaz 1:
- naj bo $r$ poljuben regularni izraz. Potem obstaja $NKA_\varepsilon \  M$, ki sprejme jezik $L(r)$.

	<font color="#92cddc">Ideja</font>:
- $P(n) \equiv$ z indukcijo po številu operatorjev v $r.i.$ bomo dokazali, da lahko za poljuben $r$ sestavimo $NKA_\varepsilon$ z enim končnim stanjem, da velja $L(m) = L(r)$.
- (kjer bomo dosegli eno končno stanje tako, da vsem končnim stanjem omogočimo tihi prehod do nekega skupnega enega končnega stanja)

- Osnova: najprej preverimo $P(0)$, pri $n = 0$ je $r$ enak $\emptyset, \varepsilon \ ali \ a$. Temu pa ustrezajo $NKA_varepsilon$: ![[predavanje-irz-4-teden 2024-10-23 13.40.49.excalidraw]]
- Induktivna hipoteza: Predpostavimo, da $P(n)$ velja za vse $n <= k-1$
- Induktivni korak: Primer za $r = r_1 + r_2$. Vsak od $r_1, r_2$ ima $<= k-1$ operatorjev. Po ind.hipotezi obstajata $NKA_varepsilon \ M_1, M_2$, da je $L(M_1) = L(r_1)$ in $L(M_2) = L(r_2)$. Tedaj je $NKA_\varepsilon \ M$, ki ustreza $r$: ![[predavanje-irz-4-teden 2024-10-23 13.46.42.excalidraw]] in podobno še za $r = r_1r_2$ in $r = r_1^*$.

Dokaz 2:
- naj bo $M$ poljuben $DKA$. Tedaj obstaja regularni izraz $r$, ki predstavlja jezik $L(M)$.

  <font color="#92cddc">Ideja</font>:
- Jezik $L(M)$, ki ga sprejema $M$, zapišemo kot unijo končno mnogo množic.
- vsaka od teh množic ustreza nekemu $končnemu \ stanju$ avtomata $M$ in vsebuje natanko tiste besede, ki privedejo $M$ iz začetnega stanja v to končno stanje.
- regularni izraz, ki predstavlja jezik $L(M)$, je potem $vsota$ regularnih izrazov, ki predstavljajo te induktivno definirane množice.

- če pišemo $R_{1j}^n \equiv$ množica besed, ki privedejo $M$ iz $q_1$ v $q_j$, ne da bi $M$ šel čez stanje $>k$. Potem je $L(U)$ unija vseh teh $R$.
- $R_{ij}^k$ lahko sestavimo induktivno, ...
- $P(k) \equiv$ "Za poljubne $i,j,k$ obstaja $r.i. \ r_{ij}^k$, ki predstavlja $R_{ij}^k$"
- Dokažemo z indukcijo: ...

Uporaba končnih avtomatov:
- nekatere probleme pri razvoju programske opreme lahko rešimo tako, da pretvorimo ustrezne regularne izraze v pripadajoče $DKA$.
1) leksikalni analizator
2) urejevalnik

[[Lastnosti regularnih jezikov]].

---

Kako je povezan razred jezikov sprejet s končnim avtomatom in razred jezikov predstavljen z regularnimi izrazi?;; Sta identična.
<!--SR:!2024-10-27,4,270-->
Kaj je 

---