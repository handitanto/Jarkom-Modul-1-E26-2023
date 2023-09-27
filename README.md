# Jarkom-Modul-1-E26-2023

Berikut adalah laporan resmi Praktikum Jaringan Komputer Modul 1 tahun 2023

Anggota Kelompok C04 :
* 5025201077 - Handitanto Herprasetyo

### 1.User melakukan berbagai aktivitas dengan menggunakan protokol FTP. Salah satunya adalah mengunggah suatu file.

#### a. Berapakah sequence number (raw) pada packet yang menunjukkan aktivitas tersebut?
    Kita diharuskan mencari packet yang ada informasi mengenai pengunggahan suatu file. 
    Pada packet 147 didapatkan suatu informasi mengenai request pengunggahan file "Request: STOR c75-GrabThePhisher.zip". 
    Jika pada packet 147 diklik 2 kali maka akan muncul informasi mengenai sequence number (raw) pada packet tersebut 
    'Sequence number (raw) = 258040667'
`258040667`
    

#### b. Berapakah acknowledge number (raw) pada packet yang menunjukkan aktivitas tersebut?
    Didapatkan informasi mengenai acknowledge number (raw) dari packet yang sama, yaitu packet 147
    'Acknowledge number (raw) = 1044861039'
`1044861039`

##### c. Berapakah sequence number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
    Suatu packet yang melakukan request sesuatu kepada server, pasti akan mendapatkan suatu response.
    Response tersebut berkaitan dengan GrabThePisher sama seperti request sebelumnya.
    Terdapat di packet 149 dengan adanya informasi "Response: 150 Opening BINARY mode data connection for c75-GrabThePhisher.zip"
    'Sequence number (raw) = "1044861039'
`1044861039`

#### d. Berapakah acknowledge number (raw) pada packet yang menunjukkan response dari aktivitas tersebut?
     Acknowledge number (raw) pada packet yang menunjukkan response didapatkan dari detail informasi pada frame sebelumnya
    'Acknowledge number (raw) = 258040696'
`258040696`

### 2.Sebutkan web server yang digunakan pada portal praktikum Jaringan Komputer!
    Mencari di display filter dengan kata kunci 'http'.
    Akan didapatkan pada salah satu paket informasi mengenai web server yaitu "Gunicorn"
`Gunicorn`

### 3.Dapin sedang belajar analisis jaringan. Bantulah Dapin untuk mengerjakan soal berikut:

#### a.Berapa banyak paket yang tercapture dengan IP source maupun destination address adalah 239.255.255.250 dengan port 3702?
      Gunakan display filter dengan expression "ip.addr == 239.255.255.250 && port == 3702".
      Akan didapatkan informasi sebanyak 21 paket yang tercapture dengan ip adrress dan port seperti yang diminta.
`21`

#### b. Protokol layer transport apa yang digunakan?
      Paket menampilkan protokol apa yang dipakai dalam paket tersebut adalah UDP
`UDP`

### 4.Berapa nilai checksum yang didapat dari header pada paket nomor 130?
    Mencari paket no 130 di display filter.
    Jika diklik 2 kali maka akan didapatkan informasi checksum.
    'Checksum = 0x18e5'
`0x18e5`

### 5.Elshe menemukan suatu file packet capture yang menarik. Bantulah Elshe untuk menganalisis file packet capture tersebut.

#### a.Berapa banyak packet yang berhasil di capture dari file pcap tersebut?
    BUka file pcap, kemudian didapatkan jumlah paket = 60
`60`

### b.Port berapakah pada server yang digunakan untuk service SMTP?
    Gunakan display filter "smtp".
    Pada frame 25, detail packet mengenai Tranmission Control Protocol didapatkan port yang dipakai adalah 25.
`25`

### c.Dari semua alamat IP yang tercapture, IP berapakah yang merupakan public IP?
    Terdapat 2 ip, yang merupakan SMTP.
    Untuk mengetahui apakah keduanya merupakan public IP, digunakan situs web "Checking ip address"
    Didapatkan ip address yang merupakan public 'ip = 74.53.140.153'.
`ip = 74.53.140.153`

### 6.Seorang anak bernama Udin Berteman dengan SlameT yang merupakan seorang penggemar film detektif. 
Sebagai teman yang baik, Ia selalu mengajak slamet untuk bermain valoranT bersama. suatu malam, terjadi sebuah hal yang tak terdUga. 
Ketika udin mereka membuka game tersebut, laptop udin menunjukkan sebuah field text dan Sebuah kode Invalid bertuliskan "server SOURCE ADDRESS 7812 is invalid". ketika ditelusuri di google, hasil pencarian hanya menampilkan a1 e5 u21. 
Jiwa detektif slamet pun bergejolak. Bantulah udin dan slamet untuk menemukan solusi kode error tersebut.

### 7.Berapa jumlah packet yang menuju IP 184.87.193.88?
    Gunakan query 'ip.dst == 184.87.193.88', didapatkan 6 paket yang terlihat.
`6`

### 8.Berikan kueri filter sehingga wireshark hanya mengambil semua protokol paket yang menuju port 80! (Jika terdapat lebih dari 1 port, maka urutkan sesuai dengan abjad)
    Untuk mengambil semua protokol paket yang menuju port 80 maka digunakan query 'tcp.dstport == 80 || udp.dstport == 80'
`tcp.dstport == 80 || udp.dstport == 80`

### 9.Berikan kueri filter sehingga wireshark hanya mengambil paket yang berasal dari alamat 10.51.40.1 tetapi tidak menuju ke alamat 10.39.55.34!
    Untuk mengambil paket yang berasal dari alamat '10.51.40.1' tetapi tidak menuju ke alamat '10.39.55.34', digunakan query 'ip.src == 10.51.40.1 && ip.dst != 10.39.55.34'
`ip.src == 10.51.40.1 && ip.dst != 10.39.55.34`

### 10. Sebutkan kredensial yang benar ketika user mencoba login menggunakan Telnet
    Pertama filter terlebih dulu "Telnet" untuk memunculkan semua paket dengan protokol telnet.
    Kemudian, cari dan perhatikan paket-paket yang terkait dengan proses login. 
    Biasanya, login akan melibatkan beberapa paket yang mengirimkan kredensial (username dan password).  
    Pada packet 259 berisi sebuah data "Password:", hal ini mengindikasikan bahwa letak data password akan ada di paket setelah ini dan untuk username ada di sebelumnya.
    Pada packet 262 berisi sebuah data password = 'kesayangannyak0k0'.
    Kemudian untuk username bisa dicari pada packet-packet yang ada di sebelum 259, tiap paket di sebelum paket 259 mengirimkan 1 huruf yang nantinya membentuk kata dhafin. 
    Hal ini diperkuat juga dengan paket 81.
`dhafin:kesayangannyak0k0`













    
