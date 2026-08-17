# Lomba BPDP — Sistem Irigasi Presisi IoT Kebun Kelapa

Proyek untuk **Lomba Riset Tingkat Mahasiswa BPDP (Badan Pengelola Dana Perkebunan) 2026–2027**: sistem IoT smart farming untuk **irigasi presisi kebun kelapa**, memanfaatkan sensor tanah (soil water tension, volumetric water content, soil moisture, dll) supaya irigasi dilakukan tepat waktu & tepat jumlah — bukan berdasarkan jadwal tetap — dengan benefit utama **hemat air**.

Kelapa dipilih sebagai fokus komoditas karena tim punya akses lahan uji coba nyata di kebun kelapa (rencana awal sempat mengarah ke kelapa sawit — lihat penjelasan di [`ide.md`](./ide.md)). BPDP sendiri mencakup 3 komoditas (sawit, kakao, kelapa) sehingga fokus ini tetap eligible untuk pendanaan.

## Peta Dokumen

| Dokumen | Isi |
|---|---|
| [`ide.md`](./ide.md) | Latar belakang masalah, motivasi pemilihan kelapa, ide inti, benefit, dan gap pengetahuan yang perlu masukan tim |
| [`architecture.md`](./architecture.md) | Arsitektur sistem 6 layer: sensor → akuisisi (Arduino) → agregasi/komunikasi (Raspberry Pi + LoRaWAN) → cloud → dashboard → aktuasi irigasi |
| [`flow.md`](./flow.md) | Alur data & keputusan irigasi end-to-end, termasuk feedback loop dan mode operasi |
| [`schema_alat.md`](./schema_alat.md) | Spesifikasi & sumber tiap sensor/alat, dipecah jadi MVP prototype vs pengembangan lanjut |
| [`prototype.md`](./prototype.md) | Rencana pembuktian konsep skala kecil: kebutuhan alat, metrik keberhasilan, rencana demo |
| [`rab.md`](./rab.md) | Draft Rincian Anggaran Biaya (RAB) — mengikuti format resmi Bab VI & Lampiran 7 BPDP, total Rp20 juta |
| [`proposal_bab1-5.md`](./proposal_bab1-5.md) | Draft narasi Bab I–V proposal (Pendahuluan, Studi Pustaka, Metode Riset, Luaran, Jadwal Kegiatan), siap dipoles ke format resmi Arial 12/1½ spasi/A4 |
| [`phase.md`](./phase.md) | Fase proyek dari riset sampai submission lomba |
| [`qna.md`](./qna.md) | Pertanyaan terbuka (biologi/agronomi, lokasi, info lomba, teknis) — sebagian sudah diisi rekomendasi awal berbasis literatur ilmiah |
| [`early-prompt.md`](./early-prompt.md) | Urutan baca dokumen untuk memulai sesi Claude Code baru secara sistematis |
| [`reference/`](./reference/) | Paper & gambar sumber ide (precision agriculture, IoT, irigasi presisi, adaptasi iklim kebun) |
| [`log-claude/`](./log-claude/) | Log kerja harian, format `[tanggal]-[topic].md` |

## Cara Mulai (untuk Kontributor Baru / Sesi Claude Baru)

1. Baca [`early-prompt.md`](./early-prompt.md) — urutan baca dokumen yang direkomendasikan.
2. Cek [`qna.md`](./qna.md) untuk pertanyaan yang masih `[BELUM DIJAWAB]`.
3. Cek log terbaru di [`log-claude/`](./log-claude/) untuk tahu progres terakhir.
4. Setiap sesi kerja wajib menghasilkan log baru (`log-claude/[tanggal]-[topic].md`) — gunakan skill `/log-harian`.

## Status Saat Ini

- Struktur dokumentasi awal: **selesai**.
- Komoditas proyek: **kelapa** (bukan kelapa sawit seperti rencana awal) — lokasi uji coba sudah tersedia, lihat [`ide.md`](./ide.md).
- Info resmi lomba (nama, deadline 31 Oktober 2026, format, dana maks Rp20 juta): **sudah terisi lengkap** di [`phase.md`](./phase.md), bersumber dari 2 dokumen resmi BPDP di `reference/`.
- Pertanyaan biologi/agronomi kunci (kedalaman akar, threshold irigasi, angka ETc/volume irigasi acuan): **terjawab dengan rekomendasi berbasis literatur kelapa** (Carr 2011 — review khusus *Cocos nucifera* — dan studi pendukung lain) di [`qna.md`](./qna.md).
- Harga pasar Indonesia untuk komponen sensor: **sudah diriset** (Tokopedia) di [`schema_alat.md`](./schema_alat.md) — ditemukan 2 risiko anggaran (tensiometer & gateway LoRaWAN penuh cukup mahal terhadap plafon Rp20 juta), sudah ada mitigasi di [`prototype.md`](./prototype.md).
- Bidang riset & judul riset: **sudah diputuskan** — "Lahan, Tanah & Budidaya" (topik GAP kebun kelapa rakyat), judul "Sistem Irigasi Presisi Berbasis IoT untuk Efisiensi Penggunaan Air pada Perkebunan Kelapa Rakyat".
- Draft narasi Bab I–V proposal: **selesai** di [`proposal_bab1-5.md`](./proposal_bab1-5.md), Bab VI (Pendanaan) di [`rab.md`](./rab.md).
- **Masih terbuka**: dosen pembimbing (wajib syarat lomba) dan detail lahan kelapa (pemilik/luas/umur tanaman) — ditandai `[TODO]` langsung di `proposal_bab1-5.md` dan tercatat di item 13 & 15 [`qna.md`](./qna.md).

Detail lengkap tiap keputusan ada di [`log-claude/`](./log-claude/).
