# 📚 E-Library Management System

Sistem manajemen perpustakaan digital berbasis web yang memungkinkan admin mengelola koleksi buku dan data peminjaman, serta pengguna untuk meminjam dan mengembalikan buku secara online.

---

## 👤 Identitas

| | |
|---|---|
| **Nama** | Muhamad Nabil Satriya Suntara |
| **NIM** | 312410365 |
| **Kelas** | I241D / TI.24.A4 |
| **Mata Kuliah** | Pemrograman Web |

---

## 📖 Deskripsi Proyek

E-Library Management adalah aplikasi *single page application* (SPA) untuk perpustakaan digital dengan dua peran pengguna:

- **Admin** — mengelola koleksi buku (tambah, ubah, hapus) dan memantau seluruh transaksi peminjaman.
- **User** — menjelajah katalog buku, meminjam buku dengan menentukan tanggal pengembalian, serta melihat dan mengelola riwayat peminjamannya sendiri.

Proyek ini dibangun dengan arsitektur **REST API** terpisah antara backend dan frontend, di mana komunikasi data dilakukan melalui format JSON dengan otentikasi berbasis token.

---

## 🛠️ Teknologi yang Digunakan

| Layer | Teknologi |
|---|---|
| Backend | PHP 8.2, Framework **CodeIgniter 4** |
| Database | MySQL (`db_elibrary`) |
| Frontend | HTML5, CSS3, JavaScript (Vanilla), **Bootstrap 5** |
| Ikon | Bootstrap Icons |
| Otentikasi | Token berbasis Base64 (custom, mirip JWT) |
| Tools | XAMPP, phpMyAdmin |

---

## 🗂️ Struktur Proyek

```
project/
│
├── backend-api/                  # REST API (CodeIgniter 4)
│   ├── app/
│   │   ├── Config/
│   │   │   └── Routes.php        # Definisi seluruh endpoint API
│   │   ├── Controllers/
│   │   │   ├── Auth.php          # Login & autentikasi
│   │   │   ├── Buku.php          # CRUD data buku
│   │   │   └── Peminjaman.php    # Transaksi peminjaman & pengembalian
│   │   ├── Filters/
│   │   │   └── AuthFilter.php    # Middleware validasi token
│   │   └── Models/
│   │       ├── UserModel.php
│   │       ├── BukuModel.php
│   │       └── PeminjamanModel.php
│   └── .env                      # Konfigurasi environment & database
│
└── frontend-spa/                 # Single Page Application
    └── index.html                # Seluruh UI, logika, dan pemanggilan API
```

## ✨ Fitur Utama

### 👑 Admin
- Dashboard ringkasan: total koleksi, jumlah sedang dipinjam, dan sudah dikembalikan
- Kelola buku: tambah, ubah, dan hapus data buku secara penuh (CRUD)
- Memantau seluruh data peminjaman dari semua pengguna
- Memproses pengembalian buku atas nama pengguna mana pun

### 📖 User
- Menjelajah katalog buku lengkap dengan fitur pencarian
- Meminjam buku dengan memilih tanggal pengembalian sendiri melalui pop-up
- Melihat riwayat peminjaman pribadi beserta status (`Dipinjam` / `Dikembalikan`)
- Mengembalikan buku secara mandiri kapan saja sebelum maupun sesudah jatuh tempo

---

## ⚙️ Cara Menjalankan Proyek

1. **Siapkan server lokal**
   Pastikan XAMPP (Apache & MySQL) sudah aktif.

2. **Buat database**
   Buat database `db_elibrary` di phpMyAdmin, lalu sesuaikan struktur tabel `users`, `buku`, dan `peminjaman`.

3. **Jalankan backend**
   ```bash
   cd backend-api
   php spark serve
   ```
   Server akan berjalan di `http://localhost:8080`.

4. **Jalankan frontend**
   Buka file `frontend-spa/index.html` langsung di browser.

5. **Login**
   Gunakan akun admin atau user yang tersedia di tabel `users`.

---

## 📌 Catatan Pengembangan

Proyek ini merupakan hasil pembelajaran mata kuliah Pemrograman Web, dengan fokus pada:
- Implementasi REST API menggunakan CodeIgniter 4
- Komunikasi frontend-backend melalui `fetch()` dan format JSON
- Manajemen otentikasi dan otorisasi berbasis token
- Penerapan logika bisnis (validasi stok, kepemilikan data, batas akses per peran)
