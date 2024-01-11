
switch, “else if” karar yapısının alternatifidir. Yani else if yerine switch de kullanılabilir.

Kullanım şekli aşağıdaki gibidir:

```cpp
switch(degiskenAdi) {

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

case degiskenSabiti:
.
.
islenecekKodlar;
.
.
break;

default: 
.
.
islenecekKodlar;
.
.

}
```

Konuyu aşağıdaki örnek ile anlamaya çalışalım:

```cpp
#include <stdio.h>

int main() {

int s1, s2, islem, mod;
float sonuc;

printf("1- toplama \n");
printf("2- cikarma \n");
printf("3- carpma \n");
printf("4- bolme \n");
printf("5- mod alma \n");

printf("yapmak istediginiz islemin numarasini giriniz: ");
scanf("%d", &islem);
printf("iki sayi giriniz: ");
scanf("%d%d", &s1, &s2);

switch(islem) {

case 1:
sonuc = s1 + s2;
printf("sonuc: %f", sonuc);
break;

case 2:
sonuc = s1 - s2;
printf("sonuc: %f", sonuc);
break;

case 3:
sonuc = s1 * s2;
printf("sonuc: %f", sonuc);
break;

case 4:
sonuc = (float)s1 / s2;
printf("sonuc: %f", sonuc);
break;

case 5:
mod = s1 % s2;
printf("sonuc: %d", mod);
break;

default: printf("islem icin yanlis sayi girisi yaptiniz");

}

return 0;
}
```

Yukarıdaki örnekte switch kullanarak 4 islem ve mod alma programı yazdık.
