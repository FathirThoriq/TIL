# Merilis Lyre v0.1.7: pemutar musik TUI mode tamu total

*2026-10-16 · lyre*

Hari ini Lyre — pemutar musik TUI untuk Spotify + YouTube Music yang kubangun dengan Rust + Ratatui — kurilis ke github.com/FathirThoriq/Lyre. Pelajaran terbesarnya bukan soal UI, tapi soal asumsi yang salah:

- **Playback ternyata tidak pernah butuh akun.** Dulu Lyre punya login Spotify dan YouTube Music. Setelah ditelusuri, audio lagu Spotify selalu dicocokkan ke YouTube (pola Spotube) dan audio YT Music diambil via yt-dlp — dua-duanya jalan tanpa login. Login hanya memberi library personal. Jadi semua login kuhapus: Lyre jadi mode tamu total, dan fitur yang hilang diganti playlist dari link share + halaman tren.
- **Bug antrean tidak lanjut otomatis:** mpv yang di-spawn tanpa `--idle` keluar di milidetik yang sama dengan `end-file`, dan nilai akhir `eof-reached` adalah `null` (bukan `true`) — flag-nya kalah balapan lawan putusnya koneksi IPC. Pelajaran: untuk event "lagu habis", dengarkan prosesnya, bukan cuma propertinya.
- **Token anonim Spotify kena HTTP 429.** Endpoint tamu punya kuota ketat dan pola panggilan aplikasiku sendiri boros (fetch tren tiap start + search 3 panggilan). Obatnya disiplin: hormati header `Retry-After`, simpan cooldown di disk supaya restart tidak menggedor ulang, search multi-type cukup 1 request, tren dilayani dari cache disk 6 jam.
- **Visualizer jangan digambar mentah.** Output raw cava yang langsung digambar terasa kaku; harus dihaluskan dua lapis (gravity/integral di cava + lerp dan peak caps di renderer), dan bar yang sedikit tapi lebar terlihat jauh lebih hidup.
- **Logo teks bisa tetap elegan:** wordmark Lyre akhirnya memakai karakter Mathematical Italic Unicode (𝐿𝑦𝑟𝑒) — teks biasa, bukan seni blok — dan tampil rapi selama font terminal punya glyph-nya.

Catatan jujurnya: API tamu Spotify dan Innertube itu jalur tidak resmi, bisa berubah kapan saja. Sikap Lyre kalau itu terjadi: gagal dengan alasan yang jelas di layar, tidak pernah mengarang data.
