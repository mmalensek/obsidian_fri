### [[opb]], 4.teden, 22-10-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #opb-flashcards

---

### Vsebina:

[[uvod v SQL|Uvod v SQL]].

1) naloga
	
```SQL
select ID, Ime as "User name", Rojen as "Birth"
from oseba
where rojen <= "22.10.2006";
```

2) naloga - nov izračunan atribut
	
```SQL
select *, Datediff(Curdate(), Rojen) / 365 as "Starost"
from oseba

```

3) naloga - sortiraj in izpiši zadnjih 5
	
```SQL
select id, date, header, content
from cable c
where embassy_id = 140
orderby date DESC
limit 5;
```

Če želimo iz vrednosti Date_time ven samo date, imamo funkcijo DATE(date), prav tako nam cable c, preimenuje cable za lažje delo.

4) naloga
	
```SQL
select *
from embassy
where name like "%Ljubljana%";
```

Kjer "%Ljubljana%" pomeni, da nam je vseeno koliko in kakšnih karakterjev je pred in po Ljubljani, ali pa "_" za samo en znak.

Stične operacije: [[uvod v SQL]].

5) naloga
```SQL
select distinct ID, Ime as "User name", tatusStan as "S"
from oseba NATURAL JOIN  stan INNER JOIN facebookon ON oid = id;
```

6) naloga
	
```SQL
select distinct f.OID
from facebook f left outer join twitter t on f.OID = t.OID or f.OID = t.SID;  
```

7) naloga
	
```SQL
select c.id, date, header
from cable c, embassy e, privacy p
where e.id = e.embassy_id and c.privacy = p.id and e.name = "Ljubljana" and p.classification = "private" and YEAR(c.date) = 2010;
```

8) naloga
	
```SQL
select distinct c1.embassy_id as "Embassy", DATE(c1.date)
from cable c1, cable c2
where c1.date = c2.date and c1.embasyy_id = c2.embassy_id and c1.id != c2.id;
```


---
