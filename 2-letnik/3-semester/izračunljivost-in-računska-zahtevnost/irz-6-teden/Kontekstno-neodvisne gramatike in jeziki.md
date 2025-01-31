[[predavanje-irz-6-teden]]; #irz-flashcards 

Definiramo pojma kontekstno-neodvisne gramatike $(KNG)$ in kontekstno-neodvisnega jezika $(KNJ)$, ki ga taka gramatika opisuje.

Te se pojavljajo npr. pri definiranju programskih jezikov, ...

<font color="#92cddc">Definicija</font>: Kontekstno-neodvisna gramatika $(KNG)$ je četverka $G = (V, T, P, S)$ kjer so:
- $V$ končna množica vmesnih simbolov,
- $T$ končna množica končnih simbolov,
- $P$ končna množica produkcij oblike $... \Rightarrow ...$, kjer je na levi strani poljuben vmesni simbol iz $V$ in na desni strani poljubna beseda iz jezika $(V\ \cup \ T)^*$,
- $S$ je poseben vmesni simbol, imenovan začetni simbol (start symbol).

<font color="#92cddc">Definicija</font>: Naj bo $A \Rightarrow \beta$ produkcija in $\alpha, \gamma \in (V \ U \ T)^*$ poljubni besedi.
- To produkcijo uporabimo na $\alpha A \gamma$ tako, da v tej besedi zamenjamo $A$ z $\beta$. Takrat rečemo, da smo iz $\alpha A \gamma$ neposredno izpeljali z uporabo produkcije.
- Besedi $\alpha_i$ in $\alpha_j$ sta v relaciji $\alpha_i \ _G\Rightarrow \alpha_j$, če je $\alpha_j$ neposredno izpeljiv iz $\alpha_i$ z uporabo neke gramatike $G$.
- naj bodo $\alpha_1, \alpha_2, ..., \alpha_m$ ...

<font color="#92cddc">Definicija</font>: Jezik kontekstno-neodvisne gramatike $G = (V,T,P,S)$ je $$L(G)=\{w\mid w \in T^* \land S \ _G\Rightarrow^* w\}$$Torej je $L(G)$ množica vseh končnih nizov, ki so izpeljivi iz začetnega simbola $S$ po gramatiki $G$.

<font color="#92cddc">Dodatne tri definicije</font>:
- jezik $L$ je kontekstno-neodvisen $(KNJ)$, če je $L = L(G)$ za neko $KNG \ \ G$.
- niz $\alpha \in (V \cup \ T)^*$ imenujemo stavčna oblika, če velja $S \ _G \Rightarrow^* \alpha$.
- gramatiki $G_1$ in $G_2$ sta ekvivalentni, če velja $L(G_1) = L(G_2)$.