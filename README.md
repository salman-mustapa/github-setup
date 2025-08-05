# 📚 Panduan Konfigurasi GitHub ke Terminal

[![MkDocs](https://img.shields.io/badge/docs-mkdocs-blue.svg)](https://www.mkdocs.org/)
[![Material](https://img.shields.io/badge/theme-material-green.svg)](https://squidfunk.github.io/mkdocs-material/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-Live-brightgreen.svg)](https://salman-mustapa.github.io/github-setup/)

Dokumentasi lengkap untuk mengkonfigurasi GitHub dengan terminal Linux. Panduan ini dibuat menggunakan MkDocs dengan tema Material untuk pengalaman membaca yang optimal.

## 🌐 Dokumentasi Online

**📖 Baca dokumentasi lengkap di:** [https://salman-mustapa.github.io/github-setup/](https://salman-mustapa.github.io/github-setup/)

> Dokumentasi selalu up-to-date dan dapat diakses dari mana saja tanpa perlu install dependencies lokal.

## 🎯 Tentang Dokumentasi Ini

Dokumentasi ini mencakup panduan lengkap dari instalasi Git hingga operasi Git tingkat lanjut, termasuk:

- ✅ **Instalasi Git** di berbagai distribusi Linux
- ✅ **Pembuatan akun GitHub** dan konfigurasi dasar
- ✅ **Setup Personal Access Token** untuk autentikasi yang aman
- ✅ **Konfigurasi SSH** sebagai alternatif autentikasi
- ✅ **Testing dan verifikasi** semua konfigurasi
- ✅ **Troubleshooting** masalah umum

## 🚀 Quick Start

### Untuk Membaca Dokumentasi

1. **Clone repository ini:**
   ```bash
   git clone https://github.com/salman-mustapa/github-setup.git
   cd github-setup
   ```

2. **Install dependencies:**
   ```bash
   pip install mkdocs mkdocs-material mkdocs-git-revision-date-localized-plugin
   ```

3. **Jalankan development server:**
   ```bash
   mkdocs serve
   ```

4. **Buka browser:** `http://127.0.0.1:8000`

### Untuk Konfigurasi GitHub Langsung

Jika Anda sudah familiar dan ingin langsung setup:

```bash
# 1. Konfigurasi identitas Git
git config --global user.name "Nama Anda"
git config --global user.email "email@anda.com"

# 2. Set credential helper
git config --global credential.helper store

# 3. Clone repository (akan diminta username dan Personal Access Token)
git clone https://github.com/username/repository.git
```

> ⚠️ **Penting**: Anda perlu membuat Personal Access Token di GitHub terlebih dahulu!

## 📖 Struktur Dokumentasi

```
docs/
├── index.md                     # Halaman beranda
├── preparation/                 # Persiapan awal
│   ├── install-git.md          # Instalasi Git
│   └── create-github-account.md # Membuat akun GitHub
├── configuration/               # Konfigurasi
│   ├── basic-git-config.md     # Konfigurasi dasar Git
│   ├── setup-pat.md            # Setup Personal Access Token
│   └── setup-ssh.md            # Konfigurasi SSH (opsional)
├── testing/                     # Testing & Verifikasi
│   ├── test-connection.md      # Test koneksi
│   └── basic-git-operations.md # Operasi Git dasar
├── troubleshooting.md           # Troubleshooting
└── faq.md                      # FAQ
```

## 🛠️ Teknologi yang Digunakan

- **[MkDocs](https://www.mkdocs.org/)** - Static site generator
- **[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)** - Material Design theme
- **[Git Revision Date Plugin](https://github.com/timvink/mkdocs-git-revision-date-localized-plugin)** - Show last update dates

## 🎨 Fitur Dokumentasi

- 🌙 **Dark/Light Mode** - Toggle tema sesuai preferensi
- 🔍 **Search** - Pencarian dalam dokumentasi
- 📱 **Responsive** - Optimal di desktop dan mobile
- 🎯 **Navigation** - Navigasi yang mudah dan terstruktur
- 📋 **Code Copy** - Copy code block dengan satu klik
- 🏷️ **Syntax Highlighting** - Highlighting untuk berbagai bahasa

## 📦 Instalasi Dependencies

### Ubuntu/Debian
```bash
# Install Python dan pip
sudo apt update
sudo apt install python3 python3-pip -y

# Install MkDocs dan dependencies
pip3 install mkdocs mkdocs-material mkdocs-git-revision-date-localized-plugin
```

### CentOS/RHEL/Fedora
```bash
# Install Python dan pip
sudo dnf install python3 python3-pip -y

# Install MkDocs dan dependencies
pip3 install mkdocs mkdocs-material mkdocs-git-revision-date-localized-plugin
```

### Arch Linux
```bash
# Install Python dan pip
sudo pacman -S python python-pip

# Install MkDocs dan dependencies
pip install mkdocs mkdocs-material mkdocs-git-revision-date-localized-plugin
```

## 🔧 Development

### Local Development

```bash
# Clone repository
git clone https://github.com/salman-mustapa/github-setup.git
cd github-setup

# Install dependencies
pip install -r requirements.txt

# Start development server
mkdocs serve

# Build untuk production
mkdocs build
```

### Deploy ke GitHub Pages

```bash
# Deploy otomatis ke gh-pages branch
mkdocs gh-deploy

# Atau manual build dan push
mkdocs build
# Upload folder site/ ke hosting
```

## 🤝 Kontribusi

Kontribusi sangat diterima! Berikut cara berkontribusi:

1. **Fork** repository ini
2. **Buat branch** untuk fitur baru: `git checkout -b feature/awesome-feature`
3. **Commit** perubahan: `git commit -m 'Add awesome feature'`
4. **Push** ke branch: `git push origin feature/awesome-feature`
5. **Buat Pull Request**

### Pedoman Kontribusi

- Pastikan dokumentasi menggunakan bahasa Indonesia yang baik dan benar
- Tambahkan contoh kode yang berfungsi
- Update daftar isi jika menambah halaman baru
- Test dokumentasi dengan `mkdocs serve` sebelum commit

## 📝 License

Dokumentasi ini dilisensikan di bawah [MIT License](LICENSE).

## 👨‍💻 Author

**Salman Mustapa**
- GitHub: [@salman-mustapa](https://github.com/salman-mustapa)
- Email: salmanmustapa@outlook.com

## 📞 Support

Jika Anda mengalami masalah atau memiliki pertanyaan:

1. Baca [FAQ](docs/faq.md)
2. Periksa [Troubleshooting](docs/troubleshooting.md)
3. Buat [Issue](https://github.com/salman-mustapa/github-setup/issues) di GitHub
4. Kirim email ke: salmanmustapa@outlook.com

## 🎯 Target Audience

Dokumentasi ini ditujukan untuk:

- **Pemula** yang baru mengenal Git dan GitHub
- **Developer** yang ingin setup environment baru
- **System Administrator** yang perlu konfigurasi Git di server
- **Students** yang belajar version control

## 📊 Status

- ✅ Dokumentasi dasar selesai
- ✅ Setup MkDocs dan tema Material
- ✅ Panduan instalasi Git
- ✅ Panduan setup Personal Access Token
- 🔄 SSH configuration (in progress)
- 🔄 Advanced Git operations (planned)
- 🔄 GitHub Actions integration (planned)

## 🙏 Acknowledgments

Terima kasih kepada:

- Tim [MkDocs](https://www.mkdocs.org/) untuk static site generator yang luar biasa
- Tim [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) untuk tema yang indah
- Komunitas open source yang telah berkontribusi pada ecosystem Git

---

⭐ **Jika dokumentasi ini membantu, jangan lupa beri star!** ⭐

[![GitHub stars](https://img.shields.io/github/stars/salman-mustapa/github-setup.svg?style=social&label=Star)](https://github.com/salman-mustapa/github-setup)
