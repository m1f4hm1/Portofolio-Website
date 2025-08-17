# Portofolio_Website
Ini adalah website portofolio saya, dikembangkan oleh saya dengan bantuan LLM terbaru milik IBM, IBM Granite Base Model (_granite-3.0-8b-base_).

---

## Abstract

Dokumen ini merinci arsitektur dan fungsionalitas dari sebuah aplikasi web statis yang berfungsi sebagai portofolio digital. Aplikasi ini dirancang untuk menyajikan data kualifikasi, proyek, dan pengalaman profesional dari subjek, Muhammad Izzuddin Fahmi. Implementasi ini memanfaatkan teknologi front-end murni untuk memastikan portabilitas, performa tinggi, dan *zero-dependency deployment*. Proyek ini dikonstruksi sebagai bagian dari evaluasi untuk Capstone Project HACKTIV8, dengan fokus pada *Code Generations and Optimization with IBM Granite*.

---

## System Architecture and Technologies

Arsitektur sistem ini sepenuhnya berbasis klien (*client-side*). Tidak ada komponen *server-side* atau *database* eksternal yang diperlukan untuk operasi.

### 2.1. Core Technologies
* **HTML5 (HyperText Markup Language 5)**
    * **Fungsi**: Membentuk struktur semantik dan hierarki konten dari aplikasi.
    * **Implementasi**: Penggunaan *tag* semantik modern (`<header>`, `<main>`, `<section>`, `<footer>`, `<nav>`) untuk meningkatkan aksesibilitas (a11y) dan *Search Engine Optimization* (SEO).

* **CSS3 (Cascading Style Sheets 3)**
    * **Fungsi**: Bertanggung jawab atas seluruh aspek presentasi visual, *layouting*, dan animasi.
    * **Modul yang Diimplementasikan**:
        * **CSS Custom Properties (Variables)**: Untuk manajemen tema global dan konsistensi palet warna.
        * **CSS Grid & Flexbox**: Digunakan secara ekstensif untuk membangun *layout* yang kompleks, responsif, dan terstruktur.
        * **CSS Transitions & Animations (`@keyframes`)**: Digunakan untuk mengimplementasikan *micro-interactions*, efek *hover*, dan animasi *reveal-on-scroll*.
        * **CSS `clip-path`**: Diaplikasikan untuk membentuk geometri visual non-standar pada elemen gambar.
        * **CSS `backdrop-filter`**: Untuk menciptakan efek *glassmorphism* pada *header*.
        * **CSS `@property` (Houdini)**: Diimplementasikan untuk menganimasikan *scroll progress bar* secara performan.

* **JavaScript (ECMAScript 2021)**
    * **Fungsi**: Menyediakan fungsionalitas dinamis dan interaktivitas pada sisi klien.
    * **API yang Diimplementasikan**:
        * **DOM (Document Object Model) Manipulation**: Untuk kontrol *real-time* pada elemen halaman.
        * **Intersection Observer API**: Untuk deteksi visibilitas elemen, memicu animasi *on-scroll* secara efisien tanpa membebani *main thread*.
        * **Event Listeners**: Untuk menangani input pengguna seperti gerakan mouse (*mousemove*), klik, dan *scroll*.

### 2.2. External Libraries & Dependencies
* **Google Fonts**: *Dependency* eksternal untuk *asset* tipografi (*font family*: "Inter").
* **Font Awesome**: *Dependency* eksternal untuk *asset* ikonografi berbasis vektor.

---

## Feature Set Analysis

Aplikasi ini mengimplementasikan serangkaian fitur yang dirancang untuk meningkatkan pengalaman pengguna (UX) dan presentasi data.

* **F-01: Interactive Custom Cursor**
    * **Deskripsi**: Menggantikan kursor sistem operasi *default* dengan dua elemen melingkar (*dot* dan *outline*). *Outline* bereaksi terhadap *hover* pada elemen interaktif.
    * **Teknologi**: JavaScript, CSS `transform`.

* **F-02: Real-time Scroll Progress Indicator**
    * **Deskripsi**: Sebuah *progress bar* horizontal di bagian atas *viewport* yang secara dinamis merefleksikan posisi *scroll* vertikal pengguna.
    * **Teknologi**: CSS `@property`, CSS `animation-timeline`.

* **F-03: Animated Text Gradient**
    * **Deskripsi**: Judul utama pada *hero section* menggunakan gradien warna yang dianimasikan secara terus-menerus.
    * **Teknologi**: CSS `background-clip: text`, CSS Animation (`@keyframes`).

* **F-04: Dynamic Typing Effect**
    * **Deskripsi**: Sebuah *string* teks pada *hero section* disimulasikan seolah-olah sedang diketik, dihapus, dan diketik ulang dari sebuah *array* yang telah ditentukan.
    * **Teknologi**: JavaScript `setTimeout`, DOM Manipulation.

* **F-05: 3D-Interactive Project Cards**
    * **Deskripsi**: Kartu-kartu pada bagian proyek bereaksi terhadap posisi kursor mouse dengan menerapkan transformasi 3D (`rotateX`, `rotateY`), menciptakan ilusi kedalaman.
    * **Teknologi**: JavaScript *event listener* (`mousemove`), CSS `transform: perspective()`.

* **F-06: Sequential Reveal-on-Scroll Animation**
    * **Deskripsi**: Elemen dan section konten diinisialisasi dalam keadaan *hidden* (`opacity: 0`, `transform: translateY(30px)`) dan akan muncul dengan animasi saat masuk ke dalam *viewport*.
    * **Teknologi**: JavaScript Intersection Observer API, CSS `transition`.

* **F-07: Direct CV Download Functionality**
    * **Deskripsi**: Sebuah tombol menyediakan fungsionalitas untuk mengunduh file CV (format .pdf) secara langsung melalui atribut `download` pada *tag* `<a>`.
    * **Teknologi**: HTML5.

---

## Operational Directives

Proyek ini tidak memerlukan *build process* atau instalasi *dependency* yang kompleks.

### 4.1. Prasyarat
* Sebuah web browser modern (misalnya, Chrome, Firefox, Edge).
* Git (opsional, untuk *cloning*).

### 4.2. Prosedur Eksekusi Lokal
1.  **Clone Repository**: Eksekusi perintah berikut pada terminal Anda.
    ```bash
    git clone [https://github.com/m1f4hm1/Portofolio-Website.git]
    ```
2.  **Navigasi Direktori**: Pindah ke direktori root proyek.
    ```bash
    cd [Portofolio-Website]
    ```
3.  **Inisialisasi**: Buka file `index.html` menggunakan web browser.

---

## AI IBM Granite Integration

Model **IBM Granite (granite-3.0-8b-base)** diintegrasikan ke dalam *workflow* pengembangan sebagai *assisting tool*. Penggunaan model ini terbatas pada fase *development* dan tidak menjadi bagian dari *final product*.

### 5.1. Rincian Pemanfaatan Model
* **Code Generation & Scaffolding**:
    * **HTML Structure**: Model diminta untuk menghasilkan struktur HTML awal berdasarkan hierarki konten yang diberikan. *Output* yang dihasilkan mencakup struktur semantik yang kompleks untuk *layout multi-kolom* dan *grid*.
    * **CSS Boilerplate**: Model menghasilkan blok kode CSS fundamental, termasuk *CSS variable definitions*, *resets*, dan *utility classes* awal.
    * **JavaScript Functions**: Model menghasilkan *boilerplate code* untuk fungsi-fungsi interaktif. Contoh: logika dasar untuk *typing effect* dan struktur awal untuk *Intersection Observer callback*.

* **Optimization & Refactoring**:
    * **CSS Modernization**: Model menyediakan rekomendasi untuk refaktorisasi. Contoh: menyarankan penggunaan fungsi `clamp()` untuk *fluid typography* dibandingkan dengan *media query breakpoints* yang berlapis-lapis.
    * **JavaScript Efficiency**: Model menganalisis *snippet* kode JavaScript dan memberikan alternatif yang lebih performan. Contoh: menyarankan penggunaan `requestAnimationFrame` untuk animasi yang lebih halus (meskipun tidak diimplementasikan pada versi final untuk menjaga kesederhanaan).

* **Problem Solving & Ideation**:
    * **Fitur Kompleks**: Untuk implementasi fitur seperti *3D card effect* dan *custom cursor*, model diberikan *prompt* berisi deskripsi fungsionalitas yang diinginkan. Model kemudian menghasilkan beberapa pendekatan teknis beserta contoh kode, yang secara signifikan mengurangi waktu riset dan pengembangan.
    * **Dokumentasi**: Model menghasilkan draf awal untuk dokumentasi teknis ini (`README.md`).

### 5.2. Dampak Kuantitatif
Estimasi dampak penggunaan model IBM Granite pada proyek ini adalah **pengurangan waktu pengembangan sekitar 35-40%** 
[Normal Deployment Time: 2 hours >> AI Help for Deployment Time: 1 hour 20 minutes)  .

### 5.3. Strategi *Prompt Engineering*
Interaksi dengan model *granite-3.0-8b-base* tidak dilakukan secara sembarangan, melainkan menggunakan pendekatan *prompt engineering* yang terstruktur untuk memaksimalkan relevansi dan kualitas *output*.
* ***Role-Playing Prompt***: Sebagian besar interaksi diawali dengan memberikan peran pada model, misalnya: *"Anda adalah seorang ahli pengembang front-end dengan spesialisasi pada animasi CSS performan dan JavaScript modern. Berikan saya implementasi untuk..."*. Pendekatan ini mengarahkan model untuk menghasilkan kode sesuai dengan praktik terbaik di bidang tersebut.
* ***Context-Rich Queries***: Alih-alih meminta "buatkan efek 3D pada kartu", *prompt* yang diberikan jauh lebih rinci: *"Saya memiliki sebuah div dengan class '.project-card'. Saya ingin menerapkan efek 3D interaktif menggunakan CSS transform. Efek ini harus bereaksi terhadap posisi kursor mouse (mousemove) di dalam elemen tersebut. Rotasi pada sumbu X dan Y harus dibatasi maksimal 15 derajat. Berikan kode JavaScript dan CSS yang diperlukan."*. Kekayaan konteks ini secara drastis mengurangi ambiguitas.
* ***Iterative Refinement***: *Output* awal dari model seringkali dijadikan sebagai dasar. *Prompt* lanjutan kemudian digunakan untuk melakukan *refactoring* atau penambahan fitur, seperti: *"Dari kode sebelumnya, bagaimana cara menambahkan transisi yang halus (smooth transition) saat kursor masuk dan meninggalkan kartu?"*.

### 5.4. Keterbatasan dan Supervisi Manusia
Penting untuk dicatat bahwa model AI berfungsi sebagai *accelerator*, bukan sebagai pengganti developer.
* **Validasi Kode**: Setiap baris kode yang dihasilkan oleh Granite tetap melalui proses validasi dan pengujian manual. Ditemukan beberapa kasus di mana model menghasilkan sintaks yang sedikit usang atau pendekatan yang kurang optimal, yang kemudian diperbaiki oleh developer.
* **Integrasi Holistik**: Model sangat baik dalam menghasilkan *snippet* fungsional yang terisolasi. Namun, tugas untuk mengintegrasikan berbagai *snippet* ini ke dalam arsitektur aplikasi yang kohesif sepenuhnya berada di tangan developer.
* **Debugging**: Ketika terjadi *bug* atau perilaku yang tidak diinginkan dari kode yang dihasilkan AI, proses *debugging* tetap memerlukan intuisi dan keahlian manusia. Model dapat membantu memberikan hipotesis tentang penyebab *bug*, tetapi verifikasi akhir tetap dilakukan secara manual menggunakan *browser developer tools*.

---

## 6. Analisis Performa dan Optimalisasi

Selain fungsionalitas, aspek performa menjadi prioritas utama dalam pengembangan aplikasi ini. Strategi optimalisasi yang diterapkan berfokus pada *rendering path*, ukuran *asset*, dan efisiensi eksekusi skrip.

### 6.1. Optimalisasi Rendering Path Kritis (*Critical Rendering Path*)
* **Struktur HTML Asinkron**: Penempatan *script* JavaScript (`<script>`) sebelum tag penutup `</body>` memastikan bahwa proses *parsing* HTML dan *rendering* DOM tidak terblokir (*render-blocking*). Ini memungkinkan pengguna untuk melihat konten visual halaman secepat mungkin.
* **Pemuatan CSS Efisien**: *Stylesheet* utama ditempatkan di dalam tag `<head>` untuk memastikan bahwa aturan gaya diterapkan sebelum konten di-render, menghindari fenomena *Flash of Unstyled Content* (FOUC).

### 6.2. Kompresi dan Manajemen Aset
* **Aset Ikonografi**: Penggunaan Font Awesome (sebuah *font icon*) lebih diutamakan daripada gambar raster (seperti .png atau .jpg) untuk ikon. Sifatnya yang berbasis vektor memastikan skalabilitas tanpa degradasi kualitas dan memiliki ukuran file yang relatif kecil.
* **Aset Tipografi**: *Font* "Inter" dari Google Fonts dimuat dengan spesifikasi *weight* yang terbatas hanya pada yang benar-benar digunakan dalam desain, mengurangi *payload* yang tidak perlu.

---

## 7. Pertimbangan Aksesibilitas (a11y) dan SEO

Pengembangan aplikasi web modern tidak terlepas dari kewajiban untuk memastikan aksesibilitas bagi semua pengguna, termasuk mereka yang menggunakan teknologi bantu (*assistive technologies*), dan visibilitas oleh mesin pencari.

### 7.1. Implementasi Aksesibilitas
* **Struktur Semantik**: Seperti yang disebutkan, penggunaan tag HTML5 semantik (`<main>`, `<nav>`, `<section>`) memberikan struktur yang jelas bagi *screen readers* untuk menavigasi konten.
* **Kontras Warna**: Pemilihan palet warna telah mempertimbangkan rasio kontras yang memadai antara teks dan latar belakang sesuai dengan pedoman *Web Content Accessibility Guidelines* (WCAG) 2.1.
* **Teks Alternatif**: Setiap elemen `<img>` yang informatif dilengkapi dengan atribut `alt` yang deskriptif, menyediakan konteks bagi pengguna yang tidak dapat melihat gambar.

### 7.2. Optimisasi Mesin Pencari (SEO)
* ***Meta Tags***: Implementasi *meta tags* yang relevan (`<meta name="description">`, `<meta name="keywords">`) di dalam `<head>` dokumen memberikan informasi ringkas kepada *crawler* mesin pencari tentang konten halaman.
* ***Title Tag***: Setiap halaman memiliki `<title>` yang unik dan deskriptif, yang merupakan salah satu faktor peringkat SEO yang paling penting.
* ***Crawlability***: Karena sifatnya yang statis dan *server-rendered* (langsung dari file HTML), konten situs ini sangat mudah di-*crawl* dan diindeks oleh mesin pencari.

---

## 8. Kesimpulan dan Pengembangan Lanjutan

### 8.1. Kesimpulan
Proyek ini berhasil mendemonstrasikan konstruksi sebuah portofolio web statis yang modern, performan, dan interaktif dengan memanfaatkan teknologi *front-end* murni. Arsitektur *zero-dependency* memastikan portabilitas dan kemudahan *deployment*. Integrasi model AI IBM Granite dalam alur kerja terbukti secara signifikan mengakselerasi fase pengembangan, terutama pada tahap *scaffolding*, ideasi fitur kompleks, dan optimisasi. Hasil akhirnya adalah sebuah produk digital yang fungsional dan estetis, yang secara efektif merepresentasikan kapabilitas subjek.

### 8.2. Potensi Pengembangan Lanjutan
* **Integrasi dengan *Headless CMS***: Untuk mempermudah pembaruan konten proyek tanpa harus mengubah kode sumber secara langsung, arsitektur dapat diperluas untuk mengambil data dari *Headless CMS* seperti Strapi atau Contentful melalui API.
* **Implementasi *Light/Dark Mode***: Menambahkan fungsionalitas untuk mengubah tema warna situs akan meningkatkan pengalaman pengguna. Hal ini dapat diimplementasikan secara efisien dengan memanfaatkan CSS Custom Properties yang telah ada.
* ***Internationalization* (i18n)**: Menambahkan dukungan multi-bahasa (misalnya, Bahasa Inggris dan Bahasa Indonesia) untuk menjangkau audiens yang lebih luas.
* **Pengujian Unit (*Unit Testing*)**: Menambahkan kerangka kerja pengujian seperti Jest atau Vitest untuk memvalidasi logika pada fungsi-fungsi JavaScript, memastikan stabilitas dan keandalan saat penambahan fitur baru di masa depan.
