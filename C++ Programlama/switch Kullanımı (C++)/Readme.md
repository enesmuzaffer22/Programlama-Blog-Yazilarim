
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
#include <iostream>
using namespace std;

int main() {

int s1, s2, islem, mod;
float sonuc;

cout << "1- toplama \n";
cout << "2- cikarma \n";
cout << "3- carpma \n";
cout << "4- bolme \n";
cout << "5- mod alma \n";

cout << "yapmak istediginiz islemin numarasini giriniz: ";
cin >> islem;
cout << "iki sayi giriniz: ";
cin >> s1 >> s2;

switch(islem) {

case 1:
sonuc = s1 + s2;
cout << "sonuc: " << sonuc;
break;

case 2:
sonuc = s1 - s2;
cout << "sonuc: " << sonuc;
break;

case 3:
sonuc = s1 * s2;
cout << "sonuc: " << sonuc;
break;

case 4:
sonuc = (float)s1 / s2;
cout << "sonuc: " << sonuc;
break;

case 5:
mod = s1 % s2;
cout << "sonuc: " << mod;
break;

default: cout << "islem icin yanlis sayi girisi yaptiniz";

}

return 0;
}
```

Yukarıdaki örnekte switch kullanarak 4 islem ve mod alma programı yazdık.
