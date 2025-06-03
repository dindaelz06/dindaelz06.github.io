---
layout: post
title : <div class="bubble-effect blog-title">menambahkan audio pada HTML</div>
---

penjelasan tentang bagaimana cara menambahkan audio pada html


![HTML audio]

---

penjelasan tentang bagaimana cara menambahkan audio pada html

#### 1. Dasar: Tag <audio>
Struktur Umum:

html
<audio controls>
  <source src="audio.mp3" type="audio/mpeg">
  <source src="audio.ogg" type="audio/ogg">
  Your browser does not support the audio element.
</audio>
controls akan menampilkan tombol Play, Pause, Volume.


---

#### 2. Atribut Penting pada <audio>
Atribut	Fungsi
controls	Menampilkan kontrol audio standar (play, pause, volume)
autoplay	Audio otomatis diputar saat halaman dibuka
loop	Mengulang audio terus-menerus setelah selesai
muted	Audio dimulai dalam keadaan mute
preload	Mengatur kapan audio dimuat (auto, metadata, none)
- Contoh lengkap:

html
<audio controls autoplay loop muted preload="auto">
  <source src="lagu.mp3" type="audio/mpeg">
</audio>


---

#### 3. Preload pada <audio>
preload mengontrol kapan browser harus mulai mengunduh audio:
•	auto : Browser memutuskan sendiri.
•	metadata : Hanya meta informasi (seperti durasi).
•	none : Tidak memuat audio sebelum user menekan play.
- Contoh:

html
<audio controls preload="metadata">
  <source src="musik.mp3" type="audio/mpeg">
</audio>


---

#### 4. Event (JavaScript) untuk <audio>
Dengan JavaScript, kita bisa mengendalikan audio:
- Contoh sederhana:

html
CopyEdit
<audio id="audioKu" src="lagu.mp3"></audio>

<button onclick="playAudio()">Play</button>
<button onclick="pauseAudio()">Pause</button>

<script>
  var audio = document.getElementById("audioKu");
  
  function playAudio() {
    audio.play();
  }

  function pauseAudio() {
    audio.pause();
  }
</script>
Event yang tersedia:
•	play
•	pause
•	ended
•	volumechange
•	timeupdate
•	loadeddata



---

#### 5. Styling <audio> (CSS)
Tag <audio> biasanya punya tampilan standar. Tapi bisa dikombinasikan dengan CSS untuk custom player:

html
<style>
  audio {
    width: 300px;
    background-color: #f0f0f0;
    border-radius: 10px;
    padding: 5px;
  }
</style>

<audio controls>
  <source src="musik.mp3" type="audio/mpeg">
</audio>
Kalau mau full custom player (dengan tombol sendiri), lebih banyak pakai JavaScript + CSS.

---

#### 6. Format Audio yang Didukung Browser
Format	Tipe MIME	Browser
MP3	audio/mpeg	Semua browser modern
OGG	audio/ogg	Chrome, Firefox, Opera
WAV	audio/wav	Semua browser modern
⚡ Saran: Utamakan MP3 karena paling kompatibel!

---

#### 7. Embed dari Layanan Streaming
Kalau mau embed dari Spotify atau SoundCloud, biasanya pakai iframe:
- Contoh Spotify:

html
<iframe style="border-radius:12px" src="https://open.spotify.com/embed/track/TRACK_ID" width="300" height="80" frameBorder="0" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>


---

#### Ringkasan
- Pakai <audio> untuk file lokal.
-	Gunakan controls untuk tombol play, pause, volume.
-	Kombinasikan dengan CSS/JavaScript untuk kontrol lebih lanjut.
-	Format MP3 paling umum dan didukung semua browser.
-	Bisa embed audio dari layanan lain pakai iframe.