
# Döngü nedir ? Neden öğrenmemiz gereklidir ?

Döngüler belirlenen koşullar sağlandığı zaman işlenen kodların, koşulların sağlanmadığı zamana kadar sürekli tekrar etmesidir.

Döngüler kod yazımından tasarruf etmenizi sağlar. Örneğin, bir işlemi birden fazla kere yazmak yerine döngü ile bir kere yazmak, sizin kod yazımından tasarruf etmenizi sağlar.

# while

while döngüsünde verilen şartlar sağlandığı sürece döngü içindeki kodlar tekrar tekrar işlenir.

while döngüsü aşağıdaki gibi yazılır:

```cpp
while(kosulIfadesi) {

.
.
islenecekKodlar
.
.

}
```

Konuyu bir örnek ile anlamaya çalışalım:

```cpp
#include <stdio.h>

int main() {

int a = 1;

while(a <= 10) {

printf("a sayisi: %d \n", a);
a = a + 1;

}

return 0;
}
```

Yukarıdaki örnekte ilk olarak a değişkenini 1 olarak tanımladık. Sonrasında ise while döngüsü ile a 10’a eşit olana kadar döngüye girdirdik. Döngü içinde ise a’yı her döngüde 1 arttırdık.

Programın çıktısı ise aşağıdaki gibi oldu:

```cpp
a sayisi: 1

a sayisi: 2

a sayisi: 3

a sayisi: 4

a sayisi: 5

a sayisi: 6

a sayisi: 7

a sayisi: 8

a sayisi: 9

a sayisi: 10
```

Yani programın asıl amacı 1 den 10 a kadar sayıların ekrana yazılmasıydı.

# for

for döngüsü while döngüsüne çok benzerdir. Yani iki döngü de birbiri yerine hemen hemen her yerde kullanılabilir. for döngüsünün while döngüsünden farkı for döngüsünü sizin belirlediğiniz kadar tekrar etmesidir. Yani olayın özeti şudur:

while döngüsü, verdiğiniz koşul sağlandığı sürece döner. for döngüsü ise sizin belirlediğiniz kadar tekrar eder.

for döngüsü aşağıdaki gibi yazılır:

```cpp
for ( donguIcinDegisken; kosulIfadesi; donguIslemi ) { 

.
.
islenecekKodlar
.
.

}
```

Konuyu bir örnek ile anlamaya çalışalım:

```cpp
#include <iostream>
using namespace std;

int main() {

int a;

for(a = 1; a <= 10; a = a + 1) {

printf("a sayisi: %d \n", a);

}

return 0;
}
```

Yukarıdaki örnekte for döngüsünün bizim belirlediğimiz kadar dönmesini sağladık.

Programın çıktısı ise aşağıdaki gibi oldu:

```cpp
a sayisi: 1

a sayisi: 2

a sayisi: 3

a sayisi: 4

a sayisi: 5

a sayisi: 6

a sayisi: 7

a sayisi: 8

a sayisi: 9

a sayisi: 10
```

Yani programın asıl amacı 1 den 10 a kadar sayıların ekrana yazılmasıydı.
