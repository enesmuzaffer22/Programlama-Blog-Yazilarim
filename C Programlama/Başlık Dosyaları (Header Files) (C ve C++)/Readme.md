 Başlık dosyaları, programlamayı kolaylaştırmak için önceden tanımlanmış ve yazılmış işlevleri içeren dosyalardır. Bu dosyaları kodlar arasında çağırmak için “**#include**” kod parçacığını kullanırız. Örneğin:

```cpp
#include <iostream> // C++ Programlama
#include <stdio.h> // C Programlama
```

Başlık dosyaları “**.h**” uzantılı dosyalardır. C++ Programlama dilinde çoğu başlık dosyasını “**.h**” uzantısı olmadan çağırabiliriz fakat aynı şey C programlama dilinde söz konusu değildir. C Programlama dilinde başlık dosyaları çağırılırken “**.h**” uzantısı kullanılır.

İki tür başlık dosyası vardır:

1.  **Kullanıcı tanımlı başlık dosyaları**
2.  **Önceden var olan başlık dosyaları**

## Kullanıcı Tanımlı Başlık Dosyaları

Kullanıcı tanımlı başlık dosyaları, kullanıcı tarafından tanımlanmış ve yazılmış kodları içeren başlık dosyalarıdır. Bu türden bir başlık dosyası oluşturmak için önce kodlarınızı yazmalısınız ardından yazdığınız kodları “**.h**” uzantılı dosya şeklinde kaydetmelisiniz. Oluşturduğunuz başlık dosyasını kodlarınız arasında kullanmak için “ **#include “baslikAdi.h”** ” kod parçacığını kullanmalısınız. Örneğin:

```cpp
int toplama(int a, int b) {
	
	int toplam = a + b;
	return toplam;
	
}
```

Bu yazdığımız kodları başlık dosyası olarak kaydedelim ve ismini “**toplama.h**” koyalım.

```cpp
#include <iostream>
#include "toplama.h" // toplama.h dosyasini cagirdik
using namespace std;

int main() {
	
	int sayi1 = 5;
	int sayi2 = 10;
	
	cout << "iki sayinin toplami = " << toplama(sayi1, sayi2) << endl;
	
	return 0;
}
```

Oluşturduğumuz başlık dosyasını yukarıda yazdığımız kodlardaki gibi çağırdık ve içerisindeki toplama fonksiyonunu kullandık.

Ekrana verilen çıktı:

```cpp
iki sayinin toplami = 15
```

## Önceden Var Olan Başlık Dosyaları

Önceden var olan başlık dosyaları, programlama dilinin kendine ait başlık dosyalarıdır. Kodlar arasında kullanmak için “**#include <baslikAdi> veya #include <baslikAdi.h> (İki kod parçasının arasındaki farktan yukarıda bahsetmiştik.)**” kod parçacığını kullanırız. Örneğin:

```cpp
#include <iostream> // C++ Programlama
#include <stdio.h> // C Programlama
```

## Birden Fazla Başlık Dosyası Kullanma

Bir programda birden fazla farklı başlık dosyası kullanabilirsiniz fakat **aynı başlık dosyasını birden fazla kez kullanamazsınız**. Böyle bir durumda derleyici aynı başlık dosyasını birden fazla kez derler ve bu olay programda hatalara yol açar. Bu durumu önlemek için iki tane yöntem vardır.

1.Yöntem (#pragma once)

Bu yöntemde başlık dosyalarının kodlarını yazarken ilk olarak “**#pragma once**” kod parçacığının eklenmesidir. Örneğin:

```cpp
#pragma once

int toplama(int a, int b) {
	
	int toplam = a + b;
	return toplam;
	
}
```

2.Yöntem (#ifndef, #define, #endif)

Bu yöntem bir önceki yöntemin benzeridir. Örneğin:

```cpp
#ifndef _toplama_h
#define _toplama_h

int toplama(int a, int b) {
	
	int toplam = a + b;
	return toplam;
	
}

#endif
```
