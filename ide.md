# Ide Proyek: Sistem Irigasi Presisi Berbasis IoT untuk Kebun Kelapa

## Latar Belakang Masalah

Irigasi di kebun kelapa selama ini umumnya dilakukan berdasarkan **jadwal tetap** atau **perkiraan visual/pengalaman petani**, bukan berdasarkan kondisi aktual tanah dan tanaman. Padahal curah hujan tidak konsisten — kadang hujan cukup, kadang kemarau panjang — sehingga:

- Penyiraman terjadwal cenderung **boros air** saat tanah sebenarnya masih cukup lembap.
- Penyiraman manual/reaktif sering **terlambat** saat tanaman sudah mengalami defisit air, yang berdampak pada pertumbuhan dan produktivitas buah kelapa.
- Tidak ada data historis yang bisa dipakai untuk mengoptimalkan jadwal irigasi dari musim ke musim.

## Kenapa Kelapa (Bukan Kelapa Sawit)?

> **Update penting:** rencana awal fokus ke kelapa **sawit**, tapi setelah dicek akses lahan uji coba yang benar-benar tersedia untuk tim adalah kebun **kelapa** (coconut, *Cocos nucifera*) — lihat [[qna]] poin 5. Dokumen ini & seluruh dokumen turunannya (arsitektur, alat, prototype) sudah disesuaikan ke komoditas **kelapa**.

Pertimbangan tim:

1. **Kemudahan pembuktian konsep (proof of concept) & akses lahan nyata.** Lokasi uji coba yang benar-benar bisa diakses tim adalah kebun kelapa — faktor paling menentukan untuk lomba riset yang butuh bukti lapangan dalam waktu terbatas, bukan cuma simulasi.
2. **Tetap relevan dengan skema pendanaan.** Lomba ini diselenggarakan oleh **BPDP (Badan Pengelola Dana Perkebunan)** — bukan khusus sawit, tapi mencakup **tiga komoditas: kelapa sawit, kakao, dan kelapa** (Perpres 132/2024). Jadi fokus ke kelapa tetap 100% eligible untuk pendanaan ini, hanya beda kategori komoditas di proposal. Detail resmi lomba ada di [[phase]] dan `reference/PENG-4 BPDP 2026 Call for Proposal Lomba Riset Mahasiswa.pdf`.
3. **Dampak ekonomi & relevansi riset.** Kelapa adalah komoditas strategis lain yang juga masuk mandat BPDP, dengan tantangan irigasi presisi yang belum banyak digarap dibanding sawit — salah satu paper referensi awal tim (Nuwarapaksha et al. 2026, *Frontiers in Climate*, tentang adaptasi iklim kebun kelapa) justru sudah lebih dulu relevan untuk komoditas ini.

*Catatan teknis: prinsip sistem (jaringan sensor tanah + irigasi presisi) berlaku generik untuk tanaman perkebunan berakar dalam seperti kelapa maupun kelapa sawit — kalau di kemudian hari akses lahan sawit tersedia, arsitektur sistem ini tidak perlu dirombak, cukup kalibrasi ulang parameter agronomi.*

## Ide Inti

Membangun **jaringan sensor IoT** yang dipasang di kebun untuk memantau secara real-time parameter yang memengaruhi kebutuhan irigasi tanaman kelapa, lalu menggunakan data tersebut untuk memberi **rekomendasi atau kontrol irigasi otomatis yang tepat waktu dan tepat jumlah**.

Parameter utama yang dipantau (lihat detail spesifikasi di [[schema_alat]]):
- **Soil water tension** (tegangan air tanah) — indikator seberapa "haus" tanah, diukur pakai tensiometer.
- **Volumetric water content (VWC)** — kandungan air tanah, diukur pakai capacitance probe/TDR sensor.
- **Soil moisture** — kelembapan tanah secara umum, sensor kapasitif murah untuk cakupan lebih luas.
- **Suhu & kelembapan udara** (microclimate) — memengaruhi evapotranspirasi.
- Parameter tambahan potensial: kualitas udara (deteksi dini hama/penyakit), cahaya (pertumbuhan tanaman), curah hujan lokal.

Sistem ini dirancang untuk menjawab pertanyaan operasional: **"Kapan dan berapa banyak kebun kelapa ini perlu diirigasi hari ini?"** — bukan berdasarkan jadwal tetap, tapi berdasarkan kondisi tanah aktual dan prediksi jangka pendek (misalnya mempertimbangkan potensi hujan).

## Benefit Utama

1. **Hemat air** — irigasi hanya dilakukan saat benar-benar dibutuhkan, sesuai jumlah defisit air aktual (benefit utama yang jadi selling point lomba).
2. **Potensi peningkatan produktivitas** — tanaman tidak mengalami stres air berkepanjangan yang bisa menurunkan hasil buah kelapa.
3. **Efisiensi operasional & biaya** — mengurangi tenaga kerja untuk penyiraman manual dan biaya pemompaan air.
4. **Basis data historis** — data sensor dari waktu ke waktu bisa dipakai untuk analisis lanjutan (korelasi irigasi vs hasil panen, deteksi dini kekeringan/penyakit).
5. **Scalable** — arsitektur berbasis LoRaWAN memungkinkan cakupan kebun yang luas dengan biaya komunikasi rendah (lihat [[architecture]]).

## Perlu Masukan Tim (Open Gaps)

Beberapa hal yang menurut pengaku VN masih perlu penjelasan/masukan dari anggota tim yang lebih paham biologi/agronomi, khususnya terkait:

- **Fisiologi akar kelapa** — pada kedalaman berapa akar aktif menyerap air (untuk menentukan kedalaman pemasangan sensor tensiometer/capacitance probe)?
- **Ambang batas (threshold) soil water tension / VWC yang ideal** untuk kelapa di berbagai fase pertumbuhan (bibit, TBM, TM) — kapan dianggap "butuh air"?
- **Interaksi dengan unsur hara** — apakah irigasi presisi ini juga perlu mempertimbangkan status hara tanah, atau cukup fokus ke air dulu untuk versi awal?
- **Variasi tanah & mikroklimat** di lokasi uji coba yang direncanakan.

Pertanyaan-pertanyaan ini didaftar lebih lengkap di [[qna]] — tim dan Mas Levi bisa mengisi jawaban di sana atau lewat live chat CLI.

## Referensi

Ringkasan dari 5 paper di folder `reference/` (integrasi sensor pintar & IoT di precision agriculture, adaptasi iklim kebun kelapa, teknik irigasi presisi, dan review kritis smart agriculture) menjadi dasar teknis ide ini — detail per paper ada di [[schema_alat]] dan [[architecture]].
