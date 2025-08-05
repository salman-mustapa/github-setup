# Test Koneksi GitHub

Setelah Anda mengonfigurasi Git dan mengatur Personal Access Token, penting untuk menguji apakah semuanya berfungsi dengan baik. Panduan ini memberikan langkah-langkah komprehensif untuk menguji koneksi dan autentikasi GitHub.

## 🔍 Verifikasi Konfigurasi Git

### 1. Cek Konfigurasi Git

Pastikan identitas Git sudah dikonfigurasi:

```bash
# Lihat konfigurasi user
git config --global --list | grep -E "(user.name|user.email)"
```

Output yang diharapkan:
```
user.name=Salman Mustapa
user.email=salmanmustapa@outlook.com
```

### 2. Cek Versi Git

```bash
git --version
```

Output contoh:
```
git version 2.48.1
```

## 🌐 Test Koneksi GitHub: Langkah Minimalis

1. **Cek Versi Git**
   ```bash
   git --version
   ```

2. **Cek Konfigurasi Git**
   ```bash
   git config --global --list
   ```

3. **Test Koneksi Internet**
   ```bash
   ping -c 2 github.com
   ```

4. **Test API GitHub**
   ```bash
   curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user
   ```

### 2. Test Koneksi SSH (Jika Menggunakan SSH)

Jika Anda menggunakan SSH untuk otentikasi:

```bash
ssh -T git@github.com
```

Output yang diharapkan:
```
Hi salman-mustapa! You've successfully authenticated, but GitHub does not provide shell access.
```

## 🚀 Test Token dan Operasi Git dalam 5 Menit

1. **Set Token di Environment**
   ```bash
   export GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
   ```

2. **Test Akses GitHub**
   ```bash
   curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user
   ```

3. **Cek Repository**
   ```bash
   curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user/repos
   ```

4. **Clone dan Push Cepat**
   ```bash
   git clone https://github.com/username/repository.git
   cd repository
   touch test.md
   git add .
   git commit -m "Test"
   git push origin main
   ```

## 🧪 Test Operasi Git Lengkap

### 1. Buat Repository Test Baru

```bash
# Buat direktori untuk test
mkdir github-test
cd github-test
git init

# Set branch default ke main
git branch -m main
```

### 2. Buat Commit Test

```bash
# Buat file README
echo "# GitHub Connection Test" > README.md
echo "" >> README.md
echo "Repository ini dibuat untuk menguji koneksi GitHub." >> README.md
echo "" >> README.md
echo "## Informasi" >> README.md
echo "- Tanggal: $(date)" >> README.md
echo "- User: $(git config user.name)" >> README.md
echo "- Email: $(git config user.email)" >> README.md

# Add dan commit
git add README.md
git commit -m "Initial commit: Add README with connection test info"
```

### 3. Test Push ke Repository Baru

```bash
# Tambahkan remote (sesuaikan dengan repository Anda)
git remote add origin https://github.com/salman-mustapa/github-test.git

# Push ke GitHub
git push -u origin main
```

!!! note "Catatan"
    Repository `github-test` harus sudah dibuat di GitHub terlebih dahulu, atau Anda bisa menggunakan repository yang sudah ada.

### 5. Pull dan Sync

Cek apakah sudah sinkron dengan remote:
```bash
git pull origin main
```

---

## ❌ Troubleshooting Cepat

1. **Error Token**
   - Pastikan token benar dan aktif.
   - Cek permission token minimal harus `repo`.

2. **Koneksi Gagal**
   - Pastikan koneksi internet stabil.
   - Coba ulangi test.

3. **Permission Denied saat Push**
   - Periksa apakah Anda memiliki akses repo.
   - Cek URL remote pada konfigurasi git.

4. **SSH Issues**
   - Pastikan public key sudah terdaftar di GitHub.

---

🎉 **Selesai!** Jika semua langkah ini berhasil, berarti GitHub dan Git Anda sudah siap digunakan.

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


