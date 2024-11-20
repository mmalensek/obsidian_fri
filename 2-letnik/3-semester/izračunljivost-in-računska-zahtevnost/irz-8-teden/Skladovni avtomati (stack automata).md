[[predavanje-irz-8-teden]]; #irz-flashcards 

Pozna poteze dveh vrst:
- <font color="#6425d0">navadna</font> (vhodni simbol se konzumira) - $\delta(q, a, Z) = \{(p_1, \gamma_1), ..., (p_m, \gamma_m)\}$
	- v odvisnosti od stanja $q$ nadzorne enote,
	- vhodnega simbola $a$ v oknu in 
	- simbola $Z$ na vrhu sklada

	- obstaja končno mnogo alternativ, kjer $i$-ta alternativa $(p_i, \gamma_m)$ vsebuje naslednje stanje nadzorne neote in niz skladovnih simbolov, ...

	- $SA$ nedeterministično izbere in izvede eno od alternativ in
	- premakne okno na naslednjo celico (konzumira vhodni simbol)

- <font color="#6425d0">tiha</font> ($\varepsilon$-poteze, vhodni simbol se NE konzumira) - $\delta(q, \varepsilon, Z)= \{(p_1, \gamma_1), ..., (p_m, \gamma_m)\}$
	- zato je v odvisnosti le od stanja $q$ nadzorne enote in 
	- simbola $Z$ na vrhu sklada

Jezik, ki ga sprejme SA, lahko definiramo na <font color="#6425d0">dva načina</font>.
1) Ko SA prebere $w$, se znajde v končnem stanju, pravimo, da je ta množica jezik, ki ga SA sprejme s končnim stanjem.
2) Ko SA prebere $w$, izprazni svoj sklad, pravimo, da je ta množica jezik, ki ga SA sprejme s praznim skladom.

Obe definiciji sta <font color="#6425d0">ekvivalentni</font>. 

Osnovni izrek o skladovnih avtomatih: $L$ sprejme $SA$ natanko, tedaj ko $L$ je $KNJ$.

$\delta$ funkcija prehodov, preslika iz $Q \times (\Sigma \cup \{\varepsilon\})\times \Gamma$ v podmnožice množice $Q \times \Gamma^*$ (oziroma $2^{Q\times \Gamma^*}$)

<font color="#6425d0">Trenutni opis</font> (TO) je trojka $(q, w, \gamma)$, kjer je $q$ stanje, $w$ niz vhodnih simbolov in $\gamma$ niz skladovnih simbolov.
- poznamo neposredni prehod in
- refleksivno tranzitivno zaprtje relacije (nekakšno kleenejevo zaprtje)

Jeziki, ki jih sprejemajo SA.
- vsak SA $M = (Q, ...)$ sprejme dva jezika:
	- $L(M)$ jezik sprejet s končnim stanjem,
	- $N(M)$ jezik sprejet s praznim skladom.