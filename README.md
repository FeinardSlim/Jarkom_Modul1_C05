# Jarkom_Modul1_Lapres_C05
Kelompok C05
- 05111840000077  Eric Amadeo S.
- 05111840000081  Feinard

## A. Display Filter
   1. Sebutkan webserver yang digunakan pada "testing.mekanis.me"!
   2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!
   3. Cari username dan password ketika login di "ppid.dpr.go.id"!
   4. Temukan paket dari web-web yang menggunakan basic authentication method!
   5. Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!
   6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, 
       temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).
   7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
       Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"
   8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!
   9. Cari username dan password ketika login FTP pada localhost!
   10. Cari file .pdf di wireshark lalu download dan buka file tersebut!
        clue: "25 50 44 46" 

## B. Capture Filter
   11. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
   12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
   13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
   14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
   15. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!
   
### Tambahan File dari Soal
   Untuk File no 1-10 dapat didownload di link dibawah ini:
   1. [No 1-5,10](https://drive.google.com/file/d/17X8b4xqRDs0S_Z1rT08s-cNETpAQkBrY/view?usp=sharing)
   2. [No 6,7,9](https://drive.google.com/file/d/1JTwaABD7oujbnc6jH-Zj4HibGaVGAOFV/view?usp=sharing)
   3. [No 8](https://drive.google.com/file/d/1xZxjVNXoYEGc1beH0_JSTuD_CDVgDw2Q/view?usp=sharing)

## Jawaban
   1. Gunakan http.host == "testing.mekanisme.me" dan gunakan follow HTTP stream dan dibaca servernya. Untuk Webservernnya digunakan nginx/1.14.0 Ubuntu.
   
   ![1a](https://user-images.githubusercontent.com/58687783/96362366-edd5bf00-1156-11eb-8de8-12cb31ce220d.png)
   ![1b](https://user-images.githubusercontent.com/58687783/96362412-4dcc6580-1157-11eb-8997-b6e23f91d162.png)
   
   3. Untuk no 3 digunakan  http.host == "ppid.dpr.go.id" && http.request.method == POST . Untuk Username 10pemuda dan passnya guncangdunia
   
   ![3a](https://user-images.githubusercontent.com/58687783/96362827-4e1a3000-115a-11eb-9950-b1f155b79187.png)
   
   5. Digunakan http.host == aku.pengen.pw, kemudian dibaca autorization dan credentialnya (ini juga dapat ditambah dengan http.authorization).Isi Credentialnya adalah kakakgamtenk:hartatahtabermuda. Setelah itu dibuka websitenya dan dimasukan credentialnya sebagai username dan passwordnya.
   
   ![5a](https://user-images.githubusercontent.com/58687783/96362971-735b6e00-115b-11eb-8432-c545e5eaf1f6.png)
   ![5b](https://user-images.githubusercontent.com/58687783/96362944-3becc180-115b-11eb-8d31-84111a8548f3.png)
   
   7. Untuk no 7 digunakan frame contains “Yes.pdf” && ftp-data. Kemudian dilakukan follow tcp stream. Setelah didapatkan datanya, diubah menjadi raw dan disimpan sesuai dengan extensinya. Kemudian tinggal dibuka file didalamnya yang bernama Yes.pdf
   
   ![9a](https://user-images.githubusercontent.com/58687783/96363022-d816c880-115b-11eb-8443-51cc39e1c0c2.png)
   ![9b](https://user-images.githubusercontent.com/58687783/96363064-1b713700-115c-11eb-966c-432257e0cc5e.png)
   ![9c](https://user-images.githubusercontent.com/58687783/96363069-21ffae80-115c-11eb-8cf6-54cfb96ff7e4.png)
   ![9d](https://user-images.githubusercontent.com/58687783/96363073-26c46280-115c-11eb-9975-58d72f9ea982.png)

   9. Untuk no 9 dapat digunakan ftp.request.command == USER || ftp.request.command == PASS, akan tetapi perlu diingat kalau ini tidak membaca localhost saja maka ditambah ip.addr = 127.0.0.1
   
![9](https://user-images.githubusercontent.com/58687783/96363129-773bc000-115c-11eb-853f-b20bf787349d.png)
   
   11. Gunakan Port 21
   
   ![11a](https://user-images.githubusercontent.com/58687783/96363184-d7326680-115c-11eb-9227-d328a5b76725.png)
   ![11b](https://user-images.githubusercontent.com/58687783/96363186-da2d5700-115c-11eb-9f9e-d645f94ef3e5.png)

   13. Gunakan dst port 443
   
   ![13](https://user-images.githubusercontent.com/58687783/96363209-0f39a980-115d-11eb-8921-0844d44e655f.png)
   
   15.Gunakan dst host monta.if.its.ac.id
   
   ![15](https://user-images.githubusercontent.com/58687783/96363268-617aca80-115d-11eb-81ce-7654f95379e3.png)
