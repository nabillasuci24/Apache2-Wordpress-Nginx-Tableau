# Cara Install Apache2-Nginx-dan-Tableau
Membahas dan menjelaskan step by step menginstall apache2, Nginx dan wordpress pada Ubuntu server

#Cara Install Apache2 di Ubuntu Server
## 1. Login User di Ubuntu Server

## 2. Melakukan Update
      sudo apt update

## 3. Install Apache2
      sudo apt install apache2

## 4. Mengecek dan Menampilkan daftar Aplikasi yang Sudah Ter Install
      sudo ufw app list
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/94cdbddd-2046-4a06-97d9-9343d33e85dd)

## 5. Cek Status Layanan Web Server Apache2
      sudo systemctl status apache2
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/2dfbb3b4-79c3-471d-8c70-f60d06a36e9a)

## 6. Periksa IP
      ip a
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/f996583f-8deb-4c6b-9024-953d54180cbd)

## 7. Copy IP Address pada Browser
Jika berhasil, akan ada tampilan seperti di bawah ini.

![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/994973e9-e3b3-402f-a85a-a0d76a737b5c)

## 8. Membuat Website <br>
### 8.1 Membuat Website Melalui Direktori /var/www/html
    cd /var/www/html

### 8.2 Membuat Direktori Baru
    sudo mkdir <nama direktori>
contoh : sudo mkdir nabilla

### 8.3 Mengubah Izin Pada Direktori
    sudo chmod 777 <nama direktori>
contoh : sudo chmod 777 nabilla

### 8.4 Pindah ke Direktori yang telah Dibuat
    cd <nama direktori>
contoh : cd nabilla

### 8.5 Edit Direktori HTML dengan Teks Editor "nano"
    nano index.html
<html>
<head>
  
<title> 'Website Nabilla' </title>
</head>
<h1>
<body> Hallo! Welcome To Website </h1>
<p> Nabilla Suci Febriani
<p> SK3C
<P> 09011182227018
  
</body>
</html>
contoh program :
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/b39f3903-ca63-4a70-ba26-79ccc7e0fe9c)

## 9. Output
Berikut ini adalah tampilan website dari proses yang telah dilakukan sebelumnya.
*192.145.1.85* adalah IP address, */nabilla/* adalah nama direktori yang ,enyimpan isi dari tampilan dibawah ini.
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/d2434900-44af-4b44-b5dd-61ec5a66330f)

## Cara Remote
### 1. CMD
    ssh<nama server>@ip a
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/bda54a44-9d4e-4e36-8926-9cd21c8cb649)

### 2. PuTTY
1. Masukkan alamat ip pada PuTTY <br>
2. Klik open <br>
3. connect once <br>
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/9d65d25d-d102-4475-8f60-c380d39312b7)

## 3. Ubuntu Desktop
1. login ke ubuntu desktop
   ssh<nama server>@ip a
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/a7b80f54-e8e4-4bdc-becf-9a5882ae85f9)

# Cara Install Nginx di Ubuntu Server

## 1. Login ke Ubuntu Server
## 2. Melakukan Update Package
    sudo apt update

## 3. Install Nginx
    sudo apt install nginx
    
## 4. Menampilkan Daftar Aplikasi yang Telah di Install
    sudo ufw app list

## 5. Menampilkan Output yang Akan Menunjukkan Lalu Lintas HTTP yang diperbolehkan
    sudo ufw status
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/5e7f806b-b073-45b6-be41-51049858814c)

## 6. Memeriksa Status Layanan Web Server Nginx
    sudo systeemctl status nginx
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/965dcd4c-d28b-46f2-b161-f4b687586a23)

## 7. Periksa IP Address
    hostname -I

## 8. Output
Masukkan IP Address pada website. Jika berhasil di buka, akan muncul tampilan seperti di bawah ini.
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/06f967f5-fcee-44dc-9c31-d1ecfc2aaa95)

# Cara Install Wordpress di ubuntu server

## 1. Masuk ke Root
    sudo su
    
## 2. Install Apache2
     apt isntall apache2

## 3. Konfirmasi Bahwa Apache Telah Terinstal
    systemctl status apache2
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/69d6fc89-bd73-4410-810d-91dba8a8b7cd)

## 4. Verivikasi dengan Membuka IP Address pada Chrome
    hostname -I
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/7b55b8d3-6838-4a41-86e8-605e865e0feb)

## 5. Install MySql
### 5.1 Install MySql
     apt install mariadb-server mariadb-client
     
### 5.2 Mengamankan Database MariaDB dan Melaranag Login root Jarak Jauh
     mysql_secure_installation

## 6. Install PHP
### 6.1 Install PHP
    apt install php php-mysql

### 6.2 Konfirmasi Bahwa PHP telah di Instal, buat file info.php di '/var/www/html/'
    nano /var/www/html/info.php
Ketikan
```sh
<?php
phpinfo();
?>
```

### 6.3 Buka pada browser "ip/info.php"
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/3e2ed874-8f68-4708-84dd-46c27fa0be3d)

## 7. Membuat Databse Wordpress
### 7.1 Masuk ke Database MatiaDB
    mysql -u root -p
### 7.2 Ketik perintah di bawah ini satu per satu
```sh
CREATE DATABASE wordpress_db;
```
```sh
CREATE USER 'wp_user'@'localhost' IDENTIFIED BY 'password';
```
```sh
GRANT ALL ON wordpress_db.* TO 'wp_user'@'localhost' IDENTIFIED BY 'password';
```
```sh
FLUSH PRIVILEGES;
```
```sh
Exit;
```

## 8. Install Wordpress CMS
### 8.1 Install
```sh
tar -xvf latest.tar.gz
```

### 8.2 Ketikan Perintah di Bawah ini Satu per Satu
```sh
cp -R wordpress /var/www/html/
```
```sh
chown -R www-data:www-data /var/www/html/wordpress/
```
```sh
chmod -R 755 /var/www/html/wordpress/
```
```sh
$ mkdir /var/www/html/wordpress/wp-content/uploads
```
```sh
chown -R www-data:www-data /var/www/html/wordpress/wp-content/uploads/
```

### 8.3 Buka Wordpress <br>
    'ip/wordpress'
Isi formulir seperti saat membuat database WordPress di database MariaDB
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/0293c7a4-fd6d-42fd-b29a-72f4d0f7cd9d)

klik *run the installation* <br>
Kemudian, isi detail tambahan yang diperlukan seperti judul situs, Nama Pengguna, dan 
Kata Sandi lalu klik install wordpress untuk login ke akun wordpress yang sudah 
kita buat

### 8.4 Jika Selesai Maka Akan Muncul Seperti Ini
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/41398dcf-8767-48e6-a852-a0eae40f14e4)

## 9. Edit File Wordpress
Agar wordpress masi bisa dibuka ketika kita menggunakan alamat ip yang berbeda, ubah konfig file wordpress
```sh
cd /var/www/html/wordpress
```
```sh
nano wp-config.php
```
salin teks ini dibawah *db_collate*
```sh
$ip = exec('ip addr show enp0s3 | grep "inet\b" | awk \'{print $2}\' | cut -d/ -f1');
if (!empty($ip)) {
  define('WP_HOME', 'http://' . $ip . '/wordpress');
  define('WP_SITEURL', 'http://' . $ip . '/wordpress');
}
```
lalu ketikan perintah
```sh
php wp-config.php
```


# Cara Instal Tableau untuk Visualisai Data
## 1. Install Tableau
1.	Buka situs web Tabelau, lalu pilih versi tableau publik.
2.	Kemudian pilih platform yang akan digunakan.
3.	Mulai menginstall, aktivasi dan registrasi tableau.
4.	Jika Sudah Selesai Maka Akan Muncul Tampilan Seperti Ini
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/7d53dbb4-3cc0-4828-bd0c-7a843e58882f)

## 2.Membuat Visualisasi data di Tableau
1. Masukkan data. Disni saya mengambil data dari data.jakarta.go.id yang berjudul Data Terpadu kesejahteraan Sosial Provinsi DKI Jakarta Tahun 2022
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/2bd6d933-e1c9-47a9-b7c8-35c268491ce8)
2. Kolom berisikan kota dan baris berisikan jumlah penerima bantuan. Sedangkan arti warna yang paling terang adalah jumlah yang paling tinggi dan warna yang pudar menandakan jumlah yang sedikit. Untuk melihat tingktan jumlahnya, maka masukkan data jumlah ke dalam label.
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/8606161b-6cd7-48ad-9ccf-77c29b57b31a)
3. Hasil dari visualisasi data yang telah di posting di tableau publik.
![image](https://github.com/nabillasuci24/Apache2-Wordpress-Nginx-Tableau/assets/150004555/703cfeb2-9e0e-4238-aa69-55f108d4b4ea)
