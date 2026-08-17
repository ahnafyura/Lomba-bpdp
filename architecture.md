# Arsitektur Sistem

Arsitektur mengikuti pola umum sistem IoT smart agriculture (lihat referensi Qazi et al. 2022; Mansoor et al. 2025) yang diadaptasi untuk konteks kebun kelapa: cakupan area luas, konektivitas terbatas, dan kebutuhan biaya rendah per titik sensor.

```
┌─────────────────────┐
│   1. SENSOR LAYER    │  (di lapangan, per titik/klaster pohon kelapa)
│  - Tensiometer        (soil water tension)
│  - Capacitance probe  (volumetric water content)
│  - Soil moisture sensor (kapasitif, murah, cakupan luas)
│  - DHT11               (suhu & kelembapan udara)
│  - SI1145               (cahaya/UV, opsional)
│  - MQ-135                (kualitas udara, opsional - deteksi dini hama/gas)
│  - GPS module              (lokasi titik sensor)
└─────────┬────────────┘
          │ analog/digital (wired ke microcontroller)
┌─────────▼────────────┐
│  2. ACQUISITION LAYER │  Arduino (per titik/node)
│  - Baca sensor, konversi ke nilai terukur
│  - Kirim data ke gateway via kabel/wireless jarak pendek
└─────────┬────────────┘
          │
┌─────────▼────────────┐
│ 3. AGGREGATION &      │  Raspberry Pi + LoRaWAN module (per klaster/gateway)
│    COMMUNICATION LAYER│  - Agregasi data dari banyak node Arduino
│                        │  - Transmisi jarak jauh (LoRaWAN) ke server pusat
│                        │  - Dipilih karena kebun kelapa luas & konektivitas
│                        │    seluler/WiFi sering tidak stabil di lapangan
└─────────┬────────────┘
          │ LoRaWAN uplink
┌─────────▼────────────┐
│  4. CLOUD / BACKEND    │
│  - Terima & simpan data time-series
│  - Threshold/rule engine (awal) → bisa dikembangkan ke ML (lanjutan)
│  - API untuk dashboard & histori
└─────────┬────────────┘
          │
┌─────────▼────────────┐
│  5. DASHBOARD &        │
│     DECISION LAYER     │
│  - Visualisasi kondisi tanah per titik/klaster
│  - Rekomendasi/alert irigasi ke petani
│  - (Opsional) trigger otomatis ke aktuator
└─────────┬────────────┘
          │ perintah irigasi
┌─────────▼────────────┐
│  6. ACTUATION LAYER    │
│  - Solenoid valve / relay pompa
│  - Eksekusi irigasi sesuai rekomendasi/kontrol otomatis
└───────────────────────┘
```

## Rasional Pilihan Komponen

| Layer | Komponen | Kenapa dipilih |
|---|---|---|
| Sensor | Tensiometer, capacitance probe, soil moisture | Kombinasi murah (soil moisture, cakupan luas) + presisi (tensiometer/capacitance probe di titik kunci) — lihat trade-off biaya di [[schema_alat]] |
| Akuisisi | Arduino | Murah, mudah kustomisasi per jenis sensor, dukungan komunitas luas |
| Agregasi | Raspberry Pi | Cukup kuat untuk agregasi multi-sensor & pre-processing sebelum kirim ke cloud |
| Komunikasi | LoRaWAN (skala produksi) / LoRa point-to-point atau WiFi (MVP) | Jangkauan jauh (km), daya rendah, cocok untuk area kebun luas dengan konektivitas seluler terbatas (sesuai temuan Nuwarapaksha et al. 2026 soal tantangan konektivitas di smallholder). **Untuk MVP dengan plafon dana Rp20 juta**, gateway LoRaWAN penuh terlalu mahal — lihat alternatif hemat biaya di [[schema_alat]] & [[prototype]] |
| Keputusan | Rule/threshold engine (awal) | Lebih mudah diverifikasi & dijelaskan ke juri lomba dibanding ML black-box; ML jadi roadmap lanjutan |

## Tantangan yang Perlu Diantisipasi (dari referensi)

Berdasarkan Nuwarapaksha et al. 2026 dan Qazi et al. 2022, hal-hal berikut adalah risiko implementasi nyata di lapangan, bukan hanya di paper:

- **Konektivitas** — LoRaWAN dipilih justru untuk memitigasi ini, tapi tetap perlu perencanaan posisi gateway.
- **Catu daya** — node di lapangan perlu solar panel + baterai (belum masuk MVP prototype, lihat [[prototype]]).
- **Kalibrasi & perawatan sensor** — perlu SOP kalibrasi berkala, terutama tensiometer.
- **Biaya investasi awal** — jadi pertimbangan dalam menentukan skala prototype vs skala produksi (lihat [[schema_alat]] untuk breakdown biaya per sensor).

## Terkait

- Alur data end-to-end: [[flow]]
- Spesifikasi detail tiap alat: [[schema_alat]]
- Cakupan MVP untuk pembuktian konsep: [[prototype]]
