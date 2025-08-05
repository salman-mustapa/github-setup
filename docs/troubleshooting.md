# Troubleshooting

Ini adalah panduan troubleshooting untuk masalah umum yang mungkin Anda hadapi saat mengonfigurasi Git dan GitHub.

## Masalah Umum dan Solusinya

### Tidak Dapat Terhubung ke GitHub
- **Cek Koneksi Internet:** Pastikan Anda terhubung ke jaringan yang stabil.
- **Periksa Firewall:** Beberapa firewall dapat memblokir koneksi ke GitHub.
- **Periksa Konfigurasi Proxy:** Jika Anda menggunakan proxy.

### Error Autentikasi
- **Periksa Username dan Password/Token:** Pastikan Anda memasukkan dengan benar.
- **Periksa Akses SSH:** Pastikan kunci SSH sudah ditambahkan ke GitHub.

### Gagal Push/Clone
- **Periksa Akses ke Repositori:** Pastikan Anda memiliki izin yang cukup.
- **Cek Remote URL:** Pastikan URL remote benar.

### Error: `Permission Denied`
- **Periksa Akses:** Pastikan Anda memiliki akses ke repo.
- **Periksa Kunci SSH:** Pastikan SSH key sudah benar.

## Tips Lainnya

- **Logs dan Output:** Selalu perhatikan pesan error yang diberikan.
- **Debug Mode:** Gunakan `GIT_TRACE=1` untuk men-debug lebih lanjut.
- **Gunakan Dokumentasi:** Banyak masalah dapat ditemukan solusinya di dokumentasi resmi Git dan GitHub.

---

⚠️ **Perhatian:** Jangan ragu untuk mencari bantuan online atau di komunitas GitHub jika masalah berlanjut!
