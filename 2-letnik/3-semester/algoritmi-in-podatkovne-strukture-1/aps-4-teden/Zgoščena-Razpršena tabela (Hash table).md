[[Abstraktni podatkovni tipi]]; #aps1-flashcards 

![[Pasted image 20241025135547.png|inv|450]]
$n$ - velikost, $H$ - kapaciteta, $\alpha = \frac{n}{H}$ - load factor

Ko postane $\alpha = 1$, se zgodi rehashing, proces, ko povečam tabelo in spremenim hash vsem.

Get - v primeru neobstoječega elementa in obstoječega je $O(\alpha)$, če pa z rehashingom obdržiš $\alpha$ vedno pod neko konstanto je lahko $O(1)$.

Prostor - $O(n)$

Implementacija v c++. 

```C++
class HashTable {
	public:
		vector<list<pair<int, int>>> t;
		int capacity, currentSize;
		int hash(int x){
			return x % capacity;
		}
		HashTable() {
			currentSize = 0;
			capacity = 1;
			t.resize(capacity);
		}

		void rehash(){
			capacity *= 2;
			vector <list<pari<int, int>>> t2(capacity);
			for(int h = 0; h < t.size(); h++){
				for(auto [key, value] : t[h]){
					int h2 = hash(key)
					t2[h2].push_back({key, value});
				}
			}
			t = t2;
		}

		void insert(int k, int v){
			if(currentSize == capacity){
				rehash(); // alfa je == 1
			}
			int h = hash(k);
			for(auto& [key, value] : t[h]){
				if(k == key) {
					value = v;
					return;
				}
			}
		}

		void get(int k){
			int h = hash(k);
			for(auto& [key, value] : t[h]){
				if(k == key){
					return value;
				}
			}
			return -1;
		}
};
```
