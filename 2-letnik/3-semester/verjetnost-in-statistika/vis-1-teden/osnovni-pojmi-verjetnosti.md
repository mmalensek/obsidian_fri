### [[vis]], 1.teden, 01-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano  #vis-flashcards

---

### Vsebina:
$$\Omega = \{w_{1}, w_2, ..., w_n\}$$je [[množica vseh izidov]] (ozr. rezultatov) nekega <font color="#92cddc">slučajnega poskusa,</font> kjer so $w_1, w_2, ..., w_n$ <font color="#92cddc">elementarni</font> izidi in so vsi <font color="#92cddc">enako</font> verjetni.

$$A = \{w_1, w_2, ..., w_k\}$$
je [[slučajni dogodek]], katerega elementi so <font color="#92cddc">ugodni izidi</font> za dogodek A.

$$n$$ je [[število vseh možnih izidov]].

$$k$$ je [[število ugodnih izidov]].

$$P(A) = \frac{k}{n}$$
je [[verjetnost slučajnega dogodka]] A.

---

Ponovi tudi [[Binomski simbol]]!

---

[[Verjetnost nasprotnega dogodka]] $A$ je $\overline{A}$ in je enak $P(\overline{A}) = 1 - P(A)$

---

[[Geometrijska verjetnost]]:
	[[množica vseh izidov|$\Omega$]] in [[slučajni dogodek|$A$]] se lahko predstavita kot merljiva geometrijska območja, kjer še vedno velja, da je verjetnost izbire neke točke enaka.
	Velja $P(A) = \frac{m(A)}{m(\Omega)}$, kjer sta $m(A)$ mera dogodka A in $m(\Omega)$ mera množice $\Omega$. (to je lahko dolžina, ploščina, volumen, ...)

---

[[Verjetnost unije dogodkov]]:
	$$P(A\cup B) = P(A) + P(B) - P(A\cap B)$$
	če pa sta dogodka nezdružljiva pa velja: $$P(A+B) = P(A) + P(B)$$

---

### Primeri:

2) 6B in 5Č kroglic; potegnemo ven tri kroglice; verjetnost da bo 1B in 2Č?
	dva načina, vrstni red ni pomemben ali pa je (dobimo enak rezultat):
	vrstni red ni pomemben:
	$$n = \binom{11}{3} = 165$$
	$$P(A) = \frac{\binom{6}{1}\binom{5}{2}}{\binom{11}{3}} = \frac{4}{11}$$
4) meče se kocka dokler ni enaka 6, a največ 3-krat, kolikšna je verjetnost uspešnega poskusa?
	$$P(A) = \frac{1}{6} + \frac{5 \cdot 1}{6^2} + \frac{5 \cdot 5 \cdot 1}{6^3} = \frac{91}{216}$$
6) napiši še to
	bla
---

### Flashcards:

Kaj mora veljati za množico vseh izidov nekega slučajnega poskusa $\Omega = \{w_1, w_2, ..., w_n\}$?;; Mora veljati da so $w_1, w_2, ..., w_n$ elementarni izidi in so vsi enako verjetni
<!--SR:!2024-10-15,3,250-->

Kakšna je enačba za verjetnost slučajnega dogodka?;; $P(A) = \frac{k}{n}$
<!--SR:!2024-10-16,4,270-->

Kaj predstavlja binomski simbol $\binom{n}{k}$?;; Predstavlja število načinov na katere lahko izmed $n$ predmetov izberemo $k$ predmetov, ne glede na vrstni red.
<!--SR:!2024-10-13,1,230-->

Meče se kocka dokler ni enaka 6, a največ 3-krat, kolikšna je verjetnost uspešnega poskusa?;; $P(A) = \frac{1}{6} + \frac{5 \cdot 1}{6^2} + \frac{5 \cdot 5 \cdot 1}{6^3} = \frac{91}{216}$
<!--SR:!2024-10-16,4,270-->

---
