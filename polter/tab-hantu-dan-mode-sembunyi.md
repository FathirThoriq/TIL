# Tab hantu Polter: mode sembunyi itu menghapus, bukan menyamarkan

*2026-10-13 · polter*

Di Polter v0.8.6–v0.8.8 kutambah kontrol "tab hantu" — tab tipis di tepi layar yang membuka panel ekstensi. Pelajaran desainnya:

- Ada dua mode yang beda niat: **transparan** (masih ada, cuma samar) vs **sembunyi total** (elemennya dihapus dari halaman). Buatku yang kedua yang benar: tab tepi, pil seleksi teks, dan semua tombol mengambang hilang sama sekali, bukan disamarkan.
- Satu preferensi harus dibaca di semua tempat: panel dan halaman Pengaturan mengontrol kunci penyimpanan yang sama, disinkronkan lewat `storage.onChanged` dan disiarkan ke semua tab — jadi mengubah di satu tempat langsung berlaku di mana-mana tanpa reload.
- Shortcut juga penting diganti kalau bertabrakan dengan browser: menu kupindah ke **Alt+Shift+M** karena Alt+Shift+P membuat grup tab baru di browserku.

Prinsip yang kubawa: UI yang "hampir tidak terlihat" tetaplah UI yang terlihat. Kalau tujuannya hilang, hapus.
