
Belirli bir görevi gerçekleştirmek için yazılan kod bloklarına **fonksiyon** denir. Fonksiyonları belirli bir görev için yazdığımız kodları tekrar tekrar yazmamak için kullanırız.

Örneğin uygulama içinde bir işlem menüsü yapmak istediniz ve bu menüyü farklı koşullara göre aktif hale getirmek istediniz. Bu durumda gereken koşulların her birine işlem menüsünü sürekli yazmanız gerekecekti. Bu durumdan sıyrılmak için fonksiyonları kullanıyoruz.

İşlevli bir kod parçacığını sürekli yazmak yerine bir kere yazıp gereken yerde kod ile çağırıyoruz.

## Fonksiyon Türleri

**Kütüphane Tarafından Tanımlanmış Fonksiyonlar**

Bu tür fonksiyonlar kullanıcı tarafından tanımlanmaz, kullanıcıya hazır olarak verilir. Fonksiyonları kullanmanız için “header” dosyalarını (.h uzantılı dosyalar) çağırmanız gerekir.

Örneğin ekrana çıktı vermek için kullandığımız “printf” fonksiyonu “stdio” kütüphanesi tarafından tanımlanmıştır.

```cpp
#include <stdio.h>  //kutuphaneyi cagirdik

int main() {

  printf("hello world");  //printf fonksiyonu ile ekrana "hello world" yazdirdik

  return 0;
}
```

**Kullanıcı Tarafından Tanımlanmış Fonksiyonlar**

Bu tür fonksiyonlar kullanıcı tarafından ihtiyacı olduğu zaman tanımlanır. Fonksiyonların çalışma mantığı aşağıdaki gibidir:

![](https://cdn.programiz.com/sites/tutorial2program/files/function-c-programming.jpg)

Önce fonksiyon tanımlanır. Sonrasında ise fonksiyon kümesinin içine işlenecek kodlar yazılır.

## Fonksiyon Tanımlama

Fonksiyonlar aşağıdaki tanımlanır:

```cpp
veriTipi fonksiyonAdi(veriTipi1 degisken1, veriTipi2 degisken2, ...);
```

Örneğin:

```cpp
float daireninAlani(float yaricap);
```

Fonksiyonun Yazımı

Fonksiyonlar aşağıdaki gibi yazılır:

```cpp
veriTipi fonksiyonAdi(veriTipi1 degisken1, veriTipi2 degisken2, ...) {

   ....
   islenecekKodlar
   ....

   return donecekOlanDeger;
}
```

Örneğin:

```cpp
float alan(float r) {
	
	float pi = 3.14, alan;
	
	alan = pi * r * r;
	
	return alan;
}
```

## Fonksiyonun Çağırılması

Fonksiyonlar aşağıdaki gibi çağırılır:

```cpp
fonksiyonAdi(degisken1, degisken2, ...);
```

Örneğin:

```cpp
alan(yaricap);
```

## Fonksiyon Kullanımı İçin Örnek

Dikkat etmişseniz konu anlatımı boyunca dairenin alanı üzerine bir örnek verdim. Konunun bu kısmında dairenin alanını fonksiyon yardımı ile bulacağız.

```cpp
#include <stdio.h>


float alan(float r);  // fonksiyonun tanimi

float alan(float r) {
	
	float pi = 3.14, alan;
	
	alan = pi * r * r;  // fonsiyonun yazimi
	
	return alan; // donecek olan deger
}

int main() {
	
float s, sonuc;

printf("bir sayi giriniz: ");
scanf("%f", &s);

sonuc = alan(s);  // fonksiyonun cagirilmasi

printf("sonuc: %f", sonuc);

	return 0;
}
```
