<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 6 - Arsitektur web browser dan web server</h1>
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

# <a name="_5x87chy0x0vj"></a>**Web browser**

![](images/tugas6/Aspose.Words.524fd46e-fbdc-4882-b866-3d3385327f99.001.jpeg)

User interfaces

Tampilan dari web browser. Tampilan browser biasanya berisi halaman konten, back button, textfield untuk address bar dan fitur lainnya.

Browser engine

Browser engine bertugas untuk menghubungkan antara user interface dengan browser engine. Ketika menginputkan url di address bar, maka browser engine akan menerima dan meneruskannya ke render engine.

Render engine

Pada Chrome, render engine nya bernama Blink. Blink bertugas menampilkan konten yang diminta. Pertama tama render engine akan mengambil kode html dan mengubahnya menjadi DOM tree. Lalu render engine juga mengambil kode css dan mengubahnya menjadi CSSOM. Render engine juga mendownload asset seperti javascript file dari network layer.

Networking layer

Bertanggung jawab untuk melakukan network call untuk mengambil suatu data

Javascript engine

Pada layer ini, terdapat engine yang berguna untuk mengeksekusi kode javascript yang tersimpan pada DOM atau CSSOM. Contoh javascript engine adalah V8 Javasciprt engine, dimana engine ini digunakan pada browser Chrome.

UI Backend

Bertanggung jawab untuk mengelola tampilan seperti input boxes dan select. Selain itu layer ini juga bertanggung jawab mengelola windows.

Data Storage

Browser memiliki storage yang bisa digunakan untuk menyimpan cookies, cache, dan lain lain.

# <a name="_x6rr40xrw2ou"></a>**Web Server**

![](images/tugas6/Aspose.Words.524fd46e-fbdc-4882-b866-3d3385327f99.002.jpeg)

Web Server

Web server menerima http request dan mengembalikannya dalam bentuk http response. Web server biasanya akan mengembalikan file tertentu atau data dari statik database. Web server yang sering digunakan adalah Apache http server.

Application Server

Ketika web server memerlukan data processing, maka akan mengirimkan servlet request kepada application server. Application server akan melakukan pengolahan data dan memanajemen dengan menggunakan application datastore. Lalu mengembalikannya dalam bentuk servlet response.
