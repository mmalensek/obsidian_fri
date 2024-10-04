[[aps1]];


```c++
//#include <stdio.h>
#include <iostram>
using namespace std;

int main(){
	int a,b;
	scanf("%d %d", &a, &b);
	printf("%d\n", a+b); // scanf / printf malenkost hitrejša, samo ni razlike
	cout << "Zivjo!\n"; // izpis, lahko tudi ločiš in uporabiš različne tipe

	cin >> a >> b;
	cout << "vsota = " << a+b << endl; // endl naredi flush - praznenje medpomnilnika
		   
	return 0;
}
```
Za prevajanje se uporablja g++.


```c++
int main(){
	string ime, priimek;
	cin >> ime >> priimek;
	cout << "Pozdravljen, " << priimek;
}

```
Stringe lahko seštevaš!


```c++
#include <utility>
pair<int, int> koordinata1;
koordinata1 = make_pair(2, 3);
cout << koordinata1.first << " " << kordinata1_second << endl;
```
Nov tip "pair", par dveh (lahko različnih) nekih vrednosti.


```c++
array<int, 3> a = {1, 2, 3};
```
(Možna) inicializacija arraya.


```c++
pair<pair<string, string>, int> ocena = {{"Janez", "Novak"}, 10};
auto ocena2 = ocena;
cout << ocena.first.first << endl;
```
Auto določitev tipa.

---

#aps1-flashcards 

---
