---
layout: post
title : <div class="bubble-effect blog-title">menambahkan vidio pada HTML</div>
---

penjelasan tentang bagaimana cara menambahkan vidio pada html


![HTML vidio]

---

penjelasan tentang bagaimana cara menambahkan vidio pada html

#### 1. Dasar: Tag <video>s
- Struktur Umum:

html
<video width="640" height="360" controls>
  <source src="video.mp4" type="video/mp4">
  Browser kamu tidak mendukung tag video.
</video>

controls menampilkan tombol Play, Pause, Volume, dan lainnya.

---

#### 2. Atribut Penting pada <video>
- Atribut	Fungsi
controls	Menampilkan kontrol video
autoplay	Memulai video otomatis saat halaman dibuka
loop	Mengulang video setelah selesai
muted	Memulai video dalam keadaan tanpa suara
poster	Menampilkan gambar sebelum video diputar
preload	Bagaimana browser memuat video (auto, metadata, none)
- Contoh lengkap:

html
<video width="640" height="360" controls autoplay loop muted poster="gambar-thumbnail.jpg">
  <source src="film.mp4" type="video/mp4">
</video>

---

#### 3. Menyediakan Beberapa Format Video
Karena tidak semua browser mendukung semua format video, sebaiknya menyediakan alternatif:

html
<video width="640" height="360" controls>
  <source src="video.mp4" type="video/mp4">
  <source src="video.webm" type="video/webm">
  <source src="video.ogv" type="video/ogg">
  Browser kamu tidak mendukung video.
</video>
Format yang sering dipakai:
•	MP4 (video/mp4) — paling umum
•	WebM (video/webm)
•	Ogg (video/ogg)

---

#### 4. Embed Video dari YouTube, Vimeo, dll.
Kalau mau menyisipkan video dari YouTube (atau platform lain), pakai <iframe>:

html
<iframe width="640" height="360" src="https://www.youtube.com/embed/ID_VIDEO" frameborder="0" allowfullscreen></iframe>
- Contoh:
URL video: https://www.youtube.com/watch?v=dQw4w9WgXcQ
Maka link untuk embed:
html
<iframe width="640" height="360" src="https://www.youtube.com/embed/dQw4w9WgXcQ" frameborder="0" allowfullscreen></iframe>
Catatan: Untuk Vimeo, tinggal ganti src dengan link embed dari Vimeo.

---

#### 5. Styling Video (CSS)
Kamu bisa ubah ukuran dan tampilan video dengan CSS:

html
<style>
  video {
    max-width: 100%;
    height: auto;
    border-radius: 10px;
    box-shadow: 0px 4px 8px rgba(0,0,0,0.2);
  }
</style>

<video controls>
  <source src="video.mp4" type="video/mp4">
</video>

---

#### 6. Mengontrol Video dengan JavaScript
Kalau mau, kita bisa kendalikan video pakai tombol custom:

html
<video id="videoKu" width="640" height="360" controls>
  <source src="film.mp4" type="video/mp4">
</video>

<button onclick="playVideo()">Play</button>
<button onclick="pauseVideo()">Pause</button>

<script>
  var video = document.getElementById("videoKu");

  function playVideo() {
    video.play();
  }

  function pauseVideo() {
    video.pause();
  }
</script>


---

#### Ringkasan
-	Gunakan <video> untuk video lokal.
-	Gunakan <iframe> untuk video YouTube/Vimeo.
-	Tambahkan controls, autoplay, loop, dan poster untuk fitur tambahan.
-	Styling video bisa dengan CSS supaya tampil lebih menarik.
-	JavaScript bisa dipakai untuk kontrol interaktif.