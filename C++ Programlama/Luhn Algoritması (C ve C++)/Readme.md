

## Luhn Algoritması Nedir ?

Luhn Algoritması **kart numaralarını doğrulamak** amacıyla kullanılır. Kartın **son hanesi ile diğer haneler arasında yapılan işlemlerin sonucu** karşılaştırılır ve bir sonuca varılır. Eğer sonuç ile son hane eşleşirse kart numarası geçerlidir.

## Luhn Algoritması Nasıl Çalışır ?

Öncelikle kart numarasının son hanesi bir kenara not edilir ve yapılacak olan işlemlere dahil edilmez. Bu nedenle bu son haneye **sağlama hanesi** denir. Geriye kalan 15 hanede sıralamaya göre tek sayıdaki haneler 2 ile çarpılır. Çarpma işlemleri yapıldıktan sonra 9’dan büyük olan her sayıdan 9 çıkarılır. Sonraki adımda elde edilen sayılar toplanır. Elde edilen toplam **10’un katı** olmalıdır. Eğer toplam 10’un katı değil ise toplamın üzerine sayı eklenir ve 10’un katı olan bir sayı elde edilir. Bunun sonucunda eklediğimiz sayı, sağlama hanesi ile karşılaştıracağımız sayıdır (Eğer toplam zaten 10’un katı ise herhangi bir sayı eklenmez ve karşılaştıracağımız sayı 0 olur).

Bir örnek ile algoritmayı kavramaya çalışalım:

![](https://i.hizliresim.com/7219wav.jpg)

**5472008906787107** numarası bizim kart numaramız olsun. Yukarıda anlattığımız gibi işlemleri uyguladığımızda elde ettiğimiz toplam “**53**” olur. Görüldüğü üzere toplam **10’un katı değil**. Bu nedenle bu toplamı 10’un katı yapmak için üzerine bir sayı eklememiz gerekir **(53 + x)**. Bunun için 53’e **7** eklememiz gerekir **(53 + 7 = 60)**. Bunun sonucunda sağlama hanesiyle karşılaştıracağımız sayıyı bulmuş olduk. Görüldüğü üzere sağlama hanesi ile bulduğumuz sayı birbirine eşittir. Bu durumda bu kart numarası geçerli bir kart numarasıdır.

## Luhn Algoritması ile Kart Numarasının Geçerliliğini Kontrol Eden Program

```cpp
//C++

#include <iostream>
#include <cstring>
#include <string>
using namespace std;

int luhnKontrol(string kartNumarasi, int bas);

int luhnKontrol(string kartNumarasi, int bas) {
	
	int i;
	int sayi, toplam = 0, saglamaHanesi;
	
	for(i = bas - 1; i >= 0; i--) {
		
		sayi = kartNumarasi[i] - '0'; /* i. indeksteki karakter sayiya donusturulur ve
		"sayi" degiskenine atanir */
		
		if((i % 2) == 0) {
			
			/* cift sayi olan indeksteki sayiyi iki ile carptik */
			
			if((sayi * 2) > 9) {
				
				/* eger sonuc 9 dan buyuk ise 9 cikardik ve toplam degiskenine
				ekledik */
				
				toplam += (sayi * 2) - 9;
				
			}
			
			else {
				
				/* eger sonuc 9 dan buyuk degilse toplam degiskenine ekledik */
				
				toplam += sayi * 2;
				
			}
			
		}
		
		else {
			
			/* tek sayi olan indeksteki sayiyi toplam degiskenine ekledik */
			
			toplam += sayi;
			
		}
		
	}
	
	toplam *= 9; // toplam degiskenini 9 ile carptik
	saglamaHanesi = toplam % 10; // saglama hanesini bulmak icin toplamin 10 ile modunu aldik
	
	if(saglamaHanesi == (kartNumarasi[bas])) {
		
		/* saglama hanesi kartin son numarasina esit ise fonksiyon "1" dondurur */
		
		return 1;
		
	}
	
	else {
		
		/* saglama hanesi kartin son numarasina esit degil ise fonksiyon "0" dondurur */
		
		return 0;
		
	}
	
}

int main() {
	
	string kartNumarasi;
	int bas = -1, kontrol;
	
	while(bas != 16) {
		
		/* 16 basamakli kart numarasi girilene kadar donguden cikilamaz */
		
		cout << "Kart numarasini giriniz: ";
		cin >> kartNumarasi;
		
		bas = kartNumarasi.length(); 
		
	}
	
	kontrol = luhnKontrol(kartNumarasi, 16);
	
	if(kontrol == 1) {
		
		/* fonksiyondan donen deger (kontrol) "1" ise kartin gecerli oldugu ekrana çikti
		olarak verilir */
		
		cout << "Kart numarasi gecerlidir.";
		
	}
	
	else {
		
		/* fonksiyondan donen deger (kontrol) "0" ise kartin gecersiz oldugu ekrana çikti
		olarak verilir */
		
		cout << "kart numarasi gecersizdir.";
		
	}
	
	return 0;
}
```

```cpp
//C

#include <stdio.h>
#include <string.h>

int luhnKontrol(char kartNumarasi[], int bas);

int luhnKontrol(char kartNumarasi[], int bas) {
	
	int i;
	int sayi, toplam = 0, saglamaHanesi;
	
	for(i = bas - 1; i >= 0; i--) {
		
		sayi = kartNumarasi[i] - '0'; /* i. indeksteki karakter sayiya donusturulur ve
		"sayi" degiskenine atanir */
		
		if((i % 2) == 0) {
			
			/* cift sayi olan indeksteki sayiyi iki ile carptik */
			
			if((sayi * 2) > 9) {
				
				/* eger sonuc 9 dan buyuk ise 9 cikardik ve toplam degiskenine
				ekledik */
				
				toplam += (sayi * 2) - 9;
				
			}
			
			else {
				
				/* eger sonuc 9 dan buyuk degilse toplam degiskenine ekledik */
				
				toplam += sayi * 2;
				
			}
			
		}
		
		else {
			
			/* tek sayi olan indeksteki sayiyi toplam degiskenine ekledik */
			
			toplam += sayi;
			
		}
		
	}
	
	toplam *= 9; // toplam degiskenini 9 ile carptik
	saglamaHanesi = toplam % 10; // saglama hanesini bulmak icin toplamin 10 ile modunu aldik
	
	if(saglamaHanesi == (kartNumarasi[bas])) {
		
		/* saglama hanesi kartin son numarasina esit ise fonksiyon "1" dondurur */
		
		return 1;
		
	}
	
	else {
		
		/* saglama hanesi kartin son numarasina esit degil ise fonksiyon "0" dondurur */
		
		return 0;
		
	}
	
}

int main() {
	
	char kartNumarasi[16];
	int bas = -1, kontrol;
	
	while(bas != 16) {
		
		/* 16 basamakli kart numarasi girilene kadar donguden cikilamaz */
		
		printf("Kart numarasini giriniz: ");
		scanf(" %s", &kartNumarasi);
		
		bas = strlen(kartNumarasi); 
		
	}
	
	kontrol = luhnKontrol(kartNumarasi, 16);
	
	if(kontrol == 1) {
		
		/* fonksiyondan donen deger (kontrol) "1" ise kartin gecerli oldugu ekrana çikti
		olarak verilir */
		
		printf("Kart numarasi gecerlidir.");
		
	}
	
	else {
		
		/* fonksiyondan donen deger (kontrol) "0" ise kartin gecersiz oldugu ekrana çikti
		olarak verilir */
		
		printf("Kart numarasi gecersizdir.");
		
	}
	
	return 0;
}
```
