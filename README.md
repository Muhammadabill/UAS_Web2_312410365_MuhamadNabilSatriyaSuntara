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



---

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

## 📌 Dokumentasi Visual & Pengujian


# 1. Skema Relasi Database
<img width="1532" height="854" alt="image" src="https://github.com/user-attachments/assets/8c378038-4e8b-4e74-8b59-e01f6353c409" />

# 2. Uji Coba Keamanan API
<img width="1919" height="1079" alt="Screenshot 2026-06-15 102127" src="https://github.com/user-attachments/assets/930c1d46-f901-4cdd-9460-6f734f9c516a" />

# 3. Uji Coba Buku
<img width="1916" height="1079" alt="Screenshot 2026-06-15 104321" src="https://github.com/user-attachments/assets/b8f5a471-2d7b-4277-b597-b3b0a8f33b6d" />

# 4. Antarmuka Aplikasi (Frontend)
Halaman Login:
<img width="1919" height="1009" alt="image" src="https://github.com/user-attachments/assets/078f0b6f-1480-4901-ae08-850ddf1eb7bd" />

# Dashboard Admin:
<img width="1896" height="1005" alt="image" src="https://github.com/user-attachments/assets/513f1d01-0c5d-4699-b77e-09bb77531eb5" />
<img width="1919" height="1006" alt="image" src="https://github.com/user-attachments/assets/5faa25f1-3efc-4c1c-8ee4-5c6f6583442d" />
<img width="1896" height="1008" alt="image" src="https://github.com/user-attachments/assets/bd9158c1-ed26-4edd-b7d7-45dd400fe9a9" />

# Dashboard Users:
<img width="1919" height="1005" alt="image" src="https://github.com/user-attachments/assets/ad0af449-2ca6-41b1-b8c4-317d3047e4d3" />
<img width="1897" height="1005" alt="image" src="https://github.com/user-attachments/assets/f524960b-bc73-48b0-8cb0-b3b45433b3bc" />
