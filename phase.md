# Fase Proyek

## Info Resmi Lomba

- **Nama:** Lomba Riset Tingkat Mahasiswa — Badan Pengelola Dana Perkebunan (BPDP) Tahun 2026–2027 (Pengumuman No. PENG-4/BPDP/2026).
- **Sumber:** `reference/PENG-4 BPDP 2026 Call for Proposal Lomba Riset Mahasiswa.pdf` dan `reference/Panduan Teknis Proposal Lomba Riset 2026-2027-aw.pdf`.
- **Komoditas proyek ini:** Kelapa (lihat perubahan di [[ide]]).
- **Bidang riset yang direkomendasikan:** *Pengolahan Limbah & Lingkungan* → Kelapa → topik "Pengembangan sistem monitoring lingkungan dan lanskap kelapa berbasis spasial dan data presisi" (cocok langsung dengan sistem sensor IoT presisi kita). Alternatif: *Lahan, Tanah & Budidaya* → Kelapa → "Penerapan GAP (Good Agricultural Practices) dalam pengelolaan perkebunan kelapa rakyat" (irigasi presisi sebagai bagian dari praktik GAP). **Perlu keputusan final tim** — lihat [[qna]].
- **Pendaftaran:** paling lambat **31 Oktober 2026**, via https://lombariset.bpdp.or.id/.
- **Pendanaan:** maksimum **Rp20.000.000 per proposal**, dicairkan 2 tahap (setelah proposal dilengkapi + setelah monitoring & evaluasi I). Ini adalah dana riset total (bukan cuma hardware) — termasuk kemungkinan biaya lain (ATK, transportasi, dsb, dirinci di Lampiran 7 Panduan Teknis).
- **Hadiah tambahan bagi 3 besar:** Juara I Rp50 juta, II Rp35 juta, III Rp25 juta (uang saku, belum termasuk pajak) — penentuan lewat presentasi ke Tim Penilai.
- **Syarat tim:** kelompok 3–5 mahasiswa aktif (S1/Vokasi, tidak terancam DO) + **1 dosen pembimbing**. Tim saat ini beranggotakan 5 orang (teknik sipil, teknik komputer, 2 teknik mesin, biologi murni) — **dosen pembimbing belum ditentukan**, lihat [[qna]].
- **Format proposal:** maksimum 20 halaman (di luar sampul/pengesahan/daftar isi/lampiran), font Arial 12, spasi 1½ (abstrak 1 spasi), kertas A4. Sistematika: Halaman Sampul → Halaman Pengesahan → Abstrak (maks 1 halaman) → Bab 1 Pendahuluan → Bab 2 Studi Pustaka → Bab 3 Metode Riset → Bab 4 Luaran Riset → Bab 5 Jadwal Kegiatan → Bab 6 Biaya & Jadwal Penelitian → Daftar Pustaka → Lampiran (biodata ketua & anggota, rincian kebutuhan dana, surat pernyataan ketua, surat keterangan mahasiswa aktif, dokumen pendukung lain).
- **Kriteria penilaian proposal:** Analisis Kesenjangan 20%, Kegiatan Riset (kreativitas/inovasi, ruang lingkup, literature review, metodologi) 30%, Kebermanfaatan (produktivitas/efisiensi/produk-pasar baru/sustainability) 30%, Prospek Pengembangan 20%.
- **Catatan penting:** riset harus **baru** (belum berjalan/belum dibiayai pihak lain), dan **HKI hasil riset sepenuhnya menjadi milik BPDP**.

## Ringkasan Fase

| Fase | Status | Output Utama | Target Waktu |
|---|---|---|---|
| 1. Riset & Studi Literatur | Berjalan | Rangkuman referensi (`reference/`), [[ide]], [[schema_alat]] | — |
| 2. Desain Sistem | Draft awal selesai | [[architecture]], [[flow]] | — |
| 2b. Legalitas & Administrasi | Belum mulai | Dosen pembimbing, surat keterangan mahasiswa aktif, lembar pengesahan proposal dari kampus | Sebelum penyusunan proposal final |
| 3. Pembuatan Prototype | Belum mulai | Hardware MVP terpasang & berfungsi (lihat [[prototype]]) | — |
| 4. Uji Lapangan | Belum mulai | Data hasil uji coba, perbandingan penghematan air | — |
| 5. Penyusunan Proposal & Submission | Belum mulai | Proposal final sesuai sistematika BPDP, submit ke lombariset.bpdp.or.id | **Paling lambat 31 Oktober 2026** |

## Detail Fase

### Fase 1 — Riset & Studi Literatur
- Kumpulkan & rangkum paper/referensi terkait smart farming, IoT precision agriculture, irigasi presisi (sudah ada 5 sumber di `reference/`).
- Rumuskan ide inti & motivasi ([[ide]]).
- Petakan sensor & spesifikasinya ([[schema_alat]]).
- **Open item**: lengkapi detail lahan uji coba (pemilik, luas, umur tanaman) dan dosen pembimbing (lihat [[qna]]).

### Fase 2 — Desain Sistem
- Rancang arsitektur end-to-end ([[architecture]]).
- Rancang alur data & keputusan irigasi ([[flow]]).
- Tentukan mode operasi (rekomendasi vs otomatis).

### Fase 3 — Pembuatan Prototype
- Rakit hardware MVP sesuai [[schema_alat]] bagian "MVP Prototype".
- Setup firmware Arduino, gateway Raspberry Pi, koneksi LoRaWAN.
- Setup backend penyimpanan data + dashboard sederhana.
- Setup aktuator (solenoid valve/pompa) untuk uji coba kontrol otomatis.

### Fase 4 — Uji Lapangan
- Pasang di lokasi uji coba (lihat [[prototype]] — lokasi masih TODO).
- Kumpulkan data minimal selama periode yang disepakati.
- Bandingkan plot sensor vs plot kontrol (metrik di [[prototype]]).

### Fase 5 — Penyusunan Proposal & Submission
- Susun proposal sesuai sistematika resmi BPDP (lihat "Info Resmi Lomba" di atas): maks 20 halaman, Arial 12, 1½ spasi.
- Bab VI Pendanaan & Lampiran 3 (Rincian Kebutuhan Dana Riset): pakai draft [[rab]] sebagai basis, sesuaikan setelah lokasi/luas lahan final dikonfirmasi.
- Lengkapi seluruh lampiran wajib: biodata ketua & anggota, rincian kebutuhan dana riset, surat pernyataan ketua peneliti, surat keterangan mahasiswa aktif, lembar pengesahan dari kampus (butuh tanda tangan dosen pembimbing/pejabat kampus — pastikan Fase 2b selesai lebih dulu).
- Siapkan materi demo (lihat rencana demo di [[prototype]]).
- Review akhir bersama tim & dosen pembimbing sebelum submit ke https://lombariset.bpdp.or.id/, **paling lambat 31 Oktober 2026**.

## Terkait

- Log kerja harian per fase ada di folder `log-claude/`, format `[tanggal]-[topic].md`.
- Pertanyaan yang perlu dijawab sebelum lanjut fase berikutnya: [[qna]]
