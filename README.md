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
   1. Langkah-langkah:
   * Gunakan http.host == "testing.mekanisme.me" 
   
   * Gunakan follow HTTP stream dan dibaca servernya
   
   ![1a](https://user-images.githubusercontent.com/58687783/96362366-edd5bf00-1156-11eb-8de8-12cb31ce220d.png)
    
   * Untuk Webservernnya digunakan nginx/1.14.0 Ubuntu.
  
   ![1b](https://user-images.githubusercontent.com/58687783/96362412-4dcc6580-1157-11eb-8997-b6e23f91d162.png)
   
   2. Langkah-langkah:

  * Buka file PCAP dengan wireshark, lalu klik file -> Export Object -> HTTP
  
![image](https://user-images.githubusercontent.com/61129358/96362420-63da2600-1157-11eb-8530-a391d930f320.png)

  * Cari nama file di text filter, lalu klik save. Pilih direktori penyimpanan gambar
  
![image](https://user-images.githubusercontent.com/61129358/96362495-ee228a00-1157-11eb-862e-d489c02bf733.png)

  * Berikut file Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg:
  
![image](https://user-images.githubusercontent.com/61129358/96362511-0c888580-1158-11eb-9eb6-25a3f085af11.png)


   
   3. Langkah-langkah:
   * Gunakan  http.host == "ppid.dpr.go.id" && http.request.method == POST pada display filter. 
   
      Untuk Username 10pemuda dan passnya guncangdunia
   
   ![3a](https://user-images.githubusercontent.com/58687783/96362827-4e1a3000-115a-11eb-9950-b1f155b79187.png)
   
   4. **Wireshark Filter Expression: http.authbasic**

Langkah-langkah:
  * Buka file PCAP dengan wireshark, lalu masukkan http.authbasic pada display filter
  
![image](https://user-images.githubusercontent.com/61129358/96362587-9f292480-1158-11eb-9d5c-ff6f4558e610.png)

 Maka Wireshark akan menampikan paket dari web-web yang menggunakan basic authentication method!
   
   5. Langkah-langkah:
   * Gunakan http.host == aku.pengen.pw pada display filter
   
   ![5a](https://user-images.githubusercontent.com/58687783/96362971-735b6e00-115b-11eb-8432-c545e5eaf1f6.png)
   
   * Kemudian dibaca autorization dan credentialnya (ini juga dapat ditambah dengan http.authorization).Isi Credentialnya adalah kakakgamtenk:hartatahtabermuda. Setelah itu dibuka websitenya dan dimasukan credentialnya sebagai username dan passwordnya.
   
   ![5b](https://user-images.githubusercontent.com/58687783/96362944-3becc180-115b-11eb-8d31-84111a8548f3.png)
   
   6. **Wireshark Filter expression: ftp-data**

**Wireshark string search : Answer.zip**

**Wireshark string search : zipkey**

Langkah-langkah:
 * Buka file PCAP dengan wireshark, lalu masukkan ftp-data pada display filter, lalu klik kanan pada paket yang betuliskan (STOR: Answer.zip) dan pilih follow -> TCP STream
 
 ![image](https://user-images.githubusercontent.com/61129358/96362714-75bcc880-1159-11eb-8d90-3fdd6c5f5059.png)
 
 * Langkah 2
 
 ![image](https://user-images.githubusercontent.com/61129358/96362753-bfa5ae80-1159-11eb-8d83-ff1e987af8f7.png)
 
 * Langkah 3
 
![image](https://user-images.githubusercontent.com/61129358/96362778-e237c780-1159-11eb-8161-dc70263bbbbd.png)

 * Langkah 4
 
 ![image](https://user-images.githubusercontent.com/61129358/96362785-ee238980-1159-11eb-9142-21d64582562a.png)
 
   7. Langkah-langkah:
   * Untuk no 7 digunakan frame contains “Yes.pdf” && ftp-data
    
   ![9a](https://user-images.githubusercontent.com/58687783/96363022-d816c880-115b-11eb-8443-51cc39e1c0c2.png)
       
   * Kemudian dilakukan follow tcp stream. 
     
   ![9b](https://user-images.githubusercontent.com/58687783/96363064-1b713700-115c-11eb-966c-432257e0cc5e.png)
    
   * Setelah didapatkan datanya, diubah menjadi raw dan disimpan sesuai dengan extensinya. Kemudian tinggal dibuka file didalamnya yang bernama Yes.pdf
    
   ![9c](https://user-images.githubusercontent.com/58687783/96363069-21ffae80-115c-11eb-8cf6-54cfb96ff7e4.png)
    
   * Berikut filenya:
    
   ![9d](https://user-images.githubusercontent.com/58687783/96363073-26c46280-115c-11eb-9975-58d72f9ea982.png)
   
 
 8. Langkah-langkah:
 * Buka file PCAP dengan wireshark, lalu masukkan Wireshark Filter Expression: ftp.request.command == RETR pada display filter
 
![image](https://user-images.githubusercontent.com/61129358/96362820-3e025080-115a-11eb-8b51-6edf7aec9076.png)
 
 * Langkah 2
 
![image](https://user-images.githubusercontent.com/61129358/96362822-4195d780-115a-11eb-880a-36e8f32d0b93.png)
 
 * Langkah 3
 
![image](https://user-images.githubusercontent.com/61129358/96362824-45295e80-115a-11eb-96fa-116f2d3e6f24.png)
   


   9. Langkah-langkah:
   * Untuk no 9 dapat digunakan ftp.request.command == USER || ftp.request.command == PASS, akan tetapi perlu diingat kalau ini tidak membaca localhost saja maka ditambah ip.addr = 127.0.0.1
   
![9](https://user-images.githubusercontent.com/58687783/96363129-773bc000-115c-11eb-853f-b20bf787349d.png)

10. **Wireshark hex value finder = 25 50 44 46**

Langkah-langkah:
 * Buka file PCAP dengan wireshark, lalu dengan menggunkan hex value finder, masukkan 25 50 44 46, lalu tekan find. Klik kanan pada  paket yang ditemukan, lalu pilih follow TCP Stream
 
![image](https://user-images.githubusercontent.com/61129358/96362820-3e025080-115a-11eb-8b51-6edf7aec9076.png)
 
 * Pada pilihan Show and save data as, pilih Raw
 
 ![image](https://user-images.githubusercontent.com/61129358/96362874-ca147800-115a-11eb-99d0-264156072322.png)
 
 
 * Simpan file tersebut dengan ekstensi .pdf
 
![image](https://user-images.githubusercontent.com/61129358/96362877-cf71c280-115a-11eb-991a-b7975704d273.png)

 * Berikut file pdf yang tersimpan:
 
 ![image](https://user-images.githubusercontent.com/61129358/96362880-d26cb300-115a-11eb-8e0c-3db5dd5a4894.png)
   
   11. Langkah-langkah:
 * Buka Wireshark, lalu masukkan src port 21 pada capture filter, pilih device yang sedang digunakan

   ![11a](https://user-images.githubusercontent.com/58687783/96363184-d7326680-115c-11eb-9227-d328a5b76725.png)
   
 * Berikut hasilnya:
 
   ![11b](https://user-images.githubusercontent.com/58687783/96363186-da2d5700-115c-11eb-9f9e-d645f94ef3e5.png)
   
12. **Wireshark capture-filter = src port 80**

Langkah-langkah:
 * Buka Wireshark, lalu masukkan src port 80 pada capture filter, pilih device yang sedang digunakan
 
![image](https://user-images.githubusercontent.com/61129358/96363012-c7fee900-115b-11eb-8042-c9e6710b12cc.png)
 
 * Berikut hasilnya: 
 
 (kosong karena port 80 merupakan http, dan posisi sedang tidak membuka web apapun)
 
 ![image](https://user-images.githubusercontent.com/61129358/96363015-cdf4ca00-115b-11eb-9ca5-654633856438.png)
 
 13. langkah-langkah:
 Seperti nomer 11 & 12, hanya saja masukkan **dst port 443** pada capture filter
  
  ![image](https://user-images.githubusercontent.com/61129358/96363812-b3711f80-1160-11eb-82ac-dd45b08f0446.png)


   ![13](https://user-images.githubusercontent.com/58687783/96363209-0f39a980-115d-11eb-8921-0844d44e655f.png)
   
  

14. **Wireshark capture-filter = src host 192.168.0.106**

Langkah-langkah:
 * gunakan command ipconfig pada cmd untuk mencari ip sendiri
 
![image](https://user-images.githubusercontent.com/61129358/96363162-aeaa6c80-115c-11eb-9d6b-1a351baa8c98.png)
 
 * Ip sendiri: 192.168.0.106
 
 ![image](https://user-images.githubusercontent.com/61129358/96363165-b36f2080-115c-11eb-80d3-5c7e891ab759.png)

 * Masukkan src host 192.168.0.106 pada capture filter, pilih network device yang sedang digunakan:
 
 ![image](https://user-images.githubusercontent.com/61129358/96363169-b833d480-115c-11eb-927f-0f6b4097d4a7.png)
 
 * Berikut hasilnya:
 
 ![image](https://user-images.githubusercontent.com/61129358/96363174-be29b580-115c-11eb-9ef6-f55a183e7602.png)
 
 15. langkah-langkah:
 Seperti nomer 11 & 12, hanya saja masukkan **dst host monta.if.its.ac.id** pada capture filter
 
 ![image](https://user-images.githubusercontent.com/61129358/96363857-f9c67e80-1160-11eb-8e8a-d15ebf40c20b.png)
 
 ![15](https://user-images.githubusercontent.com/58687783/96363268-617aca80-115d-11eb-81ce-7654f95379e3.png)
