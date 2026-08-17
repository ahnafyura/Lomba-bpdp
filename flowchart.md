# Flowchart Skema Alat — Sistem Irigasi Presisi IoT Kebun Kelapa

Diagram Mermaid berikut memvisualisasikan skema alat dari [[schema_alat]] dan [[architecture]]: enam layer arsitektur (sensor → akuisisi → agregasi/komunikasi → cloud → dashboard/keputusan → aktuasi), dengan pembeda visual antara komponen **MVP prototype** dan **pengembangan lanjut**.

## Diagram Skema Alat

```mermaid
flowchart TD
    subgraph L1["1. SENSOR LAYER — per titik/klaster pohon kelapa"]
        direction TB
        S1["Tensiometer<br/>(soil water tension)"]:::mvp
        S2["Capacitive Soil Moisture Sensor<br/>(cakupan luas, murah)"]:::mvp
        S3["DHT11<br/>(suhu & kelembapan udara)"]:::mvp
        S4["Capacitance Probe / TDR Sensor<br/>(VWC presisi tinggi)"]:::lanjut
        S5["Neutron Probe<br/>(water content profile, paling presisi)"]:::lanjut
        S6["Thermal Sensor<br/>(canopy temperature)"]:::lanjut
        S7["Pressure Transducer & Flow Meter<br/>(monitoring efisiensi irigasi)"]:::lanjut
        S8["SI1145 / MQ-135 / GPS Module<br/>(cahaya, kualitas udara, lokasi)"]:::lanjut
    end

    subgraph L2["2. ACQUISITION LAYER — per titik/node"]
        A1["Arduino<br/>(baca sensor, konversi nilai)"]:::mvp
    end

    subgraph L3["3. AGGREGATION & COMMUNICATION LAYER — per klaster/gateway"]
        B1["Raspberry Pi<br/>(agregasi multi-sensor)"]:::mvp
        B2["LoRa point-to-point (Ra-02/SX1278)<br/>atau ESP32+WiFi — MVP"]:::mvp
        B3["Gateway LoRaWAN penuh<br/>(RAK831/Dragino) — skala produksi"]:::lanjut
    end

    subgraph L4["4. CLOUD / BACKEND"]
        C1["Penyimpanan data time-series"]:::mvp
        C2["Rule/Threshold Engine"]:::mvp
        C3["ML Model<br/>(roadmap lanjutan)"]:::lanjut
        C4["API dashboard & histori"]:::mvp
    end

    subgraph L5["5. DASHBOARD & DECISION LAYER"]
        D1["Visualisasi kondisi tanah<br/>per titik/klaster"]:::mvp
        D2["Rekomendasi/alert irigasi<br/>ke petani"]:::mvp
        D3["Trigger otomatis ke aktuator<br/>(opsional)"]:::lanjut
    end

    subgraph L6["6. ACTUATION LAYER"]
        E1["Relay module"]:::mvp
        E2["Solenoid valve / pompa<br/>(eksekusi irigasi)"]:::mvp
    end

    S1 --> A1
    S2 --> A1
    S3 --> A1
    S4 -.-> A1
    S5 -.-> A1
    S6 -.-> A1
    S7 -.-> A1
    S8 -.-> A1

    A1 --> B1
    B1 --> B2
    B1 -.-> B3
    B2 --> C1
    B3 -.-> C1

    C1 --> C2
    C1 -.-> C3
    C2 --> C4
    C3 -.-> C4

    C4 --> D1
    D1 --> D2
    D2 -.-> D3

    D2 --> E1
    D3 -.-> E1
    E1 --> E2

    classDef mvp fill:#d4edda,stroke:#28a745,stroke-width:2px,color:#155724
    classDef lanjut fill:#f5f5f5,stroke:#999,stroke-width:1px,stroke-dasharray: 4 3,color:#666
```

**Legenda:**
- **Kotak hijau solid** = komponen MVP prototype (fase pembuktian konsep)
- **Kotak abu-abu putus-putus** = komponen pengembangan lanjut (roadmap pasca-prototype)
- **Panah solid (`-->`)** = alur data/koneksi MVP
- **Panah putus-putus (`-.->`)** = alur data/koneksi opsional/pengembangan lanjut

## Terkait

- Detail spesifikasi & harga tiap alat: [[schema_alat]]
- Rasional pilihan komponen per layer: [[architecture]]
- Alur data & keputusan end-to-end: [[flow]]
- Cakupan alat yang benar-benar dipakai di demo: [[prototype]]
