[[predavanje-vs-3-teden]]; #vs-flashcards 

Oziroma "scheduler".

<font color="#92cddc">Vsako</font> opravilo ima svoj <font color="#92cddc">sklad</font>. 

Opravilo se samo po sebi ne sme zaključiti, zato tudi ničesar ne vrača (void), prav tako pa se jih ne da poklicati.

npr. imamo 4 opravila
- ko se prekine prvo opravilo in se začne prekinitveno servisni program, se ne želimo vrniti nazaj na prvo opravilo ampak na drugo.
- zato naredi hardware destacking iz skladu drugega opravila.
- zato imamo rezervirano prostora v pomnilniku, da bo zadoščal za sklad vsakega od štirih opravil - $stackRegion$, ki ga navidezno razdelimo na štiri in imamo tako štiri kazalce, ki je dodeljen ustreznemu opravilu.

Imamo tudi $Task Control Block$, ki ima dva kazalca, enega za naslov opravila in eno za naslov njegovega sklada.

In funkcijo $TaskCreate$, ki napolni TaskControlBlock posameznega opravila. 

Opravila se vrtijo v neskončni 



