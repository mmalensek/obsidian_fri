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

Izpiši starost delavcev ob zaposlitvi (izračunana polja in funkcije):

```SQL
select first_name, last_name, birth_date, hite_date, DATEDIFF(hire_date, birth_date)/365
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

---

Na kaj se deli SQL sintaksa?;; Na ukaze iz skupine DML (manipulation), DDL (definition) in sprožilce, funkcije in shranjene programe

---

