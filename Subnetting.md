
# Broadcase Domain
yang melakukan broadcast adalah ethernet LAN dari host untuk :
* Menemukan perangkat lain 
* Menemukan layanan seperti 

Router tidak menyebarkan broadcast, ketika router menerima broadcast, router tidak akan meneruskan ke interfaces lain

# Permasalahan Pada Broadcast
untuk Network yang memiliki banyak host, bisa menjadi sebuah masalah karna setiap perangkan akan mengirimkan broadcast dan membuat padat lalu lintas network.  
Agar tidak membuat padat lalulintas jaringan maka network yang besar di bagi menjadi bagian-bagian kecil dan proses ini di sebut **subnetting**, bagian dari network yang besar itu di sebut **subnet**

# Bit netwrok  dan bit host
```
                Ip                   | Prefix | Subnet Mask
nnnnnnnn.hhhhhhhh.hhhhhhhh.hhhhhhhh  | /8     | 255.0.0.0
nnnnnnnn.nnnnnnnn.hhhhhhhh.hhhhhhhh  | /16    | 255.255.0.0
nnnnnnnn.nnnnnnnn.nnnnnnnn.hhhhhhhh  | /24    | 255.255.255.0
```
**keterangan** :  
`n` -> bit network   
`h` ->  bit host 


# Batas Oktet
subnet mask di konfigurasi pada interface router yang di gunakan untuk menentukan domain broadcast

Menentukan Subnet  :  
- subnet IPv4 di buat dengan mengunakan satu atau lebih bit host sebagai bit network
- untuk memperluas subnet mask , pinjam beberapa bit dari bagian host untuk di jadikan bit network
- semakin banyak bit host yang di pinjam  makan semakin banyak subnet yang dapat di definisikan

# Subnetting pada batas Oktet
Untuk mengerti subnetting pada batas Oktet, lihat contoh berikut. Asumsikan sebuah enterprise memilih private address 10.0.0.0/8  sebagai internal network address. alamat network itu akan memiliki  16.777.214 host di dalam **broadcast domain**, dan ini sangat tidak ideal,  karna akan membuat macet lalulintas jaringan

sebuah enterprise bisa membuat subnet pada address 10.0.0.0/8 dengan batas oktet /16, dan ini akan menyediakan sekitar 256 **subnet** dan setiap subnet memiliki host sekitar 65.534. Perhatikan bagaimana dua oktet pertama mengidentifikasi bagian jaringan dari alamat sementara dua oktet terakhir adalah untuk alamat IP host

Atau enterprise bisa memilih subnet pada batas oktet /24, batas oktet ini memiliki sekitar 65.536 subnet dan masing-masing subnet memiliki sekitar 254 host

# Classsless Subnetting
Subnet bisa di lakukan dengan meminjam setiap bagian bit host untuk membuat subnet mask

misal pada alamat yang memiliki batas oktet /24, bisa di pecah menjadi :

- /25 -> meminjam 1 bit dari oktet ke-4 dan mendukung 126 host
- /26 -> meminjam 2 bit dari oktet ke-4 dan mendukung 62 host 
- /27 -> meminjam 3 bit dari oktet ke-4 dan mendukung 30 host
- /28 -> meminjam 4 bit dari oktet ke-4 dan mendukung 14 host
- /29 -> meminjam 5 bit dari oktet ke-4 dan mendukung 6 host
- /30 -> meminjam 6 bit dari oktet ke-4 dan mendukung 2 host

# Menemukan subnet dengan Magic number

Daftar Magic number  
```
  2^7  |  2^6  |  2^5  |  2^4  |  2^3  |  2^2  |  2^1  |  2^0  |   
----------------------------------------------------------------
  128  |  64   |  32   |  16   |   8   |   4   |   2   |   1   |
----------------------------------------------------------------
    0  |   0   |    0  |   0   |    0  |   0   |   0   |   0   |
```

Magic number adalah ? binari terakhir yang bernilai `1` pada batas oktat  

Contoh : 
```
   192  .  168   .    0   .    0/25
11111111.11111111.11111111.10000000

```
Jadi magic numbernya adalah 128, jadi untuk mencari network cukup tambahkan alamat IP dengan 128, jadi :
```
   192.168.0.0/25 
   memiliki network 2 yaitu :
   192.168.0.0
   192.168.128.0
```

# Setelah Dapat Subenet
setelah menemukan subnet, di dalam setiap subnet harus memiliki :
```
total usable host -> 2^n-2
Network Addres ->
First host Address ->
Last host Address ->
Broadcast Address ->

Keterangan :
n -> jumlah host yang di pinjam
```

# Rumus subnet
Menghitung jumlah host 
```
2^n dimana n adalah jumlah 0 yang terdapat di bit subnet mask
```

# Subnetting berdasarkan kebutuhan
2 pertimbangan untuk membuat subnet :
- Jumlah host yang di butuhkan di setiap network
- Jumlah sub-network yang di butuhkan


# Variable Length Subnet mask (VLSM)

# kata Kunci
- network address
- first host address
- last host address
- broadcast address

# Wajib di inggat
- untuk mencari alamat network di dalam subnet, gunakan magic number untuk mempermudah