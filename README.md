# Sistem Informasi Manajemen Laundry (Smart Laundry POS)

Aplikasi **Sistem Informasi Manajemen Laundry Berbasis Web** yang dibangun menggunakan framework **Laravel** untuk memenuhi proyek **Asesmen Sumatif Akhir Semester (ASAS) Konsentrasi Keahlian Rekayasa Perangkat Lunak (RPL) Kelas XII**. Aplikasi ini membantu operasional usaha laundry mulai dari pengelolaan tarif layanan, pencatatan transaksi kasir, pelacakan progres cucian pelanggan, hingga rekapitulasi laporan keuangan.

---

## ✨ Fitur Utama

### 1. Autentikasi & Pembagian Hak Akses (Role-Based Access)
* **Admin:** Memiliki akses penuh ke seluruh fitur sistem, termasuk manajemen **CRUD Data Layanan** (tambah, ubah, hapus paket & tarif), dashboard analitik, serta pengelolaan transaksi.
* **Kasir:** Fokus pada operasional harian (input order baru, pembaruan status pengerjaan, cetak struk, notifikasi WhatsApp, dan rekap laporan). Menu pengelolaan tarif layanan diproteksi secara otomatis.

### 2. Dashboard Analitik & Grafik Interaktif
* Kartu ringkasan statistik *real-time* (Total Paket Layanan, Cucian Sedang Diproses, Cucian Selesai, dan Total Omzet Selesai).
* Visualisasi grafik menggunakan **Chart.js** (grafik batang pendapatan per jenis layanan dan grafik donat rasio status cucian).
* Daftar 5 transaksi terbaru serta panduan tarif aktif.

### 3. Manajemen Data Layanan (CRUD)
* Mengelola paket cucian seperti **Reguler**, **Ekspress**, dan **Superkilat** beserta tarif per kilogram dan estimasi waktu pengerjaan.

### 4. Transaksi Kasir & Laporan Keuangan
* **Kalkulasi Tarif Otomatis:** Menghitung estimasi total bayar secara langsung berdasarkan berat cucian (kg) dikalikan tarif layanan.
* **Manajemen Status Pengerjaan:** Memperbarui status pesanan dari **Proses** menjadi **Selesai** dengan satu klik.
* **Cetak Struk Thermal (`80mm`):** Halaman nota siap cetak lengkap dengan kode nota unik.
* **Notifikasi WhatsApp Otomatis:** Mengirim rincian pesanan atau pemberitahuan cucian selesai langsung ke WhatsApp pelanggan (`wa.me`).
* **Filter & Export Laporan:** Pencarian cepat berdasarkan nama/HP/kode nota, filter status, filter rentang tanggal, serta **Export Laporan Keuangan ke Excel (`.csv`)**.

### 5. Portal Lacak Cucian Pelanggan (`/lacak`)
* Halaman publik tanpa login yang memudahkan pelanggan memantau progres cucian secara mandiri menggunakan **Nomor HP**, **Nama**, atau **Kode Nota**.

---

## 🛠️ Teknologi yang Digunakan
* **Backend:** PHP 8.x, Laravel Framework
* **Database:** MySQL (Laragon)
* **Frontend:** Blade Template, Tailwind CSS, Chart.js

---

## 🗄️ Struktur Relasi Database
1. **`users`**: Menyimpan data akun petugas dan hak akses (`role`: `admin` / `kasir`).
2. **`layanans`**: Menyimpan master data jenis layanan, harga per kg, dan estimasi durasi.
3. **`transaksis`**: Menyimpan data pesanan pelanggan yang berelasi (*Foreign Key* `layanan_id`) dengan tabel `layanans`.

---

## 🚀 Cara Instalasi & Menjalankan di Lokal

1. **Clone repository ini:**
   ```bash
   git clone [https://github.com/whyuputrap14/aplikasi-laundry-laravel.git](https://github.com/whyuputrap14/aplikasi-laundry-laravel.git)
   cd aplikasi-laundry-laravel


1. Install dependensi Composer:Bashcomposer install
2. Salin file konfigurasi .env dan generate application key:Bashcp .env.example .env
php artisan key:generate
3. Konfigurasi Database:
Buat database baru di MySQL/phpMyAdmin bernama db_laundry, lalu sesuaikan pengaturan pada file .env:Cuplikan kodeDB_DATABASE=db_laundry
DB_USERNAME=root
DB_PASSWORD=
4. Jalankan Migrasi & Seeder Database:Bashphp artisan migrate --seed
5. Jalankan Server Lokal:Bashphp artisan serve
Buka browser dan akses http://127.0.0.1:8000.

🔐 Akun Pengujian (Default Seeder)
Role : Administrator & Kasir
Email : Administratoradmin@laundry.com & kasir@laundry.com
Password : password123

👨‍💻 Pengembang
Nama: Wahyu Putra Pujonarko
Kelas: XII RPL 1
Sekolah: SMKN 06 Kota Tangerang Selatan
---

### Langkah Setelah Klik "Commit changes..."
1. Setelah menekan **Commit changes...**, akan muncul pop-up konfirmasi di GitHub—klik sekali lagi tombol **Commit changes**[cite: 15].
2. Jika nanti kamu mengubah kode lagi di VS Code dan ingin melakukan `git push`, jalankan `git pull origin main` terlebih dahulu di terminal agar file `README.md` yang baru dibuat di web GitHub ikut tersinkron ke laptopmu[cite: 15].
