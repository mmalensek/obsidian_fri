[[predavanje-irz-5-teden]]; #irz-flashcards 

Nekatere operacije na regularnih jezikih $ohranjajo$ regularnost teh jezikov.

Definiramo: 
- Razred regularnih jezikov je <font color="#92cddc">zaprt</font> za dano operacijo;; če je rezultat te operacije pri argumentih, ki so regularni jeziki, spet regularni jezik.

Definiramo:
- Lastnost zaprtosti za dano operacijo je <font color="#92cddc">efektivna</font>;; če obstaja algoritem, ki na podlagi končnih opisov regularnih jezikov (ki so argumenti operacije) vrne končni opis regularnega jezika, ki je rezultat operacije. Zanimale nas bodo le efektivne lastnosti zaprtosti razreda regularnih jezikov.

Izrek:
- Razred regularnih jezikov je zaprt za operacije unija, stik in Kleeneovo zaprtje. (poglej si še dokaz)

Izrek:
- Razred regularnih jezikov je zaprt za operaciji komplement in presek.
- Dokaz:
	- naj bo $L$ poljuben regularen jezik,ali je jezik $\Sigma^* - L$ tudi regularen? Ker je $L$ regularen obstaja DKA $M = (Q, \Sigma, \delta, q_0, F)$, da je $L = L(M)$. Iz $M$ lahko sestavim DKA $M'$, kjer $M'$ sprejme $x$ natanko tedaj, ko $M$ zavrne $x$ to pomeni, da $M'$ sprejme jezik $\Sigma^* - L$, zato je ta regularen.
- Dokaz:
	- naj bosta $L_1, L_2$ poljubna regularna izraza, ali je $L_1 \cap L_2$ tudi regularen jezik? Vemo da velja: $L_1 \cap L_2 = \overline{\overline{L_1}\cup \overline{L_2}}$, kjer iz prejšnjega sklepa sledi, da to drži.

Izrek (ki ga ne potrebujemo):
 - Closure under substitution and homomorphism

Definiramo:
- Kvocient jezikov $L_1$ in $L_2$ oziroma: $L_1/L_2$, definiramo kot $L_1/L_2 = \{x\exists y \in L_2 : xy \in L_1\}$ 