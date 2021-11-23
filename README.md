# Jarkom-Modul-4-A12-2021
Jarkom_Modul4_Lapres_A12

**Praktikum Modul 4 - Jaringan Komputer 2021**
**A12**
-   Fiqey Indriati Eka Sari (05111940000015)
-   Dyah Putri Nariswari (05111940000047)
-   Muhammad Farrel Abhinaya (05111940000173)
---
# VLSM
Server DORIKI dan FUKUROU tidak perlu dimasukkan dalam subnet pembagian IP karena mendapat IP DMZ

![unnamed](https://user-images.githubusercontent.com/57583780/142830307-4739f053-3695-48de-acdc-097842af9fba.png)

## VLSM (Variable Length Subnet Masking) 

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
![Topology VLSM drawio](https://user-images.githubusercontent.com/57583780/142831308-75cfd242-95fe-4c28-8515-8744837eb8ad.png)


Pembagian NID
![Screenshot from 2021-11-23 14-17-24](https://user-images.githubusercontent.com/57583780/142984610-9b009dca-ec0b-4248-a2b1-278213e4a4a7.png)

Routing
![Screenshot from 2021-11-23 14-18-01](https://user-images.githubusercontent.com/57583780/142984640-99465671-63b7-43d1-8372-1b67b5344cba.png)
