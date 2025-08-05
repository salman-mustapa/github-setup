# Operasi Git Dasar: Test Token dan Autentikasi

Panduan ini mencakup langkah-langkah untuk menguji token dan autentikasi GitHub Anda dengan operasi Git.

## 🔍 Verifikasi Token GitHub

### 1. Test Token dengan GitHub API

- **Perintah**: Menggunakan `curl` untuk menguji apakah token berfungsi dengan baik.
- **Output yang Diharapkan**: Informasi akun GitHub jika token valid.

```bash
curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user
```

#### Output Contoh:
```json
{
  "login": "salman-mustapa",
  "id": 224708415,
  "name": "Salman Mustapa",
  "email": "salmanmustapa@outlook.com"
}
```

Jika output menampilkan informasi akun Anda, token telah dikonfigurasi dengan benar.

### 2. Periksa Scopes Token

- **Perintah**: Gunakan GitHub API untuk memeriksa scope dari token.
- **Output yang Diharapkan**: Daftar scope yang berlaku.

```bash
curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user | jq '.scopes'
```

## 🧪 Test Operasi Git

### 1. Clone Repository Menggunakan Token

```bash
# Format: git clone https://<username>:<token>@github.com/<username>/<repository>.git
git clone https://salman-mustapa:$GITHUB_TOKEN@github.com/salman-mustapa/test-repo.git
```

Jika berhasil, Anda sudah terautentikasi dengan baik.

### 2. Push Perubahan ke Repository

1. **Inisialisasi Repository Baru**

```bash
mkdir my-test-repo
cd my-test-repo
git init
echo "# My Test Repo" e README.md
git add README.md
git commit -m "Initial commit"
```

2. **Tambahkan Remote dan Push**

```bash
git remote add origin https://salman-mustapa:$GITHUB_TOKEN@github.com/salman-mustapa/my-test-repo.git
git push -u origin main
```

## 🚨 Troubleshooting

### Gagal Autentikasi

1. **Periksa Kevalidan Token** - Pastikan token belum expired.
2. **Cek Scope Token** - Pastikan token memiliki permission yang tepat.
3. **Verifikasi Koneksi Internet** - Pastikan Anda terhubung ke jaringan.

### Error: Permission Denied

1. **Cek Izin Repository** - Pastikan Anda memiliki akses sebagai owner/collaborator.
2. **Periksa Alamat Remote** - Pastikan URL remote benar.

---

### 📝 Catatan
- Menggunakan `curl` dan API GitHub sangat bermanfaat untuk memverifikasi dan menguji token.
- Pastikan untuk menjaga keamanan token Anda dan tidak membagikannya secara publik.

!!! success "Pengujian Berhasil"
    Jika semua langkah di atas berhasil, koneksi Git dan token GitHub Anda sudah terverifikasi dengan baik!
