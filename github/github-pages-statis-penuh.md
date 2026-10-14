# GitHub Pages itu hosting statis penuh

*2026-10-14 · github*

Hari ini kupakai sendiri buat memasang website profilku di fathirthoriq.github.io, dan ternyata GitHub Pages bukan "HTML doang":

- Semua yang statis jalan: JavaScript, animasi CSS, canvas, bahkan WebGL. Websiteku sendiri pakai perjalanan scroll 5 tahap + canvas, dan semuanya jalan dari satu file `index.html`.
- Batasnya cuma satu: tidak ada backend. Tidak ada database, tidak ada login, tidak ada kode server. Kalau butuh API, panggil layanan luar dari browser.
- Setelah push, yang tayang bisa masih versi lama beberapa menit karena cache CDN (di kasusku `Cache-Control: max-age=600`, jadi ±10 menit). Jangan panik dulu — cek pakai cache-buster sebelum menyimpulkan push gagal.
- Repo khususnya bernama `<username>.github.io` dan isinya dilayani dari branch utama.

Kesimpulan: buat portofolio dan landing page, Pages sudah lebih dari cukup — gratis pula.
