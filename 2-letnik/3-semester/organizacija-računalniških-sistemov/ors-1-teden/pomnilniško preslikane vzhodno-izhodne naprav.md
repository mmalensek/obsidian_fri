### [[ors]], 1.teden, 03-10-2024
---

<font color="#92cddc">Status/tags:</font> #dokončano #ors-flashcards 

---

### Vsebina:

![[pomnilniško preslikane vzhodno-izhodne naprav 2024-10-07 18.11.02.excalidraw]]

> CPE "vidi" le ukazni in operandni pomnilnik!

> Edini pametni način, da CPE "vidi" V/I enote, je kot pomnilniške besede v operandnem pomnilniku.

> Ta logika na skici velja, samo za pisanje v eno bitna registra

^ Zato ima vsaka V/I naprava najmanj eno pomnilniško besedo vgrajeno vase, torej vsaka vsebuje majhen [[pomnilnik]], do katerega dostopamo z *<font color="#92cddc">load</font>* in *<font color="#92cddc">store</font>* ukazi.

Nato pa z naslovnim dekodiranjem, neki neki...

Malo drugačen primer, kjer bomo da bo možno tudi branje imeli 4 1-bitne besede na naslovih: $0x00, 0x40, 0x80, 0xC0$ :
![[pomnilniško preslikane vzhodno-izhodne naprav 2024-10-10 10.27.35.excalidraw]]

- <font color="#92cddc">OE - output enable</font> - ...
- <font color="#92cddc">CE - clock enable</font> - ...
- <font color="#92cddc">CS - chip select</font> - ...
- če bi pri naslovnem dekodiranju preverjali vse bite naslova;; -> <font color="#92cddc">Popolno naslovno dekodiranje</font>
<!--SR:!2024-10-16,4,270-->
- če preverjamo le podmnožico pri naslovnem dekodiranju;; -> <font color="#92cddc">Nepopolno naslovno dekodiranje</font>, kar je drastično zmanjša kompleksnost logike za naslovno dekodiranje, a povzroči, da je določeno območje naslovov preslikano v isti naslov, določeno število <font color="#92cddc">aliasov</font>
<!--SR:!2024-10-15,3,250-->

[[pomnilniška slika računalnika STM32H750|Pomnilniška slika računalnika STM32H]].

---

<font color="#92cddc">Flashcards:</font>

Zakaj ima vsaka V/I naprava majhen pomnilnik in kako dostopamo do tega?;; Zato, ker le na tak način lahko CPE dostopa do njih (preko pomnilniških besed), to pa dela z load in store ukazi.
<!--SR:!2024-10-16,4,270-->

---
