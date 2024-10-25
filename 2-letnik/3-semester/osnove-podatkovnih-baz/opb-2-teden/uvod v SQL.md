[[predavanje-opb-2-teden]]; #opb-flashcards 

Sintaksa SQL se <font color="#92cddc">deli</font>:

- ukazi iz skupine <font color="#92cddc">DML</font> (data manipulation language)
	- za poizvedovanje in ažuriranje podatkov
	- SELECT, INSERT, UPDATE, DELETE

- ukazi is skupine <font color="#92cddc">DDL</font> (data definition language)
	- za opredelitev strukture podatkovne baze
	- CREATE, ALTER, SET TRANSACTION

- sprožilci, funkcije in shranjeni programi


Za primer uporabljamo testno podatkovno *Employees.db* bazo iz https://launchpad.net/test-db/+download.

SQL izrazi niso občutljivi na velikost črk.

Izpiše vse podatke o zaposlenih: 
```SQL
select * from employees;
```

Izpiši imena in priimke zaposlenih: 
```SQL
select first_name, last_name from employees;
```

Izpiši vse različne vrednosti, ki nastopajo v stolpcu gender:

```SQL
select distinct gender from employees;
```

Izpiši starost delavcev ob zaposlitvi (izračunana polja in funkcije) in preimenovanje:

```SQL
select first_name, last_name, birth_date, hire_date, DATEDIFF(hire_date, birth_date)/365
as 'Starost ob zaposlitvi'
from employees;
```

druga možnost..
```SQL
select first_name, last_name, YEAR(hire_date)-YEAR(birth_date)
as 'Starost ob zaposlitvi'
from employees;
```

Iskalni kriteriji, izpiši vse, ki so moškega spola in so rojeni pred 1953
```SQL
select * from employees
where YEAR(birth_date)<1953 and gender = 'M';
```
SQL sam naredi "poizvedbeni plan", zato ni treba biti pazljiv pri pisanju poizvedb (glede časovne zahtevnosti).

funkcija between: 
```SQL
between '1955-12-30' and '1955-12-31';
```

Delo z množicami, ki so zelo hitre:
```SQL
select * from titles
where title in ('Staff', 'Senior Staff');
```

Iskanje z vzorcem, primer ko izpišemo vse, ki se pišejo na 'B' in so se rodili prvega v mesecu v šestdesetih letih:
```SQL
select * from employees
where last_name like 'B%' and birth_date like '__6_____01';
```

Iskanje z NULL vrednostjo v pogoju, primer ko izpišemo vse, ki nimajo podatka o datumu zaposlitve:
```SQL
select * from employees
where hire_date is null;
```

Sortiranje vrstic v izhodni relaciji, primer ko izpišemo vse sortirane po priimku naraščujoče (to ni treba eksplicitno zapisati) in datumu rojstva padajoče, važen je tudi vrstni red tega, po čem sortiram najprej.
```SQL
select emp_no, last_name, birth_date
from employees
order by last_name, birth_date desc;
```

ISO standard definira pet [[Agregatne operacije|agregarnih funkcij]].

<font color="#92cddc">Vse</font> operacije razen COUNT(\*) najprej <font color="#92cddc">odstranijo vrstice z NULL</font> vrednostjo v stolpcu, po kateremu agregiramo.

DISTINCT <font color="#92cddc">nima učinka</font> nad MIN/MAX, lahko pa vpliva na SUM/AVG.

V tem primeru, dobimo prvo številko zaposlenega in povprečje za vse skupaj, kar je nesmiseln rezultat.
```SQL
select emp_no, avg(salary)
from salaries;
```

Da bo to pravilno, moramo dodati:
```SQL
group by emp_no;
```

Pri združevanju so $NULL$ vrednosti tretirane kot enake.

Skupine pa lahko še dodatno omejimo z dodatnimi pogoji s $having$:

```SQL
group by YEAR(birth_date)
having count(*) > 9200;
```

Poizvedbe lahko tudi gnezdimo:

```SQL
select first_name, last_name
from employees
where emp_no in (
	select emp_no
	from titles
	where title = "manager"
);
```

Ta izpiše vse sedanje in pretekle "manager"-je.

Pravila gnezdenja SELECT stavkov:
- uporaba ORDER_BY je nesmiselna,
- select vgnezdenega stavka lahko zajema samo en atribut (razen v primeru EXISTS) - a se tega implementacije ne držijo
- imena stolpcev v vgnezdenem stavku se nanašajo na tabele iz vgnezdenega ali zunanjega stavka (uporaba aliasov)
- vgnezdeni SELECT stavek ne more biti operand v izrazu.

Uporaba ANY/SOME, ALL
- ekvivalenten $\exists, \forall$ kvantifikatorjema,
- če je rezultat poizvedbe prazen je ALL $true$ in ANY/SOME $false$.

Vrstni red razen `select` in `from` je;; <font color="#92cddc">poljuben</font>.
<!--SR:!2024-10-27,4,278-->

Poizvedbe po več tabelah:
- za ločevanje med istoimenskimi stolpci uporabljamo sinonime ozr. aliase

INSERT stavek:
```SQL
insert into TableName [(columnList)]
values (dataValueList)
```
- seznam columnList ni obvezen,
- pri vnosu moramo vpisati najmanj vse obvezne vrednosti, razen za stolpce s privzeto vrednostjo
npr. 
```SQL
insert into departments (dept_no, dept_name)
values('d010', 'Education');
```

UPDATE stavek:

DELETE stavek:
```SQL
delete from TableName [WHERE searchCondition]
```
npr. brisanje podatkov o plačah delavcev, ki niso več zaposleni
```SQL
delete from salaries
where emp_no not in (
	select emp_no
	from salaraies
	where to_date = '9999-01-01'
);
```

Brisanje je zelo počasna operacija. Lahko uporabimo Drop in Truncate, a sta rahlo drugačni.
## Stične operacije

- kartezični produkt 
``` SQL
select *
from t1, t2;
```
- naravni stik 
``` SQL
select *
from t1 natural join t2;
```
- ekvistik 
``` SQL
select *
from t1, t2
where t1.A = t2.A;
```
- pogojni stik
``` SQL
select *
from t1, t2;
where t1.A >= t2.B;
```
- odprti stik
``` SQL
select *
from t1 left [outer] join t2 on t1.A >= t2.B;
```

### Operacije množic in deljenje

- unija	
```SQL
select *
from t1
union distinct
select *
from t2
```
- presek
```SQL
select *
from t1
intersect
select *
from t2

ali 

select *
from t1
where t1.A IN 
	(select t2.A from t2);
```
- razlika
```SQL
select *
from t1
MINUS
select *
from t2

ali 

select *
from t1
where t1.A NOT IN (select t2.A from t2);
```
- operatorji	
```SQL
where [NOT] exists ... neprazna tabela
where A IN ... vsebovanost
where A >= ALL ... največja vrednost
where A > ANY ... ne najmanjša vrednost
```

---

Na kaj se deli SQL sintaksa?;; Na ukaze iz skupine DML (manipulation), DDL (definition) in sprožilce, funkcije in shranjene programe
<!--SR:!2024-10-30,11,270-->
V bazi "employees" kako bi (z SQL) izpisal vse podatke o zaposlen?;; select * from employees
<!--SR:!2024-11-03,15,290-->
V bazi "employees" kako bi (z SQL) izpisal vse različne vrednosti nečesa?;; z distinct
<!--SR:!2024-11-03,15,290-->
Iskalni kriterij v SQL?;; where YEAR(birth_date)<1953 and gender = 'M'
<!--SR:!2024-10-25,6,250-->
Iskalni kriterij s pogojem?;; where last_name like 'B%' and birth_date like '__6_____01'
<!--SR:!2024-10-27,8,250-->
S katero besedo še dodatno postavimo pogoje na neko skupino?;; S $having$.


---

