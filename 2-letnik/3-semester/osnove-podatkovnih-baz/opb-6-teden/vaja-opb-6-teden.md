### [[opb]], 6.teden, 05-11-2024
---

<font color="#92cddc">Status/tags:</font> #NEpregledano #opb-flashcards 

---

### Vsebina:

### Vaje DML:

12) 
```SQL
select o.id, o.ime, count(*)
from oseba o left outer join twitter t on o.id = t.sid
group by o.id, o.ime;
```
13) 
```SQL
select (select count(*) from facebook where oid < pid), (select count(*) from twitter)
```
14) 
```SQL
select DATE(c.date), count(c.id)
from cable c
group by DATE(c.date)
having count(c.id) > 300 
oziroma za b)
having count(*) = (
	select max(value)
		from(
			select...)
)
```
15) 
```SQL
select cable_id, count(ref_cable_id), group_concat(ref_cable_id separator ', ')
from reference
group by cable_id
order by count(ref_cable_id) desc
limit 100;
```

Še novi ukazi DML:

Vstavljanje
```SQL
insert into t [(A, B)] (1, "foo"), (40, "bar"), (2, "blabla");
```
Brisanje
```SQL
delete from t [where a != 1];
```
Posodabljanje
```SQL
update t set a = a - 1 [where a != 1];
```


### Ukazi DDL: (na spletni učilnici imaš Docker)

Ustvarjanje tabele
```SQL
create table t (a int not null, b varchar(32) [null]);
```
Spreminjanje tabele
```SQL
alter table t add primary key (A);
```
Brisanje tabele
```SQL
drop table t;
```
Ustvarjanje pogleda
```SQL
create view subt as select * from t where B is not null;
```

- do pogleda se dostopa enako kot do tabele, le da je tabela fizična zadeva na nekem disku, pogled pa samo navidezna tabela

Ustvarjanje indeksa
```SQL
create index in on t (B); 
```
- podobna podatkovna struktura, kot je npr. v učbenikih ali knjigah


### Ukazi DCL:

Stavek CREATE USER in za nadzor pravic - GRANT/REVOKE

### Ukazi TPO:

Commit in rollback.

---

Flashcards: #opb-flashcards 

Kaj je relacija med tabelo in pogledom?;; Pogled je navidezna tabela.

---