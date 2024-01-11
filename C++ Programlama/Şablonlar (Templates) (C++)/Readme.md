
Şablonlar, **tek bir fonksiyona farklı veri türlerinden parametreleri göndermeyi sağlayan bir yapıdır.** Örneğin, dizideki elemanları ekrana yazdıran bir fonksiyon hayal edin. Şablonları kullanmadan fonksiyona tam sayı dizileri, karakter dizileri ve float veri tipindeki dizilerini (vb. veri tipindeki diziler) aynı fonksiyona parametre olarak gönderemezdik. Çünkü aynı fonksiyona, **tanımlanmış veri türü dışında farklı veri türünde bir parametre gönderemeyiz.** Buna çözüm olarak **şablonları** kullanırız.

Bu örneği kodlar ile anlamaya çalışalım:

```cpp
#include <iostream>
using namespace std;

void print(int a[], int size) {
	
	int i;
	
	for(i = 0; i < size; i++) {
		
		cout << a[i] << " ";
		
	}
	
	cout << endl;
	
}

int main() {
	
	int tam_sayi[5] = {1, 2, 3, 4, 5};
	char karakter[5] = {'a', 'r', 'm', 'u', 't'};
	
	print(tam_sayi, 5);
	print(karakter, 5);
	
	return 0;
}
```

Bu kodlar derleme işleminde hata verir. Bunun nedeni, “**print()**” fonksiyonunda **tam sayı** veri türü bulunur; buna bağlı olarak **karakter veri türünde bir dizi “print()” fonksiyonuna gönderilemez** ve program başlatılamaz.

Bu sorunu çözmek için şablon kullanırız:

```cpp
#include <iostream>
using namespace std;

template<typename f_param>
void print(f_param a[], int size) {
	
	int i;
	
	for(i = 0; i < size; i++) {
		
		cout << a[i] << " ";
		
	}
	
	cout << endl;
	
}

int main() {
	
	int tam_sayi[5] = {1, 2, 3, 4, 5};
	char karakter[5] = {'a', 'r', 'm', 'u', 't'};
	
	print<int>(tam_sayi, 5);
	print<char>(karakter, 5);
	
	return 0;
}
```

Fonksiyonun üstünde “**f_param**” isminde bir şablon tanımladık. Bu şablonu fonksiyon içerisinde veri türleri **değişken (dinamik)** olan parametrenin önünde kullandık. Bunun sonucunda “**main()**” fonksiyonunda aynı fonksiyona farklı veri türlerindeki dizileri göndermiş olduk.

Ekrana verilen çıktı:

```cpp
1 2 3 4 5
a r m u t
```

## Birden Fazla Farklı Parametreler ile Şablon Kullanmak

Şablonları, **birden fazla farklı parametreler ile de kullanabilirsiniz**. Örneğin:

```cpp
#include <iostream>
using namespace std;

template<typename f_param1, typename f_param2>
void print(f_param1 a[], f_param2 b[], int size) {
	
	int i;
	
	for(i = 0; i < size; i++) {
		
		cout << a[i] << " ";
		
	}

	cout << endl;

	for(i = 0; i < size; i++) {
		
		cout << b[i] << " ";
		
	}
	
	cout << endl;
	
}

int main() {
	
	int tam_sayi[5] = {1, 2, 3, 4, 5};
	char karakter[5] = {'a', 'r', 'm', 'u', 't'};
	float float_dizi[5] = {0.1, 4.5, 7.8, 6.2, 1.9};
	
	print<int, char>(tam_sayi, karakter, 5);
	print<float, int>(float_dizi, tam_sayi, 5);
	
	return 0;
}
```

Bu örneğimizde iki farklı parametre ile kullanılacak şablon oluşturduk ve “**main()**” fonksiyonunda farklı veri türleri ile fonksiyona parametreler gönderdik.

Ekrana verilen çıktı:

```cpp
1 2 3 4 5
a r m u t
0.1 4.5 7.8 6.2 1.9
1 2 3 4 5
```

**Not:** Şablonları tanımlarken kullandığımız “**class**” ve “**typename**” anahtar kelimeleri arasında önemsenmeyecek istisnalar dışında bir fark yoktur. Bu nedenle hangi anahtar kelimeyi kullanacağınız size kalmış bir durum.
