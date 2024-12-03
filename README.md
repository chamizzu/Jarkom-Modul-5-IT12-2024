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

## TREE

![vlsm-tree-modul-5-it12 drawio](https://github.com/user-attachments/assets/0ac8303b-643a-4751-9608-95c052f20165)

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

#A9
post-up route add -net 192.239.1.128 netmask 255.255.255.192 gw 192.239.1.211
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
post-up route add -net 192.239.1.216 netmask 255.255.255.252 gw 192.239.1.209

#A5
post-up route add -net 192.239.1.0 netmask 255.255.255.128 gw 192.239.1.195
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

#A1
post-up route add -net 192.239.1.216 netmask 255.255.255.252 gw 192.239.1.193

#A6
post-up route add -net 192.239.1.200 netmask 255.255.255.248 gw 192.239.1.193

#A9
post-up route add -net 192.239.1.128 netmask 255.255.255.192 gw 192.239.1.218
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


## SETUP

### NewEridu

- setup.sh

```
echo net.ipv4.ip_forward=1 >/etc/sysctl.conf
sysctl -p

ETH0_IP=$(ip -4 addr show eth0 | grep -oP '(?<=inet\s)\d+(\.\d+){3}')
iptables -t nat -A POSTROUTING -o eth0 -j SNAT --to-source $ETH0_IP
```

### OuterRing

- isc-dhcp-relay

```
# Defaults for isc-dhcp-relay initscript
# sourced by /etc/init.d/isc-dhcp-relay
# installed at /etc/default/isc-dhcp-relay by the maintainer scripts

#
# This is a POSIX shell fragment
#

# What servers should the DHCP relay forward requests to?
SERVERS="192.239.1.202"

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth0 eth1 eth2 eth3"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""
```

- setup.sh

```
echo net.ipv4.ip_forward=1 >/etc/sysctl.conf
sysctl -p

export DEBIAN_FRONTEND=noninteractive
apt update
apt install isc-dhcp-relay netcat -y
cp ~/isc-dhcp-relay /etc/default/isc-dhcp-relay

service isc-dhcp-relay start
service rsyslog start
```

### SixStreet

- isc-dhcp-relay

```
# Defaults for isc-dhcp-relay initscript
# sourced by /etc/init.d/isc-dhcp-relay
# installed at /etc/default/isc-dhcp-relay by the maintainer scripts

#
# This is a POSIX shell fragment
#

# What servers should the DHCP relay forward requests to?
SERVERS="192.239.1.202"

# On what interfaces should the DHCP relay (dhrelay) serve DHCP requests?
INTERFACES="eth0 eth1 eth2 eth3"

# Additional options that are passed to the DHCP relay daemon?
OPTIONS=""
```

- setup.sh

```
echo net.ipv4.ip_forward=1 >/etc/sysctl.conf
sysctl -p

export DEBIAN_FRONTEND=noninteractive
apt update
apt install isc-dhcp-relay netcat -y
cp ~/isc-dhcp-relay /etc/default/isc-dhcp-relay

service isc-dhcp-relay start
service rsyslog start
```

### Fairy

- setup.sh

```
export DEBIAN_FRONTEND=noninteractive
apt update
apt install isc-dhcp-server netcat -y
cp ~/dhcpd.conf /etc/dhcp/dhcpd.conf
cp ~/isc-dhcp-server /etc/default/isc-dhcp-server
echo INTERFACESv4=\"eth0\" >/etc/default/isc-dhcp-server
service rsyslog start

service isc-dhcp-server start
#iptables -A INPUT -p icmp --icmp-type echo-request -j DROP
```

- dhcpd.conf

```
#A9
subnet 192.239.1.128 netmask 255.255.255.192 {
  range 192.239.1.130 192.239.1.189;
  option routers 192.239.1.129;
  option broadcast-address 192.239.1.190;
  option domain-name-servers 192.239.1.203;
  default-lease-time 600;
  max-lease-time 7200;
}

#A5
subnet 192.239.1.0 netmask 255.255.255.128 {
  range 192.239.1.2 192.239.1.126;
  option routers 192.239.1.1;
  option broadcast-address 192.239.1.126;
  option domain-name-servers 192.239.1.203;
  default-lease-time 600;
  max-lease-time 7200;
}

#A3
subnet 192.239.0.0 netmask 255.255.255.0 {
  range 192.239.0.2 192.239.0.253;
  option routers 192.239.0.1;
  option broadcast-address 192.239.0.254;
  option domain-name-servers 192.239.1.203;
  default-lease-time 600;
  max-lease-time 7200;
}

#A6
subnet 192.239.1.200 netmask 255.255.255.248 {}
```

## PENGERJAAN

1. Jalankan 'bash setup.sh' di NewEridu

![Screenshot 2024-12-01 043343](https://github.com/user-attachments/assets/ba70cadf-1a43-4906-b9b8-62e15a3fa993)

2. Lakukan hal yang sama pada DHCP SERVER ( fairy ) dan DHCP RELAY ( OuterRing & SixStreet )

![Screenshot 2024-12-01 054755](https://github.com/user-attachments/assets/6ea8c32b-9dce-44d6-80b4-6b87978a8e83)

![Screenshot 2024-12-01 055530](https://github.com/user-attachments/assets/5c79b969-fa47-404b-b18d-3999bbb63527)

3. Jalankan juga 'service isc-dhcp-relay restart'

![Screenshot 2024-12-01 054800](https://github.com/user-attachments/assets/3ebdd8aa-927e-4e22-bd91-7f2ac000f780)

![Screenshot 2024-12-01 055549](https://github.com/user-attachments/assets/378d2553-2a5a-448e-8ff9-f8246d1e8477)

![Screenshot 2024-12-01 055657](https://github.com/user-attachments/assets/c3feb97c-7630-4bef-abaa-9f304f2336e6)

4. Coba Restart dan matikan node client lalu hidupkan kembali, lihat apakah DHCP berhasil

![image](https://github.com/user-attachments/assets/5bcee64c-26c5-4886-bec5-4a518fa0884a)
