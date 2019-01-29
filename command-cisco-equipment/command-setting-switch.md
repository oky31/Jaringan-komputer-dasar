
### Masuk ke Privileged EXEC Mode
```
Switch>enable  
Switch#
```

### Masuk ke Global Config
```
Switch#configure terminal
Switch(config)#
```

### Setting virtual interface
```
Switch(config)#interface vlan 1   
Switch(config-if)#
```

### Setting IP di interface vlan 1
```
Switch(config-if)#ip address 192.168.1.10 255.255.255.0
```

### Aktifkan Interfaces
```
Switch(config-if)#no shutdown
```

### Melihat Ip Address
```
Switch#show ip interface brief
``` 
