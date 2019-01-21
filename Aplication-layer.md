# Application Layer
Adalah protocol yang langsung berhadapan dengan end user, protocol ini menyediakan interface antara aplikasi yang di gunakan untuk berkomunikasi dan jaringan yang mengirim pesan


# Presentation dan Session Layer
Presentasion layer memiliki 3 fungsi utama yaitu :
1. memformat dan menyajikan data pada peragkat sumber kedalam bentuk data yang sesuai untuk deterima oleh perangkat tujuan
2. Mengompresi data dengan cara yang bisa decompress oleh perangkat tujuan
3. melakukan enkripsi data untuk di kirim dan decrypt data setelah di terima

Sesion layer memilki fungsi :
* Membuat dan me-maintain percakapan antara aplikasi sumber dan tujuan
* Menangani pertukaran informasi untuk menginisiasi percakapan, menjaga percakapan tetap aktif, dan mengulang kembali session yang tergangu atau diam untuk waktu yang lama


# TCP/IP Application Layer Protocols
* Domain Name System (TCP, UDP 53)
* DHCP (UDP client 68, server 67)
* Mail Transfer Protocol (TCP 25)
* Post Office Protocol (TCP 110)
* Internet Message Access Protocol (TCP 143)
* File Transfer Protocol (TCP 20 / 21)
* Trivial File Transfer Protocol (UDP 69)
* Hypertext Transfer Protocol (TCP 80, 8080)
* Hypertext Transfer Protocol Secure (TCP, UDP 443)

# Email Protocol
Email membutuhkan beberapa protokol dan layanan untuk bisa berjalan. Email juga bisa di sebut sebagai sebuah metode yang menyimpan-dan-meneruskan, menyimpan dan mengambil pesan elektronik melalui jaringan.

Email client berkomunikasi dengan  mail-server untuk mengirim dan mengabil data. Mail-server berkomunikasi dengan mail-server lain untuk mengirim pesan dari satu domain ke domain yang lain. jadi email clicent tidak berkomunikasi langsung dengan email client lain ketika mengirimkan pesan

Email mendukung 3 protocol untuk beroperasi :
* Simple Mail Transfer Protocol (SMTP)
* Post Office Protocol(POP)
* IMAP
Aplication layer memproses dan mengirim email mengunakan SMTP. Sebuah email client mengambil email mengunakan protocol POP atau IMAP

## Pekerjaan SMTP
pesan SMTP tersusun dari header dan body message. header tersusun dari email penerima dan email pengirim sedangkan body berisi sekumpulan text.
Ketika client mengirim pesan, SMTP client memulai proses konek ke SMTP server melalui port 25. Setelah koneksi berhasil di buat, client bisa mengirim pesan melalui koneksi yang telah di buat. Ketika server menerima pesan, pesan di tempatkan di **local Account**, jika penerimnya adalah local, atau meneruskan pesan ke mail server yang lain.

ketika mail server offline atau sibuk, pesan SMTP bisa di kirim nanti, dan secara periodik server melakukan pengecekan di antrian pesan mencoba untuk mengirimkan pesan itu kembali. jika pesan tidak terkirim juga dalam waktu yang telah di tentukan sebelumnya, pesan akan di kembalikan ke pengirim sebagai pesan yang tidak terkirim.

## Pekerjaan POP
POP di gunakan aplikasi untuk mengabil pesan dari mail server. dengan POP pesan di download  dari server ke client dan menghapus pesan pada server.
POP service berjalan pada TCP port 110 untuk client membuat koneksi. 

## Pekerjaan IMAP
Sama seperti POP, IMAP adalah protocol yang di gunakan untuk mengabil pesan dari server, tetapi tidak seperti POP ketika client terkoneksi ke IMAP server, pesan di copy dan di download oleh client, dan pesan asli di biarkan tetap berada pada server sampai di hapus secara manual

# Domain Name Service (DNS)
Di dalam data yang di kirim melalui jaringan, perangkat di beri alamat Yaitu IP address untuk mengirim dan menerima data melalui jaringan.  DNS di buat untuk mengkonversi numeric address ke dalam string simpel, agar mudah di kenali.

Record yang ada di DNS Server :
* A -> alamat Ipv4 End device
* NS -> authoritative name server
* AAAA -> alamat IPv6 end device
* MX -> catatan pertukaran email  

Ketika client melakukan permintaan ke  DNS server, proses yang pertama di lakukan adalah melihat record untuk menemukan nama. jika nama tidak di temukan, server akan menghubungi server lain untuk menemukan nama. setelah nama di temukan  dan di kemblikan ke server yang pertama meminta nama, lalu server menyimpan nama jika suatu saat di butuhkan lagi
   
Format Pesan DNS :
```
------------------
|   Header       |
------------------
|   Question     | 
------------------ 
|   Answer       | 
------------------
|   Authoritiy   |
------------------
|   Additional   |
------------------
```

# Dynamic Host Configuration Protocol (DHCP)
DHCP IPv4 di gunakan utuk memberi alamat, subnet masks, gateways, dan IPv4 networking parameter secara otomatis. alamat yang di berikan DHCP bersifat dynamic 