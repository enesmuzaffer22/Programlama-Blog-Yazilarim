
## while ve for Döngüleri Soruları ve Çözümleri

[admin](https://golittlecoder.com/author/admin/)[Bütün Yazılar](https://golittlecoder.com/category/butunyazilar/) Kasım 24, 2022 | 0

1) 1’den başlayarak ilk 100 doğal sayıyı ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int i;

for(i = 0; i < 100; i++) {
	printf("%d \n", i);
}

return 0;
}
```

2) 100 ve 200 arasında 9 ile tam bölünebilen sayıları ve bunların toplamını ekrana yazdıran C  
programını yazınız.

```cpp
#include <stdio.h>

int main() {

int i, sonuc = 0;

for(i = 100; i < 200; i++) {
	if((i % 9) == 0) {
		printf("9 ile bolunebilen sayi: %d \n", i);
		sonuc = sonuc + i;
	}
}

printf("toplami: %d \n", sonuc);

return 0;
}
```

3) Kullanıcıdan bir tamsayı N değeri girmesini isteyen, ilk N tane tek doğal sayıyı ve bunların  
toplamını aşağıdaki örnekte olduğu gibi ekrana yazdıran C programını yazınız.  
Örnek; Bir tamsayi giriniz: 10  
Ilk 10 tek sayi = 1 3 5 7 9 11 13 15 17 19  
Ilk 10 tek sayinin toplami = 100

```cpp
#include <stdio.h>

int main() {

int n, i, toplam = 0;

printf("n degerini giriniz: ");
scanf("%d", &n);

printf("ilk %d tek sayilar: ", n);

for(i = 1; i < n * 2; i = i + 2) {
	printf(" %d ", i);
	toplam = toplam + i;
}

printf("\ntoplam: %d", toplam);

return 0;
}
```

4) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının faktöriyelini hesaplayıp sonucu  
ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int f = 1, sayi, i;

printf("bir sayi giriniz: ");
scanf("%d", &sayi);

for(i = 1; i <= sayi; i++) {
	f = f * i;
}

printf("faktoriyel: %d", f);

return 0;
}
```

5) Kullanıcıdan bir taban değeri a ve bir üs değeri b girmesini isteyen ve a üssü b’yi hesaplayarak sonucu ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int sonuc = 1, taban, us, i;

printf("taban giriniz: ");
scanf("%d", &taban);
printf("us giriniz: ");
scanf("%d", &us);


for(i = 1; i <= us; i++){
	sonuc = sonuc * taban;
}

printf("sonuc: %d", sonuc);

return 0;
}
```

6) Kullanıcıdan iki tamsayı girmesini isteyen, girilen iki sayının en büyük ortak bölenini  
(EBOB) hesaplayarak sonucu ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int s1, s2, ebob, i, sayi1, sayi2;

printf("iki sayi giriniz: ");
scanf("%d%d", &sayi1, &sayi2); 

if(sayi1 > sayi2) {
	s1 = sayi1;
	s2 = sayi2;
}

else {
	s1 = sayi2;
	s2 = sayi1;
}

for(i = 1; i <= s2; i++)
    {
        if(s1 % i == 0 && s2 % i == 0)
            ebob = i;
    }
	

printf("ebob: %d", ebob);

return 0;
}
```

7) Kullanıcıdan iki tamsayı girmesini isteyen, girilen iki sayının en küçük ortak katını (EKOK)  
hesaplayarak sonucu ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int sayi1, sayi2, s1, s2, i, ebob, ekok;

printf("\n");
printf("iki sayi giriniz: ");
scanf("%d%d", &sayi1, &sayi2);

if(sayi1 > sayi2) {
	s1 = sayi1;
	s2 = sayi2;
}

else {
	s1 = sayi2;
	s2 = sayi1;
}

for(i = 1; i <= s2; i++)
    {
        if(s1 % i == 0 && s2 % i == 0)
            ebob = i;
    }


ekok = (s1 * s2) / ebob;

printf("ekok: %d", ekok);

return 0;
}
```

8) Kullanıcıdan ikilik tabanda bir sayı girmesini isteyen, girilen ikilik tabandaki sayının onluk  
tabandaki karşılığını hesaplayarak sonucu ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int gti, ti, to = 0, c = 1, k;  // gti: girilen (input) ikilik taban

printf ("ikilik tabanda bir sayi giriniz: ");  
scanf (" %d", &gti);   
  
ti = gti; 
      
while (gti > 0)  {
	  
    k = gti % 10; 
    to = to + k * c;  
    gti = gti / 10; 
    c = c * 2;  
   
}  
  
printf ( "ikilik taban:  %d \n", ti); 
printf ("onluk taban:  %d ", to);

return 0;
}
```

9) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının ikilik tabandaki karşılığını  
hesaplayarak sonucu ekrana yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int cto, to, r;          //ti = taban ikilik, to = taban onluk, cto = cikis onluk taban
	
printf("onluk tabanda bir sayi giriniz: ");
scanf("%d", &to);

cto = to;
	
int kat = 1;
int sonuc = 0;
	
while(to != 0) {
		
	r = to % 2;
		
	sonuc = sonuc + r * kat;
	kat = kat * 10;
		
	to = to / 2;

}
	
printf("onluk taban: %d  |  ikilik taban: %d", cto, sonuc);

return 0;
}
```
