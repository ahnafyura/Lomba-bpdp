# Q&A — Pertanyaan Terbuka

Daftar pertanyaan yang perlu dijawab oleh Mas Levi/tim, baik langsung tulis jawaban di file ini maupun lewat live chat CLI. Ditandai `[BELUM DIJAWAB]` / `[DIJAWAB]`.

## Biologi & Agronomi Kelapa

> **Update:** jawaban di bawah awalnya disusun dari literatur **kelapa sawit** (karena rencana awal proyek), lalu **direvisi ke literatur kelapa (*Cocos nucifera*) yang benar-benar spesies target** setelah lokasi uji coba dikonfirmasi kebun kelapa ([[qna]] poin 5, [[ide]]). Untungnya ada review komprehensif oleh penulis yang sama (Carr) untuk kedua komoditas, jadi kualitas sumber tetap setara.

1. `[DIJAWAB - REKOMENDASI AWAL]` **Pada kedalaman berapa akar aktif kelapa menyerap air?**

   **Rekomendasi:** pasang sensor di **dua kedalaman utama: ~20 cm dan ~80–100 cm**, dan **posisikan secara lateral ~50–100 cm dari batang** (bukan tepat di pangkal batang) — karena:
   - Kepadatan akar kelapa paling tinggi di **0–1.0 m** kedalaman tanah dan **1.0–1.5 m** lateral dari batang, meski akar bisa menembus >2 m dalam dan >3 m lateral (Carr, 2011, *Experimental Agriculture* 47(1):27–51 — review water relations & irrigation requirements kelapa).
   - Studi lapangan lain (Sri Lanka/India) menemukan **75–80% akar kelapa terkonsentrasi di kedalaman 20–100 cm**, dan **penyerapan air tertinggi justru terjadi pada akar yang berjarak 50–100 cm dari batang** (bukan yang paling dekat batang) — jadi penempatan sensor persis di pangkal pohon berisiko tidak mewakili kondisi air yang paling relevan untuk keputusan irigasi.

   *Status: rekomendasi berbasis literatur global untuk kelapa — tetap perlu divalidasi terhadap kondisi tanah & varietas di lokasi uji coba tim.*

2. `[DIJAWAB - REKOMENDASI AWAL]` **Berapa ambang batas (threshold) soil water tension / volumetric water content yang ideal untuk kelapa, dan apakah berbeda antar fase pertumbuhan?**

   **Temuan penting:** sama seperti pada kelapa sawit, **literatur kelapa juga belum punya angka kPa/threshold baku yang disepakati** untuk memicu irigasi — Carr (2011) tidak memberi angka kPa tunggal, hanya rekomendasi volume/interval (lihat di bawah). Jadi jangan pakai satu angka kPa generik dari tanaman lain (mis. tabel di [[schema_alat]]) sebagai ambang batas final untuk kelapa.

   **Rekomendasi pendekatan & angka acuan konkret dari literatur kelapa:**
   - **Kebutuhan air acuan (ETc):** kelapa dewasa punya ETc representatif **~3 mm/hari** (kisaran 2.5–3.3 mm/hari tergantung musim) dengan **crop coefficient (Kc) ≈ 0.7** (kisaran 0.54–0.70) (Carr, 2011).
   - **Volume & interval irigasi efektif (acuan langsung untuk [[prototype]]):** aplikasi irigasi **~2 mm/hari (setara ±100 liter/pohon/hari)**, diberikan dengan interval **hingga 1 minggu sekali**, terbukti efektif meningkatkan produksi bunga betina & mengurangi kerontokan buah muda — studi di Kerala mencatat **kenaikan hasil 20–40 butir kelapa/pohon/tahun** dari penerapan irigasi ini.
   - Gunakan metodologi **Field Capacity (FC) – Readily Available Water (RAW) – Permanent Wilting Point (PWP)** yang diukur langsung di tanah lokasi uji coba untuk menentukan kapan tepatnya trigger irigasi (irigasi dipicu saat air tanah turun sekitar **~35–50% depletion**, angka umum lintas tanaman non-padi) — bukan pada angka kPa mutlak, karena FC/PWP berbeda-beda tergantung tekstur tanah.
   - Fase pertumbuhan memengaruhi **volume total** (tanaman muda/TBM butuh lebih sedikit, sistem akar belum sedalam TM) — bukan lewat threshold kPa yang berbeda.

   *Status: rekomendasi metodologi + angka acuan berbasis literatur review kelapa — angka final (kPa/%RAW spesifik lokasi) tetap wajib dikalibrasi dari pengukuran FC/PWP tanah lokasi uji coba tim.*

   **Temuan tambahan (efek terhadap pembungaan/hasil):** irigasi pada kelapa terbukti **meningkatkan produksi bunga betina dan mengurangi premature nut fall (buah muda rontok sebelum matang)** (Carr, 2011) — mengindikasikan stres air berdampak ke tahap pembungaan yang terjadi jauh sebelum buah matang. *Catatan kehati-hatian: kami belum menemukan angka jeda waktu (bulan) yang terverifikasi khusus untuk kelapa.* Sebagai pembanding lintas-spesies (bukan bukti langsung untuk kelapa): pada kelapa sawit — kerabat dekat dalam famili Arecaceae — stres air terbukti berdampak ke hasil panen dengan **jeda 35–40 bulan** karena mempengaruhi sex ratio & aborsi bunga muda (PMC — *Environmental regulation of sex determination in oil palm*; ScienceDirect — *Use of multiseasonal oil palm yield data to assess drought tolerance*). Pola serupa (efek tertunda lewat jalur pembungaan) **masuk akal terjadi juga di kelapa** mengingat siklus reproduksi yang juga panjang (dari inisiasi bunga sampai buah matang bisa >12 bulan), tapi ini **ekstrapolasi, bukan temuan langsung** — perlu dicek lebih lanjut kalau mau dipakai sebagai klaim kuat di proposal.

3. `[DIJAWAB - REKOMENDASI AWAL]` **Apakah versi awal sistem cukup fokus ke kebutuhan air saja, atau perlu langsung mempertimbangkan unsur hara juga?**

   **Rekomendasi: fokus ke air dulu untuk MVP.** Alasan (berbasis Mansoor et al. 2025 di `reference/`, review precision agriculture IoT): sensor hara (NPK/EC tanah, analisis daun) punya kompleksitas kalibrasi dan biaya lebih tinggi dibanding sensor air, dan review tsb secara umum menempatkan sensor hara sebagai kategori terpisah dari sensor kelembapan/tegangan air dalam hal maturity teknologi & biaya. Menggabungkan air+hara sejak awal berisiko memperbesar scope prototype tanpa menambah kekuatan pembuktian konsep inti (hemat air) — apalagi dengan plafon dana hanya Rp20 juta (lihat [[phase]]). Hara bisa masuk sebagai **roadmap pengembangan lanjut** (sudah tercatat di [[schema_alat]] bagian "Pengembangan Lanjut").

   *Status: rekomendasi strategis berbasis referensi yang sudah ada di proyek — bukan temuan baru dari pencarian literatur tambahan.*

4. `[DIJAWAB]` Apakah ada anggota tim dengan latar belakang agronomi/ilmu tanah yang bisa memvalidasi asumsi-asumsi di atas?

    **Jawaban:** Tim terdiri dari 5 orang — 1 teknik sipil, 1 teknik komputer (ketua/kontak utama), 2 teknik mesin, 1 biologi murni. Tidak ada latar belakang agronomi/ilmu tanah spesifik, tapi anggota biologi murni adalah yang paling dekat dan bisa jadi penanggung jawab untuk memvalidasi rekomendasi threshold/kedalaman akar di poin 1–2 di atas.

    `[BELUM DIJAWAB]` **Item baru:** lomba mensyaratkan **1 dosen pembimbing** di luar 5 anggota tim ini ([[phase]]) — siapa dosen pembimbingnya, dan apakah punya latar belakang agronomi/pertanian yang bisa menutup gap ilmu tanah di atas?

## Lokasi & Logistik Prototype

5. `[DIJAWAB]` Apakah tim sudah punya akses lahan untuk uji coba prototype?

   **Jawaban:** Ya — lokasi berubah dari rencana awal (sawit) menjadi **kebun kelapa**. Seluruh dokumen proyek sudah disesuaikan ke komoditas kelapa (lihat [[ide]]).

   `[BELUM DIJAWAB]` **Detail susulan yang masih dibutuhkan** (wajib diisi sebelum Bab 3 Metode Riset proposal disusun): milik siapa lahannya, berapa luas, berapa umur tanaman kelapa, jenis tanah, dan apakah ada riwayat irigasi sebelumnya di lokasi tsb?

6. `[DIJAWAB - REKOMENDASI]` **Apakah ada plot yang bisa dijadikan "kontrol" (irigasi konvensional) untuk perbandingan dengan plot sensor?**

   **Rekomendasi:** gunakan **1 plot kelapa berdekatan** dengan kondisi tanah/naungan/umur tanaman semirip mungkin dengan plot uji, yang tetap diperlakukan **seperti biasa** (pola irigasi/tanpa irigasi tambahan yang sudah berjalan di lokasi tsb) sebagai pembanding — bukan plot baru yang direkayasa. Ini penting secara metodologis: tanpa pembanding "business as usual", klaim penghematan air tidak bisa diverifikasi Tim Penilai BPDP (kriteria penilaian proposal menuntut "metodologi penelitian/rancangan percobaan" yang jelas — lihat [[phase]]). Idealnya kedua plot juga dicatat kondisi awalnya (baseline) sebelum sensor dipasang, supaya ada data "sebelum vs sesudah" selain "sensor vs kontrol". Detail teknis rekomendasi ini ada di [[prototype]].

## Lomba & Pendanaan

7. `[DIJAWAB]` **Nama resmi lomba & dokumen panduan?**

   **Lomba Riset Tingkat Mahasiswa — Badan Pengelola Dana Perkebunan (BPDP) Tahun 2026–2027** (Pengumuman No. PENG-4/BPDP/2026, ditetapkan 27 Juli 2026). Dokumen: `reference/PENG-4 BPDP 2026 Call for Proposal Lomba Riset Mahasiswa.pdf` dan `reference/Panduan Teknis Proposal Lomba Riset 2026-2027-aw.pdf`. Ringkasan lengkap ada di [[phase]].

8. `[DIJAWAB]` **Deadline submission?**

   **31 Oktober 2026**, melalui https://lombariset.bpdp.or.id/. (Pengumuman resmi menyebut "30 Oktober 2026" sedangkan Panduan Teknis menyebut "31 Oktober 2026" — ada selisih 1 hari antar dokumen BPDP sendiri; **disarankan submit paling lambat 30 Oktober 2026** untuk aman, dan konfirmasi ke panitia/call center BPDP jika perlu kepastian.)

9. `[DIJAWAB]` **Format submission?**

   Proposal tertulis maksimum 20 halaman (Arial 12, 1½ spasi, A4) dengan sistematika baku (Abstrak, Bab 1–6, Daftar Pustaka, Lampiran) + presentasi di depan Tim Penilai untuk penentuan pemenang akhir. Detail lengkap sistematika & lampiran wajib ada di [[phase]].

10. `[DIJAWAB]` **Batasan anggaran?**

    **Rp20.000.000 per proposal** (sesuai jawaban tim) — dan ini **cocok dengan plafon resmi BPDP** ("dana untuk riset sebesar maksimum Rp20 juta", dicairkan 2 tahap). Detail alokasi ada di [[schema_alat]] bagian D dan [[prototype]].

## Teknis

11. `[DIJAWAB]` **Harga pasar Indonesia untuk sensor-sensor di [[schema_alat]]?**

    Sudah diriset (Tokopedia, per Agustus 2026) — tabel lengkap ada di [[schema_alat]] bagian D "Estimasi Harga Pasar Indonesia". Temuan penting: **tensiometer jauh lebih mahal** dari perkiraan awal (~Rp2 juta/unit) dan **gateway LoRaWAN penuh berisiko menghabiskan porsi besar dari total dana Rp20 juta** — keduanya sudah diberi catatan mitigasi di [[schema_alat]] dan [[prototype]]. *Harga marketplace berfluktuasi — wajib dicek ulang saat menyusun RAB final.*

12. `[DIJAWAB]` **Mode operasi prototype?**

    Sesuai rekomendasi: **mode rekomendasi/semi-otomatis** dulu (bukan otomatis penuh) — alasan & detail ada di [[flow]] dan [[prototype]].

---

## Sumber Referensi Tambahan (Hasil Pencarian Literatur)

Di luar 5 paper awal di `reference/` (precision agriculture/IoT umum) dan 2 dokumen resmi lomba BPDP, berikut sumber tambahan untuk menjawab pertanyaan biologi/agronomi — **fokus kelapa** (direkomendasikan diunduh & disimpan ke `reference/` jika akan dikutip resmi di proposal):

- **Carr, M.K.V. (2011). "The water relations and irrigation requirements of coconut (Cocos nucifera): A review."** *Experimental Agriculture*, 47(1), 27–51. [Cambridge Core](https://www.cambridge.org/core/journals/experimental-agriculture/article/abs/water-relations-and-irrigation-requirements-of-coconut-cocos-nucifera-a-review/E760D2AFF19FBC99F04D61CC051966BB) — **sumber utama** untuk jawaban #1 dan #2: root distribution, ETc ~3mm/hari, Kc≈0.7, rekomendasi volume irigasi ~2mm/hari (100 L/pohon/hari).
- Studi root distribution kelapa (Sri Lanka/India, ditemukan via pencarian, judul & DOI perlu ditelusuri ulang oleh tim sebelum dikutip formal di proposal — dipakai di sini hanya sebagai pendukung angka 75–80% akar di kedalaman 20–100cm dan puncak penyerapan air di 50–100cm dari batang).
- Referensi kelapa sawit (dipakai sebagai **pembanding lintas-spesies**, bukan bukti langsung untuk kelapa, ditandai jelas di jawaban #2): Carr (2011) versi kelapa sawit, *Experimental Agriculture* 47(4):629–652; PMC — *Environmental regulation of sex determination in oil palm* ([link](https://pmc.ncbi.nlm.nih.gov/articles/PMC3219494/)); ScienceDirect — *Use of multiseasonal oil palm yield data to assess drought tolerance*.

> **Catatan penting:** sama seperti kelapa sawit, **literatur kelapa juga belum punya angka soil water tension (kPa) yang baku/disepakati** — gunakan pendekatan FC/RAW/PWP yang dikalibrasi sendiri di lokasi uji coba, dan kutip ketiadaan konsensus ini secara jujur sebagai bagian dari kontribusi orisinal proyek (kalibrasi lokal via sensor) — ini justru bisa jadi nilai jual "Analisis Kesenjangan" (gap analysis, bobot 20% penilaian proposal, lihat [[phase]]).

## Item Terbuka Baru (Muncul Setelah Info Lomba Resmi Didapat)

13. `[BELUM DIJAWAB]` Siapa dosen pembimbing tim? (wajib untuk syarat peserta — lihat [[phase]])
14. `[DIJAWAB]` Bidang riset final: **Lahan, Tanah & Budidaya** — topik "Penerapan GAP (*Good Agricultural Practices*) dalam pengelolaan perkebunan kelapa rakyat". Sudah dipakai sebagai framing di [[proposal_bab1-5]] Bab I & II.
15. `[BELUM DIJAWAB]` Detail lahan kelapa uji coba: pemilik, luas, umur tanaman, jenis tanah (lihat poin 5 di atas).

## Cara Menjawab

- Edit langsung file ini: ubah `[BELUM DIJAWAB]` → `[DIJAWAB]` dan tulis jawaban di bawah poin terkait.
- Atau sampaikan lewat live chat di CLI — nanti akan diupdate ke file ini oleh Claude.
- Jawaban yang ditandai `[DIJAWAB - REKOMENDASI AWAL]` atau `[DIJAWAB - REKOMENDASI]` adalah rekomendasi berbasis literatur/praktik terbaik yang perlu dikonfirmasi/divalidasi tim — bukan keputusan final.
