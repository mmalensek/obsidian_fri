ali dvojiška kopica
[[Abstraktni podatkovni tipi]]; #aps1-flashcards 

- poravnano dvojiško drevo
- $\forall (vozlišče \leq otrok)$ 

![[Pasted image 20241018141842.png|inv]]

- višina je $O(\log n)$, prostorska zahtevnost je $O(n)$, časovna pa $O(n\log n)$

- kako bi naredil pri min heap npr. push(35)? dodamo na prvo prazno mesto ozr. nov list na dnu (kjer paziš na poravnanost), in tja vpisal 35 in bi delal zamenjaval s starši, dokler ne bi bilo pravilno poravnano

- kako bi naredil pri min heap pop()? Zamenjaš koren in najnižji (najbolj desni (zaradi poravnanosti)) list in nato menjavaš zamenjani list, dokler ni spet poravnano.

- <font color="#92cddc">implementacija</font>: lahko preprosto v array-u, kjer so relacije implicitne $$[10, 15, 30, 40, 50, 100, 40]$$
- starš od vozlišča $x$ je $\frac{x}{2}$
- levi in desni otrok od $x$ pa je $2x$ in $2x + 1$


```c++
class BinaryHeap{
	private: 
		vector<int> t={-1};
	public:
		void push(int x){
			t.push_back(x);
			int i = t.size() - 1;
			while(i > 1 && t[i] < t[i/2]){
				i /= 2;
			}
		}
		int pop(){
		int x = t[1], i = 1;
		t[1] = t.back();
		t.pop_back();
		while(1){
			int j = i;
			if(2*i<t.size() && t[2*i] < t[j]) j = 2*i;
			if(2*i<t.size() && t[2*i+1] < t[j]) j = 2*i+1;
			if(i == j) break;
			swap(t[i], t[j]);
			i = j;
			}
		}
}
```
