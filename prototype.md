# Rencana Prototype (Proof of Concept)

Tujuan prototype: membuktikan bahwa **irigasi berbasis data sensor tanah bisa lebih hemat air** dibanding pendekatan terjadwal/manual, dalam skala kecil yang bisa ditunjukkan untuk keperluan Lomba Riset BPDP (lihat info resmi di [[phase]]).

> Status: kebun **kelapa** sudah tersedia sebagai lokasi uji ([[qna]] poin 5). Anggaran riset dari BPDP maksimum **Rp20 juta total** (bukan cuma hardware) — jadi desain prototype harus benar-benar minim/efisien.

## Skala Uji Coba

- **Lokasi**: kebun kelapa milik/akses tim (detail luas, umur tanaman, pemilik — masih perlu dilengkapi tim di [[qna]] untuk keperluan proposal Bab 3 Metode Riset).
- **Plot kontrol**: **direkomendasikan** menggunakan 1 plot kelapa berdekatan (kondisi tanah/iklim semirip mungkin) yang tetap diirigasi dengan cara konvensional tim (manual/jadwal tetap/tanpa irigasi tambahan — sesuai kebiasaan lokasi tsb), sebagai pembanding terhadap plot yang pakai sistem sensor. Ini praktik standar di studi precision-irrigation (lihat pendekatan serupa di studi Kolombia yang dirujuk di [[qna]]) — tanpa plot kontrol, klaim "hemat air" tidak bisa dibuktikan secara ilmiah ke Tim Penilai.
- **Jumlah titik sensor**: usulan awal 1 klaster kecil (mis. 3–5 pohon berdekatan) sebagai plot uji + 1 plot kontrol setara, disesuaikan lagi dengan sisa anggaran setelah breakdown biaya di [[schema_alat]].
- **Durasi uji**: usulan minimal beberapa minggu hingga 1 siklus musim kering singkat, cukup untuk menunjukkan tren perbedaan penggunaan air sebelum deadline proposal 31 Oktober 2026 — perlu dihitung mundur di [[phase]].

## Kebutuhan Alat (MVP)

Diambil dari kategori "MVP Prototype" di [[schema_alat]]:

1. Tensiometer (soil water tension) — parameter kunci keputusan irigasi
2. Capacitive Soil Moisture Sensor — cakupan tambahan, murah
3. DHT11 (suhu & kelembapan udara)
4. Arduino per titik/node
5. Raspberry Pi sebagai gateway agregasi
6. LoRaWAN module (node + gateway)
7. Solenoid valve/relay pompa untuk aktuasi irigasi
8. Sumber daya: catu daya (baterai/solar panel kecil) — belum dirinci, perlu riset komponen

> **Risiko anggaran:** gateway LoRaWAN "penuh" (multi-channel, mis. RAK831/Dragino) bisa menghabiskan porsi besar dari total dana Rp20 juta. Untuk skala prototype kecil (1 klaster + 1 kontrol, lokasi kemungkinan masih terjangkau WiFi/hotspot), **pertimbangkan modul LoRa point-to-point sederhana (bukan gateway LoRaWAN network-server penuh) atau ESP32 dengan WiFi** sebagai alternatif komunikasi yang jauh lebih murah untuk MVP — LoRaWAN gateway penuh disimpan sebagai roadmap skala produksi (lihat [[schema_alat]]). Keputusan final tergantung breakdown RAB di Lampiran 7 proposal.

**Mode operasi prototype**: sesuai rekomendasi di [[flow]] — pakai **mode rekomendasi/semi-otomatis** dulu (sistem memberi alert, keputusan aktuasi tetap dikonfirmasi tim/operator), bukan otomatis penuh. Alasan: lebih aman selama kalibrasi sensor & threshold agronomi kelapa belum solid (lihat [[qna]]), dan lebih mudah dijelaskan/divalidasi ke Tim Penilai BPDP saat presentasi.

## Metrik Keberhasilan

| Metrik | Target Awal (usulan) | Cara Ukur |
|---|---|---|
| Penghematan air | ≥ X% dibanding plot kontrol (angka final TODO, tunggu baseline lapangan) | Bandingkan total volume air terpakai plot sensor vs plot kontrol |
| Akurasi rekomendasi irigasi | Rekomendasi sistem sesuai kondisi tanah aktual (tidak false alarm berlebihan) | Bandingkan alert sistem vs pengukuran manual/observasi lapangan |
| Uptime sistem | Data sensor tercatat konsisten (minim gap) selama periode uji | Cek kelengkapan data time-series di backend |
| Kemudahan operasional | Petani/operator bisa memahami & menindaklanjuti dashboard tanpa training panjang | Observasi/wawancara singkat saat demo |

## Rencana Demo (untuk Lomba/Pendanaan)

1. Tunjukkan dashboard real-time kondisi tanah (soil water tension/VWC) per titik sensor.
2. Tunjukkan histori data + momen sistem memberi rekomendasi/trigger irigasi.
3. Sajikan perbandingan penggunaan air plot sensor vs plot kontrol (kalau data sempat terkumpul sebelum submission).
4. Jelaskan roadmap pengembangan lanjut (sensor lebih presisi, ML untuk prediksi, integrasi hara — lihat [[schema_alat]] bagian "Pengembangan Lanjut").

## Terkait

- Alat & spesifikasi: [[schema_alat]]
- Alur sistem yang diuji: [[flow]]
- Timeline pembuatan prototype ini: [[phase]]
- Pertanyaan terbuka terkait lokasi/akses lahan & threshold agronomi: [[qna]]
