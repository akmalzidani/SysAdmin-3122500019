<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 5</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Kelompok 1</h3>
  <p style="text-align: center;">
    <strong>Akmal Zidani Fikri (3122500019)</strong><br>
  </p>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
<hr>
<hr>
</div>

Note : Hasil screenshot step by step mungkin ada beberapa yang kurang
sesuai dengan instalasi yang fresh pertama kali dikarenakan proses
screenshot baru saja saya lakukan setelah saya memastikan berhasil semua
step hingga tujuan akhir yaitu web mail + roundcube berhasil dibuat dan
digunakan. Sehingga banyak step by step seperti instalasi package dan
aktivasi config berisi already enable atau already installed

Pastikan BIND9 pada praktikum sebelumnya sudah terinstall dan
terkonfigurasi sesuai dengan custom domain kelompok.

Kembalikan virtualBox dalam keadaan Network NAT dan IP DNS Automatic
agar terkoneksi dengan internet.

![](images/tugas5/image001.png) <br>

<hr>

## Konfigurasi NTP Client

Jika sudah terkoneksi dengan internet, lakukan instalasi package

`sudo apt install systemd-timesyncd`

![](images/tugas5/image002.png) <br>

Konfigurasi timezone ke Asia/Jakarta, RTC ke UTC, aktivasi NTP Client,
dan edit conf

![](images/tugas5/image003.png) <br>

![](images/tugas5/image004.png) <br>

Conf diset agar NTP server mendapatkan waktu delay terpendek, Write Out
lalu exit.

Restart timesyncd dan cek status

![](images/tugas5/image005.png) <br>

<hr>

## Instalasi dan Konfigurasi Apache 2

Instal package Apache 2

`sudo apt -y install apache2`

![](images/tugas5/image006.png) <br>

Konfigurasi apache2

![](images/tugas5/image007.png) <br>

![](images/tugas5/image008.png) <br>

![](images/tugas5/image009.png) <br>

![](images/tugas5/image010.png) <br>

![](images/tugas5/image011.png) <br>

Pergi ke line 70

![](images/tugas5/image012.png) <br>

![](images/tugas5/image013.png) <br>

![](images/tugas5/image014.png) <br>

Restart apache2

![](images/tugas5/image015.png) <br>

Lalu tes ke domain yang sudah diset sebelumnya di kelompok1.local

Tapi sebelumnya ubah dulu IP dan DNS sesuai dengan yang sudah diset
sebelumnya

![](images/tugas5/image016.png) <br>

Jangan lupa setelah mengubah IP dan DNS untuk refresh dengan cara on/off
switch Internet

![](images/tugas5/image017.png) <br>

Apache berhasil diakses

![](images/tugas5/image018.png) <br>

<hr>

## Instalasi PHP 8.2

Karena instalasi package maka kembalikan lagi IP dan DNS menjadi
automatic agar tersambung koneksi internet

`sudo apt -y install php8.2 php8.2-mbstring php-pear`

![](images/tugas5/image019.png) <br>

Cek apakah sudah terinstal atau belum dengan cek version php

![](images/tugas5/image020.png) <br>

![](images/tugas5/image021.png) <br>

<hr>

## Instalasi dan Konfigurasi PHP-FM

`sudo apt -y install php-fpm`

![](images/tugas5/image022.png) <br>

Konfigurasi PHP-FM pada file config Apache

![](images/tugas5/image023.png) <br>

![](images/tugas5/image024.png) <br>

Aktivasi modul dan konfig

![](images/tugas5/image025.png) <br>

Test validasi PHP-FM

Masuk ke root superuser lalu lakukan seperti dibawah ini

`echo '\<?php phpinfo(); ?\>' \> /var/www/html/info.php`

![](images/tugas5/image026.png) <br>

Test di browser

Jangan lupa kembalikan ke IP dan DNS manual dan refresh dengan on/off
switch internet

![](images/tugas5/image027.png) <br>

![](images/tugas5/image028.png) <br>

Berhasill…

<hr>

## Instalasi dan Konfigurasi Database System : MariaDB

Set IP dan DNS auto kembali untuk melakukan instalasi MariaDB.

`sudo apt -y install mariadb-server`

![](images/tugas5/image029.png) <br>

Pastikan charset default seperti dibawah ini

![](images/tugas5/image030.png) <br>

![](images/tugas5/image031.png) <br>

Lalu restart mariadb

![](images/tugas5/image032.png) <br>

Konfigurasi mariadb

![](images/tugas5/image033.png) <br>

![](images/tugas5/image034.png) <br>

Test konek ke mariadb

![](images/tugas5/image035.png) <br>

![](images/tugas5/image036.png) <br>

![](images/tugas5/image037.png) <br>

![](images/tugas5/image038.png) <br>

Berhasil…

<hr>

## Instalasi dan Konfigurasi Email System POSTFIX : SMTP Server

`sudo apt -y install postfix sasl2-bin`

![](images/tugas5/image040.png) <br>

Pilih No Configuration tekan enter

![](images/tugas5/image041.png) <br>

Konfigurasi POSTFIX

![](images/tugas5/image042.png) <br>

Pergi ke line 82

![](images/tugas5/image043.png) <br>

Pergi ke line 98

![](images/tugas5/image044.png) <br>

Pergi ke Line 106

![](images/tugas5/image045.png) <br>

Pergi ke line 127

![](images/tugas5/image046.png) <br>

Pergi ke line 141

![](images/tugas5/image047.png) <br>

Pergi ke line 189

![](images/tugas5/image048.png) <br>

Pergi ke line 232

![](images/tugas5/image049.png) <br>

Pergi ke line 277

![](images/tugas5/image050.png) <br>

Pergi ke line 294

![](images/tugas5/image051.png) <br>

Pergi ke line 416

![](images/tugas5/image052.png) <br>

Pergi ke line 427

![](images/tugas5/image053.png) <br>

Pergi ke line 449

![](images/tugas5/image054.png) <br>

Pergi ke line 585

![](images/tugas5/image055.png) <br>

Pergi ke line 659, 664, 669, 675

![](images/tugas5/image056.png) <br>

Pergi ke line 679, 683, 688, 692 dan Comment

![](images/tugas5/image057.png) <br>

Pada line terakhir tambahkan command dibawah ini

\# disable SMTP VRFY command  
disable_vrfy_command = yes

\# require HELO command to sender hosts  
smtpd_helo_required = yes

\# limit an email size  
\# example below means 10M bytes limit  
message_size_limit = 10240000

\# SMTP-Auth settings  
smtpd_sasl_type = dovecot  
smtpd_sasl_path = private/auth  
smtpd_sasl_auth_enable = yes  
smtpd_sasl_security_options = noanonymous  
smtpd_sasl_local_domain = $myhostname  
smtpd_recipient_restrictions = permit_mynetworks,
permit_auth_destination, permit_sasl_authenticated, reject

![](images/tugas5/image058.png) <br>

WriteOut dan Exit

![](images/tugas5/image059.png) <br>

Menambahkan konfigurasi anti spam

Pada line terakhir tambahkan command dibawah ini

\# reject unknown clients that forward lookup and reverse lookup of
their hostnames on DNS do not match

smtpd_client_restrictions = permit_mynetworks,
reject_unknown_client_hostname, permit

\# rejects senders that domain name set in FROM are not registered in
DNS or

\# not registered with FQDN

smtpd_sender_restrictions = permit_mynetworks,
reject_unknown_sender_domain, reject_non_fqdn_sender

\# reject hosts that domain name set in FROM are not registered in DNS
or

\# not registered with FQDN when your SMTP server receives HELO command

smtpd_helo_restrictions = permit_mynetworks, reject_unknown_hostname,
reject_non_fqdn_hostname, reject_invalid_hostname, permit

![](images/tugas5/image060.png) <br>

![](images/tugas5/image061.png) <br>

WriteOut dan exit

Lalu restart postfix

![](images/tugas5/image062.png) <br>

<hr>

## Instalasi dan Konfigurasi Dovecot Server

`sudo apt -y install dovecot-core dovecot-pop3d dovecot-imapd`

![](images/tugas5/image063.png) <br>

Konfigurasi Dovecot

![](images/tugas5/image064.png) <br>

Pergi ke line 30

![](images/tugas5/image065.png) <br>

![](images/tugas5/image066.png) <br>

Pergi ke line 10

![](images/tugas5/image067.png) <br>

Pergi ke line 100

![](images/tugas5/image068.png) <br>

![](images/tugas5/image069.png) <br>

Pergi ke line 30

![](images/tugas5/image070.png) <br>

![](images/tugas5/image071.png) <br>

Pergi ke line 107

![](images/tugas5/image072.png) <br>

Lalu Restart dovecot

![](images/tugas5/image073.png) <br>

Check Services

![](images/tugas5/image074.png) <br>

Cek layanan Postfix

Dibawah 220 …. Ketikkan `ehlo mail kelompok1.local`

![](images/tugas5/image075.png) <br>

<hr>

## Instalasi PHP MyAdmin

`sudo apt install phpMyAdmin`

![](images/tugas5/image076.png) <br>

Pilih Apache2

![](images/tugas5/image077.png) <br>

Pilih yes

![](images/tugas5/image078.png) <br>

Kosongi password langsung OK

![](images/tugas5/image079.png) <br>

Konfigurasi PHP MyAdmin pada Apache2

![](images/tugas5/image080.png) <br>

![](images/tugas5/image081.png) <br>

Lalu coba create user dan password (123)

![](images/tugas5/image082.png) <br>

Restart MariaDB dan PHP

![](images/tugas5/image083.png) <br>

Lalu test ke browser

Jangan lupa ubah IP dan DNS manual sesuai dengan yang diset sebelumnya

BERHASIL..

![](images/tugas5/image084.png) <br>

Coba login dengan user yang telah dibuat tadi user/123

![](images/tugas5/image085.png) <br>

<hr>

## Instalasi Thunderbird

Set IP dan DNS menjadi Auto untuk instalasi package

`sudo apt-get install thunderbird`

![](images/tugas5/image086.png) <br>

Mencoba membuat 2 user bernama akmal dan mahen  
disini password saya set 123 semua agar mudah diingat

![](images/tugas5/image087.png) <br>

Mencoba login menggunakan user yang telah dibuat

Set IP dan DNS menjadi manual

![](images/tugas5/image088.png) <br>

![](images/tugas5/image089.png) <br>

![](images/tugas5/image090.png) <br>

![](images/tugas5/image091.png) <br>

![](images/tugas5/image092.png) <br>

![](images/tugas5/image093.png) <br>

![](images/tugas5/image094.png) <br>

Berhasil ….

<hr>

## Instalasi dan konfigurasi Roundcube

Set IP dan DNS ke Automatic untuk instalasi package yang membutuhkan
koneksi internet

`sudo apt install roundcube roundcube-mysql`

![](images/tugas5/image095.png) <br>

Konfigurasi roundcube

disini saya set password 123

![](images/tugas5/image096.png) <br>

Sesuaikan password pada file konfig DB roundcube

![](images/tugas5/image097.png) <br>

![](images/tugas5/image098.png) <br>

Sesuaikan dengan IP yang kita set sebelumnya

![](images/tugas5/image099.png) <br>

![](images/tugas5/image100.png) <br>

Konfigurasi roundcube pada Apache

![](images/tugas5/image101.png) <br>

Coba Roundcube

Set IP dan DNS manual kembali agar terkonek dengan server yang kita buat

![](images/tugas5/image102.png) <br>

Yeay sudah berhasil

![](images/tugas5/image103.png) <br>

![](images/tugas5/image104.png) <br>

<hr>

## Simulasi mengirim pesan melalui email

Disini saya login menggunakan user akmal/123 pada RoundCube
![](images/tugas5/image104.png) <br>

dan user mahen/123 pada ThunderBird
![](images/tugas5/image105.png) <br>
![](images/tugas5/image106.png) <br>
![](images/tugas5/image107.png) <br>
![](images/tugas5/image108.png) <br>

Berhasil login mahen@kelompok1.local pada ThunderBird
![](images/tugas5/image109.png) <br>

Sekarang pada RoundCube user akmal@kelompok1.local mencoba kirim pesan ke mahen@kelompok1.local

Klik Compose
![](images/tugas5/image110.png) <br>

Masukkan pesan dan email tujuan, jika sudah klik Send
![](images/tugas5/image111.png) <br>

Muncul Notifikasi Message sent successfully dan muncul notifikasi ThunderBird
![](images/tugas5/image112.png) <br>

Cek pada ThunderBird user mahen dan pesan dari user akmal sudah masuk
![](images/tugas5/image113.png) <br>

Sekarang pada ThunderBird user mahen mencoba membalas pesan akmal, klik Reply to Sender Only
![](images/tugas5/image114.png) <br>

Lalu klik send
![](images/tugas5/image115.png) <br>

Cek RoundCube, jika belum masuk klik refresh pada browser
![](images/tugas5/image116.png) <br>
![](images/tugas5/image117.png) <br>
Pesan berhasil masuk!
