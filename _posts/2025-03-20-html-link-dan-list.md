---
layout: post
title : <div class="bubble-effect blog-title">HTML Link dan Lists</div>
---

penjelasan tentang Link dan Lists pada HTML


![Html link dan Lists]

---

## Pengertian Link dalam HTML

Link (atau tautan) dalam HTML adalah elemen yang memungkinkan pengguna berpindah dari satu halaman ke halaman lainnya, baik dalam situs yang sama maupun ke situs lain. Link juga bisa digunakan untuk membuka file, mengarah ke bagian tertentu dalam halaman, atau membuka email.

HTML menyediakan tag <a> (anchor) untuk membuat link. Tag ini memerlukan atribut href yang menunjukkan alamat tujuan dari link tersebut.

### Contoh dasar penggunaan:
```html
<a href="https://www.google.com">Kunjungi Google</a>

Atribut penting pada tag <a>:

href: Menentukan alamat tujuan dari tautan.

target: Menentukan di mana tautan akan dibuka. Contoh:

_self: membuka di tab/jendela yang sama (default).

_blank: membuka di tab/jendela baru.


title: Memberikan informasi tambahan saat kursor diarahkan ke link.

download: Jika digunakan, link akan mengunduh file alih-alih membukanya.


Contoh dengan atribut tambahan:

<a href="file.pdf" target="_blank" title="Unduh file ini" download>Unduh File PDF</a>


---

Pengertian List dalam HTML

List (daftar) adalah elemen HTML yang digunakan untuk menampilkan data atau informasi dalam bentuk poin-poin. HTML menyediakan tiga jenis list:

1. Ordered List (<ol>)

Digunakan untuk menampilkan daftar yang memiliki urutan atau nomor.

Contoh:

<ol>
  <li>Bangun tidur</li>
  <li>Sarapan</li>
  <li>Berangkat sekolah</li>
</ol>

Atribut yang bisa digunakan:

type: Menentukan jenis penomoran (1, A, a, I, i).

start: Menentukan angka/huruf awal.


Contoh:

<ol type="A" start="3">
  <li>Langkah ketiga</li>
  <li>Langkah keempat</li>
</ol>

2. Unordered List (<ul>)

Menampilkan daftar tanpa urutan (menggunakan bullet atau titik).

Contoh:

<ul>
  <li>Apel</li>
  <li>Pisang</li>
  <li>Jeruk</li>
</ul>

Bullet dapat diubah tampilannya menggunakan CSS.

3. Description List (<dl>)

Menampilkan daftar istilah dan penjelasan. Biasanya digunakan untuk kamus, glosarium, atau data deskriptif.

Contoh:

<dl>
  <dt>HTML</dt>
  <dd>Bahasa markup untuk membuat halaman web.</dd>
  <dt>CSS</dt>
  <dd>Bahasa untuk mengatur tampilan halaman web.</dd>
</dl>


---

Kombinasi Link dan List

Keduanya sering digunakan bersamaan, misalnya untuk membuat menu navigasi situs:

<ul>
  <li><a href="index.html">Beranda</a></li>
  <li><a href="tentang.html">Tentang Kami</a></li>
  <li><a href="kontak.html">Kontak</a></li>
</ul>


---

![HTML Link dan Lists](_site/assets/images/gambar html.png)