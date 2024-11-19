### [[irz]], 7.teden, 13-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #irz-flashcards 

---

### Vsebina:

Skladovni avtomat, je končni avtomat, ki ima neskončen sklad. 
Je definiran kot: $A= (Q, \Sigma, \Gamma, \delta, q_0, Z, F)$, kjer je $\Gamma$ skladovna abeceda in $Z \in \Gamma$.

- sprejem s končnim stanjem: $(q_0, w, Z) \rightarrow* (q_F, \varepsilon, p); q_F \in F, p \in \Gamma*$ 
- sprejem z izpraznitvijo sklada: $(q_0, w, Z) \rightarrow* (q_F, \varepsilon, \varepsilon); q_F \in F$

Ti dve definiciji sta enakovredni, torej lahko izberemo kateri kriterij uporabimo.

Funkcija prehodov $\sigma : Q\times (\Sigma \cup \{\epsilon\})\times \Gamma \rightarrow 2^{Q\times \Gamma^*}$ 

Trenutni opis: $(stanje, \ preostanek \ vhoda, vsebina \ sklada)$

Primeri: 
![[vaje-irz-7-teden 2024-11-13 08.32.07.excalidraw]]

Deterministični skladovni avtomat, za vsako trojko, mora biti največ en prehod, ki imajo lahko tihe prehode, če ti ne povzročijo dvoumnosti.

Primer kako se gramatika pretvori v skladovni avtomat:
![[vaje-irz-7-teden 2024-11-13 09.58.15.excalidraw]]

---
