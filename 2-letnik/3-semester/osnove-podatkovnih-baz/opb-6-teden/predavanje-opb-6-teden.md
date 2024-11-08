### [[opb]], 6.teden, 08-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #opb-flashcards 

---

### Vsebina:

<font color="#92cddc">Alter</font> table stavek. npr:
```SQL
alter table employees alter gender set default 'M';
```

<font color="#92cddc">Delete</font> - izbriše samo podatke v tabeli, medtem ko drop - izbriše tudi celotno tabelo, lahko ali $restrict$ ali $cascade$, kjer zadnja izbriše tudi vse povezane tabele.

[[Indeksi]].

<font color="#92cddc">Pogledi</font> - nam predstavlja navidezno tabelo

---

<font color="#92cddc">Transakcije</font> - je atomarna logična enota dela z enim ali več SQL ukazi, SQL definira transakcijski model z ukazoma $COMMIT$ in $ROLLBACK$.

- spremembe znotraj transakcije so praviloma drugim skrite, dokler le ta ni končana

Izolacijske ravni transakcij:
- <font color="#92cddc">dirty read</font> - ko beremo uncommited transakcije, npr. imamo neko transakcijo ki spremeni starost nekemu uporabniku in če ravno takrat to preberemo in kasneje prejšnja transakcija izvede rollback, ...
- <font color="#92cddc">non-repeatable read</font> - se lahko zgodi pri izolacijskih ravneh read committed in read uncommitted.
- <font color="#92cddc">phantom read</font> - se lahko zgodi pri vseh razen pri serializable

![[Pasted image 20241108103315.png|350]]

Takojšnje in zapoznele omejitve:
- kdaj se upoštevajo omejitve, na začetku ali po zaključku transakcije:
	- initially immediate - na začetku
	- initially deferred - ob zaključku

```SQL
set constraints {all | constraintName [, ...]}
[deffered | immediate]
```

---

Bazni izvedbeni objekti:
- večina SUPB podpira:
	- triggerje
	- v bazi shranjene podprograme
	- funkcije

1) <font color="#92cddc">sprožilci</font> (triggers)
	- se prožijo pred ali po operaciji insert, delete, update

---
