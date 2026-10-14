# Tiga titik bottleneck TEFA Bakery

*2026-10-11 · hackathon*

Dari wawancara timku dengan unit Bakery di UPA TEFA Polije (mitra hackathon PLAY IT! PLUS), produksi roti mereka punya pola yang jelas:

- Produksi rutin harian, tapi **Senin & Kamis adalah puncak: 70 kg bahan baku**, hari biasa hanya 20 kg. Tiga varian: manis, tawar, kering.
- Mixer terbesar (25 kg) khusus roti kering; oven rotary kapasitas 16 loyang perlu **3x istirahat** untuk menurunkan suhu, dan maintenance tiap 3 bulan.

Tiga titik rawan bottleneck-nya:

1. **Penimbangan/pengukuran** — kesalahan takaran dan kelelahan SDM mulai terasa dari batch ke-3.
2. **Setting suhu oven rotary** — penentu hasil akhir, sensitif terhadap jadwal istirahat oven.
3. **Sterilitas packaging & APD** — titik kontrol mutu terakhir sebelum produk keluar.

Pelajaran buat prototipe Smart ERP kami: bottleneck itu bergerak mengikuti ritme produksi (hari puncak vs biasa, batch awal vs batch ke-3), bukan titik tetap — deteksinya harus dinamis, bukan tabel statis.
