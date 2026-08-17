# 2026-08-17 — Pivot ke Kelapa & Integrasi Info Lomba Resmi

## Ringkasan Kerja

User menjawab seluruh pertanyaan di `qna.md` langsung di file, memicu update besar ke hampir semua dokumen proyek:

1. **Pivot komoditas: kelapa sawit → kelapa.** Jawaban "jadinya kelapa" untuk pertanyaan akses lahan berarti lokasi uji coba nyata adalah kebun kelapa, bukan sawit. Dicek: BPDP (Badan Pengelola Dana Perkebunan) ternyata mencakup 3 komoditas — sawit, kakao, kelapa (Perpres 132/2024) — jadi pivot ini tetap 100% eligible untuk pendanaan.
2. **2 dokumen resmi lomba baru muncul di `reference/`** (ditambahkan user): `PENG-4 BPDP 2026 Call for Proposal Lomba Riset Mahasiswa.pdf` dan `Panduan Teknis Proposal Lomba Riset 2026-2027-aw.pdf`. Dibaca lengkap, diekstrak: nama lomba, deadline (31 Oktober 2026, pengumuman awal sebut 30 Oktober — ada selisih, disarankan submit 30 Okt untuk aman), dana maks Rp20 juta/proposal (2 tahap), syarat tim 3-5 orang + 1 dosen pembimbing, format proposal (20 halaman, Arial 12, 1.5 spasi, sistematika 6 bab + lampiran), kriteria penilaian (4 komponen, bobot 20/30/30/20%), dan daftar lengkap bidang+topik riset prioritas per komoditas.
3. **Riset ulang literatur biologi/agronomi khusus kelapa** (bukan lagi kelapa sawit) — ditemukan review tandingan oleh penulis yang sama (Carr, 2011) khusus untuk *Cocos nucifera*: root distribution (kepadatan akar 0-1.0m, lateral 1.0-1.5m dari batang, puncak penyerapan air di 50-100cm dari batang), ETc ~3mm/hari, Kc≈0.7, rekomendasi volume irigasi ~2mm/hari (100 L/pohon/hari) mingguan yang terbukti naikkan hasil 20-40 butir/pohon/tahun (studi Kerala). Jawaban qna.md poin 1-2 ditulis ulang total dari data oil-palm ke data coconut yang benar.
4. **Riset harga pasar Indonesia (Tokopedia)** untuk komponen MVP — ditemukan 2 risiko anggaran signifikan: tensiometer (~Rp2 juta/unit, jauh dari asumsi awal) dan gateway LoRaWAN penuh (~Rp1.5-4 juta) berpotensi menghabiskan porsi besar dari plafon Rp20 juta. Ditambahkan rekomendasi mitigasi (LoRa point-to-point/ESP32+WiFi untuk MVP, batasi jumlah unit tensiometer).
5. **Rekomendasi baru** untuk plot kontrol (Q6): pakai plot kelapa berdekatan dengan perlakuan business-as-usual sebagai pembanding, bukan direkayasa.

## File yang Diupdate

`qna.md` (rewrite besar poin 1-12 + tambahan poin 13-15), `ide.md` (motivasi "kenapa kelapa" ditulis ulang), `phase.md` (info resmi lomba lengkap + fase 2b baru untuk legalitas/administrasi), `prototype.md` (plot kontrol, risiko anggaran, mode operasi), `schema_alat.md` (tabel harga Indonesia baru — bagian D), `architecture.md`, `flow.md`, `early-prompt.md`, `CLAUDE.md`, `README.md` (bersihkan terminologi sawit→kelapa & sinkronkan status).

## Keputusan

- Komoditas final: **kelapa**, bukan kelapa sawit.
- Deadline kerja: submit proposal sebelum **30 Oktober 2026** (ambil tanggal lebih ketat dari 2 dokumen resmi yang berbeda).
- MVP hardware harus super efisien anggaran mengingat plafon total Rp20 juta mencakup seluruh riset, bukan cuma hardware.
- Mode operasi prototype: semi-otomatis (sesuai instruksi user "sesuai rekomendasi").

## Next Steps (Item Terbuka)

- Tim menentukan **dosen pembimbing** (syarat wajib lomba, belum ada).
- Tim melengkapi **detail lahan kelapa**: pemilik, luas, umur tanaman, jenis tanah.
- Tim/dosen pembimbing memutuskan **bidang riset final** antara 2 opsi yang direkomendasikan di `phase.md`.
- Unduh & simpan paper Carr (2011) versi kelapa ke `reference/` jika akan dikutip formal di proposal.
- Verifikasi ulang harga komponen sebelum menyusun RAB final (Lampiran 7) — harga Tokopedia di `schema_alat.md` adalah estimasi Agustus 2026, bisa berubah.
