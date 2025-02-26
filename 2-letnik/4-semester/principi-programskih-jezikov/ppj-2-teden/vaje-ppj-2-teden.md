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

## Odstranjevanje mrtve kode

to je del kode, za katero zagotovo vemo, da se nikoli ne bo izvedel.


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

