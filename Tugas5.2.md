<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 5.2 - Analisis MIME, POP3, dan SMTP</h1>
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

# <a name="_heading=h.7yog8cndlxwc"></a>**ESMTP**

![](images/tugas5.2/Aspose.Words.25120c2a-01a3-4693-87b5-1a85255b62b9.001.png)

mencoba untuk terhubung ke alamat IP 192.168.1.10 melalui protokol Telnet pada port 25. Port 25 adalah port default yang digunakan untuk layanan SMTP (Simple Mail Transfer Protocol), yang digunakan untuk mengirim email. Jadi, perintah tersebut mencoba untuk terhubung ke server email yang mungkin berjalan di alamat IP tersebut.

"EHLO kelompok1.local ESMTP" adalah bagian dari protokol SMTP (Simple Mail Transfer Protocol) yang digunakan saat koneksi ke server email dibuat.

Perintah "MAIL FROM": Perintah ini digunakan oleh pengirim email (klien) untuk menentukan alamat email pengirim. Contoh penggunaannya adalah "MAIL FROM: mahen@kelompok1.local". Artinya, email akan dikirim dari alamat "mahen@kelompok1.local".

Perintah "RCPT TO": Perintah ini digunakan oleh pengirim email (klien) untuk menentukan alamat email penerima. Contoh penggunaannya adalah "RCPT TO: syahrul@kelompok4.local". Artinya, email akan dikirim ke alamat "syahrul@kelompok4.local".

# <a name="_heading=h.rou08oqd6mzj"></a>**POP3**

![](images/tugas5.2/Aspose.Words.25120c2a-01a3-4693-87b5-1a85255b62b9.002.png)

![](images/tugas5.2/Aspose.Words.25120c2a-01a3-4693-87b5-1a85255b62b9.003.png)

Port 110 adalah port default yang digunakan untuk layanan POP3 (Post Office Protocol version 3). POP3 adalah protokol yang digunakan untuk mengambil email dari server email ke komputer klien.

user akmal artinya login sebagai <akml@kelompok1.local>, dan pass 123 artinya memasukkan passwordnya.

perintah RETR 17 digunakan untuk membaca pesan 17.

Setelah selesai membaca pesan, pastikan untuk menutup koneksi Telnet. Ini biasanya dilakukan dengan mengetikkan perintah "QUIT" untuk mengakhiri sesi dengan server.

# <a name="_heading=h.nplcrteme9kt"></a>**MIME**

**Content-Type**

Jenis konten pesan. Dalam gambar, jenis konten adalah type/subtype. Jenis konten dapat berupa teks, gambar, audio,video, atau jenis data lainnya. Subtipe menentukan format data yang lebih spesifik. Misalnya, jenis konten image/jpeg menunjukkan bahwa pesan tersebut berisi gambar JPEG.

**Content-Transfer-Encoding**

Metode yang digunakan untuk mengkodekan pesan. Dalam gambar, kode transfer konten adalah encoding type. Kode transfer konten digunakan untuk memastikan bahwa pesan dapat ditransmisikan dengan benar melalui jaringan. Misalnya,kode transfer konten base64 digunakan untuk mengkodekan pesan biner menjadi karakter ASCII.
