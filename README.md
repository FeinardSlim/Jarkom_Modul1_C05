# Jarkom_Modul1_C05

2. Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"

Langkah-langkah:
  * Buka file PCAP dengan wireshark, lalu klik file -> Export Object -> HTTP
  
![image](https://user-images.githubusercontent.com/61129358/96362420-63da2600-1157-11eb-8530-a391d930f320.png)

  * Cari nama file di text filter, lalu klik save. Pilih direktori penyimpanan gambar
  
![image](https://user-images.githubusercontent.com/61129358/96362495-ee228a00-1157-11eb-862e-d489c02bf733.png)

  * Berikut file Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg:
  
![image](https://user-images.githubusercontent.com/61129358/96362511-0c888580-1158-11eb-9eb6-25a3f085af11.png)



4. Temukan paket dari web-web yang menggunakan basic authentication method!

**Wireshark Filter Expression: http.authbasic**

Langkah-langkah:
  * Buka file PCAP dengan wireshark, lalu masukkan http.authbasic pada display filter
  
![image](https://user-images.githubusercontent.com/61129358/96362587-9f292480-1158-11eb-9d5c-ff6f4558e610.png)

 Maka Wireshark akan menampikan paket dari web-web yang menggunakan basic authentication method!
 
 6. Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

**Wireshark Filter expression: ftp-data**

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
 
 
8. Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

**Wireshark Filter Expression: ftp.request.command == RETR**

Langkah-langkah:
 * Buka file PCAP dengan wireshark, lalu masukkan Wireshark Filter Expression: ftp.request.command == RETR pada display filter
 
![image](https://user-images.githubusercontent.com/61129358/96362820-3e025080-115a-11eb-8b51-6edf7aec9076.png)
 
 * Langkah 2
 
![image](https://user-images.githubusercontent.com/61129358/96362822-4195d780-115a-11eb-880a-36e8f32d0b93.png)
 
 * Langkah 3
 
![image](https://user-images.githubusercontent.com/61129358/96362824-45295e80-115a-11eb-96fa-116f2d3e6f24.png)


10.  Cari file .pdf di wireshark lalu download dan buka file tersebut! clue: "25 50 44 46" 
**Wireshark hex value finder = 25 50 44 46**

Langkah-langkah:
 * Buka file PCAP dengan wireshark, lalu dengan menggunkan hex value finder, masukkan 25 50 44 46, lalu tekan find. Klik kanan pada  paket yang ditemukan, lalu pilih follow TCP Stream
 
![image](https://user-images.githubusercontent.com/61129358/96362820-3e025080-115a-11eb-8b51-6edf7aec9076.png)
 
 * Pada pilihan Show and save data as, pilih Raw
 
 ![image](https://user-images.githubusercontent.com/61129358/96362874-ca147800-115a-11eb-99d0-264156072322.png)
 
 
 * Simpan file tersebut dengan ekstensi .pdf
 
![image](https://user-images.githubusercontent.com/61129358/96362877-cf71c280-115a-11eb-991a-b7975704d273.png)

 * Berikut file pdf yang tersimpan:
 
 ![image](https://user-images.githubusercontent.com/61129358/96362880-d26cb300-115a-11eb-8e0c-3db5dd5a4894.png)
 
12. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
**Wireshark capture-filter = src port 80**

Langkah-langkah:
 * Buka Wireshark, lalu masukkan src port 80 pada capture filter, pilih device yang sedang digunakan
 
![image](https://user-images.githubusercontent.com/61129358/96363012-c7fee900-115b-11eb-8042-c9e6710b12cc.png)
 
 * Berikut hasilnya: 
 
 (kosong karena port 80 merupakan http, dan posisi sedang tidak membuka web apapun)
 
 ![image](https://user-images.githubusercontent.com/61129358/96363015-cdf4ca00-115b-11eb-9ca5-654633856438.png)


14. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

**Wireshark capture-filter = src host 192.168.0.106**

Langkah-langkah:
 * gunakan command ipconfig pada cmd untuk mencari ip sendiri
 
![image](https://user-images.githubusercontent.com/61129358/96363162-aeaa6c80-115c-11eb-9d6b-1a351baa8c98.png)
 
 * Ip sendiri: 192.168.0.106
 
 ![image](https://user-images.githubusercontent.com/61129358/96363165-b36f2080-115c-11eb-80d3-5c7e891ab759.png)

 * Masukkan src host 192.168.0.106 pada capture filter, pilih network device yang sedang digunakan:
 
 ![image](https://user-images.githubusercontent.com/61129358/96363169-b833d480-115c-11eb-927f-0f6b4097d4a7.png)
 
 * Berikut hasilnya:
 
 ![image](https://user-images.githubusercontent.com/61129358/96363174-be29b580-115c-11eb-9ef6-f55a183e7602.png)
 
 



 

