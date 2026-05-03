# Proyek Akhir  
## Sistem Pembaca dan Penulis TJC (The Jigsaw Card) Berbasis RFID RC522 Menggunakan Arduino UNO  

### Anggota Kelompok
- Perry  
- Gorga Friedrik Simatupang  
- Jesaya  
- Saka  

---

## Deskripsi Proyek  
Proyek ini bertujuan untuk membangun sistem pembaca dan penulis kartu berbasis RFID/NFC menggunakan modul RFID RC522 yang dihubungkan dengan Arduino UNO.  

Dalam skenario yang digunakan, Jigsaw Co. mewajibkan seluruh karyawan menggunakan TJC (The Jigsaw Card), yaitu kartu identitas yang menyimpan informasi hak akses. Kartu ini digunakan untuk berbagai kebutuhan otorisasi seperti membuka pintu atau mengakses area tertentu.  

Sistem yang dibuat mampu membaca dan menulis data ke kartu NFC sehingga hak akses dapat disimpan langsung di dalam kartu. Dalam implementasinya, kartu memiliki level tertentu (misalnya Level 1 hingga Level 3) yang menentukan kewenangan akses.  

Sebagai ilustrasi penggunaan, sistem ini dapat digunakan dalam skenario di mana seorang pengguna harus mengumpulkan kartu dengan level tertentu (misalnya Level 3) untuk membuka akses ke area dengan tingkat keamanan lebih tinggi.  

---

## Cara Kerja Sistem  
1. RFID RC522 mendeteksi kartu TJC (NFC).  
2. UID dan data kartu dibaca melalui komunikasi SPI.  
3. Sistem memproses data untuk menentukan level akses.  
4. Jika diperlukan, sistem dapat menulis data baru ke kartu (misalnya upgrade level akses).  
5. Sistem memberikan output berupa indikator (LED, Serial Monitor, atau LCD).  

---

## Bahasa Pemrograman  
Proyek ini ditulis menggunakan Assembly Language (.S) pada mikrokontroler ATmega328P yang terdapat pada Arduino UNO.  

Penggunaan Assembly memungkinkan kontrol langsung terhadap register hardware, efisiensi eksekusi program, serta pemahaman mendalam terhadap sistem embedded.  

---

## Kesesuaian dengan Modul Praktikum  

### Modul 3: Serial Port  
Digunakan untuk komunikasi antara Arduino dan komputer melalui USART, terutama untuk debugging dan menampilkan informasi UID serta status akses kartu.  
Konfigurasi dilakukan melalui register UART seperti UBRR dan UCSR menggunakan Assembly.  

---

### Modul 5: Timer  
Timer digunakan untuk mengatur delay sistem, seperti jeda pembacaan kartu dan stabilisasi proses komunikasi dengan RFID.  
Menggunakan Timer/Counter internal melalui register TCCR dan TCNT.  

---

### Modul 6: Interrupt  
Interrupt digunakan untuk menangani event seperti deteksi kartu atau event berbasis waktu tanpa harus melakukan polling terus-menerus.  
Hal ini meningkatkan efisiensi sistem.  

---

### Modul 7: PWM  
PWM digunakan sebagai indikator visual, misalnya untuk mengatur intensitas LED saat kartu berhasil dibaca atau saat akses diberikan/ditolak.  
Dikonfigurasi melalui register OCR dan Timer.  

---

### Modul 9: SPI dan I2C Sensor Interfacing  

#### SPI  
Merupakan bagian utama sistem karena RFID RC522 berkomunikasi menggunakan SPI.  
Digunakan untuk transfer data antara Arduino dan modul RFID melalui jalur MOSI, MISO, SCK, dan SS.  

#### I2C  
Digunakan untuk perangkat tambahan seperti LCD I2C untuk menampilkan informasi kartu atau status sistem.  
Menggunakan protokol TWI (Two Wire Interface).  

---

## Alat dan Bahan  

### Hardware
- Arduino UNO (ATmega328P)  
- RFID Reader RC522  
- Kartu NFC (TJC - The Jigsaw Card)  
- Breadboard  
- Kabel jumper  
- LED  
- Resistor  
- LCD I2C (opsional)  

---

### Software
- AVR Assembler atau AVR-GCC  
- Arduino IDE  
- Serial Monitor  

---

## Keunggulan Proyek  
- Menggunakan Assembly Language untuk kontrol penuh terhadap hardware  
- Mendukung pembacaan dan penulisan data kartu NFC  
- Mengimplementasikan sistem otorisasi berbasis level akses  
- Mengintegrasikan berbagai konsep penting dalam embedded system  
- Memenuhi kebutuhan modul praktikum (3, 5, 6, 7, dan 9)  

---

## Pengembangan Lanjutan  
- Integrasi dengan database untuk manajemen pengguna  
- Sistem akses pintu otomatis berbasis level kartu  
- Penambahan autentikasi multi-layer  
- Integrasi dengan sistem IoT untuk monitoring jarak jauh  
