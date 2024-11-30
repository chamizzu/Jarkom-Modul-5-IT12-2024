# Jarkom-Modul-5-IT12-2024

## Kelompok IT12
### Anggota Kelompok :
|             Nama              |     NRP    |
|-------------------------------|------------|
| Azza Farichi Tjahjono         | 5027231071 |
| Aisyah Rahmasari              | 5027231072 |


## TOPOLOGI

![image](https://github.com/user-attachments/assets/cb3d6cc1-3252-4796-95c8-6a291f7383d3)

## Pembagian IP
![image](https://github.com/user-attachments/assets/892e3e0a-4174-46ec-9556-16543bec12b7)

## Konfigurasi Network

### NewEridu

```
auto eth0
iface eth0 inet dhcp

#A1
auto eth1
iface eth1 inet static
  address 192.239.1.217
  netmask 255.255.255.252

#A2 
auto eth2
iface eth2 inet static
  address 192.239.1.221
  netmask 255.255.255.252

#A6
post-up route add -net 192.239.1.200 netmask 255.255.255.248 gw 192.239.1.218

#A7
post-up route add -net 192.239.1.208 netmask 255.255.255.248 gw 192.239.1.218

#A8
post-up route add -net 192.239.1.224 netmask 255.255.255.252 gw 192.239.1.218

#A9
post-up route add -net 192.239.1.128 netmask 255.255.255.192 gw 192.239.1.218

#A4
post-up route add -net 192.239.1.192 netmask 255.255.255.248 gw 192.239.1.222

#A3
post-up route add -net 192.239.0.0 netmask 255.255.255.0 gw 192.239.1.222

#A5
post-up route add -net 192.239.1.0 netmask 255.255.255.128 gw 192.239.1.222
```

### SixStreet

```
#A1
auto eth0
iface eth0 inet static
  address 192.239.1.218
  netmask 255.255.255.252
  gateway 192.239.1.217

#A7
auto eth1
iface eth1 inet static
  address 192.239.1.209
  netmask 255.255.255.248

#A6
auto eth2
iface eth2 inet static
  address 192.239.1.201
  netmask 255.255.255.248

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A4
#route add -net 192.239.1.192 netmask 255.255.255.248 gw 192.239.1.218

#A5
#route add -net 192.239.1.0 netmask 255.255.255.128 gw 192.239.1.218

#A3
#route add -net 192.239.0.0 netmask 255.255.255.0 gw 192.239.1.218

#A8
post-up route add -net 192.239.1.224 netmask 255.255.255.252 gw 192.239.1.210

#A9
post -up route add -net 192.239.1.128 netmask 255.255.255.192 gw 192.239.1.211
```

### HDD ( DNS )

```
#A6
auto eth0
iface eth0 inet static
  address 192.239.1.203
  netmask 255.255.255.248
  gateway 192.239.1.201

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

### FAIRY ( DHCP )

```
#A6
auto eth0
iface eth0 inet static
  address 192.239.1.202
  netmask 255.255.255.248
  gateway 192.239.1.201

up echo nameserver 192.168.122.1 > /etc/resolv.conf
```

### ScootOutpost

```
#A7
auto eth0
iface eth0 inet static
    address 192.239.1.210
    netmask 255.255.255.248
    gateway 192.239.1.209

#A8
auto eth1
iface eth1 inet static
    address 192.239.1.225
    netmask 255.255.255.252

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
post-up route add -net 192.239.1.216 netmask 255.255.255.252 gw 192.239.1.209
```

### HollowZero

```
#A8
auto eth0
iface eth0 inet static
    address 192.239.1.226
    netmask 255.255.255.252
    gateway 192.239.1.225

echo 'nameserver 192.168.122.1' > /etc/resolv.conf

#A1
#post-up route add -net 192.239.1.216 netmask 255.255.255.252 gw 192.239.1.209
```

### OuterRing (DHCP Relay)

```
#A7
auto eth0
iface eth0 inet static
  address 192.239.1.211
  netmask 255.255.255.248
  gateway 192.239.1.209

#A9
auto eth1
iface eth1 inet static
  address 192.239.1.129
  netmask 255.255.255.192

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A1
route add -net 192.239.1.216 netmask 255.255.255.252 gw 192.239.1.209
```

### Burnice (Client)

```
#A9
auto eth0
iface eth0 inet dhcp
```

### Caesar ( Client )

```
#A9
auto eth0
iface eth0 inet dhcp
```

### LuminaSquare ( DHCP Relay )

```
#A2
auto eth0
iface eth0 inet static
    address 192.239.1.222
    netmask 255.255.255.252
    gateway 192.239.1.221

#A4
auto eth1
iface eth1 inet static
    address 192.239.1.193
    netmask 255.255.255.248

#A3
auto eth2
iface eth2 inet static
    address 192.239.0.1
    netmask 255.255.255.0

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A5
post-up route add -net 192.239.1.0 netmask 255.255.255.128 gw 192.239.1.195
```

### Jane( Client )

```
#A3
auto eth0
iface eth0 inet dhcp
```

### Policeboo (Client)

```
#A3
auto eth0
iface eth0 inet dhcp
```

### HIA (Web Server)

```
#A4
auto eth0
iface eth0 inet static
    address 192.239.1.194
    netmask 255.255.255.248
    gateway 192.239.1.193
 
up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A2
post-up route add -net 192.239.1.220 netmask 255.255.255.252 gw 192.239.1.193
```

### BalletTwins

```
#A4
auto eth0
iface eth0 inet static
    address 192.239.1.195
    netmask 255.255.255.248
    gateway 192.239.1.193

#A5
auto eth1
iface eth1 inet static
    address 192.239.1.1
    netmask 255.255.255.128

up echo nameserver 192.168.122.1 > /etc/resolv.conf

#A2
post-up route add -net 192.239.1.220 netmask 255.255.255.252 gw 192.239.1.193
```

### Lycaon

```
#A5
auto eth0
iface eth0 inet dhcp
```

### Ellen

```
#A5
auto eth0
iface eth0 inet dhcp
```
