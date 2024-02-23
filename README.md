# Menggunakan LED Dot Matrix Module MAX7219 dengan Arduino UNO

> [!NOTE]
> Halo semuanya, kali ini kita akan belajar untuk menampilkan sebuah text di Modul Dot Matrix Max7219

![image1](./images/image1.png)


## ⚙️ Komponen yang Diperlukan
|No | Komponen | Jumlah | Deskripsi |
| --- | --- | --- | --- |
| 1 | Arduino UNO | 1 | [link](https://shope.ee/2LA9ZZRSl4) |
| 2 | Kabel Jumper Male to Female | 5 | [link](https://shope.ee/5V7BLyRKg1) |
| 3 | LED Dot Matrix MAX7219 | 1 | [link](https://shope.ee/9KK0btNKqP) |

## 💡 Software dan Librari yang digunakan
|No | Komponen | Deskripsi |
| --- | --- | --- |
| 1 | Arduino IDE | [Download](https://www.arduino.cc/en/software) |
| 2 | Librari MD_MAX72XX | [Download](https://downloads.arduino.cc/libraries/github.com/MajicDesigns/MD_MAX72XX-3.5.1.zip?_gl=1*1lbvcki*_ga*MjkyMTI4NTA4LjE2OTc5NDMyNjE.*_ga_NEXN8H46L5*MTcwODY3MjA3Ny42MS4xLjE3MDg2NzIzNjAuMC4wLjA.*_fplc*V29pNmc5bGZZJTJCTmdsYXplZFhUSE1TV1FMWnQlMkJUJTJGUG5vcEJId3Q5ZVJMb0RjWUhHRkJ1OHl0b1ZxckNKQ3ZZZHhwdU40bzdaWDhNZTVzZHVCcUdEOUVNb0E1bXIlMkJJSEpDQTlJakZNOUtkRWVkOFRoWkJ5NSUyQllOJTJGQVNIc0p3JTNEJTNE) |
| 3 | Librari MD_Parola | [Download](https://downloads.arduino.cc/libraries/github.com/MajicDesigns/MD_Parola-3.7.2.zip?_gl=1*lhrqsw*_ga*MjkyMTI4NTA4LjE2OTc5NDMyNjE.*_ga_NEXN8H46L5*MTcwODY3MjA3Ny42MS4xLjE3MDg2NzI0NDIuMC4wLjA.*_fplc*bUIxNk9sRFFRcEY1empYZ3FRdTJOaXdMOTE4TTRoTUNmcVNaUHBQYmlyTGx0RlgxUzJBOElaNjJCT3NrbVFHN3UzRkxYT1I3b2NUcU9vaUNMZkRRakhqWnBldUVVT1BPMk9tZ3FmUVpOVXAwZURhVDlldUNFMlJuYUc1SXB3JTNEJTNE) |

## ⌛️ Tahapan Pengerjaan


<details>
<summary>1️⃣ Rangkai Alat seperti gambar berikut</summary>

| LCD I2C | Arduino UNO |
| --- | --- |
| VCC | 5V |
| GND | GND |
| DIN | 11 |
| CS | 10 |
| CLK | 13 | 
  
![image](./images/image1.png)
</details>



<details>
<summary>2️⃣ Install Librari yang diperlukan di atas</summary>

![image](./images/image2.png)

</details>


<details>
<summary>3️⃣ Tulis Kode Utama berikut di Arduino IDE</summary>

  ```C++
#include <MD_Parola.h>  
#include <MD_MAX72xx.h>
#include <SPI.h>  

const uint16_t WAIT_TIME = 1000;

#define HARDWARE_TYPE MD_MAX72XX::FC16_HW

#define MAX_DEVICES 4  
#define CLK_PIN   13   
#define DATA_PIN  11  
#define CS_PIN    10   

MD_Parola Mx = MD_Parola(HARDWARE_TYPE, CS_PIN, MAX_DEVICES);

void setup()
{
  Mx.begin();         // instruksi untuk memulai 
  Mx.setIntensity(3); // instruksi untuk mengatur intensitas cahaya (0-15)
}

void loop()
{
  Mx.print("ALTOP");  // instruksi untuk menampilkan karakter
  delay(1000);
  Mx.displayClear();
  delay(1000);
}
```

</details>

<details>
<summary>5️⃣ Upload Kode yang sudah kamu tulis di Arduino IDE</summary>

</details>

## 🆘 Troubleshoot




