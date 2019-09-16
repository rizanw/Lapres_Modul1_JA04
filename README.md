# Lapres Modul1 Jarkom

## Kelompok A04
1. Mochamad Thiesa Nabil
2. Iman Afandy
3. Rizky Andre Wibisono

### Capture Filter
#### Nomer 1
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21

#### Jawaban
```
port 21
```
#### Nomer 2
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80 (ajk.if.its.ac.id)

#### Jawaban
```
src port 80 && host ajk.if.its.ac.id
```
#### Nomer 3
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443 (google.com)

#### Jawaban
```
dst port 443 && host google.com
```
#### Nomer 4
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian

#### Jawaban
Setelah mengecek alamat IP dengan `ipconfig`. Gunakan alamat tersebut untuk melihat paket yang dikirim dengan
```
src ip <ip pemilik>
```
#### Nomer 5
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id

### Jawaban
```
dst host monta.if.its.ac.id
```

### Display Filter
#### Nomer 1
