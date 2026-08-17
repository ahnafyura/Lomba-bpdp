# Proposal Lomba Riset Tingkat Mahasiswa BPDP 2026–2027 — Draft Bab I–V

> **Status: DRAFT.** Berisi narasi Bab I–V, disintesis dari `ide.md`, `architecture.md`, `flow.md`, `schema_alat.md`, `prototype.md`, `phase.md`, `qna.md`. Bab VI Pendanaan sudah ada terpisah di `rab.md`. Saat dipindah ke dokumen final, ikuti format resmi: **font Arial 12, spasi 1½, kertas A4** (lihat `reference/Panduan Teknis Proposal Lomba Riset 2026-2027-aw.pdf`). Bagian bertanda `[TODO: ...]` wajib diisi tim sebelum submit.

**Judul Riset:** Sistem Irigasi Presisi Berbasis *Internet of Things* (IoT) untuk Efisiensi Penggunaan Air pada Perkebunan Kelapa Rakyat

**Bidang Riset:** Lahan, Tanah & Budidaya — Komoditas Kelapa — topik "Penerapan GAP (*Good Agricultural Practices*) dalam pengelolaan perkebunan kelapa rakyat"

**Ketua Peneliti:** [TODO: nama, NIM, jurusan] · **Anggota:** 1 Teknik Sipil, 2 Teknik Mesin, 1 Biologi Murni [TODO: lengkapi nama & NIM masing-masing] · **Dosen Pembimbing:** [TODO: belum ditentukan — lihat `qna.md` poin 13]

---

## BAB I. PENDAHULUAN

### 1.1 Latar Belakang

Kelapa (*Cocos nucifera* L.) merupakan salah satu dari tiga komoditas perkebunan strategis nasional yang menjadi mandat Badan Pengelola Dana Perkebunan (BPDP) bersama kelapa sawit dan kakao, sebagaimana diatur dalam Peraturan Presiden Nomor 132 Tahun 2024 tentang Pengelolaan Dana Perkebunan. Sebagian besar kebun kelapa di Indonesia dikelola oleh petani rakyat (*smallholder*) dengan keterbatasan infrastruktur, modal, dan akses teknologi, sehingga praktik budidayanya — termasuk irigasi — masih mengandalkan jadwal tetap atau perkiraan visual, bukan berdasarkan kondisi aktual tanah dan tanaman.

Pola curah hujan yang semakin tidak menentu akibat perubahan iklim memperbesar risiko ini: pada musim hujan, penyiraman terjadwal cenderung boros air karena tanah sebenarnya masih cukup lembap; sebaliknya pada musim kemarau, penyiraman manual/reaktif sering terlambat mendeteksi defisit air tanaman. Nuwarapaksha et al. (2026) dalam kajian adaptasi iklim kebun kelapa menegaskan bahwa jaringan sensor *Internet of Things* (IoT) berbasis tanah (*ground-based sensor network*) menawarkan nilai monitoring yang tidak bisa digantikan platform penginderaan jauh maupun UAV, yaitu resolusi temporal tinggi dan berkelanjutan di titik spesifik — namun juga mencatat bahwa potensi ini sering tidak terealisasi di level petani kecil karena kendala konektivitas, catu daya, dan biaya investasi awal.

Di sisi lain, tinjauan literatur ilmiah global (Carr, 2011) tentang hubungan air dan kebutuhan irigasi kelapa secara eksplisit mencatat **belum adanya konsensus ilmiah** mengenai ambang batas (*threshold*) tegangan air tanah (*soil water tension*) yang baku untuk memicu irigasi pada tanaman kelapa — berbeda dengan tanaman pangan seperti padi yang sudah punya rekomendasi teknis mapan. Kesenjangan inilah yang menjadi celah kontribusi penelitian ini: bukan sekadar menerapkan teknologi IoT yang sudah umum di precision agriculture, tetapi mengkalibrasi ambang batas irigasi presisi secara lokal untuk kondisi kebun kelapa rakyat di Indonesia, sekaligus merumuskannya sebagai bagian dari praktik *Good Agricultural Practices* (GAP) yang dapat direplikasi petani lain — sejalan dengan salah satu topik riset prioritas BPDP 2026–2027 pada bidang Lahan, Tanah & Budidaya.

### 1.2 Rumusan Masalah

1. Bagaimana merancang sistem sensor IoT berbiaya terjangkau yang mampu memantau kondisi air tanah secara presisi (soil water tension, volumetric water content, soil moisture) pada kebun kelapa rakyat?
2. Bagaimana menentukan ambang batas (*threshold*) irigasi yang sesuai untuk kondisi tanah kebun kelapa rakyat lokal, mengingat literatur global belum memiliki angka baku untuk komoditas ini?
3. Sejauh mana penerapan irigasi presisi berbasis IoT ini mampu menghemat penggunaan air dan mendukung praktik GAP, dibandingkan dengan pola irigasi konvensional yang berjalan saat ini?

### 1.3 Tujuan Khusus

1. Merancang dan membangun purwarupa (*prototype*) sistem sensor IoT yang terintegrasi dengan mekanisme aktuasi irigasi semi-otomatis pada kebun kelapa rakyat.
2. Mengkalibrasi ambang batas irigasi berbasis pendekatan *Field Capacity* (FC) – *Readily Available Water* (RAW) – *Permanent Wilting Point* (PWP) yang spesifik terhadap kondisi tanah lokasi uji coba, sebagai jawaban atas kesenjangan threshold baku di literatur.
3. Mengukur dan membandingkan efisiensi penggunaan air antara plot yang menerapkan sistem irigasi presisi dengan plot kontrol yang menerapkan pola irigasi konvensional.
4. Merumuskan rekomendasi praktik GAP berbasis data untuk pengelolaan air pada perkebunan kelapa rakyat yang dapat direplikasi dan didiseminasikan ke petani lain.

### 1.4 Urgensi (Keutamaan) Penelitian

Urgensi penelitian ini didasarkan pada tiga hal. **Pertama**, dampak stres air pada tanaman kelapa terbukti memengaruhi tahap pembungaan — irigasi terbukti meningkatkan produksi bunga betina dan mengurangi kerontokan buah muda (*premature nut fall*) (Carr, 2011) — yang berarti kerugian akibat kesalahan pengelolaan air baru terlihat pada hasil panen jauh setelah kejadian defisit air, bukan seketika. Ini menjadikan monitoring kontinu jauh lebih bernilai dibanding pendekatan reaktif yang umum dipakai petani saat ini. **Kedua**, sebagian besar riset dan produk IoT precision agriculture yang tersedia berfokus pada tanaman pangan skala industri (Mansoor et al., 2025; Qazi et al., 2022), sementara kajian spesifik untuk kebun kelapa rakyat skala kecil di Indonesia — dengan keterbatasan konektivitas dan biaya khas *smallholder* (Nuwarapaksha et al., 2026) — masih sangat terbatas. **Ketiga**, ketiadaan angka ambang batas irigasi baku untuk kelapa di literatur global menjadikan kalibrasi lokal berbasis data lapangan sebagai kontribusi ilmiah yang orisinal, sekaligus praktis dan langsung dapat dimanfaatkan sebagai rekomendasi GAP bagi petani.

### 1.5 Target Penelitian

- Purwarupa sistem irigasi presisi IoT yang berfungsi dan teruji langsung di kebun kelapa nyata.
- Data kuantitatif pembanding efisiensi penggunaan air antara plot uji dan plot kontrol.
- Angka ambang batas (*threshold*) irigasi terkalibrasi lokal, sebagai basis rekomendasi praktik GAP.

### 1.6 Luaran (Ringkas)

Rincian lengkap ada di Bab IV. Secara ringkas, penelitian ini menghasilkan: (1) purwarupa sistem IoT irigasi presisi, (2) dataset kalibrasi threshold irigasi kelapa berbasis kondisi lokal, (3) data komparatif efisiensi air, dan (4) rekomendasi praktik GAP irigasi presisi kelapa.

### 1.7 Manfaat

- **Bagi petani kelapa rakyat:** efisiensi penggunaan air, potensi peningkatan produktivitas melalui deteksi dini defisit air, serta acuan praktik GAP yang bisa direplikasi tanpa investasi besar.
- **Bagi BPDP/pemerintah:** model penerapan GAP berbasis teknologi yang terukur dan dapat diskalakan ke kebun kelapa rakyat lain.
- **Bagi ilmu pengetahuan:** data kalibrasi ambang batas irigasi presisi kelapa yang belum banyak tersedia di literatur global, mengisi kesenjangan yang secara eksplisit dicatat oleh Carr (2011).
- **Bagi tim peneliti:** pengalaman riset terapan lintas disiplin (teknik sipil, teknik komputer, teknik mesin, biologi) yang mengintegrasikan rekayasa perangkat keras/lunak dengan agronomi.

---

## BAB II. STUDI PUSTAKA

### 2.1 Precision Agriculture dan IoT pada Perkebunan

Precision agriculture berbasis IoT telah berkembang sebagai pendekatan yang memungkinkan pengambilan keputusan berbasis data pada praktik pertanian, menggantikan pendekatan seragam (*one-size-fits-all*) dengan intervensi yang ditargetkan pada kondisi aktual lahan (Mansoor et al., 2025). Tinjauan Qazi et al. (2022) mencatat bahwa kombinasi sensor IoT berbiaya rendah dan platform pemrosesan data (Arduino, Raspberry Pi) telah membuka akses precision agriculture ke skala yang lebih kecil, meski tantangan konektivitas dan catu daya di lapangan tetap menjadi kendala nyata. Ram Gopal et al. (2025) melengkapi dengan katalog teknologi sensor untuk irigasi presisi — tensiometer, *capacitance probe*, TDR sensor, *thermal sensor*, dan sebagainya — lengkap dengan karakteristik akurasi, waktu respons, dan biaya relatif yang menjadi dasar pemilihan komponen pada penelitian ini (lihat `schema_alat.md`).

### 2.2 Hubungan Air dan Kebutuhan Irigasi Kelapa

Rujukan utama untuk fisiologi air kelapa dalam penelitian ini adalah tinjauan komprehensif Carr (2011) — *"The water relations and irrigation requirements of coconut (Cocos nucifera): A review"* (*Experimental Agriculture*, 47(1), 27–51) — yang merangkum temuan lintas studi mengenai: (a) distribusi akar kelapa, dengan kepadatan akar tertinggi pada kedalaman 0–1,0 m dan lateral 1,0–1,5 m dari batang, meski akar dapat menembus >2 m dalam dan >3 m lateral; (b) evapotranspirasi aktual (ETc) kelapa dewasa sekitar 3 mm/hari dengan koefisien tanaman (Kc) ≈ 0,7; dan (c) aplikasi irigasi sekitar 2 mm/hari (setara ±100 liter/pohon/hari) dengan interval hingga satu minggu terbukti efektif meningkatkan produksi bunga betina dan hasil panen 20–40 butir/pohon/tahun. Studi pendukung lain (root distribution di Sri Lanka/India) menemukan 75–80% akar kelapa terkonsentrasi pada kedalaman 20–100 cm, dengan penyerapan air tertinggi justru terjadi pada akar berjarak 50–100 cm dari batang — temuan yang secara langsung menjadi dasar penentuan titik dan kedalaman pemasangan sensor pada penelitian ini (lihat `architecture.md` dan `qna.md`).

### 2.3 Pembanding Lintas Spesies: Kelapa Sawit

Sebagai pembanding metodologis (bukan sebagai fakta langsung untuk kelapa), penelitian ini juga merujuk literatur kelapa sawit (*Elaeis guineensis*) — kerabat dekat kelapa dalam famili Arecaceae. Carr (2011) versi kelapa sawit (*Experimental Agriculture*, 47(4), 629–652) mencatat kesimpulan serupa: belum ada konsensus ilmiah mengenai ambang batas *depletion* air tanah yang baku. Sementara itu, kajian sex determination dan pola hasil panen kelapa sawit menemukan bahwa stres air berdampak pada hasil panen dengan jeda waktu 35–40 bulan, karena memengaruhi rasio bunga jantan-betina dan aborsi bunga muda jauh sebelum buah matang. Pola dampak tertunda melalui jalur pembungaan ini masuk akal terjadi juga pada kelapa mengingat siklus reproduksinya yang juga panjang, namun penelitian ini memperlakukannya sebagai hipotesis kerja yang perlu diverifikasi lebih lanjut, bukan fakta yang sudah terbukti untuk kelapa.

### 2.4 Studi Kasus Metodologi Irigasi Presisi Lapangan

Sebagai acuan metodologis untuk desain eksperimen lapangan, penelitian ini merujuk studi lapangan pada kelapa sawit dewasa di Kolombia (*Agronomy*, 2024, 14(9)) yang menerapkan metodologi *Field Capacity* (FC) – *Readily Available Water* (RAW) – *Permanent Wilting Point* (PWP) terkalibrasi lokal untuk menentukan pemicu irigasi, alih-alih menggunakan angka kPa mutlak yang tidak mempertimbangkan variasi tekstur tanah. Studi ini juga menguji berbagai volume air aktual (50–600 liter/hari) dan menemukan dampak signifikan terhadap pertumbuhan pada volume rendah — metodologi perbandingan volume/plot inilah yang diadaptasi pada desain plot uji vs. plot kontrol penelitian ini (lihat Bab III dan `prototype.md`).

### 2.5 Kesenjangan (*Gap Analysis*) dan Posisi Penelitian Ini

Berdasarkan sintesis literatur di atas, teridentifikasi kesenjangan berikut: **(1)** belum ada angka ambang batas irigasi (*soil water tension*/kPa) yang baku dan disepakati secara global untuk tanaman kelapa — baik dari literatur kelapa langsung maupun pembandingnya, kelapa sawit; **(2)** sebagian besar studi precision agriculture IoT berfokus pada tanaman pangan skala industri atau kelapa sawit perkebunan besar, bukan pada kebun kelapa rakyat skala kecil dengan keterbatasan infrastruktur khas Indonesia; **(3)** belum tersedia data biaya komponen IoT precision irrigation dalam konteks pasar Indonesia yang bisa jadi acuan kelayakan ekonomi bagi petani kecil.

Penelitian ini memposisikan diri untuk mengisi ketiga kesenjangan tersebut secara sekaligus: mengkalibrasi ambang batas irigasi secara lokal menggunakan metodologi FC/RAW/PWP (mengisi kesenjangan 1), merancang purwarupa yang secara eksplisit mempertimbangkan kendala biaya dan infrastruktur *smallholder* (mengisi kesenjangan 2, lihat `schema_alat.md` dan `rab.md`), serta mendokumentasikan biaya riil komponen di pasar Indonesia sebagai bagian dari luaran (mengisi kesenjangan 3) — seluruhnya dibingkai sebagai kontribusi terhadap penerapan GAP pada perkebunan kelapa rakyat.

---

## BAB III. METODE RISET

### 3.1 Lokasi dan Objek Penelitian

Penelitian dilaksanakan di kebun kelapa yang telah dikonfirmasi dapat diakses oleh tim peneliti.

`[TODO: lengkapi — nama/lokasi kebun, kecamatan/kabupaten, status kepemilikan lahan, luas lahan, jumlah dan umur tanaman kelapa (fase TBM/TM), jenis tanah. Lihat qna.md poin 15.]`

Desain eksperimen menggunakan **dua plot pembanding** (lihat `prototype.md`):

- **Plot uji:** dilengkapi node sensor IoT lengkap (tensiometer, *capacitive soil moisture sensor*, sensor suhu-kelembapan udara) dan mekanisme aktuasi irigasi (solenoid valve) yang dikendalikan sistem berdasarkan data sensor.
- **Plot kontrol:** kebun kelapa berdekatan dengan kondisi tanah, naungan, dan umur tanaman semirip mungkin dengan plot uji, tetap diperlakukan dengan pola irigasi konvensional yang sudah berjalan (*business-as-usual*) — dilengkapi sensor observasi (tanpa aktuasi) untuk mencatat kondisi tanah sebagai pembanding.

### 3.2 Tahapan Penelitian

| No | Tahapan | Luaran Tahapan | Indikator Capaian Terukur |
|---|---|---|---|
| 1 | Persiapan alat & bahan | Seluruh komponen (sesuai `schema_alat.md` dan `rab.md`) tersedia dan lulus uji fungsi dasar di laboratorium/bengkel kampus | 100% komponen lolos uji fungsi sebelum dibawa ke lapangan |
| 2 | Survei lokasi & finalisasi titik pemasangan | Peta titik sensor pada plot uji dan plot kontrol | Titik pemasangan disepakati bersama pemilik lahan, terdokumentasi dengan koordinat GPS |
| 3 | Kalibrasi sensor & perakitan sistem | Nilai *Field Capacity*, *Readily Available Water*, dan *Permanent Wilting Point* tanah lokasi; sistem node-gateway terpasang & teruji komunikasi | Data FC/RAW/PWP terukur untuk tanah lokasi; komunikasi node–gateway berhasil pada uji jarak lapangan |
| 4 | Instalasi lapangan & pengambilan data baseline | Sistem terpasang penuh di kedua plot; data kondisi awal (baseline) tercatat | Data baseline lengkap tercatat pada kedua plot sebelum periode uji dimulai |
| 5 | Pengujian & pengumpulan data lapangan | Data time-series kondisi tanah dan volume air terpakai kedua plot | Uptime pencatatan data ≥90% selama periode uji, minim *gap* data |
| 6 | Monitoring dan evaluasi (sesuai ketentuan BPDP) | Laporan kemajuan; validasi sistem oleh Tim Penilai/Monitoring BPDP | Laporan kemajuan diserahkan tepat waktu sesuai jadwal monitoring BPDP |
| 7 | Analisis data & perumusan rekomendasi | Perbandingan kuantitatif efisiensi air kedua plot; rekomendasi threshold & praktik GAP | Angka persentase penghematan air terhitung; rekomendasi threshold terdokumentasi |
| 8 | Penyusunan laporan akhir | Laporan akhir riset sesuai format BPDP | Laporan akhir lengkap dan diserahkan sesuai tenggat |

### 3.3 Teknik Pengumpulan Data

- **Data otomatis (sensor logging):** nilai soil water tension, volumetric water content/soil moisture, serta suhu dan kelembapan udara direkam pada interval waktu tertentu (mis. setiap 15–30 menit) melalui node Arduino, dikirim ke *gateway* Raspberry Pi via komunikasi LoRa, dan disimpan sebagai data *time-series* (lihat `flow.md`).
- **Data volume air:** volume air yang diaplikasikan sistem otomatis pada plot uji tercatat dari durasi aktuasi solenoid valve; volume air pada plot kontrol dicatat manual oleh tim/petani sesuai praktik yang sedang berjalan.
- **Data observasi manual:** kondisi visual tanaman (indikasi stres air, pertumbuhan daun/buah) dan catatan curah hujan lokal dicatat secara berkala sebagai data pendamping (*ground-truth*) terhadap data sensor.

### 3.4 Teknik Analisis Data

- **Analisis deskriptif komparatif:** membandingkan tren nilai soil water tension/VWC dan total volume air terpakai antara plot uji dan plot kontrol sepanjang periode pengujian.
- **Perhitungan efisiensi air:** persentase penghematan dihitung dengan rumus `(Volume Kontrol − Volume Uji) / Volume Kontrol × 100%`.
- **Kalibrasi threshold lokal:** nilai FC, RAW, dan PWP hasil pengukuran tanah lokasi digunakan untuk menetapkan titik pemicu irigasi (diusulkan pada kisaran ±35–50% *depletion* dari RAW sebagai titik awal, mengacu pada praktik umum lintas tanaman non-padi, kemudian disesuaikan dengan respons aktual tanaman di lapangan).
- **Analisis kualitatif pendukung:** korelasi sederhana antara data sensor dan observasi visual kondisi tanaman digunakan untuk memvalidasi apakah threshold yang ditetapkan efektif mencegah indikasi stres air pada plot uji dibanding plot kontrol.

### 3.5 Penyimpulan Hasil

Kesimpulan penelitian dirumuskan berdasarkan gabungan (a) bukti kuantitatif efisiensi air dari perbandingan dua plot, (b) angka kalibrasi threshold irigasi lokal yang dihasilkan, dan (c) evaluasi kualitatif kemudahan operasional sistem di lapangan. Ketiganya dirangkum menjadi rekomendasi praktik GAP irigasi presisi kelapa yang dirancang agar dapat direplikasi oleh petani kelapa rakyat lain dengan sumber daya terbatas.

---

## BAB IV. LUARAN RISET

1. **Purwarupa sistem irigasi presisi berbasis IoT** yang berfungsi dan telah teruji langsung di kebun kelapa nyata, mencakup sensor tanah, komunikasi nirkabel, dan mekanisme aktuasi irigasi semi-otomatis (rincian teknis di `architecture.md` dan `schema_alat.md`).
2. **Dataset kalibrasi ambang batas irigasi (FC/RAW/PWP)** yang spesifik terhadap kondisi tanah kebun kelapa lokasi uji coba — kontribusi baru mengingat literatur global belum memiliki angka baku untuk komoditas kelapa (lihat Bab II).
3. **Data komparatif efisiensi penggunaan air** antara plot yang menerapkan irigasi presisi dan plot kontrol konvensional, termasuk estimasi persentase penghematan air.
4. **Rekomendasi praktik GAP (*Good Agricultural Practices*)** untuk irigasi presisi kebun kelapa rakyat, dirumuskan agar dapat direplikasi dengan biaya dan kompleksitas rendah.
5. **Laporan kemajuan dan laporan akhir riset** sesuai format dan jadwal monitoring-evaluasi yang ditetapkan BPDP.
6. **Materi diseminasi** (dokumentasi/presentasi hasil) untuk keperluan presentasi akhir di hadapan Tim Penilai Lomba Riset BPDP.

*Catatan kepatuhan:* sesuai ketentuan lomba, Hak Kekayaan Intelektual (HKI) yang timbul dari kegiatan riset ini sepenuhnya menjadi milik BPDP (lihat `phase.md`).

---

## BAB V. JADWAL KEGIATAN

Jadwal berikut disusun untuk **6 (enam) bulan** pelaksanaan riset (sesuai ketentuan durasi 3–8 bulan), terhitung sejak pendanaan tahap pertama cair pasca-proposal dinyatakan lolos seleksi.

| No | Jenis Kegiatan | Bulan 1 | Bulan 2 | Bulan 3 | Bulan 4 | Bulan 5 | Bulan 6 |
|---|---|:---:|:---:|:---:|:---:|:---:|:---:|
| 1 | Persiapan alat & bahan (pengadaan sesuai RAB) | X | | | | | |
| 2 | Survei lokasi & finalisasi titik pemasangan | X | | | | | |
| 3 | Kalibrasi sensor & perakitan sistem | X | X | | | | |
| 4 | Instalasi lapangan & pengambilan data baseline | | X | | | | |
| 5 | Pengujian & pengumpulan data lapangan (monitoring rutin) | | X | X | X | X | |
| 6 | Monitoring & Evaluasi I (sesuai jadwal BPDP) | | | | X | | |
| 7 | Analisis data & perumusan rekomendasi GAP | | | | | X | X |
| 8 | Penyusunan & penyerahan laporan akhir | | | | | | X |

`[TODO: sesuaikan jumlah bulan & rincian jadwal setelah tanggal mulai pendanaan aktual diketahui — jadwal di atas adalah estimasi relatif (Bulan 1 = bulan pertama pendanaan cair), bukan tanggal kalender absolut.]`

---

## Referensi yang Dikutip di Bab Ini

*(Daftar Pustaka lengkap ditempatkan setelah Bab VI Pendanaan pada dokumen final, sesuai sistematika resmi — daftar berikut disertakan di sini agar kutipan pada Bab II dan Bab I dapat ditelusuri.)*

- Carr, M.K.V. (2011). The water relations and irrigation requirements of coconut (*Cocos nucifera*): A review. *Experimental Agriculture*, 47(1), 27–51.
- Carr, M.K.V. (2011). The water relations and irrigation requirements of oil palm (*Elaeis guineensis*): A review. *Experimental Agriculture*, 47(4), 629–652.
- Mansoor, S., Iqbal, S., Popescu, S.M., Kim, S.L., Chung, Y.S., & Baek, J.-H. (2025). Integration of smart sensors and IOT in precision agriculture: trends, challenges and future prospectives. *Frontiers in Plant Science*, 16, 1587869.
- Nuwarapaksha, T.D., Udumann, S.S., Dissanayaka, N.S., & Atapattu, A.J. (2026). Climate change impacts and adaptation strategies in coconut plantations: integrating remote sensing and real-time monitoring. *Frontiers in Climate*, 8, 1762364.
- Qazi, S., Khawaja, B.A., & Farooq, Q.U. (2022). IoT-Equipped and AI-Enabled Next Generation Smart Agriculture: A Critical Review, Current Challenges and Future Trends. *IEEE Access*, 10, 21219–21235.
- Ram Gopal et al. (2025). Precision Irrigation Techniques for Optimizing Water Use Efficiency in Agriculture. *Archives of Current Research International*, 25(12), 347–362.
- Evaluation of the Effect of Soil Water Conditions on the Development and Water Requirements of Adult Oil Palm (*Elaeis guineensis* Jacq.) in the Northern Region of Colombia. (2024). *Agronomy*, 14(9). DOI: 10.3390/agronomy14091976.

`[TODO: telusuri ulang & lengkapi sitasi studi root distribution kelapa Sri Lanka/India yang dirujuk di Bab II §2.2 dan §2.4 (PMC/ScienceDirect terkait sex determination & drought tolerance kelapa sawit) sebelum disatukan ke Daftar Pustaka resmi — lihat detail di qna.md.]`

## Terkait

- Latar belakang & motivasi lengkap: [[ide]]
- Arsitektur & alur sistem yang dijelaskan di Bab III: [[architecture]], [[flow]]
- Spesifikasi & harga alat: [[schema_alat]]
- Desain plot uji/kontrol & mode operasi: [[prototype]]
- Bab VI Pendanaan (RAB): [[rab]]
- Info resmi lomba & jadwal fase proyek: [[phase]]
- Pertanyaan terbuka yang memengaruhi bab ini: [[qna]]
