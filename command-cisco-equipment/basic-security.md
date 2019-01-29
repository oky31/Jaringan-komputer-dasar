
```
Router(config)# service password-encryption              -> untuk enkripsi password
Router(config)# security password min-length 8           -> minimal panjang password 8 karakter
Router(config)# login block-for 120 attempts 3 within 60 -> block login selama 120 detik ketika gagal 3 kali dalam waktu 60 detik
```

# mengamankan line console
```
Router(config)# line vty 0 4
Router(config-line)# exec-timeout 10  -> diskonek setelah 10 menit
Router(config-line)# end
```

# melihat konfigurasi
```
Router# show running-config
```

# setting secure ssh
1. konfigurasi ip domain name
```
R1# configure terminal
R1(config)# ip domain-name span.com
```

2. generate one-way secret key
```
R1(config)# crypto key generate rsa general-keys modulus 1024
``` 

3. verfikasi atau buat sebuah local database untuk login
```
R1(config)# username Tama secret cisco   
```

4. aktifkan ssh di VTY
```
R1(config)# line vty 0 4
R1(config-line)# login local
R1(config-line)# transport input ssh
R1(config-line)# exit

```