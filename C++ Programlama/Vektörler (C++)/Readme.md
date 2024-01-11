
Vektörler, benzer veri tipindeki değerleri depolamak için kullanılır. Bu yönüyle vektörler dizilere benzer. Vektörleri dizilerden ayıran en önemli fark vektörlerin **dinamik** olmasıdır. Yani vektörlerin boyutunu gereksinimlerimize göre değiştirebiliriz.

## Vektörlerin Tanımlanma Şekilleri

Vektörleri tanımlamak için önce “**vector**” kütüphanesini tanımlamamız gerekir.

```cpp
#include <vector>
```

Vektörler dört farklı şekilde tanımlanabilir.

```cpp
vector<veriTipi> vektorAdi; // 1

vector<int> v1; // ornek
```

```cpp
vector<veriTipi> vektorAdi = {deger1, deger2, deger3, ...}; // 2

vector<int> v2 = {1, 2, 3, 4, 5}; // ornek
```

```cpp
vector<veriTipi> vektorAdi {deger1, deger2, deger3, ...}; // 3

vector<int> v3 {1, 2, 3, 4, 5}; // ornek
```

```cpp
vector<veriTipi> vektorAdi(adet, deger); // 4

vector<int> v4(4, 3); // ornek

/* 

bu tanimlama seklinde vektore 4 tane 3 degeri atanir
vector<int> v4 = {3, 3, 3, 3}; ile vector<int> v4(4, 3) ayni
seydir. 

*/
```

## size() ve at() Fonksiyonları

Vektör dizisinin elemanlarıyla işlem yapmak için öncelikle iki tane fonksiyonu öğrenmemiz gerekir:

**at() ve size()**

**at() Fonksiyonu**

at() fonksiyonunu vektör dizisinde belirli bir indeksteki değerine erişmek için kullanırız. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	cout << v1.at(2);

	return 0;
}
```

Bu örnekte vektör dizisinin ikinci indeksteki değerini ekrana çıktı olarak verdik.

Ekrana verilen çıktı:

```cpp
3
```

at() fonksiyonunu vektör dizisinde belirli bir indeksteki değeri değiştirmek için kullanabiliriz. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	// degeri degistirmeden once
	cout << v1.at(3) << endl;

	v1.at(3) = 10;

	// degeri degistirdikten sonra
	cout << v1.at(3) << endl;

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
4
10
```

**size() Fonksiyonu**

size() fonksiyonunu vektör dizisinin boyutu ile işlem yapmak için kullanırız. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	cout << v1.size();

	return 0;
}
```

Bu örneğimizde dizinin boyutunu ekrana çıktı olarak verdik.

Ekrana verilen çıktı:

```cpp
5
```

**Bütün Vektör Dizisinin Elemanlarını Ekrana Çıktı Olarak Verme**

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	int i;

	for (i = 0; i < v1.size(); i++) {

		cout << v1.at(i) << " ";

	}

	return 0;
}
```

Bu kısımda vektör dizisinin bütün elemanlarını ekrana çıktı olarak verdik.

Ekrana verilen çıktı:

```cpp
1 2 3 4 5
```

## Vektör Dizisine Değer Ekleme

**push_back() Fonksiyonu**

push_back() fonksiyonu vektör dizisinin sonuna değer eklemek için kullanılır. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	int i;

	// fonksiyonu kullanmadan once
	for (i = 0; i < v1.size(); i++) {

		cout << v1.at(i) << " ";

	}

	v1.push_back(6);
	v1.push_back(7);

	cout << endl;

	// fonksiyonu kullandiktan sonra
	for (i = 0; i < v1.size(); i++) {

		cout << v1.at(i) << " ";

	}

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
1 2 3 4 5
1 2 3 4 5 6 7
```

## Vektör Dizisinden Değer Çıkarma

**pop_back() Fonksiyonu**

pop_back() fonksiyonu vektör dizisinin sonundan bir değer çıkarmak için kullanılır. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };

	int i;

	// fonksiyonu kullanmadan once
	for (i = 0; i < v1.size(); i++) {

		cout << v1.at(i) << " ";

	}

	v1.pop_back();
	v1.pop_back();

	cout << endl;

	// fonksiyonu kullandiktan sonra
	for (i = 0; i < v1.size(); i++) {

		cout << v1.at(i) << " ";

	}

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
1 2 3 4 5
1 2 3
```

## Yineleyiciler (Iterators)

Yineleyiciler **işaretçiler** gibi çalışır. Vektör dizisinin bir değerini işaret etmek için kullanılır.

**Yineleyicilerin Tanımlanması**

```cpp
vector<veriTipi>::iterator isaretciAdi;

vector<int>::iterator iter1; // ornek
```

**Yineleyiciler ile İşlem Yapma**

Önceki yazılarımızdan da hatırlayabileceğiniz gibi işaretçilerin kullanılabilmesi için işaretçiye bir adres atanması gerekiyordu. Bu koşul yineleyiciler için de vardır. Bu koşulu yerine getirmemiz için iki tane fonksiyon öğrenmemiz gerekir:

**begin() ve end()**

**begin() Fonksiyonu**

begin() fonksiyonu vektör dizisinin ilk indeksteki adresini döndürmeyi sağlar. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };
	vector<int>::iterator iter1;

	iter1 = v1.begin(); /* iter1 e vektor dizisinin ilk indeksinin
	adresini atadik */

	cout << *iter1;

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
1
```

**end() Fonksiyonu**

end() fonksiyonu vektör dizisinin son indeksten sonra gelen **teorik elemanın adresini** döndürmeyi sağlar. Bu nedenle vektör dizisinin son indeksinin adresini döndürmek istiyorsak “**end() – 1**” şeklinde kullanım yapmamız gerekir. Örneğin:

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };
	vector<int>::iterator iter1;

	iter1 = v1.end() - 1; /* iter1 e vektor dizisinin son indeksinin
	adresini atadik */

	cout << *iter1;

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
5
```

**Yineleyiciler İçin Örnek**

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };
	vector<int>::iterator iter1;
	vector<int>::iterator iter2;

	iter1 = v1.end() - 1; /* iter1 e vektor dizisinin son indeksinin
	adresini atadik */

	iter2 = v1.begin(); /* iter1 e vektor dizisinin ilk indeksinin
	adresini atadik */

	cout << *iter1 << endl; // 4. indeks
	cout << *(iter2 + 1) << endl; // 1. indeks
	cout << *(iter1 - 1) << endl; // 3. indeks

	return 0;
}
```

Ekrana verilen çıktı:

```cpp
5
2
4

```

## Yineleyicileri Kullanarak Vektör Dizisini Ekrana Çıktı Olarak Verme

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {

	vector<int> v1 = { 1, 2, 3, 4, 5 };
	vector<int>::iterator iter;

	for (iter = v1.begin(); iter != v1.end(); iter++) {

		cout << *iter << " ";
	
	}

	return 0;
}
```
