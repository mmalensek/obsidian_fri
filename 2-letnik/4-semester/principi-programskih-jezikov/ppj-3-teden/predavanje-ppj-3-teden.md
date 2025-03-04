### Specifikacija 
Opis tega, kaj naj program počne.

### in implementacija
Dejanski program.

Matematično bomo dokazovali, da stvari na mikro nivoju delujejo pravilno, npr. pravilnost while zanke, ...

### Hoarova logika
$\{P\}c\{Q\}$ - pomeni če velja $P$ in se izvede ukaz $c$, potem bo veljal $Q$. $P$ je predpogoj, $Q$ pa 

npr. če je $m = 2$ in $n = 3$, dobimo 

```
{ x = m AND y = n }
y := x + y;
x := y - x;
x := y - x;
{ x = n AND y = m}
```

Pravila sklepanja:
$FV$ - free variables, vse spremenljivke ki nastopajo
$FA$ - free asigned, vse tiste, ki se *lahko* spremenijo.

Aliasing problem:

```c
{ x < 10 }
*p = 15;
{ x < 10 }
```

Ni nujno da drži, ker kaj če $p$ kaže ravno na $x$.

