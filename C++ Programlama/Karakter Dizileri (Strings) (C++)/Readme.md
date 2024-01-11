
Önceki yazılarımda C Programlama dilinde string veri tipinin olmadığını ve bu tür veri tiplerini oluşturmak için dizileri kullanmamız gerektiğinden bahsetmiştik. C++ Programlama dilinde ise “string” veri tipi vardır ve kullanımı da oldukça kolaydır.

## String Veri Tipi Tanımlama

String veri tipini kullanabilmemiz için öncelikle “**string**” kütüphanesini tanımlamamız gerekir. Sonrasında dilediğimiz gibi kullanabiliriz.

```cpp
#include <iostream>
#include <string> // "string" kutuphanesinin cagirilmasi
using namespace std;

int main() {
   
   string stringOrnegi = "deneme"; 

   cout << stringOrnegi; // ekrana "stringOrnegi" degiskeninin degeri yazilir

   return 0;
}
```

## Karakter Dizilerini Birleştirme

Karakter dizilerini birleştirmek için string degişkenlerini **birbirleri ile toplarız**:

```cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
	
	string str1 = "hello";
	string str2 = "world";
	
	string str3 = str1 + str2;
	string str4 = str1 + " " + str2;
	
	cout << str3 << endl;  //alt satira gecmek icin "endl" ifadesi de kullanilabilir

	cout << str4; 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
helloworld

hello world
```

Karakter dizilerini birleştirmenin bir diğer yolu ise “**append()**” fonksiyonudur:

```cpp
#include <iostream>
#include <string> 
using namespace std;

int main() {
	
	string str1 = "hello ";
	string str2 = "world";
	
	string str3 = str1.append(str2); //str1 degiskenine str2 degiskenini ekledik
	
	cout << str3; 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
hello world
```

## Karakter Dizisinin Uzunluğu

Karakter dizisinin uzunluğunu öğrenmek için “**length()**” fonksiyonunu kullanırız:

```cpp
#include <iostream>
#include <string> 
using namespace std;

int main() {
	
	string str1 = "deneme";
	
	cout << "str1 degiskeninin uzunlugu: " << str1.length(); 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
str1 degiskeninin uzunlugu: 6
```

Not: **Önceki C Programlama yazılarımızda string veri tipi oluşturabilmek için dizilerden yararlanmıştık ve dizilerle işlem yapmıştık. Aynı işlemleri C++ Programlamada da yapabilirsiniz.**

## Kullanıcıdan Karakter Dizisi Alma

Kullanıcıdan karakter dizisi almak için “**cin**” fonksiyonu kullanılabilir fakat bu fonksiyonu kullandığınızda cümle gibi içinde boşluk bulunduran ifadeler kullanırsanız sadece boşluğa kadar olan kısım değişkene atanır. Örneğin:

```cpp
#include <iostream>
#include <string> 
using namespace std;

int main() {
	
	string str1;
	
	cout << "karakter dizisi giriniz: ";
	cin >> str1; // hello world yazildigini varsayalim
	
	cout << str1; 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
karakter dizisi giriniz: hello world
hello
```

Bu problemin çözümü ise “**getline()**” fonksiyonudur:

```cpp
#include <iostream>
#include <string> 
using namespace std;

int main() {
	
	string str1;
	
	cout << "karakter dizisi giriniz: ";
	getline(cin, str1); // hello world yazildigini varsayalim
	
	cout << str1; 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
karakter dizisi giriniz: hello world
hello world
```

## Sınırlı Sayıda Karakterler İle String Girdisi Alma

```cpp
#include <iostream>
#include <string> 
using namespace std;

int main() {
	
	char str1[50]; //50 karakter ile sinirli
	
	cout << "karakter dizisi giriniz: ";
	cin.getline(str1, 50); // 50 karakter siniri ile girdi alma
	
	cout << str1; 
	
	return 0;
}
```
