[[predavanje-vs-2-teden]];

Možnost procesorja, da ustavi trenutni program in namesto tega izvede prekinitveno-servisni program.

[[Past|Pasti]] in [[Prekinitve|prekinitve]].

Kaj se v CPE <font color="#92cddc">zgodi</font>, ko se <font color="#92cddc">proži izjema</font>?;; V trenutku, ko se zgodi izjema ima procesor v (5-stopenjskem) [[Cevovod|cevovodu]] 5 ukazov. Ne sme razveljaviti ukazov, ker jih ARM ne zna (zaradi zastavic v 3.stopnji in pomnilnika v 4.stopnji), namesto tega da bi se vsi ukazi v cevovodu izvedli do konca, ker bi bilo to predolgo. Namesto tega se zavržeta ukaza if IF in ID in izvedejo trije ukazi iz EX, MEM in WB, prav tako pa se popravi PC <= PC - 8 (zaradi dveh programov, ki sta se zavrgla).
<!--SR:!2024-10-22,1,190-->

<font color="#92cddc">Shranjevanje konteksta prekinjenega programa?</font>;; Z zagotovostjo bo prekinitveno-servisni program moral shraniti najmanj 8 registrov (prve štiri, link, PC, pa še dva). Zato ARM hardwersko (trdo-kodirano) na sklad porine teh 8 registrov. Po vrsti: PSR, PC, LR, R12, R3, R2, R1, R0. <font color="#92cddc">Sklad narašča v smeri padajočih naslovov. Torej (^ "navzgor").</font>
<!--SR:!2024-10-24,5,230-->

Kako se reče tej trdožičeni logiki shranjevanja konteksta prekinjenega programa?;; Temu se reče "<font color="#92cddc">Hardware stacking</font>". Ta del sklada pa je "<font color="#92cddc">hardware stack frame</font>".
<!--SR:!2024-10-25,6,250-->

Ko se PC shrani na sklad se začne <font color="#92cddc">prevzem naslova PSP</font>:
- PC <- M[4x številka prekinitvenega vektorja] *M - velikost pomnilniške besede
- CPE to dobi od ...
- LR <- vstavimo <font color="#92cddc">EXC_RETURN</font> (exception return - glede na to v kerem modu smo)

Nima posebnega ukaza za vračanje PSP-ja, zato se iz LR vstavi v programski števec, kako pol naj računalnik naredi <font color="#92cddc">"destacking"</font>? Prebere naslov, kjer naj ne bi bilo programa (zadnji naslov v pomnilniku npr.). 

Nato pa se <font color="#92cddc">začne izvajanje PSP</font> - prekinitveno servisni program.

Vsi podprogrami (navadni in prekinitveni) se zaključijo z ukazom (ret), ki v PC <- r14(LR), (v primeru <font color="#ff0000">prekinitev</font>) kjer bo LR s samimi enicami, procesorju povedal da potrebuje narediti <font color="#92cddc">hardware destacking</font> ozr. EXC_RETURN (exceptional return).



---

#vs-flashcards 

Kako pride do hardware destacking-a?;; Vsi podprogrami se zaključijo z ukazom, ki je v r14(LR), v primeru prekinitve bo LR iz samih enic, to procesorju pove, da potrebuje narediti hardware destacking.
<!--SR:!2024-10-22,3,264-->

---
