
1) 1’den 9’a kadar sayılar için çarpım tablosu hazırlayıp ekrana aşağıdaki gibi yazdıran C  
programını yazınız.

```cpp
int i, j;

for(i = 1; i < 10; i++) {
	
	printf("\t%d", i);
	
}

printf("\n");

for(i = 1; i <= 10; i++) {
	
	printf("--------");
	
}

printf("\n");

for(i = 1; i < 10; i++) {
	
	printf("%d|", i);
	
	for(j = 1; j < 10; j++) {
		
		printf("\t%d", i * j);
		
	}
	
	printf("\n");
```

2) Kullanıcıdan bir tamsayı alan ve girilen sayının asal sayı olup olmadığın kontrol ederek  
sonucu ekrana yazdıran C programını yazınız.

```cpp
int s, i, asalKontrol = 0;

printf("bir sayi giriniz: ");
scanf("%d", &s);

if(s == 0 || s < 0 || s == 1) {
	
	printf("%d asal sayi degildir", s);
	
}		


for(i = 2; i < s; i++) {
	
	if((s % i) == 0) {
		
		asalKontrol = 1;
		break;
		
	}
	
}
	
if(asalKontrol == 1)
printf("%d asal sayi degildir", s);

else
printf("%d asal sayidir", s);
```

3) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının kaç basamaklı bir sayı olduğunu  
(rakam sayısını) ekrana yazdıran C programını yazınız.  
Örneğin; 342761 girilirse “Girilen sayi 6 basamaklidir” yazdırılmalıdır.

```cpp
int s, sayi, bas = 0, i;

printf("bir sayi giriniz: ");
scanf("%d", &s);

sayi = s;

while(s > 0) {
	
	s = s / 10;
	bas = bas + 1;
	
}

printf("%d sayisi %d basamaklidir", sayi, bas);
```

4) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının rakamlarının toplamını  
hesaplayarak sonucu ekrana yazdıran C programını yazınız.  
Örneğin; 1234 girilirse “Rakamlarin toplam = 10” yazdırılmalıdır.

```cpp
int s, sayi, toplam = 0, i, k;

printf("bir sayi giriniz: ");
scanf("%d", &s);

sayi = s;

while(s > 0) {
	
	k = s % 10;
	toplam = toplam + k;
	s = s / 10;
	
}
	
printf("%d sayisinin rakamlari toplami: %d", sayi, toplam);
```

5) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayıyı terse çevirip ekrana yazdıran C  
programını yazınız.  
Örneğin; 12345 girilirse “Girilen sayinin tersi = 54321” yazdırılmalıdır.

```cpp
int s, k, sayi;

printf("bir sayi giriniz: ");
scanf("%d", &s);

sayi = s;

printf("%d sayisinin tersi: ", sayi);
while(s > 0) {
	
	k = s % 10;
	printf("%d", k);
	s = s / 10;
	
}
```

6) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının palindrom sayı olup olmadığını  
kontrol ederek sonucu ekrana yazdıran C programını yazınız. (Palindrom sayı, tersi kendisiyle  
aynı olan sayılardır.)  
Örneğin; 34543 girilirse “Girilen sayi palindrom sayidir” yazdırılmalıdır.  
35443 girilirse “Girilen sayi palindrom sayi değildir” yazdırılmalıdır.

```cpp
int s1, kalan, s2 = 0, sayi; 

printf("bir sayi giriniz: ");
scanf("%d", &s1);

sayi = s1;

while(s1 > 0) { //123456
	
	kalan = s1 % 10;
	s2 = s2 * 10 + kalan;
	s1 = s1 / 10;
	
}

if(sayi == s2) {
	
	printf("%d sayisi palindrom sayidir", sayi);
	
}

else {
	
	printf("%d sayisi palindrom sayi degildir", sayi);
	
}
```

7) Kullanıcıdan bir tamsayı N değeri girmesini isteyen ve Fibonacci serisinin ilk N terimini  
ekrana yazdıran C programını yazınız. Fibonacci serisi ilk terimi 0, ikinci terimi 1 olan, sonraki  
terimlerinin değeri kendisinden önceki iki terimin toplanması ile elde edilen bir seridir.

```cpp
int n, i, a = 0, b = 1, c;
 
printf("n degeri: ");
scanf("%d",&n);
 
printf("fibonacci dizisi: ");
for(i = 1; i <= n; i++) {
 
 printf("%d ",a);
 c = a + b;
 a = b;
 b = c;
 
}
```

8) Kullanıcıdan bir tamsayı N değeri girmesini isteyen, harmonik serinin ilk N terimini ve bu  
terimlerin toplamını ekrana yazdıran C programını yazınız.

```cpp
int n, sayac = 1;
float a = 1, b = 2;
 
printf("n degeri giriniz: ");
scanf("%d", &n);
 
 while(sayac <= n) {
 	
	a = a + (1 / b); //a = 1 + 1 / 2
	sayac++;
	b++;

 }

printf("toplam = %f", a);
```

9) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının pozitif tam bölenlerini (kendisi  
hariç) ve bu sayının Mükemmel sayı olup olmadığını ekrana yazdıran C programını yazınız.  
(Mükemmel sayı, kendisi hariç pozitif tam bölenlerinin toplamı kendisine eşit olan sayılara  
denir. Örneğin; 6 sayısının kendisi hariç pozitif tam bölenleri 1, 2 ve 3’tür ve 1 + 2 + 3 = 6  
olduğu için 6 sayısı mükemmel sayıdır.)  
Örnek; Bir sayi giriniz: 56  
Pozitif tam bölenleri (kendisi haric) = 1 2 4 7 8 14 28  
Toplam = 64  
56 sayisi mükemmel sayi değildir

```cpp
int s, i, bolenToplam = 0;

printf("bir sayi giriniz: ");
scanf("%d", &s);

	
printf("%d sayisini bolen sayilar: ", s);
for(i = 1; i < s; i++) {
	
	if((s % i) == 0) {
		
		printf(" %d ", i);
		bolenToplam = bolenToplam + i;
		
	}
	
}

if(bolenToplam == s) {
	
	printf("\n%d sayisi mukemmel sayidir", s);
	
}

else {
	
	printf("\n%d sayisi mukemmel sayi degildir", s);
	
}
```

10) Kullanıcıdan bir tamsayı girmesini isteyen, girilen sayının Armstrong sayı olup olmadığını  
kontrol eden ve sonucu ekrana yazdıran C programını yazınız. (Armstrong sayı, sayının tüm  
rakamlarının, sayının basamak sayısı kadar kuvvetlerinin toplamı sayının kendisine eşit olan  
sayılara denir. Örneğin; 153 = 13 + 53 + 33  
olduğu için 153 Armstrong sayıdır, 45 ≠ 42 + 52  
olduğu için de 45 Armstrong sayı değildir.)

```cpp
int s, i, b, bas = 0, sayi, carpim = 1, toplam = 0, k;

printf("bir sayi giriniz: ");
scanf("%d", &s);

sayi = s; 

while(s > 0) {
	
	s = s / 10; 
	bas++;
	
}

s = sayi; 

while(s > 0) {
	
	k = s % 10;
	
	for(i = 1; i <= bas; i++) {
		
		carpim = carpim * k;
	
	}
	
	toplam = toplam + carpim;
	
	s = s / 10;	
	carpim = 1;
		
}

s = sayi;

if(s == toplam) {
	
	printf("%d sayisi armstrong sayidir", s);
	
}

else {
	
	printf("%d sayisi armstrong sayi degildir", s);
	
}
```

11) Kullanıcıdan bir tamsayı girmesin isteyen, girilen sayının Güçlü sayı olup olmadığını  
kontrol eden ve sonucu ekrana yazdıran C programını yazınız. (Güçlü sayı, rakamlarının  
faktöriyellerinin toplamı kendisine eşit olan sayılara denir. Örneğin; 145 = 1! + 4! + 5! olduğu  
için 145 Güçlü sayıdır.)

```cpp
int s, i, sayi, f = 1, toplam = 0, k;

printf("bir sayi giriniz: ");
scanf("%d", &s);

sayi = s; 

while(s > 0) {
	
	k = s % 10;
	
	for(i = 1; i <= k; i++) {
		
		f = f * i;
	
	}
	
	toplam = toplam + f;
	
	s = s / 10;	
	f = 1;
		
}

s = sayi;

if(s == toplam) {
	
	printf("%d sayisi guclu sayidir", s);
	
}

else {
	
	printf("%d sayisi guclu sayi degildir", s);
	
}
```

12) Kullanıcıya aşağıdaki örnekte olduğu gibi bir işlem menüsü sunan, kullanıcıdan bir işlem  
seçmesini ve iki sayı girmesini isteyen, kullanıcının girdiği sayılar üzerinde seçtiği işlemi yapıp  
sonucu ekrana yazdıran, daha sonra yeni bir işlem yapmak isteyip istemediğini soran, kullanıcı  
yeni işlem yapmak isterse aynı şekilde çalışmaya devam eden, kullanıcı yeni işlem yapmak  
istemezse aşağıdaki şekilde bir mesaj vererek sonlanan C programını yazınız.  
Örnek1; 1- Toplama  
2- Cikarma  
3- Bolme  
4- Carpma  
5- Mod alma  
Yapmak istediginiz islemin numarasini giriniz: 3  
Ilk sayiyi giriniz: 9  
Ikinci sayiyi giriniz: 2  
Sonuc: 4.5  
Yeni bir işlem yapmak ister misiniz (E veya H giriniz): H  
Gorusmek uzere!  
Örnek2; 1- Toplama  
2- Cikarma  
3- Bolme  
4- Carpma  
5- Mod alma  
Yapmak istediginiz islemin numarasini giriniz: 3  
Ilk sayiyi giriniz: 9  
Ikinci sayiyi giriniz: 2  
Sonuc: 4.5  
Yeni bir işlem yapmak ister misiniz (E veya H giriniz): E  
1- Toplama  
2- Cikarma  
3- Bolme  
4- Carpma  
5- Mod alma  
Yapmak istediginiz islemin numarasini giriniz: 5  
Ilk sayiyi giriniz: 7  
Ikinci sayiyi giriniz: 3  
Sonuc: 1  
Yeni bir işlem yapmak ister misiniz (E veya H giriniz): H  
Gorusmek uzere!

```cpp
int mod, s1, s2, op, i;
char cevap = 'e';
float sonuc;

while(cevap == 'E'  || cevap == 'e') {

printf("\n");
printf("1- toplama \n");
printf("2- cikarma \n");
printf("3- bolme \n");
printf("4- carpma \n");
printf("5- mod alma \n");
printf("\n");
printf("yapmak istediginiz islemi seciniz (1, 2, 3, 4, 5): ");
scanf("%d", &op);

printf("ilk sayiyi giriniz: ");
scanf("%d", &s1);
printf("ikinci sayiyi giriniz: ");
scanf("%d", &s2);

printf("\n");

switch(op) {
	
	case 1: sonuc = s1 + s2; printf("sonuc: %f \n", sonuc); break;
	
	case 2: sonuc = s1 - s2; printf("sonuc: %f \n", sonuc); break;
	
	case 3: sonuc = (float)s1 / s2; printf("sonuc: %f \n", sonuc); break;
	
	case 4: sonuc = s1 * s2; printf("sonuc: %f \n", sonuc); break;
	
	case 5: mod = s1 % s2; printf("sonuc: %d \n", mod); break;
	
}

printf("\n");

printf("yeni bir islem yapmak ister misiniz (e/h): ");
scanf(" %c", &cevap);

}

printf("\n");

printf("Gorusmek uzere!");
```
