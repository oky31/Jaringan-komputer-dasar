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

----------------Cara komputer mencari broadcast address----------------
1. konversi subnet mask ke binari
2. konversi ip address ke binari
3. lakukan opersi bitwise OR binari subnetmask dan binari ip address

# Cara Host berkomunikasi di dalam jaringan
- Unicast -> mengirim packet dari 1 host hanya ke 1 host yang lain
- Broadcast -> mengirim packet dari 1 host ke semua host dalam network
- Multicast -> mengirim packet dari 1 host ke grup host tertentu, dan memungkinkan grup host yang memiliki network berbeda

dan ketiga jenis komunikasi ini di gunakan untuk tujuan yang berbeda.

# unicast
Digunakan :
- host ke host
- host ke server
- peer to peer network

alamat unicast berapada pada 0.0.0.0 sampai 223.255.255.255.  tetapi di rentang ini ada pula alamat yang di sediakan untuk tujuan khusus 

# broadcast
untuk mengirim paket ke semua alamat di dalam jaringan maka kirim lah paket tersebut ke broadcast address dan otomatis seluruh host menerima paket yang di kirimkan.
broadcast juga memungkin di gunakan di layer **Data Link** dengan mengirimkan data ke **MAC address FF:FF:FF:FF:FF:FF**

Digunakan :
- di gunakan oleh DHCP untuk mencari dan mengirim permintaan ke server masing-masing

# multicast
muticast mengurangi lalulintas data dengan mengirimkan paket tunggal ke kumpulan host yang di pilih.
alamat multicast ada pada 224.0.0.0 sampai 239.255.255.255 dan untuk local network berada pada 224.0.0.0 sampai 224.0.0.255.

- **multicast client** adalah host yang menerima multicast data
- setiap grup multicast di representasikan oleh 1 IPv4 address
Digunakan :
- Routeing Information Protocol(RIP)

# Ip Public dan Private 
IP public -> adalah ip yang di gunakan oleh isp, ip yang di gunakan secara global
IP private -> adalah ip yang di gunakan untuk internal host atau local area network

## IP Private
```
class A -> 10.0.0.0/8 
class B -> 172.16.0.0/12
class C -> 192.168.0.0/16

      Atau 

class A -> 10.0.0.0 sampai 10.255.255.255
class B -> 172.16.0.0/12 sampai 172.31.255.255
class C -> 192.168.0.0/16 samapi 192.168.255.255

```

# Special IPv4 Address
- Loopback Address (127.0.0.0/8) -> untuk dirisendiri
- Link-Local addresses (169.254.0.0 /16) -> private ip yang otomatis di gunakan oleh windows DHCP client untuk konfigurasi di sendiri, jika tidak ada server yang tersedia

dan dijelaskan didalam RFC 3330

# class IPv4
ip di clasifikan berdasarkan alamat ip dan netmask

```
Class A 
(0.0.0.0/8 to 127.0.0.0/8)
128 Network
16.777.214 host

Class B 
(128.0.0.0 /16 – 191.255.0.0 /16)
16.384 Network
65.534 host

Class C 
(192.0.0.0 /24 – 223.255.255.0 /24)
2.097.152 Network
254 host
```
setiap masing-masing class memiliki host yang berbeda2 berdasarkan prfix ipnya  

**Catatan Penting !!**  
pengunaan class di dalam IPv4 sudah lama di tingalkan semenjak tahun 90's.  
Dan sistem yang di gunakan sekarang adalah **Classless Inter-Domain**(CIDR, pronounced "cider") jadi intinya tidak ada pengolongan class di dalam ip.

# Lembaga Pengatur Pembagian IP address
````
IPv4 dan IPv6 -> Internet Assignet Numbers Authority(IANA)

Antar Regional
- ARIN (American Register for Internet Numbers) -> North America
- LACNIC (Latin-American and Caribbean Ip Address Registry ) -> Amerika Latin dan Pulau Karibian
- RIPE (Reseaux IP Europeans) -> Eropa, Middle Eest, Asia Tengah
- APNIC (Asian Pacific Network Information Cetner) -> Asia, pasifik termasuk australia
- AfriNIC (Afican Network Information Center) -> Afrika
````


# cari algoritma konversi desimal ke binary