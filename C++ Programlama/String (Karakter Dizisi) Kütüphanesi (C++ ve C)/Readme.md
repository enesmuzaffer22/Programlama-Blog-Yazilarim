

## cstring Kütüphanesinde Bazı Önemli Fonksiyonlar (C++)

Bu kütüphaneyi kullanabilmek için kodlar arasında tanımlamamız gerekir.

```cpp
#include <cstring>
```

strchr()

strchr() fonksiyonu karakter dizisinde karakter aramak için kullanılır.

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
	
	char k_dizisi[] = "bilgisayar";
	char karakter;
	
	cout << "harf giriniz: ";
	cin >> karakter;
		
	if(strchr(k_dizisi, karakter)) {
		
		/* 'karakter' degiskenine atanan karakter 'k_dizisi' isimli karakter degiskeninde
		var ise asagidaki ciktiyi ekrana yazdirir */
		
		cout << karakter << " harfi " << k_dizisi << " kelimesinde vardir";
		
	}
	
	else {
		
		/* 'karakter' degiskenine atanan karakter 'k_dizisi' isimli karakter degiskeninde
		yok ise asagidaki ciktiyi ekrana yazdirir */
		
		cout << karakter << " harfi " << k_dizisi << " kelimesinde yoktur ";
		
	}
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
harf giriniz: a
a harfi bilgisayar kelimesinde vardir
```

strcmp()

strcmp() fonksiyonu iki karakter dizisini karşılaştırır ve bir değer döndürür. Eğer döndürülen değer sıfırdan büyük ise ilk karakter dizisi ikinci karakter dizisinden alfabetik sıraya göre daha sonra gelir. Döndürülen değer sıfırdan küçük ise ilk karakter dizisi ikinci karakter dizisinden alfabetik sıraya göre daha önce gelir. Eğer döndürülen değer sıfıra eşit ise karakter dizileri birbirlerine eşittir.

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
	
	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim"; 
	
	if(strcmp(k_dizisi, k_dizisi_2) > 0) {
		
		cout << k_dizisi;
		
	}
	
	else if(strcmp(k_dizisi, k_dizisi_2) == 0) { 
		
		cout << k_dizisi << " " << k_dizisi_2;
		
	}
	
	else if(strcmp(k_dizisi, k_dizisi_2) < 0) {
		
		cout << k_dizisi_2;
		
	}
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
bilisim
```

strcpy()

strcpy() fonksiyonu bir karakter dizisini başka bir karakter dizisine atar.

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
	
	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim";  
	
	strcpy(k_dizisi, k_dizisi_2); /* 'k_dizisi_2' yi 'k_dizisi' ne atar */
	
	cout << k_dizisi; 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
bilisim
```

strlen()

strlen() fonksiyonu karakter dizisinin uzunluğunu döndürür.

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
	
	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim";  
	
	cout << strlen(k_dizisi) << endl;
	cout << strlen(k_dizisi_2) << endl;
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
10
7
```

strcat()

strcat() fonksiyonu bir karakter dizisini başka bir karakter dizisine kopyalar.

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
	
	char k_dizisi[] = "c "; 
	char k_dizisi_2[] = "ogrencisi";  
	
	cout << k_dizisi << endl;
	cout << strcat(k_dizisi, k_dizisi_2) << endl; /* 'k_dizisi' ne 'k_dizisi_2' yi ekledi */
	cout << k_dizisi_2 << endl;
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
c
c ogrencisi
ogrencisi
```

string.h Kütüphanesinde Bazı Önemli Fonksiyonlar (C)

Bu kütüphaneyi kullanabilmek için kodlar arasında tanımlamamız gerekir.

```cpp
#include <string.h>
```

strcat()

strcat() fonksiyonu bir karakter dizisini başka bir karakter dizisine kopyalar.

```cpp
#include <stdio.h>
#include <string.h>

int main() {

	char k_dizisi[] = "c "; 
	char k_dizisi_2[] = "ogrencisi";  
	
	printf("%s \n", k_dizisi);
	printf("%s \n", strcat(k_dizisi, k_dizisi_2)); /* 'k_dizisi' ne 'k_dizisi_2' yi ekledi */
	printf("%s \n", k_dizisi_2);
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
c
c ogrencisi
ogrencisi
```

strcmp()

strcmp() fonksiyonu iki karakter dizisini karşılaştırır ve bir değer döndürür. Eğer döndürülen değer sıfırdan büyük ise ilk karakter dizisi ikinci karakter dizisinden alfabetik sıraya göre daha sonra gelir. Döndürülen değer sıfırdan küçük ise ilk karakter dizisi ikinci karakter dizisinden alfabetik sıraya göre daha önce gelir. Eğer döndürülen değer sıfıra eşit ise karakter dizileri birbirlerine eşittir.

```cpp
#include <stdio.h>
#include <string.h>

int main() {

	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim"; 
	
	if(strcmp(k_dizisi, k_dizisi_2) > 0) {
		
		printf("%s ", k_dizisi);
		
	}
	
	else if(strcmp(k_dizisi, k_dizisi_2) == 0) { 
		
		printf("%s %s", k_dizisi, k_dizisi_2);
		
	}
	
	else if(strcmp(k_dizisi, k_dizisi_2) < 0) {
		
		printf("%s ", k_dizisi_2);
		
	}
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
bilisim
```

strcpy()

strcpy() fonksiyonu bir karakter dizisini başka bir karakter dizisine atar.

```cpp
#include <stdio.h>
#include <string.h>

int main() {

	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim";  
	
	strcpy(k_dizisi, k_dizisi_2); /* 'k_dizisi_2' yi 'k_dizisi' ne atar */
	
	printf("%s", k_dizisi); 
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
bilisim
```

strlen()

strlen() fonksiyonu karakter dizisinin uzunluğunu döndürür.

```cpp
#include <stdio.h>
#include <string.h>

int main() {

	char k_dizisi[] = "bilgisayar"; 
	char k_dizisi_2[] = "bilisim";  
	
	printf("%d \n", strlen(k_dizisi));
	printf("%d \n", strlen(k_dizisi_2));
	
	return 0;
}
```

Ekrana verilen çıktı:

```cpp
10
7
```
