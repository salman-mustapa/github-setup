# Setup SSH untuk GitHub (Opsional)

SSH adalah alternatif untuk Personal Access Token. Lebih cepat untuk operasi berulang karena tidak perlu input password.

## 🔑 Setup SSH dalam 3 Langkah

### 1. Buat SSH Key

```bash
# Buat SSH key baru
ssh-keygen -t ed25519 -C "email@anda.com"

# Tekan Enter untuk semua pertanyaan (gunakan default)
```

### 2. Copy Public Key

```bash
# Tampilkan dan copy public key
cat ~/.ssh/id_ed25519.pub
```

### 3. Tambahkan ke GitHub

1. Buka GitHub → Settings → SSH and GPG keys
2. Klik **New SSH key**
3. Paste public key yang sudah dicopy
4. Klik **Add SSH key**

## 🧪 Test SSH

```bash
# Test koneksi SSH
ssh -T git@github.com
```

Output yang diharapkan:
```
Hi username! You've successfully authenticated, but GitHub does not provide shell access.
```

## 🚀 Menggunakan SSH

```bash
# Clone dengan SSH
git clone git@github.com:username/repository.git

# Atau ubah remote yang sudah ada
git remote set-url origin git@github.com:username/repository.git
```

---

❌ **Troubleshooting SSH**:
- Jika error "Permission denied": Pastikan public key sudah ditambahkan ke GitHub
- Jika error "Host key verification failed": Jalankan `ssh-keyscan github.com >> ~/.ssh/known_hosts`
