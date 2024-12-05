#define _CRT_SECURE_NO_WARNINGS
#include <stdio.h>
#include <stdlib.h>		// Malloc ve free için gerekli
#include <string.h>

void gunlukEkle()
{
	FILE* dosya = fopen("gunluk.txt", "a");
	if (dosya == NULL)
	{
		printf("Dosya bulunamadi");
		return;
	}
	char gunluk[500];
	printf("Gunlugunuzu giriniz (500 karaktere kadar):\n");
	getchar();	// Onceki girdiden kalan newline ı temizlemek için kullanılır
	fgets(gunluk, sizeof(gunluk), stdin);

	fprintf(dosya, "%s\n", gunluk);
	fclose(dosya);
	printf("Gunlugunuz basariyla kaydedildi");

}

void gunlukOku()
{
	FILE* dosya = fopen("gunluk.txt", "r");
	if (dosya == NULL)
	{
		printf("Henuz giris yapilmadi");
		return;
	}
	char satir[500];
	printf("Gunlugunuzu Girisleri :\n");
	while (fgets(satir, sizeof(satir), dosya) != NULL)
	{
		printf("%s", satir);
	}
	fclose(dosya);
}

void metinAra()
{
	char aranan[50];
	FILE* dosya = fopen("gunluk.txt", "r");
	if (dosya==NULL)
	{
		printf("Dosya Acilmadi\n");
		return ;
	}
	char matinSatiri[500];
	int satir_numarasi = 0, bulunan = 0;

	printf("Aradiginiz istedigini kelime: ");
	getchar();
	fgets(aranan, sizeof(aranan), stdin);
	aranan[strcspn(aranan, "\n")] = '\0'; // Sonundaki '\n' karakterini kaldır

	while (fgets(matinSatiri, sizeof(matinSatiri), dosya))
	{
		satir_numarasi++;
		if (strstr(matinSatiri,aranan))
		{
			printf("Bulundu! Satir %d: %s", satir_numarasi, matinSatiri);
			bulunan = 1;
		}
	}
	if (!bulunan) {
		printf("Aranan metin dosyada bulunamadi.\n");
	}
	fclose(dosya);
}

int main()
{
	int secim;
	do
	{
		printf("\n1-Gunluk Ekle\n");
		printf("2-Gunlugu Oku\n");
		printf("3-Ara\n");
		printf("4-Cikis\n");
		printf("Seciminizi yapiniz: ");
		scanf("%d", &secim);

		switch (secim)
		{
		case 1:
			gunlukEkle();
			break;
		case 2:
			gunlukOku();
			break;
		case 3:
			metinAra();
			break;
		case 4:
			printf("Programdan cikiliyor...");
			break;
		default:
			printf("Yanlis Secim, yeniden yonlendiriliyor\n");
		}

	} while (secim != 4);

	return 0;
}
