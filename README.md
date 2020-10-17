# Jarkom_Modul1_Lapres_E10

### 1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
- Display filter : ```http.host contains testing.mekanis.me```
- Follow HTTP Stream
- Server: nginx/1.14.0 (Ubuntu)

### 2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
- File --> Export Objects --> HTTP
- Text Filter : "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"
- Save "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"

### 3. Cari username dan password ketika login di "ppid.dpr.go.id"!
- Display Filter : ``` http.request.method == POST```
Terlihat pada HTML Form URL Encoded: application/x-www-form-urlencoded bahwa
Form item: "username" = "10pemuda"
Form item: "password" = "guncangdunia"

### 4. Temukan paket dari web-web yang menggunakan basic authentication method!
- Display Filter : ```http.authbasic```
- Muncul paket-paket yang menggunakan basic authentication method

### 5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
- Buka link aku.pengen.pw, diminta memasukkan username dan password
- Wireshark Display Filter : ```http.host contains aku.pengen.pw```
- Lihat Credentials pada Basic a2FrYWtnYW10ZW5rOmhhcnRhdGFodGFiZXJtdWRh
- Credentials : kakakgamtenk:hartatahtabermuda yang artinya username = kakakgamtenk dan password = hartatahtabermuda
- Masukkan username dan password
- Menjawab pertanyaan pada link diatas Sebutkan urutan konfigurasi pengkabelan T568B!
Tuliskan jawaban anda pada kolom di bawah ini. Jangan lupa screenshot lalu masukkan ke laporan. (Tombol submit memang nggak ada. Makanya screenshot aja ya)

### 6.Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
Mencari file zip
- Display Filter : ```ftp-data```
- Cari yang infonya FTP Data: (PASV) (STOR Answer.zip)
- Follow --> TCP Stream
- Save data as RAW dengan format .zip

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

### 8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
- Display Filter : ftp.request.command == RETR
- Follow --> TCP Stream

### 9. Cari username dan password ketika login FTP pada localhost!
- Display Filter : ```ftp.request.command == USER || ftp.request.command == PASS```

### 10. Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46"
- Ctrl + F pada wireshark masukkan clue sebagai hex value
- Follow TCP Stream
- Save data as RAW dengan format .pdf

### 11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

### 12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

### 14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

### 15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
