# FAQ

Berikut adalah beberapa pertanyaan yang sering ditanyakan mengenai konfigurasi Git dan GitHub.

## Apakah saya harus menggunakan SSH atau Personal Access Token?

- **SSH** direkomendasikan jika Anda sering melakukan operasi berulang seperti `push` dan `pull`.
- **Personal Access Token** lebih aman dan direkomendasikan terutama untuk operasi yang membutuhkan otentikasi lebih ketat.

## Bagaimana jika saya lupa password GitHub?

- Pergi ke halaman login GitHub dan klik "Forgot password?" untuk mereset password Anda.

## Apa yang harus saya lakukan jika mengalami error `Permission Denied`?

- Periksa kembali user dan repository permissions, dan pastikan SSH key Anda sudah ditambahkan ke GitHub.

## Bisakah saya menggunakan Git di lebih dari satu komputer?

- Ya, Anda hanya perlu mengkonfigurasi Git dan membuat SSH key untuk setiap komputer.

## Apakah perubahan yang saya buat lokal secara otomatis tersinkronisasi ke GitHub?

- Tidak, Anda perlu melakukan `git push` untuk mengirim perubahan ke GitHub.

---

Jika ada pertanyaan lain, jangan ragu untuk mencari jawaban di [GitHub Docs](https://docs.github.com) atau tanya di komunitas GitHub.
