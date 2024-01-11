
C programlamada, veri tipleri değişkenler için değişkenin açıklamasıdır. Veri tipleri, değişkenlerle ilişkili verilerin türünü ve boyutunu belirler.

```cpp
veriTipi degiskenAdi = atananDeger;
```

Atamaları ise yukarıdaki basit bir formülle gösterilebilir.

Aşağıdaki tabloda temel veri tipleri ve bunların sahip olduğu boyutlar ve aralıkları verilmiş.

![](https://images.theengineeringprojects.com/image/main/2018/02/introduction-to-data-types-in-C-1.png)

# char

Bir değişkene karakter atamak için kullanılır. (Örneğin: a, b, x, z)

```cpp
char degiskeninAdi = 'a';
```

# int

Bir değişkene bir tam sayı atamak için kullanılır. (Örneğin: 1, 4, 5, 13)

```cpp
int degiskenAdi = 5;
```

# float

Bir değişkene ondalıklı sayı atamak için kullanılır.  (Örneğin: 1.2, 3.6, 4.55)

```cpp
float degiskenAdi = 4.67;
```

# short

Bir değişkene bir tam sayı atamak için kullanılır. int değişkeninden tek farkı tanım aralığının daha küçük olmasıdır

```cpp
short degiskenAdi =  21;
```

# double

Bir değişkene ondalıklı sayı atamak için kullanılır. float değişkeninden tek farkı virgülden sonra daha fazla basamak vardır.

```cpp
double degiskenAdi = 5.434324;
```

# long

Bir değişkene bir tam sayı atamak için kullanılır. int değişkeninden tek farkı tanım aralığı daha geniştir. (Örneğin: 1232323, 4223, 55435, 13456)

```cpp
long degiskenAdi = 23243242;
```

## Değişken Adlarının Önemi

Değişkeninize iyi bir ad vermeniz kodunuzun hem rahat okunmasını hem de değişken adlarınızın karışmamasını sağlar.

Yazılım dilleri günlük konuşma dillerinden çok da farklı değildir. Tıpkı günlük konuşma dillerinde dil bilgisi (gramer) olduğu gibi yazılım dillerinin de kendine özel dil bilgisi vardır.

# Değişken Adlarının Kuralları:

-   Değişken adları sayı ile başlayamaz.
-   Değişken adlarında Türkçe karakter bulunamaz.
-   Değişken adında boşluk kullanılamaz.
-   Değişken adında birden fazla kelime kullanılacaksa değişken aşağıdaki gibi yazılır.

```cpp
birdenFazlaKelimeliDegisken
```

Bu kullanım katı bir kural değildir. Yazılım topluluğunda genel kullanım bu şekildedir.

İlk kelimenin baş harfi küçük, diğerleri ise büyük harf ile başlar.

-   Değişken adı bir fonksiyon veya yazılım teriminin adı olamaz. Örneğin,

```cpp
int if = 5; // if yazilim terimi oldugu icin kullanilamaz
```

# Atama Şekilleri

Aşağıdaki kodlarda birden fazla atama şekline örnek gösterdim.

```cpp
#include <stdio.h>

int main() {

int a = 5;
int b;
b = 8;

int d, e = 9; // bu satirda sadece e degiskenini tanimladik

d = 2;

int x, y, z;
x = 5;
y = 6;
z = 7;

return 0;
}
```

# Son olarak;

Yazımızı genel olarak aşağıdaki kodlarla birlikte toplayabiliriz.

```cpp
#include <stdio.h>

int main() {

int a = 5;
char karakter = f;
float ondalikliSayi = 3.324;
double ondalikliSayi2 = 2.434324324;

int d, e = 9; // bu satirda sadece e degiskenini tanimladik

d = 2;

return 0;
}
```
