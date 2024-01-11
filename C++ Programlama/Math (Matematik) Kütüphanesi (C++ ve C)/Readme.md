
Math (Matematik) kütüphanesi, içinde birçok matematiksel işlemleri yapmanıza olanak sağlayan fonksiyonları bulundurur. Bu fonksiyonları kullanabilmek için math (matematik) kütüphanesini tanımlamamız gerekir.

```cpp
#include <math.h> //C
#include <cmath>  //C++
```

## max() ve min() Fonksiyonları (C++)

max() ve min() fonksiyonları, iki sayı arasında karşılaştırma yapmayı sağlayan fonksiyonlardır. Basit bir örnek ile konuyu anlamaya çalışalım:

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
	
	int a = 9, b = 7;
	
	cout << "buyuk sayi: " << max(a, b) << endl;
	cout << "kucuk sayi: " << min(a, b) << endl;
	
	return 0;
}
```

a ve b tam sayı değişkenleri tanımladık ve değerler atadık. Ekrana verilen ilk çıktıda a ve b arasında max() fonksiyonu karşılaştırma yaptı ve değeri büyük olan değişkeni ekrana yazdırdı. Benzer işlemi ikinci çıktıda da yaptık. a ve b arasında min() fonksiyonu karşılaştırma yaptı ve değeri küçük olan değişkeni ekrana yazdırdı.

## Bazı Önemli Fonksiyonlar (C++ ve C)

```cpp
//C++

#include <iostream>
#include <cmath>
using namespace std;

int main() {
	
	int a = 3, b = 4, c = 81, f = -21;
	float d = 5.56, e = 2.718281;
	
	cout << "#### C++ ####" << endl;
	
	cout << sqrt(c) << endl; /* sqrt() fonksiyonu parantez icindeki
	sayinin karekokunu alir */
	
	cout << pow(a, b) << endl; /* pow() fonksiyonu parantez icindeki
	ilk sayiyi taban, ikinci sayiyi da us kabul ederek tabanin ussunu hesaplar */
	
	cout << log(e) << endl; /* log() fonksiyonu parantez icindeki sayinin 
	logaritmasini hesaplar (tabani 'e'dir. yani dogal logaritma seklinde hesaplar)*/
	
	cout << round(d) << endl; /* round() fonksiyonu parantez icindeki sayiyi tam
	sayiya yuvarlar */
	
	cout << abs(f) << endl; /* abs() fonksiyonu parantez icindeki sayinin
	mutlak degerini alir */

	
	return 0;
}
```

```cpp
//C

#include <stdio.h>
#include <math.h>

int main() {
	
	int a = 3, b = 4, c = 81, f = -21;
	float d = 5.56, e = 2.718281;
	
	printf("#### C #### \n");
	
	printf("%f \n", sqrt(c)); /* sqrt() fonksiyonu parantez icindeki
	sayinin karekokunu alir */
	
	printf("%f \n", pow(a, b)); /* pow() fonksiyonu parantez icindeki
	ilk sayiyi taban, ikinci sayiyi da us kabul ederek tabanin ussunu hesaplar */
	
	printf("%f \n", log(e)); /* log() fonksiyonu parantez icindeki sayinin 
	logaritmasini hesaplar (tabani 'e'dir. yani dogal logaritma seklinde hesaplar)*/
	
	printf("%f \n", round(d)); /* round() fonksiyonu parantez icindeki sayiyi tam
	sayiya yuvarlar */
	
	printf("%d \n", abs(f)); /* abs() fonksiyonu parantez icindeki sayinin
	mutlak degerini alir */
	
	return 0;
}
```

Ekrana verilen çıktılar:

```cpp
#### C++ ####
9
81
1
6
21
1
```

```cpp
#### C ####
9.000000
81.000000
1.000000
6.000000
21
```

## İkinci Dereceden Bir Denklemin Köklerini Bulma

_ax2_ + _bx_ + _c_ = _0_ formatında ikinci dereceden bir denklemin köklerini bulmak için öncelikle Diskriminant Δ (delta) bulunur. Sonrasında ise aşağıdaki formüle göre kökler bulunur.

**Kök (x)=−b±√(b^2−4ac) / 2a**

**Diskriminant Δ (delta) : b^2−4ac**

```cpp
//C++

#include <iostream>
#include <cmath>
using namespace std;

int main() {

	float a, b, c, delta, kok1, kok2;

	cout << "##### IKINCI DERECEDEN BIR DENKLEMIN KOKLERINI BULMA #####" << endl;
	cout << endl;
	cout << "ax^2 + bx + c" << endl;
	cout << endl;
	cout << "yukaridaki formata gore degerleri giriniz." << endl;
	cout << "a: ";
	cin >> a;
	cout << "b: "; // kullanicidan denklemin katsayilari aliniyor 
	cin >> b;
	cout << "c: ";
	cin >> c;
	
	delta = pow(b, 2) - 4 * a * c; // delta formule gore hesaplaniyor
	
	if(delta >= 0) {
		
		cout << "denklemin iki tane koku vardir." << endl;

		kok1 = (-b + sqrt(delta)) / (2 * a); // kok1 formule gore hesaplaniyor 
		kok2 = (-b - sqrt(delta)) / (2 * a); // kok2 formule gore hesaplaniyor
		
		cout << "kok 1: " << kok1 << " | kok 2: " << kok2; /* kokler ekrana 
		yazdiriliyor */
		
	}
	
	else if(delta < 0) {
		
		cout << "denklemin reel sayilarda koku yoktur.";
		
	} 
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>
#include <math.h>

int main() {

	float a, b, c, delta, kok1, kok2;

	printf("##### IKINCI DERECEDEN BIR DENKLEMIN KOKLERINI BULMA ##### \n");
	printf("\n");
	printf("ax^2 + bx + c \n");
	printf("\n");
	printf("yukaridaki formata gore degerleri giriniz. \n");
	printf("a: ");
	scanf("%f", &a);
	printf("b: "); // kullanicidan denklemin katsayilari aliniyor 
	scanf("%f", &b);
	printf("c: ");
	scanf("%f", &c);
	
	delta = pow(b, 2) - 4 * a * c; // delta formule gore hesaplaniyor
	
	if(delta >= 0) {
		
		printf("denklemin iki tane koku vardir. \n");

		kok1 = (-b + sqrt(delta)) / (2 * a); // kok1 formule gore hesaplaniyor 
		kok2 = (-b - sqrt(delta)) / (2 * a); // kok2 formule gore hesaplaniyor
		
		printf("kok 1: %f | kok 2: %f", kok1, kok2); /* kokler ekrana 
		yazdiriliyor */
		
	}
	
	else if(delta < 0) {
		
		printf("denklemin reel sayilarda koku yoktur.");
		
	} 
	
	return 0;
}
```
