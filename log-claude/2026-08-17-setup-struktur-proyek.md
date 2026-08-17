# 2026-08-17 — Setup Struktur Proyek

## Ringkasan Kerja

Membuat struktur dokumentasi awal proyek berdasarkan VN Mas Levi dan referensi (5 paper + beberapa gambar tabel sensor) yang sudah diletakkan di folder `reference/`:

- `ide.md` — problem statement, motivasi pemilihan kelapa sawit, ide inti, benefit, dan open gaps biologi/agronomi.
- `architecture.md` — arsitektur sistem 6 layer (sensor → akuisisi Arduino → agregasi/komunikasi Raspberry Pi+LoRaWAN → cloud → dashboard → aktuasi).
- `flow.md` — alur data & keputusan irigasi end-to-end, termasuk feedback loop dan mode operasi (rekomendasi vs otomatis).
- `schema_alat.md` — tabel spesifikasi sensor gabungan dari 2 paper referensi, dipecah jadi MVP prototype vs pengembangan lanjut.
- `prototype.md` — rencana pembuktian konsep skala kecil, metrik keberhasilan, rencana demo.
- `phase.md` — kerangka 5 fase proyek (riset → desain → prototype → uji lapangan → submission), tanggal lomba masih TODO.
- `qna.md` — 12 pertanyaan terbuka (biologi/agronomi, lokasi prototype, info lomba, teknis) untuk dijawab Mas Levi/tim.
- `early-prompt.md` — urutan onboarding untuk sesi Claude baru.
- `CLAUDE.md` — instruksi proyek yang auto-load, mewajibkan baca `early-prompt.md` dan log harian.
- `.claude/skills/log-harian/SKILL.md` — skill `/log-harian` untuk membuat log baru ke depannya.

## Keputusan

- Konten dokumen ditulis sebagai draft substantif (bukan skeleton kosong), berdasarkan isi referensi yang sudah ada.
- Skill disimpan di lokasi standar `.claude/skills/` supaya benar-benar bisa di-invoke sebagai slash command.
- Bahasa dokumentasi: Bahasa Indonesia, istilah teknis tetap Inggris.
- Info lomba (nama, deadline, format) belum ada — ditandai TODO di `phase.md` dan `qna.md`.

## Next Steps

- Mas Levi/tim mengisi jawaban di `qna.md`, terutama soal biologi/agronomi kelapa sawit dan akses lahan uji coba.
- Setelah info lomba (nama/deadline/format) tersedia, update `phase.md`.
- Mulai riset komponen aktuasi (solenoid valve/pompa) dan harga pasar Indonesia untuk sensor di `schema_alat.md`.
