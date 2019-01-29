### Bentuk umum command
```
namaPerangkat>command
```

### Bentuk Ketika Berada di Privileges EXEC Mode
```
Switch#
```

### Bentuk Ketika Berada di user EXEC Mode
```
Switch>
```

### Masuk ke privileged EXEC Mode
```
Switch>enable 
Switch#
```

### Keluar dari Privileged EXEC Mode
```
Switch#disable  
Switch>
```

### Global Configure Mode (configure terminal)
```
Switch#configure terminal 
Switch(config)#
```

### Memberi nama hostname
```
Switch(config)# hostname namaHost
Switch(config)# hostname Switch-lantai-1  
Switch-lantai-1(config)#
```

### Menghapus nama host
```
Switch-lantai-1(config)# no hostname 
Switch(config)#
```



# CONFIGURATION (konfigurasi)

### Melihat configurasi yang sedang di gunakan, di ketik di dalam Priviled EXEC mode
```
Switch#show running-config
Switch#show startup-config
```

### Menyimpan configurasi
```
S1#copy running-config startup-config 
S1#copy startup-config running-config 
```

### Melihat Direktori penyimpanan configurasi
```
S1#dir ? 
S1#dir nvram: -> melihat isi direktori yang ada di nvram 
S1#dir flash: -> melihat isi direktori yang ada di flash 
```

### Setting Password untuk priveled EXEC Mode
```
S1(config)#enable password nama-passowrd   -> setting password tanpa enkripsi 
S1(config)#enable secret nama-passowrd     -> setting password dengan enkripsi
```

### Memberi banner, untuk menulis banner harus di apit oleh delimiter bisa berupa
tanda yang tidak terdapat di dalam banner seperti '#', '"', dll
```
Switch(config)#banner motd "ini berisi banner yang akan di tulis "
```

### Enkripsi semua password , di lakukan di dalam global config 
```
Switch(config)#service password-encryption
```


### Menghapus configurasi
```
S1#erase startup-config -> menghapus konfigurasi di startup config 
```

## Mereload (restart) device
```
S1#reload
```

