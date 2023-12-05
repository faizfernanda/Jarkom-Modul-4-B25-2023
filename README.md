# Jarkom-Modul-4-B25-2023

## Nama Anggota :
| No | Nama| NRP|
| ------- | ------- | ------- |
| 1 | Muhamad Faiz Fernanda | 5025211186|
| 2| Tigo S Yoga | 5025211125 |


Disini kami menggunakan perhitungan subnetting dengan cara ```CIDR```  pada ```GNS3``` sedangkan untuk ```VLSM``` kami lakukan pada ```GNS3```

## Topologi GNS CIDR 
![Topologi gns](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/438c03da-9bd2-483d-b773-fe6d90df959f)

## Topologi PKT VLSM


## CIDR 

**CIDR (Classless Inter-Domain Routing)** merupakan metode pengelolaan dan routing jaringan yang mengubah cara kita melakukan subnetting dan mengatasi sistem pengalamatan berbasis kelas secara tradisional. CIDR memungkinkan alokasi blok alamat IP yang lebih fleksibel dengan menggunakan notasi seperti 192.168.1.0/24. Ini memungkinkan penggunaan alamat IP yang efisien dengan mengelola subnet yang lebih kecil dan memfasilitasi penggabungan alamat IP untuk mengurangi jumlah entri dalam tabel routing.

Secara sederhana, **CIDR** memberikan administrator kemampuan untuk menggabungkan beberapa subnet ke dalam satu entri routing yang lebih umum, menyederhanakan manajemen alamat IP, dan meningkatkan efisiensi dalam proses routing. Bayangkan alamat IP seperti nomor rumah, dan CIDR memungkinkan kita untuk membaginya dengan cara yang lebih fleksibel. Sebagai contoh, alamat IP seperti 192.168.1.0/24 menunjukkan keberadaan sekitar 256 nomor rumah di dalamnya.

**CIDR** mempermudah pengelolaan alamat ini dengan mengizinkan pengelompokan beberapa "rumah" ke dalam entitas yang lebih besar. Hal ini tidak hanya menyederhanakan administrasi alamat, tetapi juga berkontribusi pada kinerja internet yang lebih cepat dan lebih efisien. Secara keseluruhan, CIDR membantu mengorganisir dan meningkatkan efisiensi internet dengan cara yang efektif mengelola dan mengoptimalkan alokasi alamat IP.

## Penggabungan Beberapa node 
- Untuk kondisi awal Node
  ![Screenshot 2023-12-02 113303](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/744e503a-bf8e-4f95-a838-64efe47a7c54)
- Dan Untuk rute nya
  ![rute](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/a911b527-27eb-4bc2-a6e7-b20ff68127f7)

- Setelah di lakukan penggabungan melalui beberapa tahap maka gambar nya jadi sebagai berikut :
  ![gab2](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/192ad368-b10e-45e0-b482-623525ade474)
- Sedangkan Untuk tabel penggabungan **CIDR** nya sebagai berikut :
   - I

     ![1](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/0b90f73d-620e-462e-a479-88199a20f216)
   - II

     ![2](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/4910f65f-da60-4c8f-99c2-acf0d4d311e7)
   - III

     ![3](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/792039b7-4d37-499e-a5d9-bc3cc3eb3b2d)
   - IV

     ![4](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/62dfcf70-8a8b-4b2f-b70b-352e9a6129ca)
   - V

     ![5](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/ea94af72-6097-47b4-9546-47a5a33a6d98)
   - VI

     ![6](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/c0a2063f-49ae-4275-83e4-002c9fb792ed)
   - VII

     ![7](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/4b411efe-883d-4157-b77a-daa2a982a1e2)
   - VIII

     ![8](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/73e6ff2f-6143-4755-85b7-9431e4086bc3)
   - IX

     ![9](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/81153471-1db6-4862-b854-a52a1e2d3165)
   - X

     ![10](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/b411d253-7923-4c65-a779-ef023d627b67)

## TREE 
![Screenshot 2023-12-02 120421](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/fa120417-c80d-4970-8bfd-1d0c715c71b9)

## Pembagian IP akhir 
![Pembagian ip](https://github.com/faizfernanda/Jarkom-Modul-4-B25-2023/assets/101172294/62725523-682a-4c92-9f86-5d0021fc8322)

## Berikut ini cara melakukan routing pada gns
- Pertama melakukan configurasi pada setiap node dengan ip yang kita hasilkan pada tabel di atas,
  seperti di bawah ini pada node **Aura**
  ```
    auto eth0
    iface eth0 inet dhcp
    
    auto eth1
    iface eth1 inet static
    	address 10.18.0.1
    	netmask 255.255.255.252
    
    auto eth2
    iface eth2 inet static
    	address 10.19.0.1
    	netmask 255.255.255.252
    
    auto eth3
    iface eth3 inet static
    	address 10.20.0.1
    	netmask 255.255.255.252
  ```
- Selanjut nya melakukan perintah ```route add -net <NID subnet> netmask <netmask> gw <IP gateway>``` sesuai dengan yang ada di modul 4
  berikut ini untuk masing masing node
  - ### Aura
    ```
    A19
    route add -net 10.22.0.0 netmask 255.255.255.252 gw 10.20.0.2
    A10 
    route add -net 10.23.192.0 netmask 255.255.255.248 gw 10.20.0.2
    A18
    route add -net 10.23.4.0 netmask 255.255.252.0 gw 10.20.0.2
    A17
    route add -net 10.23.0.0  netmask 255.255.255.0 gw 10.20.0.2
    A15
    route add -net 10.23.240.0 netmask 255.255.254.0 gw 10.20.0.2
    A 12
    route add -net 10.23.254.0 netmask 255.255.255.252 gw 10.20.0.2
    A13
    route add -net 10.23.252.0 netmask 255.255.255.192 gw 10.20.0.2
    A14
    route add -net 10.23.248.0 netmask 255.255.252.0 gw 10.20.0.2
    A21
    route add -net 10.16.0.0 netmask 255.255.255.0 gw 10.18.0.2 
    A7
    route add -net 10.19.128.0 netmask 255.255.255.224 gw 10.19.0.2
    A3
    route add -net 10.19.248.0 netmask 255.255.252.0 gw 10.19.0.2
    A1
    route add -net 10.19.252.0 netmask 255.255.255.248 gw 10.19.0.2
    A5
    route add -net 10.19.224.0 netmask 255.255.248.0 gw 10.19.0.2
    A2
    route add -net 10.19.254.0 netmask 255.255.255.252 gw 10.19.0.2
    A4
    route add -net 10.19.240.0 netmask 255.255.255.252 gw 10.19.0.2
    A6
    route add -net 10.19.192.0 netmask 255.255.255.252 gw 10.19.0.2
    ```
  - ### Frieren
    ```
    Aura (A8)
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.19.0.1
    A1
    route add -net 10.19.252.0 netmask 255.255.255.248 gw 10.19.192.2
    A3
    route add -net 10.19.248.0 netmask 255.255.252.0 gw 10.19.192.2
    A5
    route add -net 10.19.224.0 netmask 255.255.248.0 gw 10.19.192.2
    A2
    route add -net 10.19.254.0 netmask 255.255.255.252 gw 10.19.192.2
    A4
    route add -net 10.19.240.0 netmask 255.255.255.252 gw 10.19.192.2
    A6
    route add -net 10.19.192.0 netmask 255.255.255.252 gw 10.19.192.2
    ```
  - ### Fern
    ```
    Menerima
    Flamme (A4)
    Mengirim
     
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw  10.19.240.1
    ```
  - ### Flamme
    ```
    Menerima
    Frieren (A6)
    Mengirim
    A1
    A5
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.19.192.1
    route add -net 10.19.252.0 netmask 255.255.255.248 gw 10.19.254.2      (A2)
    route add -net 10.19.224.0 netmask 255.255.255.252 gw 10.19.240.2       (A4)
    ```
  - ### Himmel
    ```
    Menerima
    Flamme (A2)
    Mengirim
     
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.19.254.1
    ```
  - ### Eisen
  - ```
    Menerima
    Aura (A9)
    Mengirim
    A15
    A13
    A14
    A18
    A17
    A12
    
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.20.0.1
    A15
    route add -net 10.23.240.0 netmask 255.255.254.0 gw 10.23.224.2
    A13
    route add -net 10.23.252.0 netmask 255.255.255.224 gw 10.23.224.2
    A14
    route add -net 10.23.248.0 netmask 255.255.252.0 gw 10.23.224.2
    A 12
    route add -net 10.23.254.0 netmask 255.255.255.252 gw 10.23.224.2
    A18
    route add -net 10.23.4.0 netmask 255.255.252.0 gw 10.23.128.2
    A17
    route add -net 10.23.0.0  netmask 255.255.255.0 gw 10.23.128.2

    ```
  - ### Linie
    ```
    Menerima
    Eisen (A11)
    Mengirim
    A13
    A14
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.23.224.1
    A13
    route add -net 10.23.252.0 netmask 255.255.255.192 gw 10.23.254.2
    A14
    route add -net 10.23.248.0 netmask 255.255.252.0 gw 10.23.254.2
    ```
  - ### Heiter
    ```
    Menerima
    Lawine (A13)
    Mengirim
     
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.23.252.1

    ```
  - ### Lugner
    ```
    Menerima
    Eisen (A16)
    Mengirim
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.23.128.1
    ```
  - ### Denken
    ```
    Menerima
    Aura (A20)
    Mengirim
    Code
    route add -net 0.0.0.0 netmask 0.0.0.0 gw 10.18.0.1

    ```
## Vidio Tutorial
[![Video](https://img.youtube.com/vi/zlpIDt5hTIg/maxresdefault.jpg)](https://youtu.be/zlpIDt5hTIg)

