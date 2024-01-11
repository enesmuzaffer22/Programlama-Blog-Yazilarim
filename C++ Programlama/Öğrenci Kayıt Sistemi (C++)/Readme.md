
Bu yazımda sınıf yapılarını kullanarak **öğrenci kayıt sistemi** yaptım. Sistem içerisinde dört ana işlem yapılabilmektedir:

**1-Kayıt ekleme**

**2-Kayıt silme**

**3-Kayıt görüntüleme**

**4-Kayıt düzenleme**

```cpp
#include <iostream>
#include <cstring>
#include <string>
#include <vector>
#include <ctime>
#include <cstdlib>
using namespace std;

class sinif {

	private:

		/* class degiskenleri */

		int ID;
		int ogrenciNo;
		string ad;
		string soyAd;

	public:

		sinif() {

			/* default kayit fonksiyonu */

			ID = 0;
			ogrenciNo = 0;
			ad = "NULL";
			soyAd = "NULL";

		}

		void setAll(int ID, int ogrenciNo, string ad, string soyAd) {

			/* kayit fonksiyonu */

			this->ad = ad;
			this->soyAd = soyAd;
			this->ID = ID;
			this->ogrenciNo = ogrenciNo;

		}

		void getOgrenci() {

			/* ekrana yazdirma fonksiyonu */

			system("cls");

			cout << "OGRENCININ;" << endl;

			cout << endl;

			cout << "ADI: " << ad << endl;
			cout << "SOYADI: " << soyAd << endl;
			cout << "ID: " << ID << endl;
			cout << "OGRENCI NO: " << ogrenciNo << endl;

		}

		/* set fonksiyonlari */

		void setogrenciNo(int ogrenciNo_temp) { ogrenciNo = ogrenciNo_temp; }
		void setad(string ad_temp) { ad = ad_temp; }
		void setsoyAd(string soyAd_temp) { soyAd = soyAd_temp; }

		/* get fonksiyonlari */

		string getad() { return ad; }
		string getsoyAd() { return soyAd; }
		int getID() { return ID; }
		int getogrenciNo() { return ogrenciNo; }


};

int anaMenu();
void kayitSil(vector<sinif>& ogrenci);
int kayitSilAltMenu();
void kayitDuzenle(vector<sinif>& ogrenci, int sira);
int kayitDuzenleAltMenu();

int anaMenu() {

	int op = -1;

	cout << "#### ANA MENU ####" << endl;
	cout << endl;

	cout << "1- Kayit ekle" << endl;
	cout << "2- Kayit sil" << endl;
	cout << "3- Kayit goruntule" << endl;
	cout << "4- Kayit duzenle" << endl;
	cout << "5- Cikis" << endl;

	cout << endl;

	while (!(op > 0 && op < 6)) {

		/* op istenilen sarta uymadigi surece bu loop calisir */

		cout << "Yapmak istediginiz islemin numarasini giriniz (1-5): ";
		cin >> op;

	}

	return op; /* bu fonksiyon op degerini dondurur */

}

void kayitSil(vector<sinif>& ogrenci) {

	int sira, op = kayitSilAltMenu(); /* alt menuden gelen deger op 
	degiskenine atanir */
	int i, flag = 0;

	vector<sinif>::iterator iter;

	iter = ogrenci.begin();

	while (op != 3) {

		switch (op) {

			case 1:

				cout << endl;

				cout << "Silmek istediginiz kayitin ID numarasini giriniz: ";
				cin >> sira;

				for (i = 0; i < ogrenci.size(); i++) {

					if (sira == ogrenci.at(i).getID()) {

						flag = 1;
						ogrenci.erase(ogrenci.begin() + i);

						cout << "Kayit basariyla silindi" << endl;

					}

				}

				if (flag == 0) {

					cout << "Kayit bulunamadi" << endl;

				}

				cout << endl;

				op = kayitSilAltMenu(); /* islemler bittiginde tekrardan alt
				menuye donuluyor */

				break;

			case 2:

				int i;

				for (i = 0; i < ogrenci.size(); i++) {

					/* vektor dizisinde butun kayitlar siliniyor */

					ogrenci.pop_back();

				}

				cout << "Tum kayitlar basari ile silindi" << endl;

				cout << endl;

				op = kayitSilAltMenu(); /* islemler bittiginde tekrardan alt
				menuye donuluyor */

				break;

		}

	}

}

int kayitSilAltMenu() {

	int op = -1;

	cout << "#### KAYIT SIL ####" << endl;
	cout << endl;

	cout << "1- Bir ogrencinin kaydini sil" << endl;
	cout << "2- Siniftaki butun ogrencilerin kaydini sil" << endl;
	cout << "3- Ana menu" << endl;

	cout << endl;

	while (!(op > 0 && op < 4)) {

		/* op istenilen sarta uymadigi surece bu loop calisir */

		cout << "Yapmak istediginiz islemin numarasini giriniz (1-3): ";
		cin >> op;

	}

	return op;

}

void kayitDuzenle(vector<sinif>& ogrenci, int sira) {

	int i, flag = 0;
	string ad, soyAd;
	int ogrenciNo;

	int op;

	for (i = 0; i < ogrenci.size(); i++) {

		if (sira == ogrenci.at(i).getID()) {

			/* duzenlenilmek istenen kayit bulundugunda 
			if blogunun icindeki islemler yapilabilir */

			flag = 1;

			cout << endl;

			op = kayitDuzenleAltMenu(); /* alt menu acilir */

			while (op != 4) {

				switch (op) {

				case 1:

					cout << endl;

					cout << "Ogrencinin adini giriniz: ";
					cin.ignore();
					getline(cin, ad);

					ogrenci.at(i).setad(ad); /* set fonksiyonu ile ad
					degiskeninin degeri degisir */

					cout << endl;

					op = kayitDuzenleAltMenu(); /* alt menu acilir */

					break;

				case 2:

					cout << endl;

					cout << "Ogrencinin soyadini giriniz: ";
					cin.ignore();
					getline(cin, soyAd);

					ogrenci.at(i).setsoyAd(soyAd); /* set fonksiyonu ile soyAd
					degiskeninin degeri degisir */

					cout << endl;

					op = kayitDuzenleAltMenu(); /* alt menu acilir */

					break;

				case 3:

					cout << endl;

					cout << "Ogrencinin numarasini giriniz: ";
					cin >> ogrenciNo;

					ogrenci.at(i).setogrenciNo(ogrenciNo); /* set fonksiyonu ile ogrenciNo
					degiskeninin degeri degisir */

					cout << endl;

					op = kayitDuzenleAltMenu(); /* alt menu acilir */

					break;

				}

			}

		}

	}

	if (flag == 0) {

		cout << "Kayit bulunamadi " << endl;
  
	}

}

int kayitDuzenleAltMenu() {

	int op = -1;

	cout << "#### KAYIT DUZENLEME ####" << endl;
	cout << endl;

	cout << "1- Ogrencinin adini duzenleme" << endl;
	cout << "2- Ogrencinin soyadini duzenleme" << endl;
	cout << "3- Ogrencinin numarasini duzenleme" << endl;
	cout << "4- Ana menu" << endl;

	cout << endl;

	while (!(op > 0 && op < 5)) {

		/* op istenilen sarta uymadigi surece bu loop calisir */

		cout << "Yapmak istediginiz islemin numarasini giriniz (1-4): ";
		cin >> op;

	}

	return op;

}

int main() {
	
	vector <sinif> ogrenci;
	srand(time(0));
	int sayac = 1, sira, i;

	int flag = 0;

	int ogrenciNo;
	int ID;
	string ad;
	string soyAd;

	int op = anaMenu();

	while (op != 5) {

		switch (op) {
		
			case 1:

				ID = sayac; /* ID degiskenine kayit sirasina gore deger 
				verilir */

				ogrenciNo = rand() % (9999 - 1000 + 1) + 1000;
				ogrenciNo = (ogrenciNo * 100) + sayac;
				
				/* ogrenciNo degiskenine son iki hanesi ID olacak sekilde
				alti basamakli rastgele sayi verilir ve alt kisimda kayit
				islemleri yapilir */

				cout << "Ogrencinin;" << endl;
				
				cout << endl;
				
				cout << "Adi: ";
				cin.ignore();
				getline(cin, ad);

				cout << "Soyadi: ";
				getline(cin, soyAd);
				
				ogrenci.push_back(sinif());

				ogrenci.at(sayac - 1).setAll(ID, ogrenciNo, ad, soyAd);
				sayac++;

				cout << endl;
				
				op = anaMenu(); /* ana menu acilir */

				break;

			case 2:

				kayitSil(ogrenci);
				
				cout << endl;

				op = anaMenu();

				break;

			case 3:

				cout << "Goruntulemek istediginiz kaydin ID numarasini giriniz: ";
				cin >> sira;

				cout << endl;

				for (i = 0; i < ogrenci.size(); i++) {

					if (sira == ogrenci.at(i).getID()) {

						/* istenilen kayit bulundugunda ekrana yazdirilir */

						flag = 1;
						ogrenci.at(i).getOgrenci();

					}

				}

				if (flag == 0) {

					cout << "Kayit bulunamadi" << endl;

				}

				cout << endl;

				flag = 0;

				op = anaMenu();

				break;

			case 4:
				cout << "Duzenlemek istediginiz kaydin ID numarasini giriniz: ";
				cin >> sira;

				kayitDuzenle(ogrenci, sira);

				cout << endl;

				op = anaMenu();

				break;

		}

	}

	cout << "Cikis yapiliyor !" << endl;

	return 0;
}
```
