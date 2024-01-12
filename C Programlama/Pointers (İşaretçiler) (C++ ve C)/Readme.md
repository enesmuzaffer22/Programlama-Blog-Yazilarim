
C ve C++ programlama dillerinde işaretçiler, diğer değişkenlerin bellek adreslerini saklayan değişkenlerdir.

## Değişken Adreslerini Yazdırma

Değişkenin bellekteki adresini yazdırmak için değişkenin başına “&” işareti koyulur. Örneğin:

```cpp
int degiskenAdi;

cout << &degiskenAdi; //C++
printf("%d", &degiskenAdi); //C 
```

## Pointer (İşaretçi) Tanımlama

Pointer ifadeleri (işaretçiler) tanımlanırken değişkenin başına “*” işareti koyulur. Örneğin:

```cpp
int *degiskenAdi;
```

Pointer ifadelerinin (işaretçilerin) bellekteki adresleri depolamak için kullanıldığını yukarıda bahsetmiştik. Bu işlemi daha iyi anlamamız için aşağıdaki gibi bir örnek yazabiliriz:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a = 5;
	int *pointer; //pointer ifadesinin tanimlanmasi
	
	pointer = &a; //pointer degiskenine a degiskeninin adresini atadik
	
	cout << "a degiskenin adresi: " << pointer << endl;
	cout << "a degiskenin adresinde depolanan deger: " << *pointer << endl;
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 0x70fe04
a degiskenin adresinde depolanan deger: 5

```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a = 5;
	int *pointer; //pointer ifadesinin tanimlanmasi
	
	pointer = &a; //pointer degiskenine a degiskeninin adresini atadik
	
	printf("a degiskenin adresi: %d \n", pointer);
	printf("a degiskenin adresinde depolanan deger: %d \n", *pointer);	
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 6487572
a degiskenin adresinde depolanan deger: 5
```

İkinci çıktıda pointer değişkeninin başına “*” işareti koyarak a değişkeninin adresinde depolanan değeri yazdırdık.

## Pointer İfadelerinin (İşaretçilerin) Depoladığı Değeri Değiştirme

Bir önceki örnekte başına “*” işareti koyulan ifadenin adresteki değeri yazdırdığından bahsetmiştik. Şimdiki örnekte ise bu değeri değiştireceğiz:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a = 5;
	int *pointer;
	
	pointer = &a;
	
	cout << "a degiskenin adresi: " << pointer << endl;
	cout << "a degiskenin adresinde depolanan deger: " << *pointer << endl;
	
	*pointer = 7; //adreste depolanan degeri degistirdik
	
	cout << "a degiskenin adresinde depolanan deger: " << *pointer << endl;
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 0x70fe04
a degiskenin adresinde depolanan deger: 5
a degiskenin adresinde depolanan deger: 7
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a = 5;
	int *pointer; //pointer ifadesinin tanimlanmasi
	
	pointer = &a; //pointer degiskenine a degiskeninin adresini atadik
	
	printf("a degiskenin adresi: %d \n", pointer);
	printf("a degiskenin adresinde depolanan deger: %d \n", *pointer);
	
        *pointer = 7;

        printf("a degiskenin adresinde depolanan deger: %d \n", *pointer);
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 6487572
a degiskenin adresinde depolanan deger: 5
a degiskenin adresinde depolanan deger: 7
```

## Pointers (İşaretçiler) Diziler ile İşlemler

Diziler tanımlandıkları zaman boyutları kadar bellekte kendilerine yer ayrılır. Bu adreslerde işlem yapmak için yine pointer ifadelerinden (işaretçilerden) faydalanırız.

Basit bir örnek ile konuya adım atalım:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = a; /* isaretcilerde dizi atamalarinda belli bir indeks
belirtilmedigi surece "&" isareti kullanilmaz */
	
	cout << "a dizisinin baslangic adresi: " << pointer << endl;
	cout << "a dizisinin ilk indeks adresinde depolanan deger: " << *pointer << endl;
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = a; /* isaretcilerde dizi atamalarinda belli bir indeks
belirtilmedigi surece "&" isareti kullanilmaz */
	
	printf("a dizisinin baslangic adresi: %d \n", pointer);
	printf("a dizisinin ilk indeks adresinde depolanan deger: %d \n", *pointer);
	
	return 0;
}
```

Yukarıdaki örnekte pointer ifadesine “a dizisini (a dizisinde herhangi bir elemanı değil) ” tanımladık. Tanımlarken “&” işareti kullanmadık. Bunun nedeni ise doğrudan işaretçiye diziyi tanımladık. Bunun sonucunda ilk çıktıda dizinin bellekte kendisine ayrılan bölümünün başladığı adresini yazdırdık. İkinci çıktıda ise dizinin ilk indeksinin değeri yani dizinin bellekte kendisine ayrılan bölümünün başladığı adresin depoladığı değeri yazdırdık.

Dizinin belirli bir indeksinin adresini çıktı olarak aşağıdaki gibi verebiliriz:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = &a[2]; /* isaretcilerde dizi atamalarinda belli bir indeks
belirtilmedigi surece "&" isareti kullanilmaz */
	
	cout << "a dizisinin ikinci indeksinin adresi: " << pointer << endl;
	cout << "a dizisinin ikinci indeks adresinde depolanan deger: " << *pointer << endl;
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 0x70fdf8
a dizisinin ikinci indeks adresinde depolanan deger: 7
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = &a[2]; /* isaretcilerde dizi atamalarinda belli bir indeks
belirtilmedigi surece "&" isareti kullanilmaz */
	
	printf("a dizisinin ikinci indeksinin adresi: %d \n", pointer);
	printf("a dizisinin ikinci indeks adresinde depolanan deger: %d \n", *pointer);
	
	return 0;
}
```

Programın çıktısı:

```cpp
a dizisinin ikinci indeksinin adresi: 6487560
a dizisinin ikinci indeks adresinde depolanan deger: 7
```

Başka bir yol ise:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = a;
	
	cout << "a dizisinin ikinci indeksinin adresi: " << pointer + 2 << endl;
	cout << "a dizisinin ikinci indeks adresinde depolanan deger: " << *(pointer + 2) << endl;
	
	return 0;
}
```

Programın çıktısı:

```cpp
a degiskenin adresi: 0x70fdf8
a dizisinin ikinci indeks adresinde depolanan deger: 7
```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[4] = {3, 5, 7, 10};
	int *pointer;
	
	pointer = a;
	
	printf("a dizisinin ikinci indeksinin adresi: %d \n", pointer + 2);
	printf("a dizisinin ikinci indeks adresinde depolanan deger: %d \n", *(pointer + 2));
	
	return 0;
}
```

Programın çıktısı:

```cpp
a dizisinin ikinci indeksinin adresi: 6487560
a dizisinin ikinci indeks adresinde depolanan deger: 7
```

## Pointer (İşaretçi) Dizileri

Pointer ifadeleri (işaretçiler) diziler gibi kullanılabilir. Örneğin:

```cpp
//C++

#include <iostream>
using namespace std;

int main() {
	
	int a[4] = {3, 5, 7, 10}, i;
	int *pointer[4];
	
	for(i = 0; i < 4; i++) {
		
		pointer[i] = &a[i]; /* isaretci dizisine a dizisinin
indekslerinin adreslerini atadik */
		
	}
	
	for(i = 0; i < 4; i++) {
		
		cout << *pointer[i] << endl; /* atadigimiz adreslerin 
degerlerini ekrana yazdirdik */
		
	}
	
	return 0;
}
```

Programın çıktısı:

```cpp
3
5
7
10

```

```cpp
//C

#include <stdio.h>

int main() {
	
	int a[4] = {3, 5, 7, 10}, i;
	int *pointer[4];
	
	for(i = 0; i < 4; i++) {
		
		pointer[i] = &a[i]; /* isaretci dizisine a dizisinin
indekslerinin adreslerini atadik */
		
	}
	
	for(i = 0; i < 4; i++) {
		
		printf("%d", *pointer[i]); /* atadigimiz adreslerin 
degerlerini ekrana yazdirdik */
		
	}
	
	return 0;
}
```

Programın çıktısı:

```cpp
3
5
7
10
```
