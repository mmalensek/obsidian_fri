[[predavanje-irz-6-teden]]; #irz-flashcards 

Naj bo $L$ regularni jezik in $M$ $DKA$, ki sprejme $L$. Obstaja neskončno mnogo končnih avtomatov, ki so ekvivalentni $M$. Ti končni avtomati se razlikujejo v komponentah $Q, \delta \ in \ F$.

Prej definiramo dve relaciji:
1) bodi $L \subseteq \Sigma^*$ poljuben jezik. Definirajmo relacijo $R_L$ na $\Sigma^*$ tako: $$xR_Ly \ \ iff \ \ \exists z \in \Sigma^* : xz \in L \leftrightarrow yz \in L$$
- $x, y$ sta v relaciji natanko tedaj, ko sta njuni poljubni razširitvi $xz, yz$ bodisi obe v $L$ bodisi izven.
- $R_L$ je ekvivalenčna relacija, torej $R_L$ razdeli $L$ v ekvivalenčne razrede. Njihovem številu pravimo $indeks \ relacije \ R_L$. Ta je lahko končen ali neskončen.  
2) Bodi $M = (Q, \Sigma, \delta, q_0, F) \ DKA$. Definirajmo relacijo $R_M$ na $\Sigma^*$: $$xR_My \ \ iff \ \ \delta(q_0, x) = \delta(q_0, y)$$
- $x, y$ sta v relaciji natanko tedaj, ko privedeta $M$ iz začetnega stanja $q_0$ v isto stanje $q$.
- $R_M$ je spet ekvivalenčna relacija, le da je teh končno mnogo, po en razred za vsako stanje $q$, ki je dosegljivo iz $q_0$. Jezik $L(M)$ je unija ekvivalenčnih razredov relacije $R_M$, ki ustrezajo končnim stanjem $q \in F$. $R_M$ je desno invariantna.

<font color="#92cddc">Myhill-Nerodejev izrek</font> pravi, da so naslednje izjave ekvivalentne:
- $L \subseteq \Sigma^*$ je regularen jezik,
- $R_L$ ima končen indeks,
- $L$ je unija ekvivalenčnih razredov desno invariantne ekvivalenčne relacije s končnim indeksom.

Izrek: Najmanjši $DFA$, ki sprejme dani regularni jezik $L$, je enolično določen do izomorfnosti (tj. do preimenovanja stanj) natančno.