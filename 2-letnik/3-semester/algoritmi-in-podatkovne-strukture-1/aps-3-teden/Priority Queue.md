ali prioritetna vrsta
[[Abstraktni podatkovni tipi]]; #aps1-flashcards 

- hranimo neko zaporedje elementov, kjer ma vsak element neko svojo prioriteto.
- v c++, višja je številka, večja je pomembnost.

- implementacija: 
	1) najlažje kot seznam parov, a velja, da je push $O(1)$ in pop $O(n)$
	2) kot urejen seznam, velja, da je push $O(n)$ in pop $O(1)$

![[Pasted image 20241018135134.png|inv]]

- push(x, p) - element x in prioriteta p, lahko tudi implicitno
- pop()