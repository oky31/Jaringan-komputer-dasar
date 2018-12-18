# IP-Address (Alamat IP)
Alamat IP digunakan untuk komunikasi data atar host( pengguna ) dan alamat pasti unik.  ada 2 jenis Alamat IP yaitu versi 4 atau IPv4
atau versi 6 IPv6.

## IPv4
IP versi 4 di represntasikan dengan 2 jenis bilangan, yaitu: bilangan biner dan bilangan desimal. 

**IPv4 Biner**  
Alamat IPv4 dalam biner terdiri dari 32 bit dan di bagi menjadi 4 bagian yang di sebut octets dan masing-masing octects terdiri dari 8 bit.
```
11000000.10101000.00001010.00000001
```

**IPv4 Desimal**  
Alamat IPv4 dalam desimal cukum menkonversi dari biner ke desimal 
```
11000000.10101000.00001010.00000001  #biner

   192  .   168  .   10   .   1      #desimal
```

**Network dan Host**  
Alamat IP di bagi menjadi menjadi **Network** dan **Host**

**subnet mask** -> di gunakan untuk mengidentifikasi network dan host pada alamat ip

**Logika AND**  
logika ini di gunakan untuk mencari network address dengancara meng-AND kan binari IP Address dan Subnet Mask
```
1 AND 1 = 1
0 AND 1 = 0
0 AND 0 = 0
1 AND 0 = 0
```

**Menetukan Network Address**  
```
Ip Adress    192.168. 10.10  -> 11000000.10101000.00001010.00001010
Subnet Mask  255.255.255.0   -> 11111111.11111111.11111111.00000000
                                             AND       
AND Results  192.168. 10.0   -> 11000000.10101000.00001010.00000000

```
Jadi network Addressnya 192.168.10.0

**Network, Host, dan Broadcast Addresses**  
Di dalam alamat IPv4  berisi Network, Host, dan Broadcast Addresses :  
```
- Network Address --> alamat dan subnetmask untuk network
- Host Address    --> alamat unik untuk perangkat atau host (pengguna)
- First Host      --> alamat pertama yang tersedia di dalam network
- Last Host       --> alamat terakhir yang tersedia di dalam network
- Broadcase       --> alamat spesial yang berkomunikasi dengan semua host di dalam network
```

## Mencari Subnet Mask ?
1. konversi prefix ip kedalam binari
2. konversi binari prefix if ke dalam desimal

## Mencari Networ Address ?
"Network address adalah alamat ip pertama di dalam network, berdasarkan class ip nya"   
**cara komputer menentukan network address :**  
1. konversi IP address dan subnet mask ke binari
2. Operasikan Ip address dan Subnetmask dengan operator ANDing

## Mencari Broadcast address ?
"Broadcast address adalah alamat ip terakhir di dalam network, berdasarkan class ip nya"

## Mencari First usable host address ?
adalah IP address setelah network address

## Mencari Last usable host address ?
adalah IP address sebelum broadcast address

## Mencari jumlah host di dalam 1 network ?
1. lihat berapa prefix ip addres nya , jika tidak ada lihat subnet mask nya
2. jika ada prefix, maka nilai prefix itu berarti jumlah angka 1 dalam 32 digit binari ip address dan host nya adalaha 2 di pangkat jumlah banyaknya 0 di dalam 32 digit binari ip address

