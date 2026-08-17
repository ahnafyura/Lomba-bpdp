# 2026-08-17 — README dan Rekomendasi Ilmiah untuk QnA

## Ringkasan Kerja

- Membuat `README.md` di root proyek sebagai halaman utama: peta seluruh dokumen, cara mulai untuk kontributor/sesi Claude baru, dan status proyek saat ini.
- Mengisi rekomendasi jawaban berbasis literatur ilmiah untuk 3 pertanyaan biologi/agronomi di `qna.md` (poin 1–3), karena 5 paper awal di `reference/` tidak spesifik membahas kelapa sawit (Elaeis guineensis) — dilakukan pencarian literatur tambahan yang spesifik ke kelapa sawit.
- Sumber baru yang ditemukan & dikutip:
  - Carr (2011), *Experimental Agriculture* 47(4):629–652 — review komprehensif water relations & irrigation requirements kelapa sawit (sumber utama kedalaman akar & status "belum ada konsensus threshold kPa baku").
  - Agronomy 2024, 14(9), DOI 10.3390/agronomy14091976 — studi lapangan Kolombia dengan metodologi FC/RAW/PWP + uji volume air aktual (L/hari).
  - 3 sumber pendukung (PMC, ScienceDirect, Springer Tropical Plant Biology) untuk temuan delayed-effect stres air terhadap sex ratio/hasil panen (jeda 35–40 bulan).

## Keputusan

- Kedalaman sensor direkomendasikan: **~20 cm dan ~60 cm** (mayoritas akar aktif ada di 0–0.6 m menurut Carr 2011).
- **Tidak ada angka soil water tension (kPa) baku untuk kelapa sawit** di literatur — direkomendasikan pakai pendekatan **FC/RAW/PWP terkalibrasi lokal**, trigger irigasi di sekitar 50% depletion RAW, bukan angka kPa generik dari tanaman lain.
- MVP tetap fokus ke air dulu, hara jadi roadmap lanjutan (alasan: kompleksitas & biaya kalibrasi sensor hara lebih tinggi, berdasarkan Mansoor et al. 2025 yang sudah ada di `reference/`).
- Semua jawaban ditandai `[DIJAWAB - REKOMENDASI AWAL]`, bukan `[DIJAWAB]` final — karena tetap perlu validasi lapangan/tim agronomi.

## Next Steps

- Tim mengonfirmasi/memvalidasi rekomendasi di atas, terutama sebelum dipakai sebagai angka final di proposal.
- Unduh & simpan paper-paper baru (Carr 2011, Agronomy 2024, dst.) ke folder `reference/` jika akan dikutip resmi.
- Pertanyaan #4–12 di `qna.md` (lokasi lahan, info lomba, harga pasar Indonesia, mode operasi) masih `[BELUM DIJAWAB]` — tidak bisa dijawab dari literatur, butuh input langsung dari Mas Levi/tim.
