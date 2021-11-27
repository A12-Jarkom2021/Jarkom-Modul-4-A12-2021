# Jarkom-Modul-4-A12-2021
Jarkom_Modul4_Lapres_A12

**Praktikum Modul 4 - Jaringan Komputer 2021**
**A12**
-   Fiqey Indriati Eka Sari (05111940000015)
-   Dyah Putri Nariswari (05111940000047)
-   Muhammad Farrel Abhinaya (05111940000173)
---
## VLSM
Server DORIKI dan FUKUROU dimasukkan dalam subnet pembagian IP 

![unnamed](https://user-images.githubusercontent.com/57583780/142830307-4739f053-3695-48de-acdc-097842af9fba.png)

## VLSM (Variable Length Subnet Masking) 
![VLSM](https://user-images.githubusercontent.com/57583780/143045213-c8e3af26-a27b-4fee-a3f4-956da60e8491.png)

| Subnet | Jumlah IP | Netmask |
|--------|-----------|---------|
| A1     | 1001      | /22     |
| A2     | 13        | /28     |
| A3     | 502       | /23     |
| A4     | 2         | /30     |
| A5     | 2         | /30     |
| A6     | 2         | /30     |
| A7     | 101       | /25     |
| A8     | 701       | /22     |
| A9     | 2021      | /21     |
| A10    | 521       | /22     |
| A11    | 2         | /30     |
| A12    | 721       | /22     |
| A13    | 252       | /24     |
| **Total**  | **5841**      | **/19**     |

Subnet besar yang dibentuk memiliki NID **10.5.0.0** dengan netmask **/19**. Pembagian IP berdasarkan NID dan netmask dihitung menggunakan pohon pada gambar di bawah:

![VLSM-a12 drawio](https://user-images.githubusercontent.com/57583780/143043750-d4803ea1-926b-4d42-b3a0-8ee9a8e27ad5.png)


### Pembagian NID

![Screenshot from 2021-11-23 21-34-02](https://user-images.githubusercontent.com/57583780/143043687-3005a224-b794-4876-a1c1-68b1e07625fd.png)

### Routing

![VLSM-Routing](https://user-images.githubusercontent.com/57583780/143043986-1dacdc8e-f478-42cf-b25c-5ee6e533a956.png)

## CIDR - GNS3

### Pembagian Subnet

***Langkah 1***

![messageImage_1637677225023](https://user-images.githubusercontent.com/81466736/143678146-b6fc2c35-9d4c-48c8-9ecb-4781b9f46023.jpg)

***Langkah 2***

![messageImage_1637677238324](https://user-images.githubusercontent.com/81466736/143678169-84beb43f-ba71-4dd0-8c49-22397eb649e6.jpg)

***Langkah 3***

![messageImage_1637677324391](https://user-images.githubusercontent.com/81466736/143678192-59385b85-a6af-4546-9664-098dac6a4a23.jpg)

***Langkah 4***

![messageImage_1637677333386](https://user-images.githubusercontent.com/81466736/143678211-30e3fe51-99c3-4800-b693-af41342e23a1.jpg)

***Langkah 5***

![messageImage_1637677407920](https://user-images.githubusercontent.com/81466736/143678229-3245805e-8513-4ab4-8e28-d7646f5b6ee0.jpg)

***Langkah 6***

![messageImage_1637677417865](https://user-images.githubusercontent.com/81466736/143678246-f0fbdca8-b50b-4577-ba5b-879bee93b1dd.jpg)

### Pohon Pembagian

![image](https://user-images.githubusercontent.com/81466736/143678275-629d96dd-4e5d-4f65-be2a-294e6c2dbba6.png)

### Subnetting

![Screenshot from 2021-11-27 20-14-36](https://user-images.githubusercontent.com/57583780/143682956-b3730d57-c229-4546-9f5d-e50d0c98702e.png)

### Setting pada GNS3
Setting file untuk router dan client

**FOOSHA (Router)**
```
auto lo
iface lo inet loopback

#CLOUD
auto eth0
iface eth0 inet dhcp

#BLUENO
auto eth1
iface eth1 inet static
address 10.5.64.1
netmask 255.255.252.0

#WATER7
auto eth2
iface eth2 inet static
address 10.5.192.1
netmask 255.255.255.252

#GUANHAO
auto eth3
iface eth3 inet static
address 10.5.32.1
netmask 255.255.255.252

#DORIKI
auto eth4
iface eth4 inet static
address 10.5.19.1
netmask 255.255.255.252

```

**WATER7 (Router)**
```
auto lo
iface lo inet loopback

#FOOSHA
auto eth0
iface eth0 inet static
address 10.5.192.2
netmask 255.255.255.252
gateway 10.5.192.1

#PUCCI
auto eth1
iface eth1 inet static
address 10.5.144.1
netmask 255.255.255.252

#CIPHER
auto eth2
iface eth2 inet static
address 10.5.160.1
netmask 255.255.255.0

```

**GUANHOU (Router)**
```
auto lo
iface lo inet loopback

#FOOSHA
auto eth0
iface eth0 inet static
address 10.5.32.2
netmask 255.255.255.252
gateway 10.5.32.1

#OIMO
auto eth1
iface eth1 inet static
address 10.5.8.1
netmask 255.255.255.252

#JABRA
auto eth2
iface eth2 inet static
address 10.5.20.1
netmask 255.255.255.0

#ALABASTA
auto eth3
iface eth3 inet static
address 10.5.16.1
netmask 255.255.254.0
```

**ALABASTA (Router)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.16.2
netmask 255.255.254.0
gateway 10.5.16.1

#JORGE
auto eth1
iface eth1 inet static
address 10.5.18.1
netmask 255.255.255.240
```

**OIMO (Router)**
```
auto lo
iface lo inet loopback

#GUANHAO
auto eth0
iface eth0 inet static
address 10.5.8.2
netmask 255.255.255.252
gateway 10.5.8.1

#ENIESLOBBY
auto eth1
iface eth1 inet static
address 10.5.4.1
netmask 255.255.255.0

#FUKUROU
auto eth2
iface eth2 inet static
address 10.5.19.5
netmask 255.255.255.252
```

**SEASTONE (Router)**
```
auto lo
iface lo inet loopback

#ENIESLOBBY
auto eth0
iface eth0 inet static
address 10.5.4.2
netmask 255.255.255.0
gateway 10.5.4.1

#ELENA
auto eth1
iface eth1 inet static
address 10.5.0.1
netmask 255.255.252.0
```

**BLUENO (Client)**
```
auto lo
iface lo inet loopback

#FOOSHA
auto eth0
iface eth0 inet static
address 10.5.64.2
netmask 255.255.252.0
gateway 10.5.64.1
```

**CIPHER (Client)**
```
auto lo
iface lo inet loopback

#WATER7
auto eth0
iface eth0 inet static
address 10.5.160.2
netmask 255.255.252.0
gateway 10.5.160.1
```

**CALMBELT (Client)**
```
auto lo
iface lo inet loopback

#PUCCI
auto eth0
iface eth0 inet static
address 10.5.128.3
netmask 255.255.248.0
gateway 10.5.128.1
```

**COURTYARD (Client)**
```
auto lo
iface lo inet loopback

#PUCCI
auto eth0
iface eth0 inet static
address 10.5.128.2
netmask 255.255.248.0
gateway 10.5.128.1

```

**JIPANGU (Client)**
```
auto lo
iface lo inet loopback

#PUCCI
auto eth0
iface eth0 inet static
address 10.5.136.2
netmask 255.255.255.128
gateway 10.5.136.1

```

**JABRA (Client)**
```
auto lo
iface lo inet loopback

#GUANHAO
auto eth0
iface eth0 inet static
address 10.5.20.2
netmask 255.255.252.0
gateway 10.5.20.1

```

**MAINGATE (Client)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.16.3
netmask 255.255.254.0
gateway 10.5.16.1

```

**JORGE (Client)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.18.2
netmask 255.255.255.240
gateway 10.5.18.1

```

**ENIESLOBBY (Client)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.4.3
netmask 255.255.255.0
gateway 10.5.4.1

```

**ELENA (Client)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.0.2
netmask 255.255.252.0
gateway 10.5.0.1

```

**DORIKI (Server)**
```
auto lo
iface lo inet loopback

#FOOSHA
auto eth0
iface eth0 inet static
address 10.5.19.2
netmask 255.255.255.252
gateway 10.5.19.1

```

**FUKUROU (Server)**
```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet static
address 10.5.19.6
netmask 255.255.255.252
gateway 10.5.19.5

```

Lakukan routing pada Foosha, Water7, Guanhou, dan Oimo
**FOOSHA**
```
route add -net 10.5.128.0 netmask 255.255.128.0 gw 10.5.192.2
route add -net 10.5.0.0 netmask 255.255.192.0 gw 10.5.32.2
route add -net 10.5.64.0 netmask 255.255.252.0 gw 10.5.64.2

route add -net 10.5.19.0 netmask 255.255.255.252 gw 10.5.19.2
route add -net 10.5.19.4 netmask 255.255.255.252 gw 10.5.32.2
route add -net 10.5.4.0 netmask 255.255.255.0 gw 10.5.32.2

```

**WATER7**
```
route add -net 10.5.128.0 netmask 255.255.224.0 gw 10.5.144.2
route add -net 10.5.160.0 netmask 255.255.252.0 gw 10.5.160.2
```

**GUANHOU**
```
route add -net 10.5.16.0 netmask 255.255.254.0 gw 10.5.16.3
route add -net 10.5.16.0 netmask 255.255.254.0 gw 10.5.16.2
route add -net 10.5.20.0 netmask 255.255.252.0 gw 10.5.20.2
route add -net 10.5.0.0 netmask 255.255.252.0 gw 10.5.8.2
route add -net 10.5.19.4 netmask 255.255.255.252 gw 10.5.8.2
route add -net 10.5.4.0 netmask 255.255.255.0 gw 10.5.8.2
```

*OIMO*
```
route add -net 10.5.19.4 netmask 255.255.255.252 gw 10.5.19.6
route add -net 10.5.0.0 netmask 255.255.252.0 gw 10.5.4.3
route add -net 10.5.0.0 netmask 255.255.252.0 gw 10.5.4.2

```

Setelah itu, jalankan command ``` iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.5.0.0/16 ``` pada Foosha.
Kemudian jangan lupa setiap router/pc di echo namserver dari Foosha dengan `echo nameserver 192.168.122.1 > /etc/resolv.conf`

# Kendala

# Pembagian Tugas

-   Fiqey Indriati Eka Sari (05111940000015) : VLSM
-   Dyah Putri Nariswari (05111940000047) : Routing dan Configure CIDR
-   Muhammad Farrel Abhinaya (05111940000173) : Perhitungan CIDR
