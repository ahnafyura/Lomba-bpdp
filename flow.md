# Alur Sistem (Data Flow & Control Flow)

Dokumen ini menjelaskan alur end-to-end dari data sensor sampai eksekusi irigasi, melengkapi gambaran layer di [[architecture]].

## Alur Utama

1. **Pembacaan sensor** — tiap node Arduino membaca sensor terpasang (soil water tension, VWC, soil moisture, suhu/kelembapan udara, dst.) secara berkala (mis. tiap 15–30 menit; interval final ditentukan saat [[prototype]] diuji).
2. **Pra-proses lokal** — Arduino melakukan validasi dasar (rentang nilai wajar, deteksi sensor error) sebelum kirim data.
3. **Pengiriman ke gateway** — data dikirim ke Raspberry Pi terdekat (per klaster titik sensor).
4. **Agregasi & uplink LoRaWAN** — Raspberry Pi menggabungkan data dari beberapa node, lalu mengirim via LoRaWAN ke server/cloud pusat.
5. **Penyimpanan time-series** — data masuk ke database di backend, tersimpan dengan timestamp + lokasi (GPS) titik sensor.
6. **Evaluasi rule/threshold engine** — sistem membandingkan nilai soil water tension/VWC terbaru terhadap ambang batas kebutuhan air kelapa (ambang ini masih perlu kalibrasi lokal, lihat rekomendasi metodologi FC/RAW/PWP di [[qna]]).
7. **Keputusan irigasi**:
   - Jika di bawah ambang batas → sistem membuat **rekomendasi/alert irigasi** ke dashboard petani, dan/atau
   - **Trigger otomatis** ke aktuator (solenoid valve/pompa) jika mode otomatis diaktifkan.
8. **Eksekusi irigasi** — aktuator menyalakan irigasi selama durasi/volume yang dihitung sistem.
9. **Feedback loop** — perubahan soil water tension/VWC pasca-irigasi terekam kembali oleh sensor di siklus pembacaan berikutnya, sehingga sistem bisa "melihat" efektivitas irigasi yang baru dilakukan dan menyesuaikan rekomendasi berikutnya.

## Diagram Alur Sederhana

```
Sensor (baca) → Arduino (pra-proses) → Raspberry Pi (agregasi)
      → LoRaWAN (kirim) → Cloud/DB (simpan)
      → Rule Engine (evaluasi threshold)
            ├─ di bawah ambang → Alert/Rekomendasi → Dashboard Petani
            │                                              │
            │                                       (petani approve, jika mode manual)
            │                                              ▼
            └─ (jika mode otomatis) ─────────► Aktuator (valve/pompa) → Irigasi
                                                              │
                                                              ▼
                                        Sensor membaca ulang kondisi tanah (feedback loop)
```

## Mode Operasi

Untuk demo/prototype, direncanakan dua mode (final ditentukan bersama tim, lihat [[prototype]]):

- **Mode rekomendasi (semi-otomatis)** — sistem hanya memberi alert/rekomendasi, keputusan akhir tetap di tangan petani/operator. Lebih aman untuk fase awal pembuktian konsep.
- **Mode otomatis penuh** — sistem langsung trigger aktuator tanpa intervensi manusia. Cocok untuk demo yang menonjolkan otomatisasi, tapi butuh tingkat kepercayaan lebih tinggi terhadap kalibrasi sensor.

## Terkait

- Layer sistem yang menjalankan tiap langkah: [[architecture]]
- Spesifikasi alat per langkah: [[schema_alat]]
- Skenario pengujian alur ini secara nyata: [[prototype]]
