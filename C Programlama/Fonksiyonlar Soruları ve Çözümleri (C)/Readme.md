
1) Parametre olarak iki virgüllü sayı alan ve toplamını hesaplayarak sonucu geri döndüren bir  
fonksiyon yazınız.

```cpp
float toplama(float, float);

float toplama(float s1, float s2) {
	
	return s1 + s2;
}

 int main() {   
 
 	float sonuc, a, b;
 	
 	printf("iki sayi giriniz: ");
 	scanf("%f%f", &a, &b);
 	
 	sonuc = toplama(a, b);
 	
 	printf("sonuc: %f", sonuc);
	
    return 0;    
 }    
```

2) Parametre olarak üç tamsayı alan ve ortalamasını hesaplayarak sonucu geri döndüren bir  
fonksiyon yazınız.

```cpp
 float ort(int, int, int);
 
 float ort(int s1, int s2, int s3) {
 	
 	float ortalama;
 	
 	ortalama = (float)(s1 + s2 + s3) / 3;
 	
 	return ortalama;
 }
 
 int main() {
 	
 	int a, b, c;
 	float ort_main;
 	
 	printf("uc sayi giriniz: ");
 	scanf("%d%d%d", &a, &b, &c);
 	
 	ort_main = ort(a, b, c);
 	
 	printf("sonuc: %f", ort_main);
 	
 	return 0;
 }
```

3) Taban (x) ve üs (y) değerlerini parametre olarak alan ve x üssü y değerini (xy) hesaplayarak  
sonucu geri döndüren bir fonksiyon yazınız.

```cpp
 int usluSayi(int, int);
 
 int usluSayi(int taban, int us) {
 	
 	int i, sonuc_usluSayi = 1;
 	
 	for(i = 1; i <= us; i++) {
 		
 		sonuc_usluSayi *= taban;
 		
	 }
	 
 	return sonuc_usluSayi;
 }
 
 
 int main() {
 	
 	int u, t, sonuc;
 	
 	printf("taban giriniz: ");
 	scanf("%d", &t);
 	printf("us giriniz: ");
 	scanf("%d", &u);
 	
 	sonuc = usluSayi(t, u);
 	
 	printf("sonuc: %d", sonuc);
 	
 }
```

4) İki tamsayı değişkeni parametre olarak alan maksimum değeri hesaplayarak sonucu geri  
döndüren bir fonksiyon yazınız.

```cpp
 int buyukSayi(int, int);
 
 int buyukSayi(int s1, int s2) {
 	
 	if(s1 > s2) {
 		
 		return s1;
 		
	 }
 	
 	else {
 		
 		return s2;
 		
	 }
 	
 }
 
 int main() {
 	
 	int a, b, sonuc;
 	
 	printf("iki sayi giriniz: ");
 	scanf("%d%d", &a, &b);
 	
 	sonuc = buyukSayi(a, b);
 	
 	printf("buyuk sayi: %d", sonuc);
 	
 }
```

5) Üç virgüllü sayıyı parametre olarak alan ve minimum değeri hesaplayarak sonucu geri  
döndüren bir fonksiyon yazınız.

```cpp
float kucukSayi(float, float, float);
 
float kucukSayi(float s1, float s2, float s3) {
 	
 	if(s1 > s2) {
 		
 		if(s3 > s2) {
 			
 			return s2;
 			
		 }
		 
		 else {
		 	
		 	return s3;
		 	
		 }
 		
	 }
 	
 	else {
 		
 		if(s3 > s1) {
 			
 			return s1;
 			
		 }
 		
 		else {
 			
 			return s3;
 			
		 }
 		
	 }
 	
 }
 
 int main() {
 	
 	float a, b, c, sonuc;
 	
 	printf("uc sayi giriniz: ");
 	scanf("%f%f%f", &a, &b, &c);
 	
 	sonuc = kucukSayi(a, b, c);
 	
 	printf("kucuk sayi: %f", sonuc);
 	
 }
```

6) Bir tamsayı değerini parametre olarak alan, bu sayının asal sayı olup olmadığını kontrol  
ederek asal sayı ise 1, değilse -1 geri döndüren fonksiyonu yazınız.

```cpp
 int asalKontrol(int);
 
 int asalKontrol(int s) {
 	
 	int i, kontrol = 0;
 	
 	for(i = 2; i < s; i++) {
 		
 		if((s % i) == 0) {
 			
 			kontrol = 1;
 			break;
 			
		 }
 		
	 }
	 
	if(kontrol == 1) {
		
		return 1;
		
	}
	
	else if(kontrol == 0) {
		
		return 0;
		
	}
 	
 }
 
 int main() {
 	
 	int a, sonuc;
 	
 	printf("bir sayi giriniz: ");
 	scanf("%d", &a);
 	
 	sonuc = asalKontrol(a);
 	
 	if(sonuc == 1) {
 		
 		printf("-1");
 		
 	}
 	
 	else if(sonuc == 0) {
 		
 		printf("1");
 		
	 }
	 
	 return 0;
 }
```

7) Bir tamsayı değerini parametre olarak alan ve sayının tersini hesaplayarak sonucu döndüren  
fonksiyonu yazınız.

```cpp
 int ters(int, int);
 
 int ters(int s, int b) { 
 	
 	int i, d[b], sonuc_ters, k = 1, toplam;
 	
 	for(i = 0; i < b; i++) {
 		
 		d[i] = s % 10;
 		s = s / 10;
 		
	 }
	 
	 for(i = b - 1; i >= 0; i--) {
	 	
	 	sonuc_ters = d[i] * k;
	 	k = k * 10;
	 	
	 	toplam = toplam + sonuc_ters;
	 	
	 }
 	
 	
 	return toplam;
 }
 
 int main() {
 	
 	int sonuc, a, bas, a1;
 	
 	printf("bir sayi giriniz: ");
 	scanf("%d", &a);
 	
 	a1 = a;
 	
 	while(a > 0) {
 		
 		a = a / 10;
 		bas++;
 		
	 }
 	
 	sonuc = ters(a1, bas);
 	
 	printf("sayinin tersi: %d", sonuc);
 	
 	return 0;
 }
```

8) Bir tamsayı değeri parametre olarak alan ve ikilik tabandaki karşılığını hesaplayarak sonucu  
geri döndüren fonksiyonu yazınız.

```cpp
 int ikilik(int);
 
 int ikilik(int s) {
 	
 	int k, toplam = 0, kat = 1;
 	
	while(s > 0) {
		
		k = s % 2; 
		s = s / 2;
		
		toplam = toplam + k * kat;
		
		kat = kat * 10;
		
	}
 	
 	return toplam;
 	
 }
 
 int main() {
 	
 	int to, sonuc, to1;
 	
 	printf("bir sayi giriniz: ");
 	scanf("%d", &to);
 	
 	to1 = to;
	 
	sonuc = ikilik(to);
	
	printf("onluk taban: %d | ikilik taban: %d", to1, sonuc);
 	
 	return 0;
 }
```

9) Bir tamsayı değerini alan ve rakamlarından maksimum olanını geri döndüren fonksiyonu  
yazınız. Örneğin; 482 için 8 rakamını, 154 için 5 rakamını geri döndürmelidir.

```cpp
 int buyukRakam(int, int);
 
 int buyukRakam(int s, int bas) {
 	
 	int d[bas], i, s_MAX;
 	
 	for(i = 0; i < bas; i++) {
 		
 		d[i] = s % 10;
 		s = s / 10;
 		
	 }
	 
	 s_MAX = d[0];
	 
	 for(i = 0; i < bas; i++) {
	 	
	 	if(s_MAX < d[i]) {
	 		
	 		s_MAX = d[i];
	 		
		 }
	 	
	 }
	 
	 return s_MAX;
 	
 }
 
 int main() {
 	
 	int a, a1, b = 0, sonuc;
 	
 	printf("bir sayi giriniz: ");
 	scanf("%d", &a);
 	
 	a1 = a;
 	
 	while(a > 0) {
 		
 		a = a / 10;
 		b++;
 		
	 }
 	
 	sonuc = buyukRakam(a1, b);
 	
 	printf("buyuk rakam: %d", sonuc);
 	
 	return 0;
 }
```

10) Parametre olarak bir N değeri alan ve 10 ile N arasında tüm rakamları aynı olan sayıları  
ekrana yazdıran fonksiyonu yazınız. (N= 1000 için; 11, 22, 33, … , 999)

```cpp
 void ayniSayilar(int);
 
 void ayniSayilar(int s) {
 	
	int i, j, sayi = 0, sayi_kontrol = 0, kat = 1, bas = 2;
	
	while(sayi_kontrol < s) {
	
		for(i = 1; i < 10; i++) {
		
			for(j = 1; j <= bas; j++) {
			
				sayi = sayi + (kat * i);
				kat = kat * 10;
			
			}
			
			sayi_kontrol = sayi;
		
			if(sayi < s) {
			
				printf(" %d ", sayi);
							
			}
		
			kat = 1;
			sayi = 0;
		
		}
		
		bas++;
	
	}
 	
 }
 
 int main() {

	int n;
	
	printf("bir sayi giriniz (10 dan buyuk sayilar): ");
	scanf("%d", &n);
	
	ayniSayilar(n);
 	
 	return 0;
 }
```

11) Bir tamsayı N değerini parametre olarak alan ve bu N satır kadar aşağıdaki şekilde *  
karakteri ile bir piramit ekrana yazdıran fonksiyonu yazınız. (Örnek, satır sayıyı 5 içindir.)

```cpp
 void piramit(int);
 
 void piramit(int satir) {
 	
 	int i, j, bosluk, k;
 	
 	
    for(i = 1; i <= satir; i++, k = 0) {
    
		for(bosluk = 1; bosluk <= satir - i; bosluk++) {
    
	    	printf("  ");
    
	  	}
    
	  	while(k != 2 * i - 1) {
    
	    	printf("* ");
         	k++;
    
	  	}	
    
	  	printf("\n");
   	
	}

 }

 int main() {

	int n;
	
	printf("satir sayisini giriniz: ");
	scanf("%d", &n);
	
	piramit(n);
 	
 	return 0;
 }
```

12) Parametre olarak bir tamsayı alan ve bu sayının jenerik kökünü hesaplayarak geri döndüren  
fonksiyonu yazınız. (Bir sayının jenerik kökü, tek bir rakam olana kadar bir sayının  
rakamlarının toplamının rakamlarının toplamı alınarak bulunur.)  
Örnek1; 456 sayısının rakamlarının toplamı 4 + 5 + 6 = 15 bir rakam değil,  
bu toplamın da rakamlarını topluyoruz 15→ 1 + 5 = 6 bir rakam,  
çıktı olarak “456 sayının jenerik kökü 6’dır” diyoruz.  
Örnek2; 8759 sayısının rakamları toplamı 8+ 7 + 5 + 9 = 29 bir rakam değil,  
bu toplamın da rakamlarını topluyoruz 29→2 + 9 = 11 bir rakam değil,  
bu toplamın da rakamlarını topluyoruz 11→1 + 1 = 2bir rakam,  
çıktı olarak “8759 sayısının jenerik kökü 2’dir” diyoruz.

```cpp
int jenerikKok(int);
 
 int jenerikKok(int s) {
 	
 	int toplam = 10, kalan;
 	
 	while(toplam > 9) {
 		
 		toplam = 0;
 		
 		while(s > 0) {
		  	
	 		kalan = s % 10;
			toplam = toplam + kalan;
			s = s / 10;	
 		
 		}
 		
 		s = toplam;

	}
	
	return s;
 	
 }
 
 int main() {
 	
 	int n, sonuc;
 	
 	printf("bir sayi giriniz: ");
 	scanf("%d", &n);
 	
 	sonuc = jenerikKok(n);
 	
 	printf("jenerik kok: %d", sonuc);
 	
 	return 0;
 }
```
