# Skema & Spesifikasi Alat (Sensor & Perangkat)

Tabel di bawah menggabungkan data dari dua sumber utama di `reference/`:
- **Table 1** (Mansoor et al. 2025, *Frontiers in Plant Science*) — sensor umum precision agriculture.
- **Table 2** (Ram Gopal et al. 2025, *Precision Irrigation Techniques*) — sensor spesifik irigasi presisi, lengkap dengan range/akurasi/biaya.

## A. Sensor & Perangkat Precision Agriculture (Table 1)

| Sensor/Device | Tipe | Fungsi | Aplikasi |
|---|---|---|---|
| DHT11 | Sensor suhu/kelembapan | Monitoring suhu & kelembapan udara | Crop monitoring & kontrol lingkungan |
| Capacitive Soil Moisture Sensor | Sensor tanah | Mengukur kelembapan tanah | Manajemen irigasi & kesehatan tanah |
| BMP180 | Sensor tekanan | Monitoring cuaca | Prediksi cuaca & analisis iklim |
| LM35 | Sensor suhu | Mengukur suhu | Monitoring kesehatan tanaman |
| SI1145 | Sensor cahaya | Mengukur UV & IR | Monitoring pertumbuhan tanaman |
| GPS Module | Sensor GPS | Pelacakan lokasi | Precision farming |
| MQ-135 | Sensor kualitas udara | Monitoring kualitas udara | Deteksi hama & monitoring lingkungan |
| Raspberry Pi | Platform IoT | Pemrosesan data & komunikasi | Agregasi data multi-sensor |
| Arduino | Platform IoT | Akuisisi data | Integrasi sensor kustom |
| LoRaWAN Module | Perangkat komunikasi | Transmisi data jarak jauh | Transmisi data remote untuk kebun luas |

## B. Sensor Teknologi Irigasi Presisi (Table 2)

| Sensor | Parameter Diukur | Rentang Pengukuran | Akurasi | Response Time | Estimasi Biaya (referensi asli ₹, India) |
|---|---|---|---|---|---|
| Tensiometer | Soil water tension | 0–85 kPa | ±2 kPa | 5–10 menit | 2.000–5.000 |
| Capacitance Probe | Volumetric water content | 0–100% | ±3% | Instan | 15.000–30.000 |
| TDR Sensor | Soil moisture | 0–100% | ±2% | Instan | 25.000–50.000 |
| Neutron Probe | Water content profile | 0–60% | ±1% | 1–2 menit | 200.000–400.000 |
| Thermal Sensors | Canopy temperature | -10–60°C | ±0.5°C | Real-time | 5.000–15.000 |
| Pressure Transducers | System pressure | 0–10 bar | ±0.5% | Instan | 8.000–20.000 |
| Flow Meters | Water discharge | Variabel | ±2% | Real-time | 10.000–100.000 |

> Catatan: harga di kolom terakhir dari paper sumber (mata uang Rupee India, ₹) — hanya untuk gambaran akurasi/response time relatif antar sensor, **jangan dipakai untuk budgeting**. Harga pasar Indonesia riil ada di bagian D di bawah.

## D. Estimasi Harga Pasar Indonesia (untuk RAB Proposal)

Hasil riset harga di marketplace Indonesia (Tokopedia, Agustus 2026) untuk komponen MVP. **Harga berfluktuasi antar penjual/waktu — wajib dicek ulang saat menyusun RAB final (Lampiran 7 proposal), ini hanya estimasi perencanaan awal.**

| Komponen | Estimasi Harga Satuan (Rp) | Catatan |
|---|---|---|
| Capacitive Soil Moisture Sensor | 6.500 – 15.000 | Murah, cakupan luas — hasil riset harga terkonfirmasi |
| Tensiometer (soil water tension) | 1.980.000 – 2.600.000 | **Jauh lebih mahal** dari asumsi awal — model analog gauge standar (mis. Irrometer TEN-120). Ini risiko anggaran besar untuk MVP, lihat catatan di bawah |
| DHT11 (suhu & kelembapan udara) | 8.000 – 20.000 | Umum & murah |
| Arduino Uno R3 (clone/kompatibel) | ± 50.000 – 120.000 | Versi original Arduino-brand lebih mahal (~250.000–400.000); clone cukup untuk prototype |
| Raspberry Pi 4 (gateway/agregasi) | ± 900.000 – 1.300.000 | Tergantung varian RAM; alternatif lebih murah: Raspberry Pi Zero W (~250.000–400.000) jika beban proses ringan |
| Modul LoRa (Ra-02/SX1278, point-to-point) | ± 35.000 – 70.000 / modul | Jauh lebih murah dari gateway LoRaWAN penuh (lihat catatan [[prototype]]) |
| Gateway LoRaWAN penuh (mis. RAK831/Dragino) | ± 1.500.000 – 4.000.000+ | **Berisiko menghabiskan porsi besar dari total dana Rp20 juta** — pertimbangkan LoRa point-to-point atau ESP32+WiFi untuk MVP |
| Solenoid valve 12V (irigasi) | 30.000 – 250.000 | Rentang lebar tergantung kualitas/ukuran (basic vs grade irigasi/brass) |
| Relay module 1-channel | 5.000 – 15.000 | Untuk switching solenoid valve/pompa |

> **Implikasi untuk MVP**: dengan plafon dana BPDP Rp20 juta **untuk seluruh riset** (bukan cuma hardware — termasuk kemungkinan biaya lain di Lampiran 7 seperti transportasi/ATK), realistis hanya cukup untuk **1–2 unit tensiometer** (item termahal), sisanya pakai capacitive soil moisture sensor yang jauh lebih murah untuk cakupan titik tambahan. Ini memperkuat rekomendasi di [[qna]] soal pendekatan FC/RAW/PWP: kalibrasi 1-2 titik tensiometer sebagai referensi presisi, sensor kapasitif murah untuk sebaran titik lebih luas.

## C. Klasifikasi untuk Proyek Ini

### MVP Prototype (fase pembuktian konsep — lihat [[prototype]])
Prioritas: murah, mudah didapat, cukup untuk membuktikan konsep irigasi presisi bekerja.

- Capacitive Soil Moisture Sensor (cakupan luas, murah)
- Tensiometer (soil water tension — parameter kunci keputusan irigasi)
- DHT11 (suhu & kelembapan udara)
- Arduino (akuisisi)
- Raspberry Pi (agregasi)
- LoRaWAN Module (komunikasi jarak jauh)
- Solenoid valve/relay pompa (aktuasi — belum ada di tabel referensi, perlu riset komponen terpisah)

### Pengembangan Lanjut (roadmap pasca-prototype)
Presisi lebih tinggi tapi mahal/kompleks — cocok untuk skala produksi jika lolos pendanaan.

- Capacitance Probe / TDR Sensor (VWC lebih presisi daripada soil moisture kapasitif biasa)
- Neutron Probe (paling presisi tapi paling mahal & butuh keahlian khusus — kemungkinan besar di luar jangkauan prototype)
- Thermal Sensors (canopy temperature — untuk deteksi stres tanaman lebih dini)
- Pressure Transducer & Flow Meter (untuk sistem irigasi otomatis skala penuh dengan monitoring efisiensi penyaluran air)
- SI1145, MQ-135, GPS Module (pelengkap: cahaya, kualitas udara/deteksi hama, pemetaan lokasi presisi)

## Terkait

- Bagaimana alat-alat ini terhubung dalam sistem: [[architecture]]
- Bagaimana data dari alat ini mengalir & diproses: [[flow]]
- Alat mana yang benar-benar dipakai di demo: [[prototype]]
