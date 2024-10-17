[[predavanje-irz-3-teden]]; #irz-flashcards 

Jezike, ki jih <font color="#92cddc">sprejemajo končni avtomati</font> lahko predstavimo z enostavnimi izrazi oziroma;; t.i. <font color="#92cddc">regularnimi izrazi</font>.

1) Naj bo $\Sigma$ abeceda ter $L_1$ in $L_2$ množici besed iz [[Formalni jezik|$\Sigma^*$]]. Stik $L_1L_2$ jezikov $L_1$ in $L_2$ je jezik, definiran z: $$L_1L_2 = \{xy \mid x \in L_1 \ and \ y \in L_2\}$$
2) Naj bo $L \subseteq \Sigma^*$. Definirajmo $L^0 = \{0\}$ in $L^{i} = LL^{i-1}$ za $i >= 1$.
	- Kleeneovo zaprtje - $L^*$ jezika $L$ je jezika $L^* = x$
	- Tranzitivno zaprtje - ...


Primer: $L_1 = \{10, 1\}$ in $L_2 = \{011, 11\}$
	- tedaj je $L_1L_2 = \{10011, 1011, 111\}$
	- in še $L_1^* = \{10, 1\}^* = \{\varepsilon, 10, 1, 1010, 101, 110, 11, ...\}$
	- in $L_1⁺ = \{10, 1\}⁺ = \{10, 1, 1010, 101, 110, 11, ...\}$

Definicija regularnega izraza; naj bo $\Sigma$ abeceda. Regularni izraz (r.i.) nad $\Sigma$ in jezik, ki ga r.i. predstavlja, sta definirana induktivno takole:
1) $\emptyset$ je r.i. ; predstavlja jezik $\emptyset$ 
2) $\varepsilon$ je r.i. ; predstavlja jezik $\{\varepsilon\}$
3) za vsak $a \in \Sigma$ je $a$ r.i. ; predstavlja jezik $\{a\}$
4) če sta $r$ in $s$ r.i. in predstavljata jezika $R$ in $S$, potem:
	- $(r+s)$ je r.i. ; predstavlja jezik $R \cup S$ - unija
	- $(rs)$ je r.i. ; predstavlja jezik $RS$ - stik
	- $(r^{s})$ je r.i. ; predstavlja jezik $R^*$ - kleeneovo zaprtje


Dogovori:
- če upoštevamo, da ima $*$ prednost pred stikom, ta pa prednost pred $+$
	- npr. $((0(1^*))+0)$ se poenostavi v ekvivalenten r.i. $01^*+0$ in pomeni da je to beseda, ki se začne z $0$ in nato nadaljuje s poljubnim številom $1$.
- regularne izraze oblike $rr^*$ krajše zapišemo z $r⁺$
- regularne izraze oblike $rrr...r$, kjer je staknjenih $k$ r.i. $r$, okrajšamo z $r^k$
- z $L(r)$ bomo označili jezik, ki ga $r$ predstavlja

