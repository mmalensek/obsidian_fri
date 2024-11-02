[[predavanje-irz-5-teden]]; #irz-flashcards 

Potrebujemo algoritme, ki bodo odgovarjali na razna vprašanja o regularnih jezikih. npr. ali je dani regularni jezik $L$ neprazen, neskončen, ali sta dva končna avtomata ekvivalentna, ...

Ta vprašanja zahtevajo odgovor DA ali NE, zato je to odločitveni problem, ki ga rešujemo z odločitvenim algoritmom.

Vhodni podatki odločitvenih algoritmov bodo končni opisi regularnih jezikov tj. DKA, NKA, NKA$_\varepsilon$ 

Praznost in končnost regularnih jezikov:
- Izrek: Jezik $L(M)$, ki ga sprejme končni avtomat $M$ z $n$ stanji, je:
	1) neprazen $iff$ $M$ sprejme neko besedo dolžine $l$, kjer je $l < n$
	2) neskončen $iff$ $M$ sprejme neko besedo dolžine $l$, kjer je $n \leq l < 2n$ 
	^($iff$ - if and only if)
- Odločitvena algoritma: 
	1) ali je $L(M)$ neprazen? - preveri če v $L(M)$ obstaja beseda dolžine $l < n$
	2) ali je $L(M)$ neskončen? - preveri če v $L(M)$ obstaja beseda dolžine $n \leq l < 2n$.

Ekvivalentnost končnih avtomatov:
- Definicija: Končna avtomata $M_1$ in $M_2$ sta ekvivalentna če sprejmeta isti jezik torej če je $L(M_1)=L(M_2)$
- Izrek: Obstaja algoritem, ki odloči, ali sta končna avtomata $M_1$ in $M_2$ ekvivalentna.
	- Dokaz: Naj bosta $M_1$ in $M_2$ končna avtomata in $L_1 = L(M_1)$ in $L_2 = L(M_2)$, definirajmo jezik $L_3$ tako: $L_3 = (L_1 \cap \overline{L_2})\cup (\overline{L_1}\cap L_2)$, $L_3$ je regularen jezik, zato ga sprejme nek končni avtomat $M_3$, tega lahko sestavimo iz $M_1$ in $M_2$ na podlagi zgornjega izraza. 
	- Torej $M_3$ sprejme besedo $iff \ L_1 \neq L_2$, torej moramo samo preveriti, ali je $L_3$ neprazen regularen jezik.