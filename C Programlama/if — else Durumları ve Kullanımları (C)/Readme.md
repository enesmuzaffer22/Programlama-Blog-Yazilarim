
# if

if kelimesinin Türkçe karşılığı “eğer” dir. if, bir koşula bağlı olarak işlenecek kodlar için kullanılır. Örneğin:
```cpp
#include <stdio.h>

int main() {

	int a = 5, b = 4;

	if(a > b) {
		printf(“a b den buyuktur”);
	}

return 0;
}
```

Yukarıdaki örneğimizde a, b olarak iki değişken tanımladık. Sonrasında ise bir koşul belirledik. Eğer a b’den büyükse “a b den buyuktur” yazdırır. Örnekte de görüldüğü üzere a b’den büyüktür ( 5 > 4 ). Bu durumda ekrana aşağıdaki çıktıyı vericektir.

```cpp
a b den buyuktur
```

Sonuç olarak if ifadesini aşağıdaki gibi özetleyebiliriz:

```cpp
if(kosulIfadesi) {..islenecekKodlar;..}
```

# if — else

if — else ifadesinin if ifadesinden tek farkı, koşul sağlanmaz ise koşulun sağlanmadığı durum için yazılan kodlar işlenir. else kelimesinin Türkçe karşılığı “aksi halde, başka”dır. Örneğin:

```cpp
#include <stdio.h>

int main() {

	int a = 5, b = 4;

	if(a < b) {
		printf(“b a dan buyuktur”);
	}

	else {
		printf(“a b den buyuktur”);
	}

	return 0;  
}
```

Yukarıdaki örnekte if ifadesinin içindeki koşul sağlanmaz ve koşulun sağlanmadığı duruma yani “else” ifadesine geçilir. Programa ise aşağıdaki çıktı verilir:

```cpp
a b den buyuktur
```

Sonuç olarak else ifadesini aşağıdaki gibi özetleyebiliriz:

```cpp
if(kosulIfadesi) {
.
.
islenecekKodlar;
.
.
}

else {
.
.
islenecekKodlar;
.
.
}
```

# if — else if

if — else if birden fazla koşullu ifadeyi belirtmek için kullanılır. Örneğin:

```cpp
#include <stdio.h>

int main() {

int a = 5, b = 4;

if(a < b) {

printf("b a dan buyuktur"); 

}

else if(a == b) {

printf("b a ya esittir"); 

}

else if(a > b) {

printf("a b den buyuktur"); 

}

return 0;
}
```

Yukarıdaki örnekte birden fazla koşullu ifade kullandık. Doğru koşul sağlandığında ise aşağıdaki gibi bir çıktı verdi:

```cpp
a b den buyuktur
```

# Çok Önemli Not:

Birden fazla koşullu ifadeyi “else if” yerine “if” kullanarak yazarsanız, program koşulları doğru olan bütün kodları işler. Örneğin:

```cpp
#include <stdio.h>

int main() {

int a = 5, b = 4;

if(b < a) {

printf("a b den buyuktur 1. ifade \n");   // "\n" alt satira geçmek icin kullanilir

}

if(a == b) {

printf("b a ya esittir 2. ifade \n"); 

}

if(a > b) {

printf("a b den buyuktur 3. ifade \n"); 

}

return 0;
}
```

Yukarıdaki örnek aşağıdaki gibi çıktı vericektir:

```cpp
a b den buyuktur 1. ifadea b den buyuktur 3. ifade
```

Eğer yukarıdaki örneği aşağıdaki gibi yazarsanız, koşulu doğru olan kodları işlediğinde diğer koşulları önemsemiyecektir.

```cpp
#include <stdio.h>

int main() {

int a = 5, b = 4;

if(b == a) {

printf("b a ya esittir 1. ifade \n");

}

else if(b < a) {

printf("a b den buyuktur 2. ifade \n"); 

}

else if(a > b) {

printf("a b den buyuktur 3. ifade \n"); 

}

return 0;
}
```

Programın çıktısı aşağıdaki gibi olucaktır:

```cpp
a b den buyuktur 2. ifade
```

# if İçinde if, else if, if — else

Koşul sağlandığı zaman ek olarak bir koşul daha koymak için if içinde if, else if, if — else ifadeleri yazılır. Örneğin:

```cpp
#include <stdio.h>

int main() {

int a = 5, b = 4;

if(a > b) {

printf("a b den buyuktur \n");

if((a % 2) == 1) {   

printf("a tek sayidir");
}

else {

printf("a cift sayidir"); 

}

}

else {

printf("b a dan buyuktur \n");

if((a % 2) == 1) {   

printf("b tek sayidir");

}

else {

printf("b cift sayidir"); 

}

}

return 0;
}
```

Yukarıdaki örnekte büyük sayının tek mi çift mi olduğunu inceledik. İlk olarak a ve b’nin büyüklük kıyaslamasını yaptık. Sonrasında ise büyük olan sayının tek mi çift mi olduğunu inceledik.

Program aşağıdaki gibi çıktı verir:

```cpp
a b den buyuktura tek sayidir
```
