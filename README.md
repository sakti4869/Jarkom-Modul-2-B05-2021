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
![2021-10-29 (12)](https://user-images.githubusercontent.com/71221969/139472726-000102fa-099e-4470-b213-7d1196755bce.png)<br>
Kemudian pada folder `kaizoku` ditambah file `2.179.192.in-addr.arpa` dengan isi sebagai berikut
![2021-10-29 (13)](https://user-images.githubusercontent.com/71221969/139473069-35bedb44-4edd-4410-b193-76134a87f810.png)<br>
Lalu dilakukan pengecekan dengan cara 
![2021-10-29 (14)](https://user-images.githubusercontent.com/71221969/139473326-5a7f5ea3-1127-4431-ad79-58eeaf2ffba7.png)

## Nomor 5
membuat Water7 sebagai DNS Slave untuk domain utama untuk memback up DNS master jika DNS master mati dengan cara menambahkan zone `frangky.B05.com` dengan tipe slave pada `Water7`
![2021-10-30 (1)](https://user-images.githubusercontent.com/71221969/139519380-4bc7adb0-cc00-4c47-a31e-7b6a3bd9467b.png)<br>
Lalu tidak lupa memberi tahu `EniesLobby` jika dia memiliki slave yaitu `Water7` dengan menambahkan:
![2021-10-30](https://user-images.githubusercontent.com/71221969/139519894-318c097a-1bc1-4abc-bfb3-cf2c8258dad8.png)

## Nomor 6
membuat subdomain `mecha.frangky.B05.com` dengan alias `www.mecha.frangky.B05.com` yang didelegasikan dari EniesLobby ke Water7 dengan IP menuju ke Skypie dalam folder sunnygo

 - Langkah 1: Tambahkan code seperti pada kotak kuning pada `EniesLobby` pada file `frangky.B05.com`
![2021-10-30 (4)](https://user-images.githubusercontent.com/71221969/139529227-afbdd785-4e8b-49ff-a7cf-94f58a3ace70.png)
 - Langkah 2: Tambahkan code seperti pada gambar pada `Sunnygo`:
![2021-10-30 (6)](https://user-images.githubusercontent.com/71221969/139529386-925dcdcb-b2c2-4f11-91cd-b31ebd5e0ee7.png)

## Nomor 7
Menambahkan code seperti pada kotak hijau untuk membuat subdomain `general` kemudian diarahkan ke IP `Skypie`
![2021-10-30 (6)](https://user-images.githubusercontent.com/71221969/139529460-2917008f-502f-45b4-89c0-4b763973181c.png)

## Nomor 8
Menambahkan file `frangky.B05.com.conf` dengan isi:
```
ServerAdmin webmaster@localhost
DocumentRoot /var/www/frangky.B05.com
ServerName frangky.B05.com
ServerAlias www.frangky.B05.com
```
pada directory `/etc/apache2/sites-available`
![2021-10-30 (7)](https://user-images.githubusercontent.com/71221969/139529787-08ea7b0c-d305-403e-8534-37c4556f8733.png)

Kemudian menambahkan directory `frangky.B05.com` dengan isi file yang telah didownload dari github `https://github.com/FeinardSlim/Praktikum-Modul-2-Jarkom`bagian `franky`:
![2021-10-30 (8)](https://user-images.githubusercontent.com/71221969/139530358-38e1fe50-6bc0-44ac-b5e7-361bef7d5ce5.png)

Sehingga ketika dijalankan dengan `lynx frangky.B05.com`:
![2021-10-30 (9)](https://user-images.githubusercontent.com/71221969/139530410-cf945dff-8fb8-4d8c-b3e0-fd8a15b9c235.png)

## Nomor 9
Melakukan rewrite sehingga `www.franky.yyy.com/index.php/home` dapat menjadi menjadi `www.franky.yyy.com/home`<br>

pada file `frangky.B05.com.conf` ditambah dengan 
```
<Directory /var/www/frangky.B05.com>
        Options +FollowSymLinks -Multiviews
        AllowOverride All
</Directory>
```
Kemudian menambahkan file `.htaccess` dengan isi:
```
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^([^\.]+)$ $1.html [NC,L]
```
sehingga kita bisa access dengan `lynx www.franky.B05.com/home` lalu keluar halaman:
![2021-10-30 (9)](https://user-images.githubusercontent.com/71221969/139530726-ab9d14df-f991-4182-8856-7b94aa929344.png)

## Nomor 10
Membuat subdomain `www.super.frangky.B05.com` yang memiliki DocumentRoot pada `/var/www/super.franky.B05.com`<br>

 - Langkah 1:
Menambahkan directory `super.frangky.B05.com` yang digunakan untuk menyimpan file yang telah di download dari `https://github.com/FeinardSlim/Praktikum-Modul-2-Jarkom` bagian `super.franky`:<br>
 - Langkah 2: 
Menambahkan file `super.frangky.B05.com.conf` dengan isi:
```
ServerAdmin webmaster@localhost
DocumentRoot /var/www/super.frangky.B05.com
ServerName super.frangky.B05.com
ServerAlias www.super.frangky.B05.com
```
 - Langkah 3: 
Dilakukan pengecekan menggunakan `lynx super.frangky.B05.com`:
![2021-10-30 (10)](https://user-images.githubusercontent.com/71221969/139531089-f68bf51a-6704-4773-8742-144017493440.png)

## Nomor 11
hanya dapat melakukan directory listing saja pada folder `public` pada `/var/www/super.frangky.B05.com`<br>
Dapat dilakukan dengan cara menambahkan code:
```
<Directory /var/www/super.frangky.B05.com/public/js>
        Options -Indexes
</Directory>

<Directory /var/www/super.frangky.B05.com/public/images>
        Options -Indexes
</Directory>

<Directory /var/www/super.frangky.B05.com/public/css>
        Options -Indexes
</Directory>
```
pada file `super.frangky.B05.com.conf`. Sehingga ketika folder dalam `public` dibuka akan menampilkan:
![2021-10-30 (11)](https://user-images.githubusercontent.com/71221969/139531272-106e2748-0bc8-475f-9d97-98ad00cafed8.png)

## Nomor 12
Pada file `super.frangky.B05.com.conf` ditambahkan `ErrorDocument 404 /error/404.html` untuk melemparkan jika dns tidak sesuai akan dilempar ke file `404.html` pada directory `/var/www/super.frangky.B05.com/error`<br>
Ketika mengakses dengan `lynx super.frangky.B05.com/hsahs` akan menampilkan:
![2021-10-30 (12)](https://user-images.githubusercontent.com/71221969/139531488-31d0f380-bee2-40d4-aebf-e11d7e20c00a.png)

## Nomor 13
dapat mengakses file asset `www.super.frangky.B05.com/public/js` menjadi `www.super.frangky.B05.com/js` dapat dilakukan dengan directory alias yaitu menambahkan 
```
Alias "/js" "/var/www/super.frangky.B05.com/public/js"
```
pada file `super.frangky.B05.com.conf`<br>
Ketika dilakukan pengecekan `lynx super.frangky.B05.com/js` akan menampilkan folder js dalam public yang mana sebelumnya telah di forbiden:
![2021-10-30 (11)](https://user-images.githubusercontent.com/71221969/139531272-106e2748-0bc8-475f-9d97-98ad00cafed8.png)

## Nomor 14
web `www.general.mecha.franky.B05.com` hanya bisa diakses dengan port 15000 dan port 15500<br>

Langkah 1:
Pada file `ports.conf` tambahkan Listen menjadi:
```
Listen 15000
Listen 15500
```
supaya dapat menerima request dari port 15000 dan 15500<br>

Langkah 2:
Ubah virtual host pada file `general.mecha.frangky.B05.com.conf` menjadi:
```
VirtualHost *:15000 *:15500
```
dengan demikian file dapat diakses melalui port :15000 dan :15500 
![2021-10-30 (15)](https://user-images.githubusercontent.com/71221969/139532245-3f863d18-ad7f-48a8-adb6-4a02dcd09895.png)

## Nomor 15 
- Langkah 1: Membuat sebuah autentikasi username dan password pada server menggunakan :
```
htpasswd -c /etc/apache2/.htpasswd luffy 
```
- Langkah 2: Edit file `.htaccess` pada directory `general.mecha.franky.B07` dengan menambahkan:
```
AuthType Basic
AuthName "Restricted Content"
AuthUserFile /etc/apache2/.htpasswd
Require valid-user
```
- Langkah 3: tambahkan code
```
<Directory /var/www/general.mecha.franky.e07.com>
        AuthType Basic
        AuthName "Restricted Content"
        AuthUserFile /etc/apache2/.htpasswd
        Require valid-user
</Directory>
```
dalam file `general.mecha.frangky.B05.com.conf`
- Langkah 4: Kemudian cek menggunakan `lynx frangky.B05.com:15000` maka akan me redirect menuju `frangky.B05.com`
![2021-10-30 (13)](https://user-images.githubusercontent.com/71221969/139533794-87f1ac3e-3f42-4573-adfa-652cddc50bd7.png)
![2021-10-30 (14)](https://user-images.githubusercontent.com/71221969/139533828-2e6e38b4-4899-4dab-a549-a25bc347f2cc.png)

## Nomor 16
Setiap kali mengakses IP Skypie akan dialihkan secara otomatis ke `www.franky.B05.com` maka tinggal tambahkan code
```
ServerAdmin webmaster@localhost
DocumentRoot /var/www/frangky.B05.com
```
pada `000-default.conf` Sehingga ketika dibuka dengan `lynx 192.179.2.4` akan menampilkan:
![2021-10-30 (9)](https://user-images.githubusercontent.com/71221969/139530726-ab9d14df-f991-4182-8856-7b94aa929344.png)
