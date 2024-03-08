<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 3</h1>
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

## 1. Mencoba Install Package Eksternal - GDebi - DPKG

Intstall gdebi menggunakan apt
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.001.png)
<br>

Pilih package .deb lalu pilih untuk install melalui gdebi
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.002.png)
<br>

Pada tampilan gdebi klik untuk install package
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.003.png)
<br>

Sebelum install, kita akan dimintai untuk memasukkan password user
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.004.png)
<br>

Berikut adalah proses instalasi dari .deb file
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.005.png)
<br>

Kita bisa menghapus package dengan menekan menu dari remove package
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.006.png)
<br>

**DPKG**
<br>

Install deb file menggunakan dpkg di cli
<br>

![](images/tugas3/Aspose.Words.3d8914c0-3b43-4fc2-85cb-8c852fe7c974.007.png)
<br>

Jika terdapat error maka install satu per satu dependency yang diperlukan menggunakan apt
<br>

Untuk menghapus package deb bisa menggunakan command
`dpkg –purge nama_package`
<br>

<br>

## 2. Setting Mikrotik Lab Jaringan PENS

### Topologi

![](images/tugas3/0.png)

Buka WinBox dan pastikan terhubung dengan LAN Mikrotik.
Menghubungkan MAC Address Mikrotik dengan mode Legacy.
<br>

![](images/tugas3/1.png)

<br>
Set IP Address baru untuk ethernet 1 dengan masuk ke menu IP Address.
<br>

![](images/tugas3/2.png)
![](images/tugas3/3.png)

IP Baru berhasil ditambahkan
<br>

![](images/tugas3/4.png)

Set Bridge
<br>

![](images/tugas3/5.png)

Buat bridge baru
<br>

![](images/tugas3/6.png)

Bridge berhasil ditambahkan.
<br>

![](images/tugas3/7.png)
<br>
Pindah ke tab submnu ports untuk menambahkan port secara manual,
untuk port ether2,3,4,5 agar menjadi satu switch bridge.
<br>

![](images/tugas3/8.png)
<br>

![](images/tugas3/9.png)
<br>

![](images/tugas3/10.png)
<br>

![](images/tugas3/11.png)
<br>

![](images/tugas3/12.png)
<br>

![](images/tugas3/13.png)
<br>

![](images/tugas3/14.png)
<br>

![](images/tugas3/15.png)
<br>

Setelah set bridge dan menyatukan port ether2,3,4,5 menjadi satu switch,
selanjutnya tambahkan ip address untuk port yang jadi satu tadi.
<br>

![](images/tugas3/16.png)
<br>

![](images/tugas3/17.png)
<br>

![](images/tugas3/18.png)
<br>

Setelah itu set route, agar bisa tersambung ke gateway
<br>

![](images/tugas3/19.png)

<br>
Ini default setelah set IP pada step sebelumnya
<br>

![](images/tugas3/20.png)
<br>

![](images/tugas3/21.png)

Route ke gateway berhasil ditambahkan
<br>

![](images/tugas3/22.png)
<br>

Selanjutnya set DHCP, agar setiap device yang connect mendapatkan IP secara otomatis atau dinamis.
<br>

![](images/tugas3/23.png)
<br>

![](images/tugas3/24.png)
<br>

Masuk DHCP Setup, lalu pilih interface Bridge1 yaitu bridge yang sudah kita setup pada step sebelumnya.
<br>

![](images/tugas3/25.png)
<br>

![](images/tugas3/26.png)
<br>

![](images/tugas3/27.png)
<br>

![](images/tugas3/28.png)
<br>

![](images/tugas3/29.png)
<br>

Disini kami coba set IP yang akan diberikan mulai dari .200 - .254
<br>

![](images/tugas3/30.png)
<br>

![](images/tugas3/31.png)
<br>

![](images/tugas3/32.png)
<br>

Setup DHCP berhasil ditambahkan
<br>

![](images/tugas3/33.png)
<br>

![](images/tugas3/34.png)
<br>

Koneksi sudah tersambung, tetapi belum bisa mengakses internet
<br>

![](images/tugas3/35.png)
<br>

![](images/tugas3/36.png)
<br>

![](images/tugas3/37.png)
<br>

Step terakhir agar bisa tersambung ke akses internet yaitu dengan set Firewall
<br>

![](images/tugas3/38.png)
<br>

Masuk ke tab submenu NAT
<br>

![](images/tugas3/39.png)
<br>

Tambahkan rule NAT baru untuk Network bridge kita ke semua destination network
<br>

![](images/tugas3/40.png)
<br>

Lalu masuk ke tab submenu Action dan ubah action menjadi masquerade.
<br>

![](images/tugas3/41.png)
<br>

Berhasil ditambahkan rule NAT.
<br>

![](images/tugas3/42.png)
<br>

Kita coba kembali tes apakah sudah terkoneksi ke akses internet
<br>

![](images/tugas3/43.png)
<br>

Berhasil terkoneksi
<br>

![](images/tugas3/44.png)
<br>

![](images/tugas3/45.png)
<br>

SELESAI

```

```
