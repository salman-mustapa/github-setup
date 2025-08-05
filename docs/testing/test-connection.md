# Test Koneksi

Setelah Anda mengonfigurasi Git dan mengatur Personal Access Token, penting untuk menguji apakah semuanya berfungsi dengan baik. Panduan ini memberikan langkah-langkah untuk menguji koneksi dan otentikasi.

## 🔗 Test Koneksi dengan GitHub

### 1. Cek Koneksi Internet

Pastikan Anda terhubung ke internet:

```bash
ping -c 4 google.com
```

### 2. Test Koneksi SSH (Opsional)

Jika Anda menggunakan SSH untuk otentikasi:

```bash
ssh -T git@github.com
```

Output yang diharapkan:
```
Hi <username>! You've successfully authenticated, but GitHub does not provide shell access.
```

### 3. Test Koneksi HTTP(S)

Jika Anda menggunakan Personal Access Token (PAT), coba clone repositori:

```bash
git clone https://github.com/<username>/<repository>.git
```

Jika berhasil, koneksi HTTPS Anda telah dikonfigurasi dengan benar.

## 🧪 Test Operasi Git Dasar

### 1. Buat dan Inisialisasi Repositori

```bash
mkdir test-repo
cd test-repo
git init
```

### 2. Tambahkan dan Commit Perubahan

```bash
echo "# Test Repository" > README.md
git add README.md
git commit -m "Initial commit"
```

### 3. Sambungkan ke Remote Repository

```bash
git remote add origin https://github.com/<username>/test-repo.git
git push -u origin main
```

Jika semua langkah di atas berhasil tanpa error, konfigurasi Git dan koneksi ke GitHub telah terverifikasi.

## ❌ Troubleshooting

### Tidak Dapat Terhubung ke GitHub

Jika Anda mengalami masalah koneksi:

1. **Periksa Koneksi Internet** - Pastikan terhubung ke jaringan yang stabil
2. **Periksa Konfigurasi Git** - Pastikan `user.name` dan `user.email` telah terkonfigurasi
3. **Periksa Token dan Autentikasi** - Jika menggunakan PAT, pastikan token valid dan memiliki izin yang benar

### Error Otentikasi

Jika Anda mengalami error saat autentikasi:

1. **Periksa Username dan Password/Token** - Pastikan benar saat dimasukkan pertama kali
2. **Periksa SSH Keys (jika menggunakan SSH)** - Pastikan public key terdaftar di GitHub

### Tidak Dapat Push/Clone

Jika mengalami **permission denied**:

1. **Periksa Izin Repositori** - Pastikan Anda punya akses ke repo (sebagai owner/collaborator)
2. **Periksa Konfigurasi Remote** - Pastikan remote URL benar (https:// atau git@)

---

!!! success "Koneksi Terverifikasi"
    Anda telah berhasil menguji semua koneksi dan otentikasi. Lanjutkan dengan [Operasi Git Dasar](basic-git-operations.md) untuk mulai bekerja dengan Git!


