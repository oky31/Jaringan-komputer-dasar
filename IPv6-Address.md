# IPv6 Address
Alamat ini di desain sebagi pengganti IPv4, IPv6 di representasikan dengan 128-bit dan di tulis dengan bilangan hexadesimal,  jadi bisa menampung sekitar 340 undecillion alamat

* 128 bits(panjang) = 32 digit hexadecimal
* 4 bits(panjang) diwakili oleh satu digit hexadisimal
* 4 hexadecimal digit = 16 biniary digit
* tidak case-senstive

# Format penulisan IPv6

```
x:x:x:x:x:x:x:x
```
Dimana :  
* x terdiri dari 4 digit hexadesimal
* 4 digit hexadesimal = 16 binary digit
* 4 digit hexadesimal atau 16 digit binari disebut **segment**

# Aturan 
1. Abaikan setiap 0 yang ada 16-bit section  atau hexa, cara melihatnya 
dari kiri ke kanan
```
2001 : 0DB8 : 0000 : 1111 : 0000 : 0000 : 0000 : 0200
                
                    Menjadi 

2001 :  DB8 :    0 : 1111 :    0 :    0 :    0 :  200

```
2. Abaikan semua segment yang bernilai 0 dengan mengunakan ``::`` dan sayarat, ``::`` hanya bisa di gunakan 1 kali di dalam alamat

```
# contoh 1
2001 : 0DB8 : 0000 : 1111 : 0000 : 0000 : 0000 : 0200
                   Menjadi 
2001 :  DB8 :    0 : 1111 :    0 :    0 :    0 :  200
                   Menjadi
2001:DB8:0:1111::200


# contoh 2
2001 : 0DB8 : 0000 : 0000 : ABCD : 0000 : 0000 : 0100
                   Menjadi
2001 :  DB8 :    0 :    0 : ABCD :    0 :    0 :  100
                   Menjadi

2001:DB8::ABCD:0:0:100
        Atau 
2001:DB0:0:0:ABCD::100
```

# Teknik Migrasi dari IPv4 ke IPv6
- **Dual Stack** -> membuat IPv4 dan IPv6 ada pada network segemnt yang sama
- **Tunneling** -> mengirimkan packet IPv6 melalui IPv4 network. Packet IPv6 di enkapsulasi ke dalam IPv4
- **Translation** -> mengunakan teknik NAT64. teknik ini membuat IPv4 dan IPv6 bisa berkomunikasi melalui penerjemah, yaitu NAT64

# Tipe Alamat IPv6
* Unicast -> Alamat unicast IPv6 secara unik mengidentifikasi antarmuka pada perangkat yang mendukung IPv6.
* Multicast -> Alamat multicast IPv6 digunakan untuk mengirim paket IPv6 tunggal ke beberapa tujuan
* Anycast -> Adalah alamat unicast IPv6 yang dapat ditetapkan ke beberapa perangkat

# Prefix Atau network portion

* IPv6 tidak mengunakan desimal subnetmask
* prefix yang di gunakan untuk mengindikasikan network portion
* prefix length bisa antar 0 sampai 128

```
2001:0DB8:A::/64 
     =
64 bits Prefix(networ parition) dan 64 bits Interface ID
     =
2001:0DB8:000A:0000   0000:0000:0000:0000
```

# IPv6 Unicast
2 tipe umum  IPv6 unicast :
```  
- Global unicast -> sama seperti ip public pada IPv4

- Link-local -> di gunakan untuk berkomunikasi dengan alamat dengan local link yang sama, local link di sini mengarah ke subnet

- Unique local ->  sama seperti private address di IPv4 dan ini di jelaskan dalam RFC 1918, alamat ini tidak boleh di route kan kedalam  global IPv6 .berada pada range ``FC00::/7`` sampai ``FDFF::/7``
```

# IPv6 Link-Local unicast address
- adalah alamat yang di gunakan agar bisa berkomunikasi dengan host yang memiliki Link-local sama (subnet)
- setiap network interface membutuhkan link-local address
- jika link local address tidak di konfigurasi secara manual, maka perangkat akan otomatis membuat nya sendiri dengan bantuan DHCP server.


# Struktur IPv6 Global Unicast Address