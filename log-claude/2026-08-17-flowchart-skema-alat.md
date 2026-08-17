# 2026-08-17 — Flowchart Skema Alat

## Ringkasan Kerja
- User minta dibuatkan `flowchart.md` berisi diagram Mermaid skema alat.
- Dibaca ulang `early-prompt.md`, `schema_alat.md`, dan `architecture.md` sebagai dasar isi diagram.
- Dibuat `flowchart.md` di root proyek: diagram Mermaid `flowchart TD` dengan 6 subgraph sesuai layer arsitektur (Sensor → Acquisition → Aggregation & Communication → Cloud/Backend → Dashboard & Decision → Actuation).
- Setiap node komponen diberi styling beda untuk membedakan **MVP prototype** (hijau, solid) vs **pengembangan lanjut** (abu-abu, dashed) — konsisten dengan klasifikasi di `schema_alat.md` bagian C.
- Panah solid dipakai untuk alur MVP, panah dashed untuk alur opsional/pengembangan lanjut.

## Keputusan
- Struktur diagram mengikuti persis 6 layer di `architecture.md` (bukan bikin struktur baru) supaya konsisten dengan dokumen lain.
- Komponen dikelompokkan berdasarkan klasifikasi MVP vs Pengembangan Lanjut dari `schema_alat.md` bagian C, bukan dari Table 1/2 mentah — supaya relevan dengan proyek ini, bukan daftar generik dari paper sumber.

## Next Steps
- Tidak ada — dokumen ini murni output visual pelengkap, tidak mengubah keputusan teknis lain. Bisa dirujuk balik dari `schema_alat.md`/`architecture.md` jika perlu.
