# Setup Personal Access Token

Personal Access Token (PAT) adalah metode autentikasi yang direkomendasikan untuk mengakses GitHub dari terminal. Token ini lebih aman daripada password dan dapat dikustomisasi aksesnya.

## 🔐 Membuat Personal Access Token

### 1. Masuk ke GitHub Settings

1. Login ke [github.com](https://github.com)
2. Klik foto profil → **Settings**
3. Di sidebar kiri, scroll ke bawah dan klik **Developer settings**
4. Klik **Personal access tokens** → **Tokens (classic)**

### 2. Generate New Token

1. Klik **Generate new token** → **Generate new token (classic)**
2. Isi form berikut:

| Field | Value | Keterangan |
|-------|--------|------------|
| **Note** | `Terminal Access` | Nama untuk mengidentifikasi token |
| **Expiration** | `90 days` atau `No expiration` | Masa berlaku token |

### 3. Pilih Scopes (Permissions)

Centang permission berikut sesuai kebutuhan:

#### ✅ Wajib untuk Git Operations:
- `repo` - Full control of private repositories
- `workflow` - Update GitHub Action workflows

#### ✅ Opsional:
- `write:packages` - Upload packages to GitHub Package Registry
- `delete:packages` - Delete packages from GitHub Package Registry
- `notifications` - Access notifications
- `user` - Update user profile information
- `read:org` - Read org and team membership
- `gist` - Create gists

!!! warning "Penting"
    Minimal centang **`repo`** untuk bisa melakukan push/pull repository.

### 4. Generate Token

1. Klik **Generate token**
2. **PENTING**: Copy token yang muncul dan simpan dengan aman
3. Token hanya ditampilkan sekali - jika hilang harus buat yang baru

Contoh token:
```
ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## ⚙️ Konfigurasi Token di Terminal

### Metode 1: Git Credential Store (Recommended)

```bash
# Set credential helper untuk menyimpan token
git config --global credential.helper store

# Clone repository pertama kali (akan diminta username dan token)
git clone https://github.com/salman-mustapa/repository-name.git

# Saat diminta:
# Username: salman-mustapa
# Password: [paste token di sini]
```

Token akan tersimpan di `~/.git-credentials` dan tidak perlu diinput lagi.

### Metode 2: Environment Variable

```bash
# Set token sebagai environment variable
export GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

# Tambahkan ke ~/.bashrc agar permanen
echo 'export GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx' >> ~/.bashrc
source ~/.bashrc
```

### Metode 3: URL dengan Token

```bash
# Clone dengan token di URL
git clone https://salman-mustapa:ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx@github.com/salman-mustapa/repository-name.git

# Set remote dengan token
git remote set-url origin https://salman-mustapa:ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx@github.com/salman-mustapa/repository-name.git
```

!!! danger "Keamanan"
    Metode 3 tidak direkomendasikan karena token akan tersimpan dalam history command dan konfigurasi Git.

## 🧪 Test Autentikasi

### Test dengan API

```bash
# Test token dengan GitHub API
curl -H "Authorization: token $GITHUB_TOKEN" https://api.github.com/user
```

Output yang diharapkan:
```json
{
  "login": "salman-mustapa",
  "id": 224708415,
  "name": "Salman Mustapa",
  "email": "salmanmustapa@outlook.com"
}
```

### Test dengan Git Operations

```bash
# Test clone repository
git clone https://github.com/salman-mustapa/test-repo.git

# Test push (buat file test)
cd test-repo
echo "# Test" > test.md
git add test.md
git commit -m "Test commit"
git push origin main
```

## 🔄 Update dan Management Token

### Melihat Token yang Ada

Di GitHub → Settings → Developer settings → Personal access tokens

### Update Token

1. Klik token yang ada
2. Klik **Regenerate token**
3. Update expiration date jika perlu
4. Copy token baru dan update di terminal

### Revoke Token

Jika token tidak digunakan atau keamanan terganggu:

1. Di GitHub, klik token yang ingin dihapus
2. Klik **Delete**
3. Konfirmasi dengan klik **I understand, delete this token**

## 📋 Contoh Konfigurasi Lengkap

Berikut contoh setup lengkap dengan token:

```bash
# 1. Set identitas Git
git config --global user.name "Salman Mustapa"
git config --global user.email "salmanmustapa@outlook.com"

# 2. Set credential helper
git config --global credential.helper store

# 3. Set environment variable (opsional)
export GITHUB_TOKEN=ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

# 4. Test dengan clone repository
git clone https://github.com/salman-mustapa/my-project.git

# 5. Saat pertama kali push, input:
# Username: salman-mustapa
# Password: [paste token]
```

## ❌ Troubleshooting

### Token Tidak Valid

Error: `remote: Invalid username or password`

**Solusi**:
1. Pastikan token masih valid (belum expired)
2. Cek scope permissions - minimal harus ada `repo`
3. Pastikan username benar

### Token Expired

Error: `remote: Invalid username or password` setelah sekian waktu

**Solusi**:
1. Generate token baru di GitHub
2. Update token di terminal:
   ```bash
   # Hapus credentials lama
   git config --global --unset credential.helper
   rm ~/.git-credentials
   
   # Set ulang credential helper
   git config --global credential.helper store
   ```

### Permission Denied

Error: `remote: Permission to repo denied`

**Solusi**:
1. Pastikan Anda adalah owner/collaborator repository
2. Cek scope token - pastikan ada `repo` permission
3. Untuk organization repo, mungkin perlu `read:org` scope

## 🔒 Best Practices

1. **Gunakan expiration date** - Set masa berlaku token (3-6 bulan)
2. **Minimal permissions** - Hanya berikan scope yang diperlukan
3. **Simpan dengan aman** - Jangan commit token ke repository
4. **Revoke unused tokens** - Hapus token yang tidak digunakan
5. **Monitor activity** - Cek aktivitas token secara berkala

## ✅ Langkah Selanjutnya

Setelah token dikonfigurasi:

- [Test Koneksi](../testing/test-connection.md)
- [Operasi Git Dasar](../testing/basic-git-operations.md)

---

!!! success "Token Siap!"
    Personal Access Token Anda sudah dikonfigurasi! Sekarang Anda bisa melakukan semua operasi Git dengan aman.
