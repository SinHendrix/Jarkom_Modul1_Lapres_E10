# Jarkom_Modul1_Lapres_E10

### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
- Display filter : ```http.host contains testing.mekanis.me```
- Follow HTTP Stream
- Server: nginx/1.14.0 (Ubuntu)
Gambar :
![1](https://user-images.githubusercontent.com/57068224/96351235-59327900-10e4-11eb-8419-f319fce0db96.png)

### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
- File --> Export Objects --> HTTP
- Text Filter : "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"
- Save "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"
Gambar :
![2](https://user-images.githubusercontent.com/57068224/96351241-5fc0f080-10e4-11eb-9285-7d7b99984e1a.png)

### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
- Display Filter : ``` http.request.method == POST```
- Terlihat pada HTML Form URL Encoded: application/x-www-form-urlencoded bahwa
- Form item: "username" = "10pemuda"
- Form item: "password" = "guncangdunia"
Gambar :
![3](https://user-images.githubusercontent.com/57068224/96351282-85e69080-10e4-11eb-9ee5-ab5a924c8b83.png)

### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
- Display Filter : ```http.authbasic```
- Muncul paket-paket yang menggunakan basic authentication method
Gambar :
![4](https://user-images.githubusercontent.com/57068224/96351284-88e18100-10e4-11eb-9946-7b22a07f44a4.png)

### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
- Buka link aku.pengen.pw, diminta memasukkan username dan password
- Wireshark Display Filter : ```http.host contains aku.pengen.pw```
- Lihat Credentials pada Basic a2FrYWtnYW10ZW5rOmhhcnRhdGFodGFiZXJtdWRh
- Credentials : kakakgamtenk:hartatahtabermuda yang artinya username = kakakgamtenk dan password = hartatahtabermuda
- Masukkan username dan password
- Menjawab pertanyaan pada link diatas Sebutkan urutan konfigurasi pengkabelan T568B!
Tuliskan jawaban anda pada kolom di bawah ini. Jangan lupa screenshot lalu masukkan ke laporan. (Tombol submit memang nggak ada. Makanya screenshot aja ya)
Gambar :
![5a](https://user-images.githubusercontent.com/57068224/96351289-8e3ecb80-10e4-11eb-977d-ba81acf23e46.png)
![5b](https://user-images.githubusercontent.com/57068224/96351296-9991f700-10e4-11eb-9caf-00b073f22d25.png)
![5c](https://user-images.githubusercontent.com/57068224/96351297-9bf45100-10e4-11eb-94e8-0c169fd0d82e.png)

### 6.Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
Mencari file zip
- Display Filter : ```ftp-data```
- Cari yang infonya FTP Data: (PASV) (STOR Answer.zip)
- Follow --> TCP Stream
- Save data as RAW dengan format .zip
Gambar :
![6a](https://user-images.githubusercontent.com/57068224/96351320-c2b28780-10e4-11eb-8d80-6bb6b1c92d21.png)
![6b](https://user-images.githubusercontent.com/57068224/96351322-c514e180-10e4-11eb-8036-57374e524a8c.png)
![6c](https://user-images.githubusercontent.com/57068224/96351323-c7773b80-10e4-11eb-964b-d435ffebd159.png)
![6d](https://user-images.githubusercontent.com/57068224/96351327-cc3bef80-10e4-11eb-9591-bc561740c4fc.png)
![6e](https://user-images.githubusercontent.com/57068224/96351333-d1993a00-10e4-11eb-9745-c59b1af55215.png)

Cari Password
- Display Filter : ```ftp-data```
- CCari yang infonya FTP Data: (PASV) (STOR zipkey.txt)
- Follow --> TCP Stream
- Mendapat password untuk membuka zip 

### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut. Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
- Display Filter : ```frame contains "Yes"```
- Menemukan zip yang menyimpan pdf tersebut yaitu ```473.zip```
- Follow --> TCP Stream
- Save data as RAW dengan format zip
- Buka pdf yang ada di dalam zip
Gambar :
![7a](https://user-images.githubusercontent.com/57068224/96351348-e70e6400-10e4-11eb-8542-f46262d3181b.png)
![7b](https://user-images.githubusercontent.com/57068224/96351354-ebd31800-10e4-11eb-86ec-d703cbb42676.png)
![7c](https://user-images.githubusercontent.com/57068224/96351356-ee357200-10e4-11eb-8194-b0721f74f5e0.png)

### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
- Display Filter : ftp.request.command == RETR
- Follow --> TCP Stream
Gambar :
![8](https://user-images.githubusercontent.com/57068224/96351363-f7beda00-10e4-11eb-9ad5-b1c167c63578.png)

### 9. Cari username dan password ketika login FTP pada localhost!
- Display Filter : ```ftp.request.command == USER || ftp.request.command == PASS```
Gambar :
![9](https://user-images.githubusercontent.com/57068224/96351364-fa213400-10e4-11eb-9810-db2952124933.png)

### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
- Ctrl + F pada wireshark masukkan clue sebagai hex value
- Follow TCP Stream
- Save data as RAW dengan format .pdf
Gambar :
![10a](https://user-images.githubusercontent.com/57068224/96351389-28067880-10e5-11eb-8047-2b6b9df013ec.png)
![10b](https://user-images.githubusercontent.com/57068224/96351390-2b016900-10e5-11eb-8939-fd2d0f99c40a.png)
![10c](https://user-images.githubusercontent.com/57068224/96351394-2dfc5980-10e5-11eb-8f35-14edd7bd3375.png)

### GAMBAR UNTUK NO 11-15
![Wireshark](https://user-images.githubusercontent.com/57068224/96351159-c42f8000-10e3-11eb-9f33-a5f3abc9c756.png)

### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
- Buka Wireshark
- Pilih dokumen/jaringan yang ingin di filter
- Type `tcp port 21`

### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
- Buka Wireshark
- Pilih dokumen/jaringan yang ingin di filter
- Type `tcp src port 80`

### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
- Buka Wireshark
- Pilih dokumen/jaringan yang ingin di filter
- Type `tcp dst port 443`

### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
- Buka CMD
- Type `ipconfig`
- Dapet IP Address (Kasusku 192.168.100.6)
- Buka Wireshark
- Pilih jaringan yang ingin di filter
- Type `src 192.168.100.6`

### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
- Buka CMD
- Type `PING monta.if.its.ac.id`
- Dapet IP Address (103.94.190.11)
- Buka Wireshark
- Pilih jaringan yang ingin di filter
- Type `dst 103.94.190.11`
