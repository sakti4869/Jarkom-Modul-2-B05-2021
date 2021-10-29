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
 - Langkah 4: Tidak lupa menambahkan:
   ```
   type master;
   file "/etc/bind/kaizoku/frangky.B05.com";
   ```
   pada zone `frangky.B05.com` untuk menandai file dari domain ada pada directory `/etc/bind/kaizoku/frangky.B05.com` seperti pada kotak hijau dibawah:
   ![2021-10-29 (4)](https://user-images.githubusercontent.com/71221969/139355780-ff24c7f5-4562-4d34-8d33-ece4ff108db7.png)
 - Langkah 5: Untuk melakukan pengecekan, perlu dijalankan `ping www.frangky.B05.com` apabila sudah sukses seperti gambar dibawah maka pembuatan domain telah berhasil
   ![2021-10-29 (5)](https://user-images.githubusercontent.com/71221969/139356064-14e90e9d-c4f3-4ef7-8599-39455b149f8f.png)

## Nomor 3
Pada soal nomor 3 dibuat subdomain `super.franky.yyy.com` dengan alias `www.super.franky.yyy.com` yang diatur DNS nya di EniesLobby dan mengarah ke Skypie dengan menambahkan (kotak hijau) pada directory `etc/bind/kaizoku/frangky.B05.com`
![2021-10-29 (10)](https://user-images.githubusercontent.com/71221969/139470390-ce66eb1b-ceb3-4628-8b23-a98aeada394a.png)

## Nomor 4
Pada soal nomor 4 dibuat juga reverse domain untuk domain utama dengan cara menambahkan zone `2.179.192.in-addr.arpa` pada file `/etc/bind/named.conf.local`
![2021-10-29 (12)](https://user-images.githubusercontent.com/71221969/139472726-000102fa-099e-4470-b213-7d1196755bce.png)
Kemudian pada folder `kaizoku` ditambah file `2.179.192.in-addr.arpa` dengan isi sebagai berikut
![2021-10-29 (13)](https://user-images.githubusercontent.com/71221969/139473069-35bedb44-4edd-4410-b193-76134a87f810.png)
Lalu dilakukan pengecekan dengan cara 
![2021-10-29 (14)](https://user-images.githubusercontent.com/71221969/139473326-5a7f5ea3-1127-4431-ad79-58eeaf2ffba7.png)

