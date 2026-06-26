# Website Penjualan Barang (PHP + MySQL)

## Struktur Folder
```
toko/
├── admin/              -> Panel admin (dashboard, produk, kategori, transaksi)
├── css/style.css        -> Styling
├── includes/            -> header.php & footer.php (reusable)
├── uploads/             -> Tempat gambar produk diupload
├── config.php           -> Koneksi database
├── database.sql         -> Skema + data contoh
├── index.php            -> Halaman utama (daftar produk)
├── login.php / register.php / logout.php
├── cart.php             -> Keranjang belanja
├── checkout.php         -> Proses checkout
└── riwayat.php          -> Riwayat transaksi customer
```

## Cara Menjalankan di VS Code

1. **Install XAMPP / Laragon** (jika belum ada) — untuk menyediakan Apache + MySQL + PHP.
2. **Salin folder `toko`** ke folder `htdocs` (XAMPP) atau `www` (Laragon).
3. **Buat database**:
   - Buka phpMyAdmin (`http://localhost/phpmyadmin`)
   - Klik "Import", pilih file `database.sql`, lalu jalankan.
4. **Buka folder project di VS Code**:
   ```
   code toko
   ```
5. Install extension **PHP Intelephense** dan **Live Server / PHP Server** (opsional, untuk kenyamanan).
6. Pastikan Apache & MySQL di XAMPP/Laragon sudah running.
7. Akses di browser:
   ```
   http://localhost/toko/
   ```

## Login Admin
Hash password contoh di `database.sql` mungkin tidak valid untuk MySQL versi Anda.
**Cara paling aman**: daftar akun baru lewat `register.php`, lalu ubah manual kolom
`role` pada tabel `users` di phpMyAdmin dari `customer` menjadi `admin`.

## Fitur
- Customer: lihat produk, cari & filter kategori, keranjang, checkout, riwayat transaksi
- Admin: dashboard statistik, CRUD produk (dengan upload gambar), CRUD kategori, kelola status transaksi
- Keamanan dasar: `password_hash`, prepared-style escaping (`mysqli_real_escape_string`), session-based auth

## Pengembangan Lanjutan (opsional)
- Tambahkan validasi input lebih ketat & prepared statements (PDO)
- Tambahkan metode pembayaran (midtrans/payment gateway)
- Tambahkan pagination pada daftar produk
- Tambahkan rating & review produk
