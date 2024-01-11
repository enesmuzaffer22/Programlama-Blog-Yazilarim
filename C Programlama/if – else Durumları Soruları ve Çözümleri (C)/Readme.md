
1) Kullanıcıdan üç sayı girmesini isteyen, girilen sayılardan en küçük olan değeri ekrana  
yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int a, b, c;

printf("uc sayi giriniz: ");
scanf("%d%d%d", &a, &b, &c);

if(a < b && b < c) {
	
	printf("%d en kucuk sayidir", a);
	
}

else if(c < b && b < a) {
	
	printf("%d en kucuk sayidir", c);
	
}

else if(c < a && a < b) {
	
	printf("%d en kucuk sayidir", c);
	
}

else if(a < c && c < b) {
	 
	printf("%d en kucuk sayidir", a);
	
}

else if(b < c && c < a) {
	
	printf("%d en kucuk sayidir", b);
	
}

else if(b < a && a < c) {
	
	printf("%d en kucuk sayidir", b);
	
}

return 0;
}
```

2) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayı pozitif ise ekrana 1, negatif ise -1 ve  
0 ise ekrana 0 yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {

int a;

printf("bir sayi giriniz: ");
scanf("%d", &a);

if(a < 0) {
	
	printf("-1");
	
}

else if(a > 0) {
	
	printf("1");
	
}

else if(a == 0) {
	
	printf("0");
	
}

return 0;
}
```

3) Kullanıcıdan bir sıcaklık değeri girmesini isteyen, girilen sıcaklık değeri için aşağıdaki aralıklara göre ekrana uygun mesajı veren C programını yazınız. (Aşağıdaki aralıklarda alt sınırlar aralığa dâhil, üst sınırlar dâhil değildir.) • Sıcaklık < 0 → Dondurucu • Sıcaklık 0-10 → Çok soğuk • Sıcaklık 10-20 → Soğuk • Sıcaklık 20-30 → Normal • Sıcaklık 30-40 → Sıcak • Sıcaklık >=40 → Çok sıcak

```cpp
#include <stdio.h>

int main() {

int s;

printf("sicaklik degeri giriniz: ");
scanf("%d", &s);

if(s < 0) {
	
	printf("dondurucu");
	
}

else if(s >= 0 && s < 10) {
	
	printf("cok soguk");
	
}

else if(s >= 10 && s < 20) {
	
	printf("soguk");
	
}

else if(s >= 20 && s < 30) {
	
	printf("normal");
	
}

else if(s >= 30 && s < 40) {
	
	printf("sicak");
	
}

else if(s >= 40) {
	
	printf("cok sicak");
	
}

return 0;
}
```

4) Kullanıcıdan üç adet kenar uzunluğu girmesini isteyen, girilen uzunluklarla bir üçgen çizilip  
çizilemeyeceğini kontrol eden ve sonucu ekrana yazdıran C programını yazınız. (Üç kenarın  
bir üçgen oluşturabilmesi için, herhangi iki kenarın toplamının mutlaka üçüncü kenarın  
değerinden büyük olması gerekmektedir.)

```cpp
#include <stdio.h>

int main() {

int a, b, c;

printf("3 tane deger giriniz: ");
scanf("%d%d%d", &a, &b, &c);

if((a + b) > c && (a + c) > b && (b + c) > a) {
	
	printf("ucgen olusur");
	
}

else {
	
	printf("ucgen olusmaz");
	
}

return 0;
}
```

5) Kullanıcıdan X-Y koordinat düzlemindeki bir noktanın X ve Y değerlerini girmesini  
isteyen, girilen koordinat değerlerine göre bu noktanın kaçıncı bölgede olduğunu ekrana  
yazdıran C programını yazınız. (Nokta eksenler üzerinde ise çıktı olarak “X ekseni uzerinde”  
veya “Y ekseni uzerinde” yazdırınız, orijinde ise “Orijinde” diye çıktı veriniz.)

```cpp
#include <stdio.h>

int main() {

int x, y;

printf("x degerini giriniz: ");
scanf("%d", &x);
printf("y degerini giriniz: ");
scanf("%d", &y);

if(x > 0 && y > 0) {
	
	printf("birinci bolge");
	
}

else if(x < 0 && y > 0) {
	
	printf("ikinci bolge");
	
}

else if(x < 0 && y < 0) {
	
	printf("ucuncu bolge");
	
}

else if(x > 0 && y < 0) {
	
	printf("dorduncu bolge");
	
}

else if(x == 0) {
	
	printf("y ekseni uzerinde");
	
}

else if(y == 0) {
	
	printf("x ekseni uzerinde");
	
}

else if(x == 0 && y == 0) {
	
	printf("orijinde");
	
}

return 0;
}
```

6) Kullanıcıdan aşağıdaki örnekte olduğu gibi iki sayı ve bu sayılar üzerinde yaptırmak istediği  
işlemin operatörünü girmesini isteyen, girilen sayılar üzerinde istenen işlemi yapıp sonucu  
ekrana yazdıran C programını yazınız.  
Örnek; Ilk sayiyi giriniz: 7  
Ikinci sayiyi giriniz: 5  
Yapmak istediginiz islemin operatorunu (+, -, /, *, %) giriniz: *  
Sonuc: 7 * 5 = 35

```cpp
#include <stdio.h>

int main() {

int s1, s2, mod;
float sonuc;
char op;


printf("yapmak istediginiz islemin operatorunu giriniz giriniz(+, -, *, /, %%): ");
scanf(" %c", &op);
printf("iki sayi giriniz: ");
scanf("%d%d", &s1, &s2);


if(op == '+') {
	
sonuc = s1 + s2;
printf("sonuc: %f", sonuc);
	
}


else if(op == '-') {
	
sonuc = s1 - s2;
printf("sonuc: %f", sonuc);

	
}


else if(op == '*') {
	
sonuc = s1 * s2;
printf("sonuc: %f", sonuc);

	
}


else if(op == '/') {
	
sonuc = (float)s1 / s2;
printf("sonuc: %f", sonuc);

	
}


else if(op == '%') {
	
mod = s1 % s2;
printf("sonuc: %d", mod);

	
}


else {
	
	printf("islem icin yanlis operator girisi yaptiniz");
	
}

return 0;
}
```

7) Kullanıcıdan üç tamsayı girmesini isteyen, girilen değerlerden ortanca olan değeri ekrana  
yazdıran C programını yazınız.  
Örneğin; 5, 19, 7 girilirse ekrana 7 yazdırılmalıdır.  
5, 13, 5 girilirse ekrana 5 yazdırılmalıdır.  
5, 20, 20 girilirse ekrana 20 yazdırılmalıdır.  
5, 5, 5 girilirse ekrana 5 yazdırılmalıdır.

```cpp
#include <stdio.h>

int main() {

int s1, s2, s3, ort;

printf("uc sayi giriniz: ");
scanf("%d%d%d", &s1, &s2, &s3);

if(s1 > s2 && s2 > s3) {
	
	printf("ort: %d", s2);
	
}

else if(s2 > s1 && s1 > s3) {
	
	printf("ort: %d", s1);
	
}

else if(s3 > s2 && s2 > s1) {
	
	printf("ort: %d", s2);
	
}

if(s2 > s3 && s3 > s1) {
	
	printf("ort: %d", s3);
	
}

return 0;
}
```

8) Kullanıcıya aşağıdaki örnekte olduğu gibi alanını hesaplamak istediği geometrik cismin  
hangisi olduğunu soran, kullanıcının seçtiği geometrik cisme göre kullanıcıdan gerekli değerleri  
girmesini isteyen, girilen değerlere göre seçilen cismin alanını hesaplayan ve sonucu ekrana  
yazdıran C programını yazınız.  
Örnek1; 1- Dikdortgen  
2- Ucgen  
3- Daire  
Alanini hesaplamak istediginiz cismin numarasini giriniz: 2  
Yuksekligi giriniz: 5  
Taban uzunlugunu giriniz: 3  
Alan = 7.5  
Örnek2; 1- Dikdortgen  
2- Ucgen  
3- Daire  
Alanini hesaplamak istediginiz cismin numarasini giriniz: 3  
Yaricapi giriniz: 5  
Alan = 28.26

```cpp
#include <stdio.h>

int main() {

float sonuc, r, a, b, pi = 3.14;
int islem;

printf("1- dikdortgen: \n");
printf("2- ucgen: \n");
printf("3- daire: \n");

printf("yapmak istediginiz islemi giriniz: ");
scanf("%d", &islem);

if(islem == 1) {
	
	printf("iki sayi giriniz: ");
	scanf("%f%f", &a, &b);
	
	sonuc = a * b;
	
	printf("sonuc: %f", sonuc);
	
}

else if(islem == 2) {
	
	printf("yukseklik ve taban uzunluk giriniz: ");
	scanf("%f%f", &a, &b);
	
	sonuc = (a * b) / (float)2;
	
	printf("sonuc: %f", sonuc);
	
}

else if(islem == 3) {
	
	printf("yaricap giriniz: ");
	scanf("%f", &r);
	
	sonuc = pi * r * r;
	
	printf("sonuc: %f", sonuc);
	
}

return 0;
}
```

9) Kullanıcıya aşağıdaki örnekte olduğu gibi sıcaklık değerini hangi ölçekten hangi ölçeğe  
çevirmek istediğini soran, kullanıcının seçtiği çevirim için gerekli değeri girmesini isteyen ve  
aşağıdaki formüle göre çevirme işlemini yaparak sonucu ekrana yazdıran C programını yazınız.  
Örnek: Fahrenheit’dan Celsius’a çevirmek için F giriniz.  
Celsius’dan Fahrenheit’a çevirmek için C giriniz.  
Seciminizi giriniz (C veya F): C  
Celsius değerini giriniz: 40  
Girdiginiz değerin Fahrenheit karsiligi = 104

```cpp
#include <stdio.h>

int main() {

float ce, fa, sonuc;
char s;


printf("Fahrenheit dan Celsius a cevirmek icin F giriniz \n");
printf("Celsius dan Fahrenheit a cevirmek icin C giriniz \n");

printf("seciminizi giriniz (F ve C): ");
scanf(" %c", &s);

if(s == 'F' || s == 'f') {
	
	printf("Fahrenheit degeri giriniz: ");
	scanf("%f", &fa);
	
	sonuc = (fa - 32) * 0.5;
	
	printf("sonuc: %f", sonuc);
	
}

else if(s == 'C' || s == 'c') {
	
	printf("Celsius degeri giriniz: ");
	scanf("%f", &ce);
	
	sonuc = (ce * 1.8) + 32;
	
	printf("sonuc: %f", sonuc);
	
}

return 0;
}
```

10) Kullanıcıdan iki sayı girmesini isteyen, girilen sayılardan hangisinin X ekseni üzerinde 0’a  
daha yakın olduğunu ekrana yazan C programını yazınız.  
Örneğin; 5 ve 19 girilirse ekrana 5 yazdırılmalıdır.  
-10 ve 13 girilirse ekrana -10 yazdırılmalıdır.

```cpp
#include <stdio.h>

int main() {

int s1, s2, sayi1, sayi2;

printf("iki sayi giriniz: ");
scanf("%d%d", &sayi1, &sayi2);

if(sayi1 < 0) {
	
	s1 = sayi1 * -1;
	
	if(sayi2 < 0) {
		
		s2 = sayi2 * -1;
		
	}
		
	if(s1 > s2) {
		
		printf("%d sifira daha yakindir", sayi2);
		
	}
	
	else {
		
		printf("%d sifira daha yakindir", sayi1);
		
	}
		
}

else if(sayi2 < 0) {
	
	s2 = sayi2 * -1;
	
	if(sayi1 < 0) {
		
		s1 = sayi1 * -1;
		
	}
		
	if(s1 > s2) {
		
		printf("%d sifira daha yakindir", sayi2);
		
	}
	
	else {
		
		printf("%d sifira daha yakindir", sayi1);
		
	}
		
}


else if(sayi1 > sayi2) {
		
	printf("%d sifira daha yakindir", sayi2);
		
}

	
else if (sayi2 > sayi1){
		
	printf("%d sifira daha yakindir", sayi1);
		
}

return 0;
}
```

11) Kullanıcıdan sırasıyla Matematik, Fizik, Giriş ve Programlama derslerinden aldığı 0-100  
arasındaki (sınırlar dâhil) notları girmesini isteyen, girilen notlardan en büyük olanı, en küçük  
olanı ve tüm notların ortalamasını ekrana yazdıran, son olarak tüm notların ortalaması 70 ve  
üzeri ise ekrana “Basarili” değilse “Basarisiz” yazdıran C programını yazınız.

```cpp
#include <stdio.h>

int main() {	

int m,f,g,p;

	printf("Sirasiyla matematik, fizik, giris ve programlama derslerine ait 0 ila 100 arasi notlarinizi giriniz:\n");
	scanf("%d%d%d%d" , &m, &f, &g, &p);
	
	int max = m;
	if( max < f )
    	max = f;
	if( max < g )
    	max = g;
	if( max < p )
    	max = p;
	
	printf("\nEn yuksek not alinan dersin notu: %d" , max);
	
	int min=m;
	if(min>f)
		min=f;
	if(min>g)
		min=g;
	if(min>p)
		min=p;
		
	printf("\nEn dusuk alinan dersin notu: %d", min);
	
	float ort=(float)(m+f+g+p)/4;
	printf("\nTum derslerin not ortalamasi: %f", ort);
	
	if(ort>=70)
		printf("\nBasarili");
	else
		printf("\nBasarisiz");

return 0;
}
```
