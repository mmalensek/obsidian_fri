[[predavanje-vs-2-teden]];
[[Programski model ARM Cortex-M]];

Na kaj delimo delovanje CPE?;; Delimo na <font color="#92cddc">THREAD (NEpriviligirani)</font> in <font color="#92cddc">HANDLER (ali priviligirani način)</font> mode.
<!--SR:!2024-10-16,4,270-->

Thread:
- uporablja Process Stack Pointer (PSP)
- deluje vsa koda, ki ni del operacijskega sistema

Handler:
- uporablja Main Stack Pointer (MSP)
- delujejo prekinitveni servisni programi

Kako prehajamo iz threada in handler modea?;; Iz thread v handler način se preide lahko z <font color="#92cddc">izjemo</font> ([[Prekinitve|prekinitev]] ali [[Past|past]]), v tem primeru vedno shranimo kontekst, prekinjenega programa. Procesor avtomatično spremenil dva bita v Control registru. Nazaj pa se vračamo z <font color="#92cddc">Exception return</font> in hkrati obnovimo kontekst.
<!--SR:!2024-10-16,4,270-->


---

#vs-flashcards

Kaj se izvaja v Thread načinu delovanja CPE?;; Vsa koda, ki ni del operacijskega sistema.
<!--SR:!2024-10-16,4,270-->
Kaj se izvaja v Handler načinu delovanja CPE?;; Delujejo prekinitveni servisni programi.
<!--SR:!2024-10-16,4,270-->

---


