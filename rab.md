# RAB (Rincian Anggaran Biaya) — Draft Awal

> **Status: DRAFT.** Format tabel di bawah mengikuti persis **Lampiran 7: Format Rincian Kebutuhan Dana Riset** dan **Bab VI Pendanaan** dari `reference/Panduan Teknis Proposal Lomba Riset 2026-2027-aw.pdf` (hal. 21 & 25). Angka harga satuan mengacu ke riset harga Tokopedia di [[schema_alat]] (Agustus 2026) — **wajib dicek ulang** sebelum jadi lampiran resmi proposal, karena harga marketplace berfluktuasi. Total anggaran dipatok ke plafon resmi **Rp20.000.000** (lihat [[phase]]).

## Ringkasan Anggaran Biaya (untuk BAB VI Proposal)

Format & rentang persentase wajib sesuai Panduan Teknis BPDP:

| No | Jenis Pengeluaran | Persentase Pendanaan (ketentuan BPDP) | Persentase Diambil | Estimasi Biaya |
|---|---|---|---|---|
| 1 | Peralatan penunjang | 20–30% | 30% | Rp6.000.000 |
| 2 | Bahan habis pakai | 30–40% | 40% | Rp8.000.000 |
| 3 | Perjalanan | maks 15% | 15% | Rp3.000.000 |
| 4 | Lain-lain (administrasi, publikasi, seminar, laporan) | maks 15% | 15% | Rp3.000.000 |
| | **TOTAL** | 100% | 100% | **Rp20.000.000** |

*Catatan: alokasi ini sengaja diambil di batas atas rentang yang diizinkan (30%/40%/15%/15%) supaya pas Rp20 juta — kalau kebutuhan aktual berubah, sesuaikan lagi tapi tetap wajib berada dalam rentang di atas.*

---

## Rincian Anggaran Kegiatan (untuk Lampiran 3 Proposal)

Asumsi desain prototype yang mendasari rincian ini (lihat [[prototype]] untuk detail): **1 node sensor di plot uji** (kelapa, dilengkapi tensiometer + soil moisture + aktuasi irigasi) dan **1 node observasi di plot kontrol** (soil moisture saja, tanpa aktuasi — irigasi tetap business-as-usual). Komunikasi pakai **LoRa point-to-point** (bukan gateway LoRaWAN penuh) sesuai rekomendasi mitigasi anggaran di [[schema_alat]].

### 1. Peralatan Penunjang

| Material | Justifikasi Pemakaian | Kuantitas | Harga Satuan (Rp) | Jumlah (Rp) |
|---|---|---|---|---|
| Tensiometer (soil water tension) | Sensor presisi utama di plot uji, acuan kalibrasi FC/RAW/PWP (lihat [[qna]]) | 1 unit | 2.000.000 | 2.000.000 |
| Capacitive Soil Moisture Sensor | Sensor tambahan cakupan luas — 2 di plot uji, 2 di plot kontrol (observasi) | 4 unit | 15.000 | 60.000 |
| DHT11 (suhu & kelembapan udara) | 1 per node (plot uji & plot kontrol) | 2 unit | 15.000 | 30.000 |
| Arduino Uno R3 (clone) | Akuisisi data per node | 2 unit | 100.000 | 200.000 |
| Raspberry Pi 4 | Gateway agregasi data pusat | 1 unit | 1.200.000 | 1.200.000 |
| Modul LoRa Ra-02/SX1278 | Komunikasi point-to-point node → gateway (2 node + 1 di gateway) | 3 unit | 60.000 | 180.000 |
| Solenoid valve 12V (grade irigasi) | Aktuasi irigasi otomatis di plot uji | 1 unit | 200.000 | 200.000 |
| Relay module 1-channel | Switching solenoid valve | 1 unit | 15.000 | 15.000 |
| Enclosure/box tahan cuaca + power supply/adaptor | Melindungi elektronik di lapangan, 1 set per node | 2 set | 300.000 | 600.000 |
| Panel surya kecil + baterai/power bank | Catu daya mandiri node lapangan (lokasi kebun kemungkinan jauh dari listrik PLN) | 2 set | 400.000 | 800.000 |
| Cadangan komponen (sensor/relay pengganti) | Antisipasi kerusakan selama masa uji lapangan | 1 paket | 515.000 | 515.000 |
| | | | **SUB TOTAL** | **6.000.000** |

### 2. Bahan Habis Pakai

| Material | Justifikasi Pemakaian | Kuantitas | Harga Satuan (Rp) | Jumlah (Rp) |
|---|---|---|---|---|
| Pipa PVC & selang irigasi tetes + fitting | Instalasi jalur irigasi dari solenoid valve ke titik tanam | 1 paket | 1.500.000 | 1.500.000 |
| Kabel listrik, konektor waterproof, terminal blok | Instalasi kelistrikan & sambungan sensor di lapangan | 1 paket | 500.000 | 500.000 |
| Baterai isi ulang/aki kecil (cadangan) | Cadangan daya node lapangan, 2 set | 2 set | 400.000 | 800.000 |
| Token listrik/pulsa data internet | Monitoring jarak jauh selama masa uji (±2–3 bulan) | 1 paket | 900.000 | 900.000 |
| Materai Rp10.000 | Surat pernyataan, dokumen administrasi lomba (Lampiran 4–6) | 10 lembar | 10.000 | 100.000 |
| ATK & cetak form observasi lapangan | Dokumentasi manual pendamping data sensor | 1 paket | 300.000 | 300.000 |
| Jasa kalibrasi/verifikasi awal sensor | Validasi akurasi tensiometer & soil moisture sebelum dipasang | 1 paket | 1.000.000 | 1.000.000 |
| Bahan pendukung instalasi (semen/pasir dudukan tiang sensor, cat pelindung) | Pemasangan fisik struktur sensor di kebun | 1 paket | 500.000 | 500.000 |
| Cetak & jilid proposal, laporan kemajuan, laporan akhir | Kebutuhan administratif wajib lomba | 1 paket | 400.000 | 400.000 |
| Honor tenaga bantu lapangan (non-tim inti) | Bantuan pemasangan & perawatan rutin di kebun | 1 paket | 2.000.000 | 2.000.000 |
| | | | **SUB TOTAL** | **8.000.000** |

### 3. Perjalanan

| Material | Justifikasi Perjalanan | Kuantitas | Harga Satuan (Rp) | Jumlah (Rp) |
|---|---|---|---|---|
| Survei awal lokasi kebun kelapa | Verifikasi kondisi lahan & titik pemasangan sebelum instalasi | 2 kali | 300.000 | 600.000 |
| Mobilisasi tim untuk instalasi alat | Pemasangan sensor, gateway, dan aktuator di plot uji & kontrol | 1 kali | 500.000 | 500.000 |
| Kunjungan monitoring rutin | Pengecekan alat & pengambilan data manual pendamping selama masa uji | 6 kali | 250.000 | 1.500.000 |
| Pembongkaran & evaluasi akhir | Dokumentasi penutup + pengambilan alat pasca uji coba | 1 kali | 400.000 | 400.000 |
| | | | **SUB TOTAL** | **3.000.000** |

### 4. Lain-lain

| Material | Justifikasi | Kuantitas | Harga Satuan (Rp) | Jumlah (Rp) |
|---|---|---|---|---|
| Administrasi (fotokopi, jilid, materai tambahan) | Kelengkapan dokumen proposal & laporan | 1 paket | 300.000 | 300.000 |
| Publikasi/dokumentasi (poster, banner, video demo) | Materi presentasi ke Tim Penilai BPDP | 1 paket | 800.000 | 800.000 |
| Seminar/presentasi internal kampus | Uji coba presentasi sebelum submit/tampil di depan Tim Penilai | 1 paket | 500.000 | 500.000 |
| Laporan kemajuan & laporan akhir | Kewajiban pelaporan monitoring & evaluasi ([[phase]]) | 1 paket | 400.000 | 400.000 |
| Dana tak terduga (kontingensi) | Antisipasi kebutuhan di luar rincian di atas | 1 paket | 1.000.000 | 1.000.000 |
| | | | **SUB TOTAL** | **3.000.000** |

---

## TOTAL Keseluruhan

**Rp20.000.000** (Peralatan Penunjang Rp6.000.000 + Bahan Habis Pakai Rp8.000.000 + Perjalanan Rp3.000.000 + Lain-lain Rp3.000.000) — pas dengan plafon maksimum BPDP.

## Catatan & Asumsi yang Perlu Divalidasi Tim

- **Harga satuan** bersumber dari riset Tokopedia Agustus 2026 ([[schema_alat]]) — beberapa item (jasa kalibrasi, honor tenaga bantu, token internet) adalah **estimasi kasar**, belum ada riset harga spesifik.
- **Honor tenaga bantu lapangan (Rp2.000.000)** perlu dicek apakah diizinkan sebagai komponen bahan habis pakai menurut aturan BPDP — kalau tidak diizinkan, alokasikan ulang ke item lain di kategori yang sama agar sub total tetap 40%.
- **Jumlah node/titik sensor** (1 plot uji + 1 plot kontrol) adalah asumsi minimal MVP sesuai [[prototype]] — kalau tim memutuskan menambah titik/klaster, RAB ini perlu direvisi proporsional.
- Rincian ini **belum termasuk** biaya di luar kendali tim (mis. sewa lahan, jika lahan bukan milik tim/keluarga — lihat [[qna]] poin 15 soal status kepemilikan lahan).
- Setelah lokasi & luas lahan final dikonfirmasi ([[qna]] poin 15), sesuaikan lagi kuantitas pipa irigasi, jarak kabel, dan biaya perjalanan.

## Terkait

- Harga satuan sensor & alasan pemilihan komponen: [[schema_alat]]
- Desain plot uji vs kontrol & mode operasi: [[prototype]]
- Plafon dana & format resmi Bab VI/Lampiran 3/7: [[phase]]
- Pertanyaan terbuka terkait lahan & anggaran: [[qna]]
