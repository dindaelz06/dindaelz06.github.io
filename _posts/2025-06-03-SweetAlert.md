---
layout: post
title : <div class="bubble-effect blog-title">SweetAlert</div>
---

penjelasan tentang bagaimana cara menambahkan SweetAlert

![HTML SweetAlert]

---
penjelasan tentang SweetAlert

SweetAlert adalah pustaka JavaScript yang digunakan untuk membuat dialog atau pop-up yang menarik dan interaktif di halaman web. Dibandingkan dengan kotak dialog bawaan JavaScript seperti alert(), confirm(), atau prompt(), SweetAlert menyediakan desain yang lebih modern dan fitur tambahan yang dapat dengan mudah disesuaikan.

SweetAlert populer karena kesederhanaan sintaksnya, kompatibilitasnya dengan berbagai browser, dan kemampuannya untuk meningkatkan pengalaman pengguna dengan pop-up yang responsif dan estetis.

---

### *1. Memulai dengan SweetAlert*

#### *1.1. Instalasi*

Ada beberapa cara untuk mulai menggunakan SweetAlert:

##### *a. Menggunakan CDN*

Tambahkan tautan ke pustaka SweetAlert dalam file HTML Anda:

html
<head>
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
</head>


##### *b. Menggunakan NPM*

Jika Anda menggunakan manajer paket seperti NPM, instal SweetAlert dengan perintah berikut:

bash
npm install sweetalert2


Kemudian impor pustaka dalam file JavaScript Anda:

javascript
import Swal from 'sweetalert2';


---

### *2. Membuat Dialog Dasar dengan SweetAlert*

SweetAlert menyediakan berbagai jenis dialog. Berikut adalah contoh dialog dasar:

#### *2.1. Alert Sederhana*

javascript
Swal.fire('Hello, world!');


#### *2.2. Alert dengan Judul dan Teks*

javascript
Swal.fire(
  'Judul',
  'Ini adalah teks deskripsi.',
  'info'
);


#### *2.3. Alert dengan Ikon*

SweetAlert mendukung beberapa ikon bawaan seperti success, error, warning, info, dan question.

javascript
Swal.fire(
  'Berhasil!',
  'Data telah disimpan.',
  'success'
);


---

### *3. Fitur Lanjutan SweetAlert*

#### *3.1. Dialog dengan Tombol Kustom*

Anda dapat menyesuaikan tombol dalam dialog:

javascript
Swal.fire({
  title: 'Konfirmasi',
  text: 'Apakah Anda yakin ingin melanjutkan?',
  icon: 'warning',
  showCancelButton: true,
  confirmButtonText: 'Ya',
  cancelButtonText: 'Batal'
});


#### *3.2. Input Formulir dalam Dialog*

SweetAlert mendukung input formulir seperti teks, email, atau password:

javascript
Swal.fire({
  title: 'Masukkan nama Anda',
  input: 'text',
  inputPlaceholder: 'Nama lengkap Anda'
}).then((result) => {
  if (result.isConfirmed) {
    console.log('Nama:', result.value);
  }
});


#### *3.3. Loading Indicator*

Untuk menampilkan loading indicator:

javascript
Swal.fire({
  title: 'Mohon tunggu...',
  allowOutsideClick: false,
  didOpen: () => {
    Swal.showLoading();
  }
});


#### *3.4. Menampilkan Timer*

SweetAlert dapat secara otomatis menutup dialog setelah beberapa detik:

javascript
Swal.fire({
  title: 'Auto close alert!',
  text: 'Dialog ini akan tertutup dalam 3 detik.',
  timer: 3000,
  timerProgressBar: true
});


---

### *4. Kustomisasi SweetAlert*

SweetAlert memungkinkan pengembang untuk menyesuaikan tampilan dialog agar sesuai dengan kebutuhan aplikasi.

#### *4.1. Mengubah Warna Tombol*

javascript
Swal.fire({
  title: 'Kustomisasi Tombol',
  confirmButtonText: 'Ya',
  confirmButtonColor: '#3085d6',
  cancelButtonText: 'Tidak',
  cancelButtonColor: '#d33',
  showCancelButton: true
});


#### *4.2. Menambahkan Gambar*

javascript
Swal.fire({
  title: 'Gambar Kustom',
  text: 'Dialog ini memiliki gambar kustom.',
  imageUrl: 'https://via.placeholder.com/150',
  imageWidth: 150,
  imageHeight: 150,
  imageAlt: 'Gambar kustom'
});


---

### *5. Mengintegrasikan SweetAlert dengan Aplikasi Web*

#### *5.1. Menangani Respon Pengguna*

Anda dapat menggunakan metode then() untuk menangani hasil dari dialog.

javascript
Swal.fire({
  title: 'Konfirmasi',
  text: 'Apakah Anda yakin?',
  icon: 'question',
  showCancelButton: true
}).then((result) => {
  if (result.isConfirmed) {
    Swal.fire('Tindakan Berhasil!', '', 'success');
  } else if (result.dismiss === Swal.DismissReason.cancel) {
    Swal.fire('Tindakan Dibatalkan', '', 'error');
  }
});


#### *5.2. Validasi Formulir dengan SweetAlert*

SweetAlert dapat digunakan untuk memberikan feedback pada pengguna setelah pengiriman formulir.

javascript
function submitForm(event) {
  event.preventDefault();
  Swal.fire('Formulir berhasil dikirim!', '', 'success');
}

document.getElementById('form').addEventListener('submit', submitForm);


---

### *6. Kesimpulan*

SweetAlert adalah pustaka yang sangat berguna untuk meningkatkan interaksi pengguna di aplikasi web. Dengan desain yang modern, fitur yang mudah digunakan, dan kemampuan kustomisasi yang luas, SweetAlert membantu Anda menciptakan pengalaman pengguna yang lebih baik. Pustaka ini cocok digunakan dalam berbagai proyek web untuk menampilkan pesan, menangani konfirmasi, atau bahkan membuat formulir sederhana.