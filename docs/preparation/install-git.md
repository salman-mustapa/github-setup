# Install Git

Git adalah sistem version control yang diperlukan untuk berinteraksi dengan GitHub. Panduan ini akan menunjukkan cara menginstall Git di berbagai distribusi Linux.

## 🔍 Cek Instalasi Git

Sebelum menginstall, cek apakah Git sudah terinstall:

```bash
git --version
```

Jika Git sudah terinstall, Anda akan melihat output seperti:
```
git version 2.48.1
```

!!! success "Git Sudah Terinstall"
    Jika Git sudah terinstall, Anda bisa langsung ke [Membuat Akun GitHub](create-github-account.md)

## 📦 Instalasi Git

### Ubuntu/Debian

```bash
# Update package list
sudo apt update

# Install Git
sudo apt install git -y

# Verifikasi instalasi
git --version
```

### CentOS/RHEL/Fedora

=== "CentOS 7/RHEL 7"

    ```bash
    # Install Git
    sudo yum install git -y
    
    # Verifikasi instalasi
    git --version
    ```

=== "CentOS 8/RHEL 8/Fedora"

    ```bash
    # Install Git
    sudo dnf install git -y
    
    # Verifikasi instalasi
    git --version
    ```

### Arch Linux

```bash
# Install Git
sudo pacman -S git

# Verifikasi instalasi
git --version
```

### openSUSE

```bash
# Install Git
sudo zypper install git

# Verifikasi instalasi
git --version
```

## 🔧 Konfigurasi Awal (Opsional)

Setelah instalasi, Anda bisa melakukan konfigurasi dasar:

```bash
# Set default branch ke 'main' (recommended)
git config --global init.defaultBranch main

# Set default editor (opsional)
git config --global core.editor nano  # atau vim, code, dll

# Enable colored output
git config --global color.ui auto
```

## 📋 Verifikasi Instalasi

Pastikan Git terinstall dengan benar:

```bash
# Cek versi Git
git --version

# Cek konfigurasi Git
git config --list

# Cek lokasi executable Git
which git
```

Output yang diharapkan:
```bash
$ git --version
git version 2.48.1

$ which git
/usr/bin/git
```

## ❌ Troubleshooting

### Git Command Not Found

Jika mendapat error "command not found":

1. **Pastikan instalasi berhasil**:
   ```bash
   sudo apt install git -y  # Ubuntu/Debian
   ```

2. **Restart terminal atau reload PATH**:
   ```bash
   source ~/.bashrc
   ```

3. **Cek PATH**:
   ```bash
   echo $PATH
   ```

### Permission Denied

Jika mendapat error permission:

```bash
# Fix ownership (jika diperlukan)
sudo chown -R $USER:$USER ~/.gitconfig

# Set permission yang tepat
chmod 644 ~/.gitconfig
```

## ✅ Langkah Selanjutnya

Setelah Git berhasil terinstall, lanjutkan ke:

- [Membuat Akun GitHub](create-github-account.md)
- [Konfigurasi Dasar Git](../configuration/basic-git-config.md)

---

!!! tip "Tips Instalasi"
    - Selalu gunakan package manager resmi distribusi Anda
    - Update system sebelum menginstall Git
    - Verifikasi instalasi setelah selesai
