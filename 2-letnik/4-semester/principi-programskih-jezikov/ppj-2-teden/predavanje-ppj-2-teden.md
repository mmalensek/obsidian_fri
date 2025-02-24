### Ukazni programski jezik
Jezik:
- cela števila +, $\times$, =, <
- boolovi izrazi: true, false, $\land$, ...
- if-then -else, while, spremenljivke

Razčlenjevanje izrazov npr. $7 + 5 * 8$, v tem primeru je to dvoumno:

```
⟨aritmetični-izraz⟩ ::=
  ⟨spremenljivka⟩ |
  ⟨številka⟩
  ⟨aritmetični-izraz⟩ + ⟨aritmetični-izraz⟩ |
  ⟨aritmetični-izraz⟩ * ⟨aritmetični-izraz⟩
```

Saj lahko dobimo $<stevilka>$ $+$  $<aritmeticni-izraz>$ in obratno $<aritmeticni-izraz> * <stevilka>$, zato določimo prioriteto (kateri ima prednost) in asociativnost operatorjev (ali je levo, desno ali nič, npr. $7 - 5 - 8$, lahko najprej izračunamo najprej 7 in 5, ali pa 5 in 8, kar predstavlja čisto drugačen rezultat).

Asociativnost:
levo* : a * b * c = (a * b) * c ; npr. $+, - , *$
desno* : a * b * c = a * (b * c) ; npr. potenciranje
nič* : ali ne pustimo brez oklepajev, ali dobimo dvoumnost ; npr. ekvivalenca

Wadlerjev zakon...

### Operacijska semantika aritmetičnih izrazov

```
—————————-
η | n ↪ n


 η(x) = n
————————––
η | x ↪ n

η | e₁ ↪ n₁     η | e₂ ↪ n₂
———————————————————————–———
 η | e₁ + e₂ ↪ n₁ + n₂
.
.
.
```

### in še boolovih izrazov

npr. 
```
     η | b₁ ↪ false
———————————-–—————————–
 η | b₁ and b₂ ↪ false
 .
 .
 .
```

Kjer je to napisano kratkostično (tako kot npr. v javi), kjer se ne izračuna vrednost $b_2$, to predstavlja manj računanja, je pa to dobro v primeru...

```java
if(i < a.length && a[i] > 0) {...}
```

kjer želiš, da se preverita oba pogoja.

### Operacijska semantika ukazov
...

### Denotacijska semantika
(matematični pomen programov)

### Ekvivalenca programov
Programa sta ekvivalentna, če se v vseh kontekstih obnašata enako, vedno lahko enega zamenjamo z drugim.

Del programske kode, ki ga primerjamo je $evalvacijski \ kontekst$. 

npr. 

```
i := 1 ;
s := 0 ;
while i < 101 do
  s := s + i ;
  i := i + 1
done
```

in

```
s := 5050
```

nista ekvivalentna, saj v drugem primeru, ne postavimo $i = 101$.

### Prevajalnik
...