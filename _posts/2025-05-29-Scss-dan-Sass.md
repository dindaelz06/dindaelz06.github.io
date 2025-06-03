---
layout: post
title : <div class="bubble-effect blog-title">menambahkan Scss dan Sass pada HTML</div>
---

penjelasan tentang bagaimana cara menambahkan Scss dan Sass pada html


![HTML Scss dan Sass]

---
penjelasan tentang SCSS dan SASS

## Pendahuluan

SCSS (Sassy CSS) dan SASS (Syntactically Awesome Stylesheets) adalah preprocessor CSS yang dirancang untuk meningkatkan produktivitas dan efisiensi dalam penulisan stylesheet. Dengan fitur seperti variabel, nesting, mixins, dan inheritance, SCSS/SASS membantu pengembang menulis kode yang lebih terorganisir, mudah dipelihara, dan dinamis.

---

## Apa Itu SASS dan SCSS?

* *SASS:* Format sintaks original yang lebih ringkas, tanpa kurung kurawal {} dan titik koma ;.
* *SCSS:* Sintaks modern yang mirip dengan CSS, sehingga lebih ramah bagi pengembang yang sudah familiar dengan CSS.

### Perbandingan Sintaks:

#### SASS:

sass
$primary-color: #3498db
body
  background-color: $primary-color


#### SCSS:

scss
$primary-color: #3498db;
body {
  background-color: $primary-color;
}

---

## Manfaat Menggunakan SCSS/SASS

1. *Reusabilitas Kode:* Komponen dapat digunakan kembali dengan mixins atau inheritance.
2. *Fleksibilitas:* Mendukung variabel dan operasi matematika.
3. *Organisasi File:* Struktur modular melalui partials dan import.
4. *Kompatibilitas:* File SCSS dikompilasi menjadi CSS standar yang dapat dibaca oleh browser.

---

## Instalasi dan Setup

### Prasyarat:

* *Node.js* terinstal di komputer.
* *Package Manager* seperti npm atau yarn.

### Langkah Instalasi:

1. Install SASS secara global:

   bash
   npm install -g sass
   
2. Verifikasi instalasi:

   bash
   sass --version
   
3. Kompilasi file SCSS menjadi CSS:

   bash
   sass input.scss output.css
   
4. Aktifkan mode watch untuk kompilasi otomatis:

   bash
   sass --watch scss:css
   

---

## Fitur Utama SCSS

### 1. Variabel

Variabel digunakan untuk menyimpan nilai yang sering digunakan, seperti warna, ukuran, atau font:

scss
$primary-color: #3498db;
$font-size: 16px;

body {
  color: $primary-color;
  font-size: $font-size;
}


### 2. Nesting

Nesting memungkinkan Anda menulis CSS yang bersarang, mencerminkan struktur HTML:

scss
nav {
  ul {
    margin: 0;
    padding: 0;
    li {
      list-style: none;
    }
  }
}


### 3. Partials dan Import

Gunakan partials untuk memecah kode menjadi file kecil yang dapat diimpor:

* File _variables.scss:

  scss
  $primary-color: #3498db;
  
* File main.scss:

  scss
  @import 'variables';

  body {
    color: $primary-color;
  }
  

### 4. Mixin

Mixin adalah blok kode yang dapat digunakan kembali:

scss
@mixin border-radius($radius) {
  border-radius: $radius;
  -webkit-border-radius: $radius;
}

button {
  @include border-radius(5px);
}


### 5. Extend/Inheritance

Gunakan inheritance untuk berbagi properti antar selektor:

scss
%button-style {
  padding: 10px 20px;
  font-size: 14px;
}

.primary-btn {
  @extend %button-style;
  background-color: blue;
}

.secondary-btn {
  @extend %button-style;
  background-color: gray;
}


### 6. Operasi Matematis

SCSS mendukung operasi aritmatika langsung pada nilai:

scss
$base-padding: 10px;

.container {
  padding: $base-padding * 2;
}


---

## Studi Kasus: Membuat Sistem Button dengan SCSS

### Struktur Folder:


project/
|-- scss/
|   |-- _variables.scss
|   |-- _mixins.scss
|   |-- _buttons.scss
|   |-- styles.scss
|-- css/
|   |-- styles.css
|-- index.html


### File _variables.scss:

scss
$primary-color: #3498db;
$secondary-color: #2ecc71;
$font-family: 'Arial, sans-serif';


### File _mixins.scss:

scss
@mixin transition($property, $duration) {
  transition: $property $duration;
}


### File _buttons.scss:

scss
@import 'variables';
@import 'mixins';

.button {
  font-family: $font-family;
  padding: 10px 20px;
  border: none;
  cursor: pointer;

  &.primary {
    background-color: $primary-color;
    color: #fff;
    @include transition(all, 0.3s);

    &:hover {
      background-color: darken($primary-color, 10%);
    }
  }

  &.secondary {
    background-color: $secondary-color;
    color: #fff;
    @include transition(all, 0.3s);

    &:hover {
      background-color: darken($secondary-color, 10%);
    }
  }
}


### File styles.scss:

scss
@import 'variables';
@import 'mixins';
@import 'buttons';


### File HTML:

html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="css/styles.css">
  <title>SCSS Buttons</title>
</head>
<body>
  <button class="button primary">Primary Button</button>
  <button class="button secondary">Secondary Button</button>
</body>
</html>


---