# Early Prompt — Mulai dari Sini

Dokumen ini adalah titik awal untuk setiap sesi Claude Code baru di proyek ini, supaya kerja tetap sistematis dan tidak mengulang konteks yang sudah ada.

## Urutan Baca di Awal Sesi

1. **`ide.md`** — pahami dulu problem statement, motivasi (kenapa kelapa, bukan kelapa sawit), ide inti, dan benefit utama proyek.
2. **`architecture.md`** — pahami arsitektur sistem (sensor → edge → komunikasi → cloud → dashboard → aktuasi).
3. **`flow.md`** — pahami alur data & keputusan end-to-end.
4. **`schema_alat.md`** — pahami spesifikasi & klasifikasi alat (MVP vs pengembangan lanjut).
4b. **`rab.md`** — draft anggaran (RAB), format resmi Bab VI/Lampiran 7 BPDP, total Rp20 juta.
4c. **`proposal_bab1-5.md`** — draft narasi Bab I–V proposal resmi (judul, latar belakang, studi pustaka, metode, luaran, jadwal).
5. **`phase.md`** — cek fase proyek saat ini sedang di mana.
6. **`qna.md`** — cek pertanyaan terbuka yang masih `[BELUM DIJAWAB]`, terutama sebelum mengambil keputusan teknis yang bergantung pada jawaban tersebut (mis. threshold agronomi, lokasi uji coba).
7. **`log-claude/`** — baca log dengan tanggal paling baru untuk tahu progres & keputusan terakhir sebelum melanjutkan kerja.

## Aturan Kerja

- **Setiap sesi kerja wajib menghasilkan/mengupdate log** di `log-claude/[YYYY-MM-DD]-[topic].md`. Gunakan skill `/log-harian` untuk membuat log baru dengan format yang konsisten.
- Jika menemukan keputusan/asumsi baru yang penting, update dokumen terkait (`ide.md`, `architecture.md`, dst.) — jangan biarkan keputusan hanya ada di chat history.
- Jika muncul pertanyaan yang butuh jawaban dari Mas Levi/tim (bukan sesuatu yang bisa diasumsikan wajar), tambahkan ke `qna.md` alih-alih menebak.
- Dokumentasi ditulis dalam **Bahasa Indonesia** (istilah teknis boleh tetap Inggris, mis. "soil water tension", "threshold").

## Referensi Sumber

Semua paper & gambar sumber ide ada di folder `reference/` — dirujuk dari `schema_alat.md` dan `architecture.md`.
