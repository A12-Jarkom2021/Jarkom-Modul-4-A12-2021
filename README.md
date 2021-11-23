# Jarkom-Modul-4-A12-2021
Jarkom_Modul4_Lapres_A12

**Praktikum Modul 4 - Jaringan Komputer 2021**
**A12**
-   Fiqey Indriati Eka Sari (05111940000015)
-   Dyah Putri Nariswari (05111940000047)
-   Muhammad Farrel Abhinaya (05111940000173)
---
# VLSM
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


Pembagian NID
![Screenshot from 2021-11-23 21-34-02](https://user-images.githubusercontent.com/57583780/143043687-3005a224-b794-4876-a1c1-68b1e07625fd.png)

Routing!
![VLSM-Routing](https://user-images.githubusercontent.com/57583780/143043986-1dacdc8e-f478-42cf-b25c-5ee6e533a956.png)


