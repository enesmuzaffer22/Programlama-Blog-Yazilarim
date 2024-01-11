
1) 10 adet eleman içeren bir diziyi ekrana yazdıran C programını yazınız.

```cpp
int i, a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
	
	for(i = 0; i < 10; i++) {
		
		printf("%d. indeks: %d \n", i, a[i]);
		
	}
```

2) Kullanıcıdan 10 adet tamsayı girmesini isteyen, girilen değerleri bir dizide tutan ve  
sonrasında diziyi ekrana yazdıran C programını yazınız.

```cpp
int i, a[10];

for(i = 0; i < 10; i++) {
	
	printf("bir sayi giriniz: ");
	scanf("%d", &a[i]);
	
}
	
for(i = 0; i < 10; i++) {
	
	printf("%d. indeks: %d \n", i, a[i]);
	
}
```

3) Kullanıcıdan 10 adet tamsayı girmesini isteyen, girilen değerleri bir dizide tutan ve  
sonrasında diziyi tersten ekrana yazdıran C programını yazınız.

```cpp
int i, a[10];

for(i = 0; i < 10; i++) {
	
	printf("bir sayi giriniz: ");
	scanf("%d", &a[i]);
	
}

for(i = 9; i >= 0; i--) {
	
	printf("%d. indeks: %d \n", i, a[i]);
	
}
```

4) Bir dizideki negatif elemanları yazdıran C programını yazınız.

```cpp
int i, a[10] = {1, 2, -3, 4, -5, 6, 7, -8, 9, 0};
	
	for(i = 0; i < 10; i++) {
		
		if(a[i] < 0) {
		
		printf("%d. indeks: %d \n", i, a[i]);
		
	        }
		
        }
```

5) Bir dizideki elemanların toplamını ve ortalamasını ekrana yazdıran C programını yazınız.

```cpp
int i, a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
float toplam = 0, ort;
	
	
	for(i = 0; i < 10; i++) {
		
		toplam = toplam + a[i];
		
	}

ort = toplam / 10;

printf("toplam: %f | ortalamasi: %f", toplam, ort);
```

6) Bir dizideki tek sayıların adetini ekrana yazdıran C programını yazınız.

```cpp
int i, toplam = 0, a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
	
	for(i = 0; i < 10; i++) {
		
		if((a[i] % 2) == 1) {
		
		toplam++;
		
	}
		
	}

printf("tek sayilarin adedi: %d", toplam);
```

7) Bir dizideki maksimum ve minimum elemanı ekrana yazdıran C programını yazınız.

```cpp
int i, max, min, a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
	
	max = a[1];  //max ve min degerleri rastgele verilebilir
	min = a[1];  //cunku program butun listeyi karsilastiracaktir
	
	for(i = 0; i < 10; i++) {
		
		if(max < i) {
		
		max = i;
		
	}
		
		if(min > i) {
		
		min = i;
		
	}
		
	}
	
printf("max: %d | min: %d", max, min);
```

8) Kullanıcıdan en fazla 10 basamaklı bir sayı girmesini isteyen, bu sayının tersini ekrana  
yazdıran C programını yazınız.  
Beklenen çıktı:  
En fazla 10 basamakli bir sayi yaziniz: 234  
Sayinin tersi: 432

```cpp
int s, a[10], i = 0;

printf("bir sayi giriniz: ");
scanf("%d", &s);


printf("sayinin tersi: ");

while(s != 0) {
	
	a[i] = s % 10;
	printf("%d", a[i]);
	s = s / 10; 
	i++;

}
```
