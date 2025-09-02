# Blender — Layanan Kesehatan Mental

Proyek ini adalah situs statis untuk layanan kesehatan mental bernama Blender. Situs mencakup halaman \Landing, \About Us, \How It Works, \Testimoni, dan \Contact Us (dengan verifikasi \reCAPTCHA terlebih dahulu).

## Fitur
- Navigasi responsif dengan hamburger menu
- Halaman \Home dengan hero section
- Halaman \About Us berisi tujuan dan misi
- Halaman \How It Works berisi alur 3 langkah dan profil konsultan
- Bagian \Testimoni
- Form \Contact Us yang terlindungi \Google reCAPTCHA (v2)
- Efek animasi scroll dan kartu layanan
- Desain responsif untuk \Laptop, \Tablet, dan \Mobile

## Struktur Proyek
web_2-main/
├─ index.html                # Halaman utama
├─ about_us.html            # Halaman About Us + layanan & topik
├─ How.html                 # How It Works + People + Testimoni
├─ contact_us/
│  └─ index.html            # Form Contact Us
├─ authen/
│  ├─ verify.html           # Halaman verifikasi reCAPTCHA (client)
│  ├─ verify.php            # Verifikasi reCAPTCHA (server, \PHP)
│  └─ style.css             # Style halaman verifikasi
├─ img/                     # Aset gambar (hero, ikon, avatar, dll.)
├─ style.css                # Style global situs
├─ script.js                # Interaksi UI (hamburger, observer)
└─ README.md

## Teknologi
- \HTML5, \CSS3, \JavaScript (Vanilla)
- \PHP (untuk verifikasi \Google reCAPTCHA)
- \Google Fonts (\Ubuntu)
- \Google reCAPTCHA v2

## Prasyarat
- Web server untuk menyajikan file statis (\VS Code Live Server, \Nginx, atau \Apache)
- \PHP 7\.4+ (untuk menjalankan `authen/verify.php`)
- Kunci \Google reCAPTCHA v2 (site key dan secret key)
- Opsional: \Node.js hanya jika Anda ingin menambahkan tool dev, tidak diperlukan saat ini

## Menjalankan Secara Lokal
1. Clone repositori
2. Jalankan server \PHP (contoh bawaan \PHP):

Atau gunakan ekstensi \Live Server (untuk halaman statis). Untuk alur verifikasi reCAPTCHA, gunakan server \PHP karena `verify.php` butuh eksekusi server.

## Konfigurasi reCAPTCHA
- File: `authen/verify.html`
  - Atribut `data-sitekey="..."`
- File: `authen/verify.php`
  - Variabel `\$recaptchaSecret = "..."`

Ganti dengan kredensial milik Anda:
- `data-sitekey="<SITE_KEY_ANDA>"`
- `\$recaptchaSecret = "<SECRET_KEY_ANDA>"`

## Cara Pakai
- Navigasi:
  - \Home: `index.html`
  - \About Us: `about_us.html` (terdapat section layanan dan topik)
  - \How It Works: `How.html` (alur 3 langkah dan daftar konsultan)
  - \Contact Us: melalui `authen/verify.html` -> sukses -> `contact_us/index.html`
- Hamburger menu aktif di \Tablet/Mobile
- Animasi scroll aktif pada section tertentu (observer di `script.js`)

## Keamanan
- reCAPTCHA mencegah spam pada \Contact Us
- Hindari mengekspos kunci reCAPTCHA di publik
- Pertimbangkan validasi sisi server untuk input \Contact Us jika nantinya dikirim ke backend

## Aksesibilitas & SEO (saran perbaikan)
- Tambahkan atribut `alt` yang deskriptif di semua `<img>`
- Gunakan heading terstruktur (H1, H2, ...)
- Tambahkan \meta description pada setiap halaman
- Pastikan kontras warna sudah memadai untuk teks pada background gelap

## Lisensi
Blender © 2025 @KevinWahyu 

## Kontributor
@arvareza
