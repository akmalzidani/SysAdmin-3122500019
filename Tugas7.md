<div align="center">
  <h1 style="text-align: center;font-weight: bold">LAPORAN WORKSHOP ADMINISTRASI JARINGAN<br>Tugas 6 : Docker 101 Tutorial - Play Labs</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <p style="text-align: center;">
    <strong>Akmal Zidani Fikri (3122500019)</strong><br>
  </p>

<h3 style="text-align: center;line-height: 1.5">Politeknik Elektronika Negeri Surabaya<br>Departemen Teknik Informatika Dan Komputer<br>Program Studi Teknik Informatika<br>2023/2024</h3>
<hr>
<hr>
</div>

# Getting Started

Buka `https://labs.play-with-docker.com/`

Pastikan sudah sign up atau log in terlebih dahulu

![](images/tugas7/image1.png)

Klik start lalu akan diarahkan di page ini

![](images/tugas7/image2.png)

Lalu klik add New Instance, untuk mulai menjalankan terminal

![](images/tugas7/image3.png)

Lalu masukkan `docker run -dp 80:80 docker/getting-started:pwd` untuk
mencoba run

![](images/tugas7/image4.png)

Lalu masukkan `docker ps -a` untuk mengecek apakah sudah ada

![](images/tugas7/image5.png)

Coba klik 80, lalu akan diarahkan ke hasil container yang telah dirun
sebelumnya

![](images/tugas7/image6.png)

![](images/tugas7/image7.png)

<hr>

# Our Application

## Getting our App into PWD

Setelah itu coba pergi ke Our Application

![](images/tugas7/image8.png)

Scroll ke bawah, download zip nya untuk contoh project app nya
![](images/tugas7/image9.png)

Download lalu jika sudah, drag and drop ke instance Terminal tadi, lalu
cek apakah sudah berhasil diupload apa belum dengan ls

![](images/tugas7/image10.png)

Jika sudah ada maka lanjutkan sesuai step by stepnya

![](images/tugas7/image11.png)

1.  `unzip app.zip`

![](images/tugas7/image10.png)

2.  Mengecek apakah file sudah terunzip

![](images/tugas7/image12.png)

## Building the App\'s Container Image##

![](images/tugas7/image13.png)

Buat Dockerfile lalu isi dengan content seperti diatas

FROM node:10-alpine

WORKDIR /app

COPY . .

RUN yarn install \--production

CMD \[\"node\", \"/app/src/index.js\"

\]

![](images/tugas7/image14.png)

![](images/tugas7/image15.png)

Lalu build container image `docker build -t docker-101 .`

![](images/tugas7/image16.png)

## Starting an App Container

![](images/tugas7/image17.png)

Coba menjalankan container image yang sudah kita build tadi

`docker run -dp 3000:3000 docker-101`

![](images/tugas7/image18.png)

Lalu klik port 3000 dan akan diarahkan ke container image yang telah di
run

![](images/tugas7/image20.png)

Bisa dilihat bahwa Todo App sudah bisa dibuka, mari kita coba

Berhasil Add

![](images/tugas7/image21.png)

Berhasil hapus

![](images/tugas7/image22.png)

<hr>

# Updating our App

## Updating our Source Code

![](images/tugas7/image23.png)

Klik editor pada instance

![](images/tugas7/image24.png)

Sesuai dengan arahan dockerLabs pergi ke `app/src/static/js/app.js`

![](images/tugas7/image25.png)

Lalu update line 56

![](images/tugas7/image26.png)

Dan jangan lupa save

![](images/tugas7/image25.png)

Update dengan build kembali `docker build -t docker-101 .`

![](images/tugas7/image27.png)

Start container baru dengan kode yang sudah diupdate

`docker run -dp 3000:3000 docker-101`

![](images/tugas7/image28.png)

Ternyata muncul error sesuai dengan arahan dockerLabs

## Replacing our Old Container

![](images/tugas7/image29.png)

Jalankan `docker ps` untuk melihat container lama yang akan diganti

![](images/tugas7/image30.png)

Stop container lama `docker stop \<container-tujuan\>`, disini nama
dari port 3000 adalah wonderful_haibt

![](images/tugas7/image31.png)

Hapus container yang sudah diberhentikan

`docker rm \<container-tujuan\>`

![](images/tugas7/image32.png)

Run app yang sudah diupdate

![](images/tugas7/image33.png)

Coba refresh page port 3000 tadi

![](images/tugas7/image34.png)

Sudah berhasil terupdate

<hr>

# Sharing Our App

## Create a Repo

![](images/tugas7/image35.png)

Pergi ke Docker Hub dan login

![](images/tugas7/image36.png)

Lalu Create Repository

![](images/tugas7/image37.png)

Isi nama repository dan visibility public

![](images/tugas7/image38.png)

Lalu klik Create button

![](images/tugas7/image39.png)

## Pushing our Image

![](images/tugas7/image40.png)

Mencoba push

`docker push dockersamples/101-todo-app`

![](images/tugas7/image41.png)

Terdapat error, coba login terlebih dahulu melalui command

![](images/tugas7/image42.png)

Jalankan docker tag

![](images/tugas7/image43.png)

Lalu coba push lagi

![](images/tugas7/image44.png)

## Running our Image on a New Instance

![](images/tugas7/image45.png)

Add new instance pada PWD

![](images/tugas7/image46.png)

Start pada new instance

![](images/tugas7/image47.png)

Coba jalankan port 3000, jika tidak ada link langsung maka klik OPEN
PORT lalu isi 3000

![](images/tugas7/image48.png)

![](images/tugas7/image49.png)

Berhasil di buka, Hooray!

![](images/tugas7/image50.png)

<hr>

## Persisting our DB

![](images/tugas7/image51.png)

Kembali ke node 1 192.168.0.18

Run docker run -d ubuntu

`docker run -d ubuntu bash -c \"shuf -i 1-10000 -n 1 -o /data.txt && tail -f /dev/null\"`

![](images/tugas7/image52.png)

Run docker exec

![](images/tugas7/image53.png)

![](images/tugas7/image54.png)

Run container ubuntu lain

`docker run -it ubuntu ls /`

![](images/tugas7/image55.png)

Hapus container bash ubuntu

![](images/tugas7/image56.png)

![](images/tugas7/image57.png)

## Persisting our Todo Data

![](images/tugas7/image58.png)

Buat volume

![](images/tugas7/image59.png)

Run todo container, dan stop container 3000 yang masih nyala.

![](images/tugas7/image60.png)

![](images/tugas7/image61.png)

Open container

![](images/tugas7/image62.png)

Remove Container

![](images/tugas7/image63.png)

![](images/tugas7/image65.png)

Start lagi seperti step sebelumnya

![](images/tugas7/image66.png)

Bisa dilihat, list tadi masih ada Hooray!

![](images/tugas7/image67.png)

## Diving into our Volume

![](images/tugas7/image68.png)

<hr>

# Using Bind Mounts

## Starting a Dev-Mode Container

Stop dulu port 3000 yang masih berjalan

![](images/tugas7/image69.png)

![](images/tugas7/image70.png)

Run command ini

![](images/tugas7/image71.png)

Melihat logs

![](images/tugas7/image72.png)

![](images/tugas7/image73.png)

Buka editor PWD

Update line 109

![](images/tugas7/image74.png)

![](images/tugas7/image75.png)

Jangan lupa save

![](images/tugas7/image76.png)

Tanpa build dan run seperti step sebelumnya, hanya dengan refresh
langsung bisa dilihat updatenya

![](images/tugas7/image77.png)

<hr>

# Multi-Container Apps

## Starting MySQL

Sebelumnya ctrl+c untuk menghentikan node js

![](images/tugas7/image78.png)

Start MySql

![](images/tugas7/image79.png)

Run exec

![](images/tugas7/image80.png)

Masukan password sesuai setup sebelumnya yaitu secret

![](images/tugas7/image81.png)

![](images/tugas7/image82.png)

## Connect to MySQL

Dari step sebelumnya exit terlebih dahulu dari mysql

![](images/tugas7/image83.png)

![](images/tugas7/image84.png)

![](images/tugas7/image85.png)

## Running our App with MySQL

Karena pada saat step ini saya mengalami error no disk space, maka saya
membuat session baru dan mengulangi dari awal dan mendapatkan ip root
192.168.0.28

![](images/tugas7/image86.png)

![](images/tugas7/image87.png)

![](images/tugas7/image88.png)

![](images/tugas7/image89.png)

![](images/tugas7/image90.png)

![](images/tugas7/image91.png)

![](images/tugas7/image92.png)

Execute melalui container sql

![](images/tugas7/image93.png)

![](images/tugas7/image94.png)

<hr>

# Using Docker Compose

## Defining the App Service

Stop container port 3000 yang masih berjalan

![](images/tugas7/image95.png)

![](images/tugas7/image96.png)

![](images/tugas7/image97.png)

![](images/tugas7/image98.png)

![](images/tugas7/image99.png)

## Defining the MySQL Service

![](images/tugas7/image100.png)

![](images/tugas7/image98.png)

![](images/tugas7/image101.png)

## Running our Application Stack

Stop port 3000 yang masih berjalan

![](images/tugas7/image102.png)

![](images/tugas7/image103.png)

![](images/tugas7/image104.png)

<hr>

# Image Building Best Practices

## Image Layering

Karena tadi docker-101 saya hapus maka saya build lagi dan run lagi, dan
jangan lupa stop yang masih jalan :3000

![](images/tugas7/image105.png)

![](images/tugas7/image106.png)

![](images/tugas7/image107.png)

![](images/tugas7/image108.png)

![](images/tugas7/image109.png)

![](images/tugas7/image110.png)

## Layer Caching

![](images/tugas7/image111.png)

![](images/tugas7/image112.png)

Update menjadi seperti ini

![](images/tugas7/image113.png)

![](images/tugas7/image114.png)

Sekarang ubah src/static/index.html title pada line 11, jangan lupa save

![](images/tugas7/image115.png)

Build lagi setelah update

![](images/tugas7/image116.png)
