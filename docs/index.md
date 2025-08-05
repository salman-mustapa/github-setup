# Panduan Konfigurasi GitHub ke Terminal

![GitHub Logo](https://github.githubassets.com/images/modules/logos_page/GitHub-Mark.png){ align=right width="100" }

Selamat datang di panduan lengkap untuk mengkonfigurasi GitHub dengan terminal Linux! Dokumentasi ini akan memandu Anda langkah demi langkah untuk mengatur GitHub agar dapat digunakan dengan terminal, termasuk operasi `clone`, `push`, `pull`, dan `branch`.

## 📋 Yang Akan Anda Pelajari

- **Instalasi Git** - Cara cepat install Git
- **Setup Git dan GitHub** - Konfigurasi dasar dan Personal Access Token
- **Testing** - Memastikan semuanya berjalan tanpa hambatan
- **Troubleshooting** - Langkah cepat mengatasi error

## 🚀 Quick Start

Jika Anda sudah memiliki akun GitHub dan ingin langsung mulai:

```bash
# 1. Konfigurasi identitas Git
git config --global user.name "Nama Anda"
git config --global user.email "email@anda.com"

# 2. Clone repository
git clone https://github.com/username/repository.git

# 3. Masuk ke direktori project
cd repository

# 4. Buat perubahan dan commit
git add .
git commit -m "Initial commit"
git push origin main
```

!!! warning "Perhatian"
    Quick start di atas memerlukan konfigurasi autentikasi terlebih dahulu. Ikuti panduan lengkap untuk setup yang tepat.

## 🛠️ Prasyarat

Sebelum memulai, pastikan Anda memiliki:

- [x] Komputer dengan sistem operasi Linux (Ubuntu/Debian/CentOS/dll)
- [x] Akses terminal/command line
- [x] Koneksi internet yang stabil
- [x] Email aktif untuk mendaftar GitHub

## 📚 Struktur Dokumentasi

### Persiapan
- **Install Git** - Cara menginstall Git di berbagai distribusi Linux
- **Membuat Akun GitHub** - Panduan registrasi dan setup awal

### Konfigurasi
- **Konfigurasi Dasar Git** - Setup nama, email, dan preferensi
- **Setup Personal Access Token** - Metode autentikasi yang direkomendasikan
- **Konfigurasi SSH** - Alternatif autentikasi menggunakan SSH key

### Testing & Verifikasi
- **Test Koneksi** - Memastikan konfigurasi berjalan dengan baik
- **Operasi Git Dasar** - Clone, push, pull, branch, dan merge

## 🔧 Metode Autentikasi

Dokumentasi ini mencakup dua metode autentikasi utama:

=== "Personal Access Token (Recommended)"

    - ✅ Lebih aman dan mudah dikelola
    - ✅ Dapat dibatasi scope akses
    - ✅ Mudah di-revoke jika diperlukan
    - ✅ Bekerja dengan HTTPS

=== "SSH Key"

    - ✅ Tidak perlu memasukkan kredensial berulang
    - ✅ Lebih cepat untuk operasi berulang
    - ✅ Standar industri untuk developer
    - ⚠️ Setup awal sedikit lebih kompleks

## 🎯 Target Audience

Dokumentasi ini ditujukan untuk:

- **Pemula** yang baru mengenal Git dan GitHub
- **Developer** yang ingin mengoptimalkan workflow
- **System Administrator** yang perlu setup Git di server
- **Student** yang belajar version control

## 📞 Bantuan dan Dukungan

Jika Anda mengalami kesulitan:

1. Periksa halaman [Troubleshooting](troubleshooting.md)
2. Baca [FAQ](faq.md) untuk masalah umum
3. Buat issue di [GitHub repository](https://github.com/salman-mustapa/github-setup-docs)

---

!!! tip "Tips"
    Ikuti panduan ini secara berurutan untuk hasil terbaik. Setiap langkah telah diuji dan dipastikan berfungsi dengan baik.

**Mari kita mulai dengan [Install Git](preparation/install-git.md)!** 🚀
