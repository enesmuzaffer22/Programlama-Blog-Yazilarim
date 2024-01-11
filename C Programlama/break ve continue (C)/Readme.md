# break

Bir döngünün durdurulmasını sağlar.

Aşağıdaki örnek ile konuyu anlamaya çalışalım:

```cpp
#include <stdio.h>int main() {
	
	int sayi, toplam = 0, i;
	
	for(i = 1; i <= 10; i++) {
		printf("bir sayi giriniz: ");
		scanf("%d", &sayi);
		
		if(sayi < 0){
			break;
		}

                else {
                      toplam = toplam + a;
                }  
		
	} 
	
	printf("toplam: %d", toplam);
	
	return 0;
}
```

Yukarıdaki örnekte kullanıcıdan 10 kere sayı girişi isteniyor ve girilen sayıların toplamı ekrana yazılıyor. Buradaki asıl olay, eğer bir kullanıcı negatif bir sayı girişi yaparsa döngü kesilir ve kesildiği adımdaki sayı işleme alınmaz. Yani negatif sayı toplama dahil olmaz.

Programı çalıştırdığımızda ise aşağıdaki gibi çıktı verir:

```cpp
bir sayi giriniz: 3bir sayi giriniz: 4bir sayi giriniz: 6bir sayi giriniz: -1toplam: 13
```

# continue

Bir döngüde bulunduğu adımın es geçilmesini sağlar.

Aşağıdaki örnek ile konuyu anlamaya çalışalım:

```cpp
#include <stdio.h>int main() {
	
	int sayi, toplam = 0, i;
	
	for(i = 1; i <= 10; i++) {
		printf("bir sayi giriniz: ");
		scanf("%d", &sayi);
		
		if(sayi < 0){
			continue;
		}
		
                else {
                      toplam = toplam + a;
                }  
		
	} 
	
	printf("toplam: %d", toplam);
	
	return 0;
}
```

Verilen örnek, ilk verdiğimiz örneğin neredeyse aynıdır. Tek farkı break yerine continue kullanmamızdır. Bu örnekteki asıl olay ise, eğer kullanıcı negatif bir sayı girişi yaparsa döngüdeki negatif giriş yapılan adım es geçilir. Yani kullanıcı negatif sayı girse bile sayı girişi yapılmaya devam eder fakat negatif sayılar toplama dahil olmaz.

Programı çalıştırdığımızda ise aşağıdaki gibi çıktı verir:

```cpp
bir sayi giriniz: 2bir sayi giriniz: 4bir sayi giriniz: 6bir sayi giriniz: -1bir sayi giriniz: 2bir sayi giriniz: 4bir sayi giriniz: 6bir sayi giriniz: -1bir sayi giriniz: 3bir sayi giriniz: 4toplam: 29
```
