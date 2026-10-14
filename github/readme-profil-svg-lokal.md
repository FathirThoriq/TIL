# README profil GitHub: yang andal itu SVG lokal

*2026-10-13 · github*

Semalam menghabiskan waktu membuat README profil mirip referensi video, dan pelajaran terbesarnya soal sanitasi GitHub:

- GitHub membersihkan HTML di README: lebar tabel kuabaikan, gaya heading bawaan menimpa desain, dan layanan gambar eksternal bisa mati sewaktu-waktu (badge pihak ketiga tampil sebagai teks tautan biru di browserku; satu layanan grafik kontribusiku balas HTTP 402).
- Pola yang akhirnya persis seperti desain: semua panel kubuat sebagai **SVG lokal selebar penuh** di folder `assets/`, dirujuk dari README sebagai gambar. Teks, garis, foto — semua di dalam SVG-nya.
- Animasi tetap bisa: animasi SMIL di dalam SVG berjalan saat SVG dimuat sebagai `<img>` (bintang kompasku naik-turun dengan cara ini).
- Untuk judul animasi dua tema, elemen `<picture>` dengan `prefers-color-scheme` memisahkan varian gelap/terang.
- Badge juga lebih aman dibuat SVG sendiri: angkanya statis, tapi tidak pernah rusak.

Intinya: di README GitHub, anggap HTML itu tidak bisa dipercaya — gambar (SVG) yang membawa desainnya sendiri jauh lebih patuh.
