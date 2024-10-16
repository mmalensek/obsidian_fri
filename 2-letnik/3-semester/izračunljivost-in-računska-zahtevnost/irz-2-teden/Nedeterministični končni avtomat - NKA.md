[[Končni avtomat]]; #irz-flashcards

Kako lahko dobimo NKA?;; dobimo iz DKA če dopustimo *nič*, enega ali celo *več* prehodov iz kakega stanja pri <font color="#92cddc">istem vhodnem simbolu</font>.
<!--SR:!2024-10-26,11,270-->

npr. ![[Pasted image 20241009143258.png]]
NKA <font color="#92cddc">sprejme</font> vhodno besedo $x = a_1a_2 ... a_n$, če obstaja (vsaj eno) zaporedje prehodov, označeno z $a_1a_2 ... a_n$, ki vodi iz začetnega stanja v katerokoli končno stanje.

<font color="#92cddc">Nedeterminizem</font>:
- NKA sam bo ugotovil ali obstaja zaporedje prehodov, ki se konča v končnem stanju za neko besedo.
- NKA ni realističen, predpostavljamo namreč, da NKA to vedno pravilno ugane oziroma se ustavi, če takšnega ni.

Zato je NKA <font color="#92cddc">neuresničljiv</font>, <font color="#92cddc">nerealističen</font> model. A vseeno <font color="#92cddc">koristi</font>, ker če dokažemo, da za reševanje nekega problema nedeterminističen model potrebuje $T$ časa, potem bo tudi za kakršnokoli deterministično različico tega modela zahtevalo najmanj $T$ časa, saj ta nima magične sposobnosti pravilnega ugibanja. 

Pravtako je pogosto sestaviti NKA in ko je ta sestavljen iz tega modela izpeljati ekvivalentno deterministično različico.

<font color="#92cddc">Definicija</font>: NKA je peterka:
- $Q$ končna množica stanj,
- $\Sigma$ vhodna abeceda,
- $q_0 \in Q$ začetno stanje,
- $F \subseteq Q$ množica končnih stanj,
- $\delta$ funkcija prehodov tj. $\delta : Q \times \Sigma \rightarrow 2^Q$, (edina razlika tu, med DKA)

![[Pasted image 20241009145057.png]]

V primeru neveljavnega simbola (npr. če smo v stanju $q_1$ in dobimo $0$, se avtomat) ustavi.

$\delta$ spet razširimo rekurzivno, ter tudi tako, da je prvi argument tudi množica stanj.

NKA $M = (Q, \Sigma, \delta, q_0, F)$ sprejme besedo x, če $\delta(q_0, x)$ vsebuje kako končno stanje $p\in F$

Jezik, sprejet z NKA $M$ je množica $L(M)$ vseh besed, ki jih sprejme $M$: $$L(M) = \{x \in \Sigma^* \mid \delta(q_0, x)\ contains\ a \ state\ in\ F\}$$ tukaj je [[Formalni jezik|$\Sigma^*$]].

---
Kdaj NKA sprejme besedo?;; Če obstaja vsaj eno zaporedje, ki vodi iz začetnega v katerokoli končno stanje.
<!--SR:!2024-10-26,11,270-->
Zakaj je NKA nedeterminističen?;; Ker ima na voljo več opcij in sam "izbira", pravilne možnosti, da pride do končnih stanj, kar je nerealistično, a vseeno uporabno.
<!--SR:!2024-10-16,4,270-->
Zakaj je NKA vseeno uporaben?;; Ker nam vseeno pove, v kakšnem minimalnem času so problemi rešljivi in iz njih lahko lažje sestavimo DKA.
<!--SR:!2024-10-16,4,270-->




