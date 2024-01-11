
C ve C++ Programlama dillerinde ihtiyaç halinde rastgele sayılar üretilebilir. Bu yazımızda bu sayıların nasıl üretildiğine göz atacağız.

## C++ Programlama Dilinde Rastgele Sayılar Üretme

C++ Programlamada rastgele sayılar üretmek için öncelikle “cstdlib, ctime” kütüphanelerini tanımlamalıyız. Bunun nedeni ise kodlar arasında kullanacağımız “srand(), rand(), time()” fonksiyonlarına erişmektir.

Bir örnek ile konuyu kavramaya çalışalım:

```cpp
#include <iostream>
#include <ctime>
#include <cstdlib> 
using namespace std;

int main() {
    
    srand(time(0)); /* bilgisayarin saatine gore ayarlanmis, rastgele 
    sayilar uretmek icin baslangic noktasi olusturan fonksiyon */
    
    int a; 
    
    a = rand(); /* rand() fonksiyonu ile rastgele sayilar a 
    degiskenine tanimlanir */
    
    cout << a;

    return 0;
}

```

Bu örneğimizde herhangi bir alt sınır veya üst sınır olmadan rastgele sayı ürettik ve bu sayıyı “a” değişkeni ile ekrana bastırdık.

Programın çıktısı:

```cpp
53245
```

## Belirli Sınırlar Arasında Rastgele Sayı Üretme

Rastgele sayılar belirli sınırlar arasında üretilebilir. Bunun için basit bir formül vardır:

**rand() % (üst sınır – alt sınır + 1) + alt sınır**

Bir örnek ile konuyu kavramaya çalışalım:

```cpp
#include <iostream>
#include <ctime>
#include <cstdlib> 
using namespace std;

int main() {
    
    srand(time(0)); /* bilgisayarin saatine gore ayarlanmis, rastgele 
    sayilar uretmek icin baslangic noktasi olusturan fonksiyon*/
    
    int a, i; 
    
    for(i = 1; i <= 5; i++) {
        
        a = rand() % (30 - 10 + 1) + 10; /* 30 ile 10 arasinda rastgele sayilar
    üretilip a degiskenine atanir*/
    
        cout << a << endl;
        
    }

    return 0;
}

```

Bu örneğimizde for döngüsü ile “a” değişkenine 10 ile 30 arasında rastgele sayılar atadık ve bu sayıları döngü yardımı ile ekrana 5 defa yazdırdık.

Programın çıktısı:

```cpp
12
17
11
25
21
```

## C Programlama Dilinde Rastgele Sayılar Üretme

C Programlamada rastgele sayılar üretmek için öncelikle “stdlib.h, time.h” kütüphanelerini tanımlamalıyız. Bunun nedeni ise kodlar arasında kullanacağımız “srand(), rand(), time()” fonksiyonlarına erişmektir.

Bir örnek ile konuyu kavramaya çalışalım:

```cpp
#include <stdio.h>
#include <time.h>
#include <stdlib.h> 

int main() {
    
    srand(time(0)); /* bilgisayarin saatine gore ayarlanmis, rastgele 
    sayilar uretmek icin baslangic noktasi olusturan fonksiyon */
    
    int a; 
    
    a = rand(); /* rand() fonksiyonu ile rastgele sayilar a 
    degiskenine tanimlanir */
    
    printf("%d", a);

    return 0;
}
```

Bu örneğimizde herhangi bir alt sınır veya üst sınır olmadan rastgele sayı ürettik ve bu sayıyı “a” değişkeni ile ekrana bastırdık.

Programın çıktısı:

```cpp
634268
```

## Belirli Sınırlar Arasında Rastgele Sayı Üretme

Rastgele sayılar belirli sınırlar arasında üretilebilir. Bunun için basit bir formül vardır:

**rand() % (üst sınır – alt sınır + 1) + alt sınır**

Bir örnek ile konuyu kavramaya çalışalım:

```cpp
#include <stdio.h>
#include <time.h>
#include <stdlib.h> 

int main() {
    
    srand(time(0)); /* bilgisayarin saatine gore ayarlanmis, rastgele 
    sayilar uretmek icin baslangic noktasi olusturan fonksiyon*/
    
    int a, i; 
    
    for(i = 1; i <= 5; i++) {
        
        a = rand() % (30 - 10 + 1) + 10; /* 30 ile 10 arasinda rastgele sayilar
    üretilip a degiskenine atanir*/
    
        printf("%d \n", a); 
        
    }

    return 0;
}
```

Bu örneğimizde for döngüsü ile “a” değişkenine 10 ile 30 arasında rastgele sayılar atadık ve bu sayıları döngü yardımı ile ekrana 5 defa yazdırdık.

Programın çıktısı:

```cpp
13
10
26
15
23
```
