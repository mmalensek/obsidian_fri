### Ali so programi ekvivalentni?
1. `a = a ^ b; b = a ^ b; a = a ^ b;`
    
2. `temp = a; a = b; b = a;`
    
3. `temp = b; b = a; a = temp;`
    
4. `a = a + b; b = a - b; a = a - b;`
    
5. `x[i] = x[i] ^ x[j]; x[j] = x[i] ^ x[j]; x[i] = x[i] ^ x[j];`
    
6. `temp = x[i]; x[i] = x[j]; x[j] = x[i];`
    
7. `temp = x[j]; x[j] = x[i]; x[i] = temp;`
    
8. `x[i] = x[i] + x[j]; x[j] = x[i] - x[j]; x[i] = x[i] - x[j];`
    
9. `if (i != j) { x[i] = x[i] ^ x[j]; x[j] = x[j] ^ x[i]; x[i] = x[i] ^ x[j]; }`

![[vaje-ppj-2-teden 2025-02-26 09.24.08.excalidraw]]

Za vsako celo število `X`, poišči okolje v katerem sta naslednja programa ekvivalentna?

1.
```java
while(i > 1){
	if(i * i + 26 == 15 * i){
		break;
	}
	i = i + 1;
}
```

2.

```java
i = X
```

![[vaje-ppj-2-teden 2025-02-26 09.59.03.excalidraw]]

### Pretvorba zanke `for` v zanko `while`

```java
for(A; P; C){
	B;
}
```

spremenimo v:


```java
while(P){
	B;
	C;
}
```

### Pretvorba zanke `do` v zanko `while`

```java
do {
	A;
} while(P);
```

spremenimo v:

```java
A;
while(P){
	A;
}
```

### Odstranjevanje mrtve kode

to je del kode, za katero zagotovo vemo, da se nikoli ne bo izvedel.

Prvi primer:

```java
print("Kdor to bere je "); 
a = 3; 
if (a * a < 10) { 
	print("mula"); 
} else { 
	print("osel"); 
}
```

spremenimo v: 

```java
print("Kdor to bere je ");
a = 3;
print("mula");
```

Drugi primer:

```java
k = n + (n - 1); 
if (k % 2 == 0) { 
	print("foo"); 
} else { 
	print("bar"); 
	} 
m = k * (-k); 
while (m > 0) { 
	m = m - 1; 
	print(m); 
}
```

Kaj se lahko zgodi pri $k$? Overflow ali kaj podobnega, imamo dve opciji za $k$, ta je lahko $2n -1$ ali $2n - 1 - 2^{64}$, a je least significant bit, v obeh primerih enak $1$, zato se vedno izvede `print("bar")` .

Ali je `while(m > 0)` mrtva koda? $m = -4n^2 + 4n - 1$, a v registru se bo gledal le prvi bit (predznak: $0; x = 0$ ali $1, x < 2^{63}$ ali $-1 ...$?), tako da ne smemo tega odstraniti.

### Odstranjevanje ukaza `break`

Prvi primer:
```java
while (n > 0) { 
	digit = n % 10; 
	if (digit == 7) { 
		print(n + " vsebuje števko 7"); 
		break; 
	} else { } 
	n = n / 10; 
}
```

spremenimo v:

```java
stop = false;
while (n > 0 && !stop) { 
	digit = n % 10; 
	if (digit == 7) { 
		print(n + " vsebuje števko 7"); 
		stop = true;
	} else { } 
	if(!stop){
		n = n / 10; 
	}
}
```

Kar lahko nekateri jeziki delajo avtomatsko, da zamenjajo med compilanjem breake s pogoji.