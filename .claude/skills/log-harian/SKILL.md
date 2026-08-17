---
name: log-harian
description: Buat entri log kerja harian baru di log-claude/[tanggal]-[topic].md untuk proyek Lomba BPDP. Gunakan setiap kali menyelesaikan/mengakhiri sesi kerja di proyek ini, atau saat user memanggil /log-harian.
---

# Skill: Log Harian

Skill ini membuat file log baru di folder `log-claude/` mengikuti konvensi proyek: **`[YYYY-MM-DD]-[topic-slug].md`**.

## Langkah

1. Tentukan tanggal hari ini (format `YYYY-MM-DD`).
2. Tentukan `topic` dari argumen yang diberikan user (kalau ada), atau simpulkan dari topik kerja di sesi berjalan. Ubah jadi slug kebab-case singkat (mis. "setup sensor tensiometer" → `setup-sensor-tensiometer`).
3. Buat file baru `log-claude/[tanggal]-[topic-slug].md` dengan template berikut:

```markdown
# [YYYY-MM-DD] — [Topik]

## Ringkasan Kerja
- (poin-poin apa yang dikerjakan/dibahas sesi ini)

## Keputusan
- (keputusan penting yang diambil, kalau ada — termasuk alasan singkat)

## Next Steps
- (langkah berikutnya / hal yang masih menggantung)
```

4. Isi template berdasarkan konteks percakapan/kerja pada sesi berjalan — jangan biarkan section kosong tanpa isi kalau ada informasi yang relevan; kalau memang belum ada, tulis "Tidak ada" secukupnya.
5. Jika ada keputusan/asumsi baru yang seharusnya juga tercermin di dokumen lain (`ide.md`, `architecture.md`, `phase.md`, `qna.md`, dst.), ingatkan atau langsung update dokumen tersebut juga.

## Catatan

- Satu file log per topik/sesi kerja, bukan satu file besar per hari — kalau dalam satu hari ada beberapa topik berbeda, buat beberapa file dengan slug topik berbeda.
- Jangan menimpa (overwrite) log tanggal lama; log lama adalah histori kerja proyek.
