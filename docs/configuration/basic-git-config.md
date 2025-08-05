# Konfigurasi Dasar Git

Setelah Git terinstall dan akun GitHub siap, langkah selanjutnya adalah mengkonfigurasi Git dengan identitas Anda. Konfigurasi ini diperlukan untuk setiap commit yang Anda buat.

## 🆔 Konfigurasi Identitas

### Set Nama dan Email

Konfigurasi nama dan email yang akan digunakan untuk semua commit:

```bash
# Set nama lengkap
git config --global user.name "Salman Mustapa"

# Set email (gunakan email yang sama dengan GitHub)
git config --global user.email "salmanmustapa@outlook.com"
```

!!! important "Penting"
    Gunakan email yang sama dengan yang terdaftar di GitHub untuk memastikan commit terhubung dengan akun Anda.

### Verifikasi Konfigurasi

Cek apakah konfigurasi sudah benar:

```bash
# Lihat konfigurasi user
git config --global --list | grep -E "(user.name|user.email)"

# Atau lihat individual
git config --global user.name
git config --global user.email
```

Output yang diharapkan:
```
user.name=Salman Mustapa
user.email=salmanmustapa@outlook.com
```

## ⚙️ Konfigurasi Tambahan

### Default Branch

Set default branch ke `main` (standar modern):

```bash
git config --global init.defaultBranch main
```

### Editor Default

Set editor default untuk commit message:

```bash
# Untuk nano (mudah untuk pemula)
git config --global core.editor nano

# Untuk vim
git config --global core.editor vim

# Untuk VS Code (jika terinstall)
git config --global core.editor "code --wait"
```

### Colored Output

Enable warna untuk output Git yang lebih mudah dibaca:

```bash
git config --global color.ui auto
```

### Credential Helper

Untuk menyimpan kredensial dan menghindari input berulang:

```bash
git config --global credential.helper store
```

## 🔧 Konfigurasi Advanced (Opsional)

### Line Ending

Untuk konsistensi line ending (penting jika bekerja dengan tim):

```bash
# Linux/Mac
git config --global core.autocrlf input

# Windows (jika dual boot)
git config --global core.autocrlf true
```

### Push Default

Set behavior default untuk `git push`:

```bash
# Push hanya branch yang sedang aktif
git config --global push.default current
```

### Aliases

Buat shortcut untuk command yang sering digunakan:

```bash
# Shortcut untuk status
git config --global alias.st status

# Shortcut untuk commit
git config --global alias.ci commit

# Shortcut untuk branch
git config --global alias.br branch

# Shortcut untuk checkout
git config --global alias.co checkout

# Log yang lebih cantik
git config --global alias.lg "log --oneline --decorate --graph --all"
```

## 📋 Verifikasi Semua Konfigurasi

Lihat semua konfigurasi global:

```bash
git config --global --list
```

Atau lihat lokasi file konfigurasi:

```bash
# Lokasi file konfigurasi global
git config --global --list --show-origin

# Edit langsung file konfigurasi (jika diperlukan)
git config --global --edit
```

## 📂 Contoh File Konfigurasi

File konfigurasi Git (`.gitconfig`) akan terlihat seperti ini:

```ini
[user]
    name = Salman Mustapa
    email = salmanmustapa@outlook.com
[init]
    defaultBranch = main
[core]
    editor = nano
    autocrlf = input
[color]
    ui = auto
[credential]
    helper = store
[push]
    default = current
[alias]
    st = status
    ci = commit
    br = branch
    co = checkout
    lg = log --oneline --decorate --graph --all
```

## 🔍 Level Konfigurasi Git

Git memiliki 3 level konfigurasi:

| Level | Scope | Lokasi File | Command Flag |
|-------|-------|-------------|--------------|
| **System** | Semua user di system | `/etc/gitconfig` | `--system` |
| **Global** | User saat ini | `~/.gitconfig` | `--global` |
| **Local** | Repository spesifik | `.git/config` | `--local` |

!!! tip "Tips Konfigurasi"
    - Gunakan `--global` untuk konfigurasi umum
    - Gunakan `--local` untuk konfigurasi khusus per project
    - Local config akan override global config

## ❌ Troubleshooting

### Error: "Please tell me who you are"

Jika mendapat error saat commit:
```
*** Please tell me who you are.
Run
  git config --global user.email "you@example.com"
  git config --global user.name "Your Name"
```

**Solusi**: Set identitas seperti dijelaskan di atas.

### Konfigurasi Tidak Tersimpan

Jika konfigurasi tidak tersimpan:

```bash
# Cek permission file config
ls -la ~/.gitconfig

# Fix permission jika diperlukan
chmod 644 ~/.gitconfig
```

### Reset Konfigurasi

Untuk reset konfigurasi tertentu:

```bash
# Hapus konfigurasi spesifik
git config --global --unset user.name

# Reset semua konfigurasi global (hati-hati!)
rm ~/.gitconfig
```

## ✅ Langkah Selanjutnya

Setelah konfigurasi dasar selesai, lanjutkan ke:

- [Setup Personal Access Token](setup-pat.md) - **Direkomendasikan**
- [Konfigurasi SSH](setup-ssh.md) - Alternatif

---

!!! success "Konfigurasi Selesai"
    Identitas Git Anda sudah dikonfigurasi! Sekarang Anda siap untuk mengatur autentikasi ke GitHub.
