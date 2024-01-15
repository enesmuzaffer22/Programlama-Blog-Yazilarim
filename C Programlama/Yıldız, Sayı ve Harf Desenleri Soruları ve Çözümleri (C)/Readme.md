![](https://i.hizliresim.com/fpahcj3.jpg)
![](https://i.hizliresim.com/c2gzl63.jpg)
![](https://i.hizliresim.com/brt0gbf.jpg)
![](https://i.hizliresim.com/imsdt9o.jpg)
![](https://i.hizliresim.com/nvk0i65.jpg)
![](https://i.hizliresim.com/9bbz1t6.jpg)
![](https://i.hizliresim.com/i7phn52.jpg)
![](https://i.hizliresim.com/crdlv3s.jpg)
![](https://i.hizliresim.com/pdre51l.jpg)
1)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		printf("*****\n");
		
	}
```

2)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

3)

```cpp
	int i, j, satir = 5, bosluk = satir - 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = bosluk; j >= i; j--) {
			
			printf(" ");
			
		}
		
		for(j = 1; j <= i; j++) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

4)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

5)

```cpp
	int i, j, satir = 5, bosluk = satir - 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf(" ");
			
		}
		
		for(j = satir; j >= i; j--) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

6)

```cpp
	int i, j, satir = 5, bosluk = satir - 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = bosluk; j >= i; j--) {
			
			printf(" ");
			
		}
		
		for(j = 1; j <= 5; j++) {   //dongudeki "5" degerinin satir sayisi ile alakasi yoktur
			
			printf("*");            //yildiz sayisini ifade eder
			
		}
		
		printf("\n");
		
	}
```

7)

```cpp
	int i, j, satir = 5, bosluk = satir - 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf(" ");
			
		}
		
		for(j = 1; j <= 5; j++) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

8)

```cpp
	int i, j, satir = 5, bosluk = satir - 1, k;
	
    for(i = 1; i <= satir; i++, k = 0) {
    
		for(bosluk = 1; bosluk <= satir - i; bosluk++) {
    
	    	printf(" ");
    
	  	}
    
	  	while(k != 2 * i - 1) {
    
	    	printf("*");
         	k++;
    
	  	}	
    
	  	printf("\n");
   	
	}
```

9)

```cpp
	int i, satir = 5, bosluk, j;
	
	for (i = satir; i >= 1; --i) {
     
	 	for (bosluk = 0; bosluk < satir - i; bosluk++)
     	printf(" ");
     
	  	for (j = i; j <= 2 * i - 1; ++j)
	     printf("*");
     
		for (j = 0; j < i - 1; ++j)  
		printf("*");
     
	  printf("\n");
   
   }
```

10)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
	
	for(i = 1; i <= satir - 1; i++) {
		
		for(j = satir - 1; j >= i; j--) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

11)

```cpp
	int i, j, satir = 5, bosluk = satir - 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = bosluk; j >= i; j--) {
			
			printf(" ");
			
		}
		
		for(j = 1; j <= i; j++) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
	

	
	for(i = 1; i <= satir - 1; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf(" ");
			
		}
		
		for(j = satir - 1; j >= i; j--) {
			
			printf("*");
			
		}
		
		printf("\n");
		
	}
```

12)

```cpp
	int i, j, satir = 5, bosluk = satir - 1, k;
	
    for(i = 1; i <= satir; i++, k = 0) {
    
		for(bosluk = 1; bosluk <= satir - i; bosluk++) {
    
	    	printf(" ");
    
	  	}
    
	  	while(k != 2 * i - 1) {
    
	    	printf("*");
         	k++;
    
	  	}	
    
	  	printf("\n");
   	
	}
	
	for (i = satir - 1; i >= 1; --i) {
     
	 	for (bosluk = 0; bosluk <= (satir - 1) - i; bosluk++)
     	printf(" ");
     
	  	for (j = i; j <= 2 * i - 1; ++j)
	    printf("*");
     
		for (j = 0; j < i - 1; ++j)  
		printf("*");
     
	  	printf("\n");
   
   }
```

13)

```cpp
    int satir, yildiz = 5, bosluk, i;

	for(satir = 1; satir <= yildiz - 1; satir++) {
		
		
		for(i = 1; i <= satir; i++)
		
			printf("*");
		
		for(bosluk = 1; bosluk <= 2 * (yildiz - satir); bosluk++)
		
			printf(" ");
		
		printf("\b");
		
		for(i = satir; i >= 1; i--)
		
			printf("*");
		
		printf("\n");
	}

	for(satir = yildiz; satir >= 1; satir--) {
		
		
		for(i = 1; i <= satir; i++)
		
			printf("*");
		
		for(bosluk = 1; bosluk <= 2 * (yildiz - satir); bosluk++)
		
			printf(" ");
		
		printf("\b");
		
		for(i = satir; i >= 1; i--)
		
			printf("*");
		
		printf("\n");
	}
```

14)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		printf("11111\n");
		
	}
```

15)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		if((i % 2) == 1) {
			
			printf("11111");
			
		}
		
		else if((i % 2) == 0) {
			
			printf("00000");
			
		}
		
		printf("\n");
		
	}
```

16)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		printf("01010\n");
		
	}
```

17)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= satir; j++) {
			
			printf("%d", i);
			
		}
		
		printf("\n");
		
	}
```

18)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		printf("12345\n");
		
	}	
```

19)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", i);
			
		}
		
		printf("\n");
		
	}
```

20)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", j);
			
		}
		
		printf("\n");
		
	}
```

21)

```cpp
	int i, j, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", i);
			
		}
		
		printf("\n");
		
	}
```

22)

```cpp
	int i, j, satir = 5, e_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", e_f);
			
		}
		
		e_f--;
		printf("\n");
		
	}
```

23)

```cpp
	int i, j, satir = 5, e_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", e_f);
			
		}
		
		e_f--;
		printf("\n");
		
	}
```

24)

```cpp
	int i, j, satir = 5, a_f = 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		a_f = 1;
		printf("\n");
		
	}
```

25)

```cpp
	int i, j, satir = 5, a_f = 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", a_f);
			a_f--;
			
		}
		
		a_f = i + 1;
		printf("\n");
		
	}
```

26)

```cpp
	int i, j, satir = 5, a_f = satir, e_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f--;
			
		}
		
		e_f--;
		a_f = e_f;
		printf("\n");
		
	}
```

27)

```cpp
	int i, j, satir = 5, a_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", a_f);
			a_f--;
			
		}
		
		a_f = satir;
		printf("\n");
		
	}
```

28)

```cpp
	int i, j, satir = 5, a_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f--;
			
		}
		
		a_f = satir;
		printf("\n");
		
	}
```

29)

```cpp
	int i, j, satir = 5, a_f = satir, e_f = satir;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		e_f--;
		a_f = e_f;
		printf("\n");
		
	}
```

30)

```cpp
	int i, j, satir = 5, a_f = 1, a_f2 = 1;

	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		a_f2++;
		a_f = a_f2;
		printf("\n");
		
	}
```

31)

```cpp
	int i, j, satir = 5, a_f = 1, a_f2 = 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		a_f2++;
		a_f = a_f2;
		printf("\n");
		
	}
```

32)

```cpp
	int i, j, satir = 5, a_f = satir, a_f2 = satir;

	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		a_f2--;
		a_f = a_f2;
		printf("\n");
		
	}
```

33)

```cpp
	int i, j, satir = 5, a_f = 1, a_f2 = 1;

	for(i = 1; i <= satir; i++) {
		
		for(j = satir; j >= i; j--) {
			
			printf("%d", a_f);
			a_f += 2;
			
		}
		
		a_f2 += 2;
		a_f = a_f2;
		printf("\n");
		
	}
```

34)

```cpp
	int i, j, a_f = 1, a_f2 = 1, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= 5; j++) {
			
			printf("%d", a_f);
			a_f++;
			
		}
		
		a_f2++;
		a_f = a_f2;
		printf("\n");
		
	}
```

35)

```cpp
	int i, j, a_f = 1, satir = 5;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= 5; j++) {
			
			printf("%d\t", a_f);
			a_f++;
			
		}
		
		printf("\n");
		
	}
```

36)

```cpp
	int i, j, satir = 5, a_f = 1;
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%d\t", a_f);
			a_f++;
			
		}
		
		printf("\n");
		
	}
```

37)

```cpp
	int satir, s = 5, a_f, bosluk;

	for(satir = 1; satir <= s; satir++) {
		
		for(a_f = 1; a_f <= satir; a_f++)
			printf("%d ", a_f);
		
		for(bosluk = 1; bosluk <= 2 * (s - satir); bosluk++)
			printf("  ");
		
		printf("\b");
		
		for(a_f = satir; a_f >= 1; a_f--)
			printf(" %d", a_f);
		
		printf("\n");
	}
```

38)

```cpp
	int i, j, satir = 6;
	char h = 'A';
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%c", h);
			
		}
		
		h++;
		printf("\n");
		
	}
```

39)

```cpp
	int i, j, satir = 6;
	char h = 'A';
	
	for(i = 1; i <= satir; i++) {
		
		for(j = 1; j <= i; j++) {
			
			printf("%c", h);
			h++;
			
		}
		
		h = 'A';
		printf("\n");
		
	}
```

40)

```cpp
int i, j, satir = 6, bosluk = satir - 1;
char h = 'A';

for(i = 1; i <= satir; i++) {

    for(j = bosluk; j >= i; j--) {

        printf(" ");

    }

    for(j = 1; j <= i; j++) {

        printf(" %c", h);
        h++;

    }

    h = 'A';
    printf("\n");

}
```
