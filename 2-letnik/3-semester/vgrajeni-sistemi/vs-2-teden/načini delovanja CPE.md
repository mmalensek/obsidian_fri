[[predavanje-vs-2-teden]];
[[Programski model ARM Cortex-M]];

Delimo na <font color="#92cddc">THREAD (NEpriviligirani)</font> in <font color="#92cddc">HANDLER (ali priviligirani način)</font> mode.

Thread:
- uporablja Process Stack Pointer (PSP)
- deluje vsa koda, ki ni del operacijskega sistema

Handler:
- uporablja Main Stack Pointer (MSP)
- delujejo prekinitveni servisni programi

Iz thread v handler način se preide lahko z <font color="#92cddc">izjemo</font> ([[Prekinitve|prekinitev]] ali [[Past|past]]), v tem primeru vedno shranimo kontekst, prekinjenega programa. Procesor avtomatično spremenil dva bita v Control registru. 

Nazaj pa se vračamo z <font color="#92cddc">Exception return</font> in hkrati obnovimo kontekst.


---

#vs-flashcards

vprasanje;; odgovor

---


