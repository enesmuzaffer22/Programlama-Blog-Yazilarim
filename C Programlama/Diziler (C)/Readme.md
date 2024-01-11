
Diziler birden çok değeri tek bir değişkende tutmak için kullanılır. Yani birden fazla değişkenle yapabileceğimiz işlemleri tek bir değişken ile yapabiliriz.

Dizilerin kullanım şekli aşağıdaki gibidir:

```cpp
int degiskenAdi[5] = {1, 2, 3, 4, 5};
```

Yukarıdaki ifadede “degiskenAdi” değişkenine beş tane değer atadık ve bu değerleri liste şeklinde görebiliyoruz.

## Peki bu değerlerin çıktısını nasıl alabiliriz ?

Bunun için dizinin “indeks” numarasından faydalanırız. İndeks numaraları “0 (sıfır)” dan başlar (yani 0, 1, 2.. şeklinde devam eder).

Bu durumu aşağıdaki kodlarla ifade edebiliriz:

```cpp
a[0] = 1; //sifirinci indeks 1'e esit
a[1] = 2; //birinci indeks 2'ye esit
a[2] = 3; //ikinci indeks 3'e esit
a[3] = 4; //ucuncu indeks 4'e esit
a[4] = 5; //dorduncu indeks 5'e esit
```

O halde bu kodlara benzer bir yazım ile aşağıdaki kodlar ile herhangi bir indeksteki sayının çıktısı alınabilir:

```cpp
#include <stdio.h>

int main() {

int a[5] = {1, 2, 3, 4, 5};

printf("ikinci indeksteki sayi: %d", a[2]);

return 0;
}
```

Programın çıktısı aşağıdaki gibi olacaktır.

```cpp
ikinci indeksteki sayi: 3
```

## Döngüden Faydalanarak Çıktı Alma

```cpp
#include <stdio.h>

int main() {

int i, a[5] = {1, 2, 3, 4, 5};

for(i = 0; i < 5; i++) {
	
	printf("%d. indeksteki sayi: %d \n", i, a[i]);
	
}

return 0;
}
```

Yukarıda yazdığımız kodlar sayesinde bütün indeksteki sayıları ekrana yazdırdık. “Printf” içerisindeki “a[i]” ifadesindeki “i” birer birer artacağından dolayı 5. indekse kadar olan sayıları ekrana yazdırır.

Ekrana verilen çıktı ise aşağıdaki gibidir:

```cpp
0. indeksteki sayi: 1
1. indeksteki sayi: 2
2. indeksteki sayi: 3
3. indeksteki sayi: 4
4. indeksteki sayi: 5
```

## İndekse Değer Atama

İndekse değer atamak herhangi bir değişkene değer atamak ile aynıdır. Sadece yazılışları farklıdır. Örneğin:

```cpp
#include <stdio.h>


int main() {
	
int a[3];

printf("sifirinci indeks icin sayi giriniz: ");
scanf("%d", &a[0]);
printf("birinci indeks icin sayi giriniz: ");
scanf("%d", &a[1]);
printf("ikinci indeks icin sayi giriniz: ");
scanf("%d", &a[2]);

printf("sifirinci indeks: %d \n", a[0]);
printf("birinci indeks: %d \n", a[1]);
printf("ikinci indeks: %d \n", a[2]);


	return 0;
}
```

Ekrana verilen çıktı ise aşağıdaki gibidir:

```cpp
sifirinci indeks icin sayi giriniz: 1
birinci indeks icin sayi giriniz: 2
ikinci indeks icin sayi giriniz: 3
sifirinci indeks: 1
birinci indeks: 2
ikinci indeks: 3
```

## Döngüden Faydalanarak Değer Atama

```cpp
#include <stdio.h>


int main() {
	
int i, a[5];

for(i = 0; i < 5; i++) {
	
	printf("%d. indeks icin sayi giriniz: ", i);
	scanf("%d", &a[i]);
	
}

for(i = 0; i < 5; i++) {
	
	printf("%d. indeks: %d \n", i, a[i]);
	
}
	
	return 0;
}
```

Yukarıda yazdığımız kodlar sayesinde bütün indeksteki sayıları ekrana yazdırdık. “printf” içerisindeki “a[i]” ifadesindeki “i” birer birer artacağından dolayı 5. indekse kadar olan sayıları ekrana yazdırır ve Yukarıda yazdığımız kodlar sayesinde bütün indeksteki sayıları ekrana yazdırdık ve “scanf” içerisindeki “a[i]” ifadesindeki “i” birer birer artacağından dolayı 5. indekse kadar olan sayılara kullanıcı tarafından değer atanır.

Program aşağıdaki gibi çıktı verir:

```cpp
0. indeks icin sayi giriniz: 1
1. indeks icin sayi giriniz: 2
2. indeks icin sayi giriniz: 3
3. indeks icin sayi giriniz: 4
4. indeks icin sayi giriniz: 5
0. indeks: 1
1. indeks: 2
2. indeks: 3
3. indeks: 4
4. indeks: 5
```
