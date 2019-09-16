# Lapres_Modul1_JA04

### Oleh:
- Iman Afandi ()
- Tisa Nabil ()
- Rizky Andre Wibisono (05111740000183)

## Capture Filter
### NO1
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21
#### Jawab:
langsung gunakan `` port <alamat port>``
```
port 21
```
##### Screenshot:
<img src="img/Capture1.PNG" width="600">
port 21 adalah port ftp, dan tidak ada ftp yang sedang saya buka.
<img src="img/Capture2.PNG" width="600">

### NO2
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80 (ajk.if.its.ac.id)
#### Jawab:
Untuk mencari paket yang berasal dari port 80 yaitu ajk.if.its.ac.id dapat dengan menggabungkan command ``src port <port>`` dengan ``host <alamat host>``.
```
src port 80 && host ajk.if.its.ac.id
```
##### Screenshot:
<img src="img/Capture3.PNG" width="600">
<img src="img/Capture4.PNG" width="600">

### NO3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443 (google.com)
#### Jawab:
````
dst port 443 && host google.com
````
##### Screenshot:
<img src="img/Capture5.PNG" width="600">
<img src="img/Capture6.PNG" width="600">

### NO4
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian
#### Jawab:
cek ip kita dengan ``ipconfig`` lalu gunakan ``ip src <ip4 kita>``
```
ip src <ip kalian>
```
##### Screenshot:
<img src="img/Capture7.PNG" width="600">
<img src="img/Capture8.PNG" width="600">

### NO5
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id
#### Jawab:
````
dst host monta.if.its.ac.id
````
##### Screenshot:
<img src="img/Capture9.PNG" width="600">
<img src="img/Capture10.PNG" width="600">

<br />

## Display Filter
### NO1
Tampilkan semua paket yang hostnya mengandung www.ne.its.ac.id
#### Jawab:
```
http.host == ne.its.ac.id
```
#### Screenshot:
<img src="img/Capture11.PNG" width="600">

### NO2
Tampilkan paket yang hanya berasal dari IP 10.151.36 81 dan menuju web "mb.its.ac.id"
#### Jawab:
```
ip.src == 10.151.36.81 && http.host == "mb.its.ac.id"
```
#### Screenshot:
<img src="img/Capture12.PNG" width="600">

### NO3
Simpan gambar ckedokteran.PNG
#### Jawab:
Tidak ada karena gambar ckedokteran.PNG memang tidak ada.

#### Screenshot:
<img src="img/Capture13.PNG" width="600">

### NO4
Cari charset dari halaman "ajk.if.its.ac.id"
#### Jawab:
Tidak ada juga 

### NO5
Cari username dan password ketika login di "freeshare.lp.if.its ac.id"
#### Jawab:
```
http.host == freeshare.lp.if.its.ac.id && frame contains login
```

#### Screenshot:
<img src="img/Capture14.PNG" width="600">

### NO6
Sebutkan web server yang digunakan pada "www.ne.its.ac.id"
#### Jawab:
```
http.host == ne.its.ac.id
```
lalu klik kanan > follow > TCP stream.

#### Screenshot:
<img src="img/Capture15.PNG" width="600">

### NO7
Sebutkan versi PHP dan yang digunakan pada "riset.ajk.if.its.ac.id"
#### Jawab:
```
http.host == riset.ajk.if.its.ac.id
```
lalu klik kanan > follow > TCP stream.

#### Screenshot:
<img src="img/Capture16.PNG" width="600">

### NO8
Filter pada wireshark kalian sehingga menampilkan hasil ping
#### Jawab:
```
icmp
```

#### Screenshot:
<img src="img/Capture17.PNG" width="600">

### NO9
Dapatkan semua metode GET yang mengakses "monta.if.its.ac.id"
#### Jawab:
```
http.request.method == GET && http.host == monta.if.its.ac.id
```

#### Screenshot:
<img src="img/Capture18.PNG" width="600">

### NO10
Tunjukkan username dan password yang dimasukkan ketika login FTP
#### Jawab:
```
ftp.request.command == USER || ftp.request.command == PASS
```

#### Screenshot:
<img src="img/Capture19.PNG" width="600">

### NO11
Tunjukkan di wireshark, paket mana yang dikirimkan FTP client ketika upload file 
#### Jawab:
```
ftp.request.command == STOR && ftp.request.arg == qwpeaspojdasjfpasjfpaosuhuy.jpg
```

#### Screenshot:
<img src="img/Capture20.PNG" width="600">

### NO12
Tunjukkan di wireshark, paket mana yang dikirimkan FTP client ketika menghapus file 
#### Jawab:
harusnya:
```
ftp.request.command == DELE && ftp.request.arg == qwpeaspojdasjfpasjfpaos.jpg
```
tidak akan muncul, karena file tersebut tidak ada.
cek:
```
ftp.request.command == DELE
```
hanya file tersebut yg ada (cek Capture22.PNG)
#### Screenshot:
<img src="img/Capture21.PNG" width="600">
<img src="img/Capture22.PNG" width="600">

### NO13
Tunjukkan di wireshark, paket mana yang dikirimkan FTP client ketika mengganti nama file "sutlin.PNG"
#### Jawab:
```
ftp.request.command == RNFR && ftp.request.arg == sutlin.PNG
```
#### Screenshot:
<img src="img/Capture23.PNG" width="600">

### NO14
Tunjukkan di wireshark, paket mana yang dikirimkan FTP client ketika download file "sutlun.PNG"
#### Jawab:
```
ftp.request.command == RETR && ftp.request.arg == sutlun.PNG
```

#### Screenshot:
<img src="img/Capture24.PNG" width="600">

### NO15
Cari file .zip di wireshark lalu download dan extract file tersebut <br />
clue: "50 4B 03 04"
#### Jawab:
1. cari data ftp
```
ftp-data
```
2. Cari file zip
3. klik kanan > Follow > TCP Stream
4. dengan clue tersebut, mungkin berarti mengandung hexadecimal.
5. maka, pastikan dalam raw.
6. jika iya, Save as folder berformat zip.
7. ekstrak zip dan lihat keajaibannya!

#### Screenshot:
<img src="img/Capture25.PNG" width="600">
<img src="img/Capture26.PNG" width="600">
<img src="img/Capture27.PNG" width="600">
<img src="img/Capture27.PNG" width="600">
<img src="img/Capture28.PNG" width="600">
