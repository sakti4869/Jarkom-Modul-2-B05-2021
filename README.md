# Jarkom-Modul-2-B05-2021

## Nomor 1
Pada soal nomor 1 diminta untuk membuat Topologi yang nantinya EniesLobby akan dijadikan sebagai DNS Master, Water7 akan dijadikan DNS Slave, dan Skypie akan digunakan sebagai Web Server. Terdapat 2 Client yaitu Loguetown, dan Alabasta. Semua node terhubung pada router Foosha, sehingga dapat mengakses internet:
![2021-10-29](https://user-images.githubusercontent.com/71221969/139354127-69f0f318-e934-4337-8240-a2521002b7f9.png)

## Nomor 2
Pada soal nomor 2 diminta untuk membuat website utama dengan mengakses frangky.B05.com dengan alias www.frangky.yyy.com pada folder kaizoku:
 - Langkah 1: Dibuat folder kaizoku dimana isinya adalah file `frangky.B05.com`
   ![2021-10-29 (1)](https://user-images.githubusercontent.com/71221969/139354593-79d7c23b-e23b-4fe0-beff-22d8bf759dd2.png)
 - Langkah 2: dalam file `frangky.B05.com` ditambahkan domain `frangky.B05.com`(kotak merah) dan alias `www.frangky.B05.com`(kotak hijau)
   ![2021-10-29 (2)](https://user-images.githubusercontent.com/71221969/139354859-de08b1a1-e829-4141-b1c7-bd27f39cb8e5.png)
 - Langkah 3: tambahkan nameserver pada `Loguetown` dan `Alabasta` menjadi IP dari `EniesLobby`(kotak hijau) yaitu `192.179.2.2` supaya kita bisa mengakses DNS server `EniesLobby` melalui `Loguetown` atau `Alabasta`
   ![2021-10-29 (3)](https://user-images.githubusercontent.com/71221969/139355259-18d5ecd6-4b58-4f12-8c02-86c451d4f6c8.png)
