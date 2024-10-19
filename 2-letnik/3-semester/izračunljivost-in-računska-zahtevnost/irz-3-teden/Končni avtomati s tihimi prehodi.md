[[predavanje-irz-3-teden]]; #irz-flashcards 

Kako definiramo $NKA_\varepsilon$?;; Definicijo NKA razširimo tako, da ji dodamo sposobnost <font color="#92cddc">spontanega prehajanja</font> med stanji, tj. prehajanja v nova stanja, ne da bi NKA pri tem prebral simbol v oknu, temu rečemo <font color="#92cddc">tihi prehod</font> ($\varepsilon$-prehod). Primer: ![[Pasted image 20241016134541.png]]
Kdaj $NKA_\varepsilon$ sprejme besedo $x$?;; Če obstaja pot, označena z $x$ iz $q_0$ v $q_2$, kjer so $\varepsilon$ lahko sestavni del te poti, če tudi $\varepsilon$ ni eksplicitno naveden v $x$. (npr. $x = ab = \varepsilon a \varepsilon b \varepsilon$).

<font color="#92cddc">Definicija</font>: NKA s tihimi prehodi ($NKA_\varepsilon$):
- $Q$ končna množica stanj,
- $\Sigma$ vhodna abeceda,
- $q_0 \in Q$ začetno stanje,
- $F \subseteq Q$ množica končnih stanj,
- $\delta$ funkcija prehodov, $\delta : Q \times (\Sigma \cup \{\varepsilon\}) \rightarrow Q$

$\delta$ razširimo tako, da je lahko njen drugi argument niz simbolov (tudi prazen), zato tudi definiramo $\varepsilon - Zaprtje(q)$, npr. za prejšnjo sliko velja: $$\varepsilon - Zaprtje(q_0) = \{q_0, q_1, q_2\}$$ in $$\varepsilon - Zaprtje(q_2) = \{q_2\}$$

Sedaj ne velja več v splošnem $NKA \ s \ tihimi\ prehodi \ \rightarrow \delta(q,a) \neq \delta(q,a) \leftarrow NKA$.

$NKA_\varepsilon \ M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo $x$, če;; $\delta(q_0, x)$ vsebuje kako končno stanje $p \in F$. Jezik, sprejet z $NKA_\varepsilon \ M$ je množica $L(M)$ vseh besed, ki jih sprejme M.

Jezik sprejet z $NKA_\varepsilon$;; je <font color="#92cddc">enak</font> razredu jezikov, sprejetih z $NKA$.
 