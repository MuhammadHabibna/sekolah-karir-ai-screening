# Sekolah Karir — AI Talent Screening Workflow Portal

> **Portal Web Simulasi Seleksi & Penilaian Talenta AI (Decision Support System)**  
> 100% Serverless, Static Hosting & Vercel Ready.

---

## 📁 Struktur Direktori `submission/web_app/`

Folder ini sepenuhnya mandiri (*self-contained*), terisolasi, dan siap dideploy langsung ke Vercel tanpa dependensi runtime pihak ketiga:

```
web_app/
├── index.html               # Halaman utama aplikasi (Alur 3 Langkah Workflow)
├── style.css                # Desain formal enterprise korporat (strict boxy, no neon)
├── app.js                   # Client controller: kalkulasi rubrik dinamis, ekstraksi client-side, export
├── vercel.json              # Konfigurasi deployment Vercel 1-klik
├── screening_summary.csv    # Basis data terstruktur 24 kolom hasil screening
├── screening_results.json   # Basis data relasional lengkap (5 kandidat)
├── test_web_live.py         # Skrip pengujian integritas (8/8 PASS 100%)
└── sample_cvs/              # 5 File PDF CV asli untuk simulasi
    ├── CV Raka Pratama Wijaya.pdf      (Strong Fit — 1-kolom ATS)
    ├── CV Nadia Putri Kusuma.pdf       (Partial Fit — 1-kolom ATS)
    ├── CV Bima Aditya Saputra.pdf      (Low Alignment — 1-kolom ATS)
    ├── CV Kevin Reynaldi Santoso.pdf   (Strong Fit — 2-kolom kreatif non-ATS)
    └── CV Farhan Rizky Alamsyah.pdf    (Strong Fit — format tabel datasheet)
```

---

## 🚀 Cara Menjalankan & Deployment

### 1. Deployment ke Vercel (100% Serverless)
Aplikasi ini menggunakan teknologi HTML5, CSS3, dan client-side JavaScript murni:
* **Langkah 1**: Hubungkan repositori GitHub ke akun Vercel.
* **Langkah 2**: Atur **Root Directory** ke `submission/web_app`.
* **Langkah 3**: Klik **Deploy**. Website akan langsung aktif dalam hitungan detik tanpa build step dan tanpa butuh server backend Python!

### 2. Membuka Langsung di Peramban (Lokal Offline)
Cukup klik ganda (*double-click*) file `index.html` di File Explorer. Seluruh fitur (upload CSV, parsing berkas, kalkulasi 7 rubrik, animasi otomasi, dan download CSV 24 kolom) berjalan 100% lancar di peramban.

---

## ✨ Alur Kerja Utama Aplikasi

1. **Langkah 1: Konfigurasi Lowongan & Kriteria PT (Owner Setup)**:
   - Form input judul posisi, divisi, deskripsi kerja, keahlian wajib/pilihan, dan tabel bobot 7 dimensi rubrik penilaian (sesuai Sel 1 notebook).
   - Tombol preset: AI Engineer Intern & Prompt Engineer Specialist.
2. **Langkah 2: Upload CSV / PDF & Otomasi AI**:
   - Area unggah batch CSV pelamar (lengkap dengan template CSV dan sampel batch).
   - Area unggah berkas CV PDF/Word satuan.
   - Animasi visual proses otomasi AI (progress bar 0–100% dan log tahapan real-time).
   - **Kartu Overview Hasil Ekstraksi PDF**: Menampilkan Nama, Asal Universitas, Pengalaman Kerja, Proyek AI/ML, Pemetaan Keahlian (Terbukti vs Klaim), dan Kontak.
   - **Kartu Skoring & Evaluasi Rubrik**: Menampilkan Skor Kesiapan (Readiness Score %), Confidence Score, Tabel 7 Rubrik Penilaian, Kutipan Bukti EVR, Caveats, dan Pertanyaan Wawancara (*Interview Probes*).
3. **Langkah 3: Rekapitulasi Pelamar & Database CSV**:
   - Tabel ringkasan seluruh pelamar dengan metrik kohor.
   - Tombol unduh file `screening_summary.csv` (24 kolom lengkap) dan `screening_results.json`.
