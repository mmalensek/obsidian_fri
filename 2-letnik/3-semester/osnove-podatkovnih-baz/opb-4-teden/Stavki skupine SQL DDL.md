[[predavanje-opb-4-teden]]; #opb-flashcards 

Imamo različne podatkovne tipe:
- boolean
- character
- bit
- ekzaktne numerične: decimal, integer, smallint, ...
- neekzaktne numerične: float, ...
- datetime: date, time, timestamp
- interval
- large objects: character large object, binary large object

SQL standard ponuja več vrst omejitev, ki so lahko definirane v CREATE in ALTER TABLE stavkih.

npr. obveznost podatkov 
```SQL
emp_no numeric(5) not null
```
npr. omejitve domene
```SQL
gender char not null 
check (gender in ('M', 'F')) 
```

Kreiranje podatkovnih objektov:
- strežnik -> instance -> DB=Katalogi (shema je znotraj, čeprav je formalno ločena) -> Tabele

