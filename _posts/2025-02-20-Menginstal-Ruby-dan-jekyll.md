---
layout: post
title : <div class="bubble-effect blog-title"> Menginstall Ruby dan Jekyll</div>
---
Penjelasan tentang instalasi Ruby dan Jekyll

---

# 1. *Instalasi Ruby*

*Ruby* adalah bahasa pemrograman yang dinamis dan berorientasi objek. Untuk mengembangkan situs dengan *Jekyll*, Anda memerlukan Ruby sebagai bagian dari persyaratan instalasi.

## 1.1. *Langkah-langkah Instalasi Ruby*

### *A. Cek apakah Ruby sudah terinstal*
Sebelum melakukan instalasi, pastikan Ruby belum terinstal pada sistem Anda. Anda dapat memeriksa dengan perintah berikut di terminal:

bash
ruby -v


Jika Ruby sudah terinstal, Anda akan melihat versi Ruby yang terpasang. Jika tidak, Anda akan melihat pesan kesalahan.

### *B. Instalasi Ruby di macOS*

Di macOS, Ruby sudah terinstal secara default, tetapi mungkin perlu diperbarui ke versi terbaru. Berikut adalah cara memperbarui Ruby atau menginstalnya jika belum ada:

1. *Menggunakan Homebrew (Manajer Paket untuk macOS)*

   Jika Anda belum memiliki *Homebrew*, Anda dapat menginstalnya dengan menjalankan perintah berikut di terminal:

   bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   

   Setelah Homebrew terinstal, Anda dapat menginstal Ruby dengan menjalankan perintah:

   bash
   brew install ruby
   

2. *Menambahkan Ruby ke PATH*
   
   Setelah instalasi selesai, Anda perlu menambahkan Ruby ke PATH agar sistem mengenali perintah Ruby. Tambahkan baris berikut ke file ~/.zshrc atau ~/.bash_profile (tergantung pada shell yang Anda gunakan):

   bash
   export PATH="/usr/local/opt/ruby/bin:$PATH"
   

   Setelah itu, jalankan perintah berikut untuk memuat ulang konfigurasi shell:

   bash
   source ~/.zshrc   # Untuk pengguna zsh
   # atau
   source ~/.bash_profile  # Untuk pengguna bash
   

3. *Verifikasi Instalasi Ruby*
   
   Cek versi Ruby setelah menginstalnya dengan menjalankan:

   bash
   ruby -v
   

### *C. Instalasi Ruby di Windows*

Untuk Windows, Anda dapat menginstal Ruby menggunakan *RubyInstaller*:

1. Kunjungi [halaman unduhan RubyInstaller](https://rubyinstaller.org/downloads/).
2. Pilih versi Ruby yang sesuai dengan sistem operasi Anda (misalnya, versi 64-bit).
3. Unduh dan jalankan penginstal.
4. Selama proses instalasi, pastikan untuk mencentang opsi "Add Ruby executables to your PATH".
5. Setelah instalasi selesai, buka *Command Prompt* dan verifikasi instalasi Ruby dengan perintah:

   bash
   ruby -v
   

### *D. Instalasi Ruby di Linux (Ubuntu/Debian)*

Di sistem berbasis Debian/Ubuntu, Anda bisa menginstal Ruby menggunakan perintah berikut:

1. Perbarui daftar paket:

   bash
   sudo apt update
   

2. Instal Ruby:

   bash
   sudo apt install ruby-full
   

3. Verifikasi instalasi:

   bash
   ruby -v
   

---

# 2. *Instalasi Jekyll*

*Jekyll* adalah pembuat situs statis yang menggunakan Ruby. Setelah Ruby terinstal, Anda bisa melanjutkan dengan menginstal Jekyll.

## 2.1. *Langkah-langkah Instalasi Jekyll*

### *A. Instalasi Jekyll Menggunakan Gem*

Jekyll diinstal melalui *RubyGems*, manajer paket Ruby. Untuk menginstalnya, jalankan perintah berikut di terminal atau command prompt:

bash
gem install jekyll bundler


- *jekyll*: Ini adalah alat untuk membuat situs statis.
- *bundler*: Digunakan untuk mengelola dependensi Ruby dalam proyek.

Jika instalasi berhasil, Anda bisa memverifikasi instalasi Jekyll dengan menjalankan:

bash
jekyll -v


Ini akan menampilkan versi Jekyll yang terinstal.

### *B. Mengatur Situs Jekyll Baru*

Setelah menginstal Jekyll, Anda dapat membuat situs baru dengan perintah berikut:

bash
jekyll new my-site


Perintah ini akan membuat folder my-site dengan struktur dasar proyek Jekyll di dalamnya. Anda dapat mengganti my-site dengan nama proyek sesuai keinginan Anda.

### *C. Menjalankan Server Jekyll*

Setelah situs baru dibuat, pindah ke direktori proyek yang baru saja Anda buat dan jalankan server lokal:

bash
cd my-site
bundle exec jekyll serve


Perintah ini akan memulai server Jekyll dan Anda bisa mengakses situs Anda di browser dengan alamat:


http://localhost:4000


### *D. Menyunting Situs Jekyll*

Setelah situs Jekyll berjalan, Anda dapat mulai mengedit konten di dalam folder proyek tersebut. File-file utama yang dapat Anda edit adalah:

- *_posts/*: Tempat untuk menyimpan artikel blog (dengan format YYYY-MM-DD-nama-post.md).
- *_config.yml*: File konfigurasi untuk pengaturan situs Jekyll (seperti nama situs, URL, dsb).
- *index.md* atau *index.html*: Halaman utama situs.

Anda bisa menambahkan lebih banyak halaman, mengedit tema, dan mengubah tampilan situs sesuai kebutuhan.

---

# 3. *Menggunakan Bundler untuk Manajemen Dependensi*

Dalam proyek Jekyll, sering kali Anda akan menggunakan Bundler untuk mengelola dependensi Ruby. Bundler memungkinkan Anda untuk mendefinisikan dan mengunci versi paket yang digunakan dalam proyek.

## 3.1. *Instalasi Bundler*

Jika Anda belum menginstal Bundler, lakukan dengan perintah berikut:

bash
gem install bundler


## 3.2. *Menggunakan Bundler*

1. Setelah itu, buat file Gemfile di direktori proyek Jekyll, dengan isi seperti berikut:

   ruby
   source 'https://rubygems.org'

   gem 'jekyll'
   gem 'jekyll-feed'
   

2. Jalankan perintah berikut untuk menginstal semua gem yang ada di Gemfile:

   bash
   bundle install
   

3. Setelah instalasi selesai, Anda dapat menjalankan Jekyll menggunakan Bundler:

   bash
   bundle exec jekyll serve
   

---

# 4. *Kesimpulan*

- *Instalasi Ruby*: Ruby adalah bahasa pemrograman yang diperlukan untuk menjalankan Jekyll. Instalasi Ruby bervariasi tergantung pada sistem operasi (macOS, Windows, Linux), dan bisa dilakukan menggunakan manajer paket seperti Homebrew (macOS) atau RubyInstaller (Windows).
  
- *Instalasi Jekyll*: Setelah Ruby terinstal, Anda bisa menginstal Jekyll menggunakan RubyGems (gem install jekyll bundler). Setelah itu, Anda dapat membuat situs baru menggunakan jekyll new, menjalankan server lokal dengan jekyll serve, dan mulai mengembangkan situs atau blog statis.

- *Bundler*: Menggunakan Bundler membantu Anda mengelola dependensi proyek Ruby, termasuk Jekyll, dengan cara yang lebih terstruktur.

Dengan mengikuti langkah-langkah di atas, Anda dapat menginstal Ruby, Jekyll, dan mengembangkan situs atau blog statis menggunakan Jekyll dengan mudah

