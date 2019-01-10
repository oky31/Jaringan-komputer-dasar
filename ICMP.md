# ICMP
Stack Protokol TCP/IP menyediakan sebuah mekanisme untuk mengecek ketika terjadi kesalan pada jaringan. mekanisme ini adalah ICMP, ini berupa pesan yang di kirim jika terjadi kesalahan tertentu, tujuan dari pesan ini adalah untuk menerima umpan balik tentang masalah yang terjadi.

## Pesan ICMP
* Host confirmation
* Destination atau Service Unreachable
* Time exceeded
* Route redirection


### Host Confirmation 
pesan yang berupa Echo yang di gunakan untuk menentukan jika host itu
beroperasi, jika local host mengirim ICMP Echo Request ke sebuah host maka akan di balas ICMP Echo oleh host yang menandakan host itu aktif


### Destination Atau Service Unreachable
ketika host atau gateway menerima packet yang tidak bisa di kirm, bisa mengunakan ICMP Destination Unreachable massage untuk memberitahu pengirim bahwa tujuan atau service tidak bisa di jangkau

kode untuk ICMPv4 :  
* 0 -> menandakan Network tidak terjangkau
* 1 -> menandakan Host tidak terjangkau
* 2 -> menandakan Protokol tidak terjangkau
* 3 -> menandakan Port tidak terjangaku

### Time Exceeded
ICMPv4 Time Exceeded di gunakan oleh router untuk menunjukan sebua paket tidak bisa di teruskan karena Time To Live (TTL) dari paket mendekati ke 0. jika router menerima paket yang memiliki TTL 0 maka router akan mengabaikan paket lalu mengirim pesan ke host sumber yaitu pesan Time Exceede


# ICMPv6
Note: DAD is not required, but RFC 4861 recommends that DAD is performed on unicast addresses


# bersambung ke  Trace rouce dan Ping ....