[[predavanje-vs-2-teden]];

Možnost procesorja, da ustavi trenutni program in namesto tega izvede prekinitveno-servisni program.

[[Past|Pasti]] in [[Prekinitve|prekinitve]].

Kaj se v CPE <font color="#92cddc">zgodi</font>, ko se <font color="#92cddc">proži izjema</font>?;; V trenutku, ko se zgodi izjema ima procesor v (5-stopenjskem) [[Cevovod|cevovodu]] 5 ukazov. Ne sme razveljaviti ukazov, ker jih ARM ne zna (zaradi zastavic v 3.stopnji in pomnilnika v 4.stopnji), namesto tega da bi se vsi ukazi v cevovodu izvedli do konca, ker bi bilo to predolgo. Namesto tega se zavržeta ukaza if IF in ID in izvedejo trije ukazi iz EX, MEM in WB, prav tako pa se popravi PC <= PC - 8 (zaradi dveh programov, ki sta se zavrgla).
<!--SR:!2024-10-13,1,230-->

<font color="#92cddc">Shranjevanje konteksta prekinjenega programa?</font>;; Z zagotovostjo bo prekinitveno-servisni program moral shraniti najmanj 8 registrov (prve štiri, link, PC, pa še dva). Zato ARM hardwersko (trdo-kodirano) na sklad porine teh 8 registrov. Po vrsti: PSR, PC, LR, R12, R3, R2, R1, R0. <font color="#92cddc">Sklad narašča v smeri padajočih naslovov. Torej (^ "navzgor").</font>
<!--SR:!2024-10-13,1,230-->

Kako se reče tej trdožičeni logiki shranjevanja konteksta prekinjenega programa?;; Temu se reče "<font color="#92cddc">Hardware stacking</font>". Ta del sklada pa je "<font color="#92cddc">hardware stack frame</font>".
<!--SR:!2024-10-13,1,230-->

Ko se PC shrani na sklad se začne <font color="#92cddc">prevzem naslova PSP</font>:
- PC <- M[4x številka prekinitvenega vektorja] *M - velikost pomnilniške besede
- CPE to dobi od ...
- LR <- vstavimo EXC_RETURN (glede na to v kerem modu smo)

Nato pa se <font color="#92cddc">začne izvajanje PSP</font> - prekinitveno servisni program.

Vsi podprogrami (navadni in prekinitveni) se zaključijo z ukazom (ret), ki v PC <- r14(LR), (v primeru <font color="#ff0000">prekinitev</font>) kjer bo LR s samimi enicami, procesorju povedal da potrebuje narediti <font color="#92cddc">hardware destacking</font> ozr. EXC_RETURN (exceptional return). 

---

#vs-flashcards 

---
