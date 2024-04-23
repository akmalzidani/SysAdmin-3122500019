<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 5.1 - Kirim Pesan Web Mail Server antar Kelompok</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : <br>Kelompok 1</h3>
  <p style="text-align: center;">
    <strong>Mahendra Khibrah Rabbani Sayyid (3122500013)</strong><br>
    <strong>Akmal Zidani Fikri (3122500019)</strong><br>
    <strong>Bagus Bimo Prakoso (3122500028)</strong>
  </p>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
<hr>
<hr>
</div>

## Pastikan tugas 5 (Setup Web Mail Server )sudah dilakukan dan berhasil untuk digunakan.

## Pada praktikum ini memerlukan sedikit penyesuaian dari konfigurasi yang telah dilakukan pada tugas 5 dengan settingan pada Mikrotik Lab Jaringan, karena kita akan mencoba mengirim pesan antar server kelompok.

<hr>
Sambung kabel LAN Mikrotik lalu set NetworkSetting Debian pada Virtual Box

![](images/tugas5.1/image001.png) <br>

Lalu buka winBox dan connect ke IP yang tersedia

![](images/tugas5.1/image002.png) <br>

Pada Debian set Manual IP dan DNS NetworkManager seperti dibawah ini

![](images/tugas5.1/image003.png) <br>

<hr>

## Lalu pastikan settingan beberapa konfigurasi seperti dibawah ini

`sudo nano /etc/bind/named.conf.options`

![](images/tugas5.1/image004.png) <br>
![](images/tugas5.1/image005.png) <br>

Selanjutnya `sudo nano /etc/resolv.conf`

![](images/tugas5.1/image006.png) <br>

Selanjutnya `sudo nano /var/lib/bind/db.kelompok1.local`

![](images/tugas5.1/image007.png) <br>

Selanjutnya `sudo nano /etc/postfix/main.cf`

![](images/tugas5.1/image008.png) <br>

Selanjutnya `sudo nano /etc/roundcube/config.inc.php`

![](images/tugas5.1/image009.png) <br>

Setelah memastikan semua konfig seperti diatas, jangan lupa restart untuk refresh

![](images/tugas5.1/image010.png) <br>

<hr>

## Menambahkan DHCP Server pada WinBox

Buka kembali winBox yang telah connect tadi, lalu buka IP > DHCP Server

![](images/tugas5.1/image011.png) <br>

Setelah itu hapus bridge yang telah ada, jika sudah dihapus klik DHCP Setup

![](images/tugas5.1/image012.png) <br>

Pada DHCP Setup pilih interface bridge1

![](images/tugas5.1/image013.png) <br>
![](images/tugas5.1/image014.png) <br>
![](images/tugas5.1/image015.png) <br>
![](images/tugas5.1/image016.png) <br>

Pada DNS Servers selain DNS kelompok, tambahkan DNS 10.10.10.1

![](images/tugas5.1/image017.png) <br>

Lalu selanjutnya next saja dengan settingan default hingga selesai

<hr>
 
<h2> Mencoba mengirim pesan email ke kelompok lain </h2>

Setelah semua step diatas sudah disetup dan dikonfigurasi ulang, tes dengan login lagi melalui ThunderBird atau RoundCube sama saja.

Yang perlu diperhatikan adalah seharusnya email user sekarang menjadi `@mail.kelompok1.local`, Dimana pada konfigurasi tugas 5 sebelumnya email user adalah `@kelompok1.local`.

Note : mahen@kelompok1.local merupakan kondisi login saat melakukan percobaan kirim email dalam satu server pada tugas 5

Disini saya login menggunakan user akmal/123 pada ThunderBird
Bisa dilihat bahwa akmal@mail.kelompok1.local berhasil mengirimkan beberapa pesan ke user mail.kelompok....local kelompok lain

![](images/tugas5.1/image018.png) <br>

Dan bisa dilihat juga bahwa akmal@mail.kelompok1.local berhasil menerima pesan yang dikirimkan dari kelompok lain.

![](images/tugas5.1/image019.png) <br>

<h1 style='text-align:center;'> -- Percobaan Berhasil -- </h1>
