### [[ors]], 4.teden, 24-10-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #ors-flashcards 

---

### Vsebina:

[[Prekinitve]],
[[Izjeme pri RISC-V|izjeme pri RISC-V]],
[[izjeme pri ARM Cortex]].

Glavna razlika med RISC-V in Cortex M7 je to, da Cortex M7 nima cause in tvec registrov, torej ne sporoča kdo je povzročil izjemo in nima shranjenega naslova prekinitven servisnega programa.

Cortex uporablja čiste vektorske prekinitve, torej takoj ob izjemi skoči v pravi prekinitveno servisni podprogram. $$pc \leftarrow M[prek. vektor]$$
Prekinitveni vektorji so konstante, ki pripadajo vsaki izjemi. Od $0$ naprej. Od naslova $0$ naprej moramo zgraditi prekinitveno tabelo.

---
