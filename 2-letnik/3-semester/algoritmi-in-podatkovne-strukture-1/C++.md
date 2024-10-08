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
Za prevajanje se uporablja;; g++.
Za input output?;; cin in cout


```c++
int main(){
	string ime, priimek;
	cin >> ime >> priimek;
	cout << "Pozdravljen, " << priimek;
}

```
Stringe lahko seštevaš!
	Katero operacijo nad stringi omogoča c++?;; Seštevanje.


```c++
#include <utility>
pair<int, int> koordinata1;
koordinata1 = make_pair(2, 3);
cout << koordinata1.first << " " << kordinata1_second << endl;
```
Nov tip "pair"?;; par dveh (lahko različnih) nekih vrednosti.


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
	Tip lahko določamo tudi kako??; auto


```c++
vector<int> v;
for(int i = 0; i < 1024; i*=2){
	v.push_back(i); // add
}
for(int i = 0; i < v.size(); i++){
	cout << v[i] << endl;
}
```
Sezname nam reši "vector" - podobno ArrayList
	namesto ArrayList imamo?;; vector


```c++
for(auto it=v.begin()); it!=v.end(); it++){
	cout << *it << endl;
}
```
Iterator od začetka


```c++
for(int x : v){
	cout << x << endl;
}
```
Iterator "for-each"


```c++
vector<pair<int,int>> koord = {{2,3}, {-4,7}, {1,1}};
for(auto [x, y] : koord){
	cout << x << " " << y << endl;
}
```
"Razpakiranje"


```c++
map<string, int> vpisna = {{"Ana",123}, {"Miha",456}, {"Martin", 789}};
vpisna["Teja"] = 321;
cout << vpisna["Miha"] << endl;
```
Map


```c++
int x = 12;
int y = x;
x = 3;
cout << x << " " << y << endl;
// zaenkrat normalno delovanje, lahko pa
int z = 10;
int w = &z;
int z = 999;
cout << z << " " << w << endl;
// sedaj sta in w in z == 999, to je uporabno pri seznamih
```
Reference


```c++
#include <algorithm>
int main(){
	vector<int> a = {9,3,2,4};
	cout << *min_element(a.begin(), a.end()) << endl;
}
```
Knjižnica Algorithm (* zvezdica je, ker min_element vrača komparator)


```c++
sort(a.begin(), a.end(), [](int x, int y){return x < y;}); 
//                       ^ vstavi zunanjo spremenljivko
// sortiraj poljubno strukturo, tudi z anonimno funkcijo
```
funkcija Sort

---

#aps1-flashcards 

---
