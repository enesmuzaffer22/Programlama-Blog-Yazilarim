

## Karakter Dizileri

Karakter dizileri, elemanları karakter olan (char veri tipi) ve belirli bir uzunluğa sahip olan dizilerdir. Örneğin aşağıdaki diziler birer karakter dizisidir:

```cpp
char ornekDizi[5] = {'a', 'c', 'b', 'g', 'k'};
char ornekDizi2[3] = {'j', 'k', 'm'};
```

## Stringler

Normal şartlarda C programlama dilinde string veri tipi yoktur fakat string veri tipinin olmaması string yapısının oluşmasına engel değildir. Yukarıda da bahsettiğimiz **karakter dizileri** sayesinde string yapıları oluşturulabilir. Örneğin:

```cpp
char stringOrnegi[7] = "deneme";
```

Yukarıdaki ifade aslında bir karakter dizisidir ve aşağıdaki gibi de yazılabilir:

```cpp
char stringOrnegi[7] = {'d', 'e', 'n', 'e', 'm', 'e', 'char stringOrnegi[7] = {'d', 'e', 'n', 'e', 'm', 'e', '\0'};'};
```

Stringler konu başlığı altındaki ilk örnekte dikkat ederseniz, “deneme” sözcüğü “6” harfli olmasına rağmen dizinin boyutunu “7” olarak tanımladık. Bunun nedeni ise string yapılarının **“\0”** ile sonlanmasıdır. “\0” karakteri dizinin sonlandığını ifade etmek için eklenir.

**Not: Karakter dizilerinin normal dizilerden hiçbir farkı yoktur. İndeks mantığı tamamen aynıdır.**

## String Yapısında Input Alma

String yapısında input almanın birden fazla yolu vardır.

gets

```cpp
#include <stdio.h>

int main() {
	
	char stringOrnegi[20];
	
	gets(stringOrnegi);
	
	printf("%s", stringOrnegi);
	
	return 0;
}
```

fgets

```cpp
#include <stdio.h>

int main() {
	
	char stringOrnegi[20];
	
	fgets(stringOrnegi, 20, stdin);
	
	printf("%s", stringOrnegi);
	
	return 0;
}
```

scanf

scanf kullanımında dikkat edilmesi gereken bir şey vardır. Eğer ki aşağıdaki gibi bir input alırsanız sadece boşluk bıraktığınız kısma kadar input alır.

```cpp
#include <stdio.h>

int main() {
	
	char stringOrnegi[20];
	

        printf("cumle ornegi giriniz: ");
	scanf("%s", &stringOrnegi);
	
	printf("%s", stringOrnegi);
	
	return 0;
}
```

Programın çıktısı:

```cpp
cumle ornegi giriniz: bugun hava cok guzel
bugun
```

Böyle bir durumun yaşanmaması için aşağıdaki gibi input alınır:

```cpp
#include <stdio.h>

int main() {
	
	char stringOrnegi[20];

        printf("cumle ornegi giriniz: ");
	scanf("%[^\n]", &stringOrnegi);
	
	printf("%s", stringOrnegi);
	
	return 0;
}
```

Programın çıktısı:

```cpp
cumle ornegi giriniz: bugun hava cok guzel
bugun hava cok guzel
```
