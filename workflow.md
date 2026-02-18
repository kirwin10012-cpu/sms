# 📋 Workflow Dokumentasi Proyek — Lingua Multi Language

> **Versi**: v1.0.0  
> **Tanggal**: 2026-02-18  
> **Status**: Dokumen Awal  

---

## 📁 Daftar Isi

- [1. Ringkasan Proyek](#1-ringkasan-proyek)
- [2. Struktur Folder](#2-struktur-folder)
- [3. File Konfigurasi](#3-file-konfigurasi)
- [4. Kode Sumber (src/)](#4-kode-sumber-src)
- [5. Database](#5-database)
- [6. Aset Publik (public/)](#6-aset-publik-public)
- [7. GitHub Actions dan CI/CD](#7-github-actions-dan-cicd)
- [8. Skrip Otomatisasi](#8-skrip-otomatisasi)
- [9. Dokumentasi](#9-dokumentasi)
- [10. Catatan Versi](#10-catatan-versi)

---

## 1. Ringkasan Proyek

| Field | Keterangan |
|-------|------------|
| **Nama** | Lingua Multi Language |
| **Tipe** | Aplikasi Web (React + TypeScript + Vite) |
| **Fungsi** | Platform terjemahan multi-bahasa dengan dukungan WhatsApp Bot |
| **Teknologi** | React, TypeScript, Vite, Tailwind CSS, Shadcn UI |
| **Node.js** | Versi 20 |
| **Paket Manager** | npm |
| **Lisensi** | MIT |
| **Repo Sumber** | Bitungsu/lingua-multi-languag |

---

## 2. Struktur Folder

```
lingua-multi-languag/
├── .github/                    # Konfigurasi GitHub (workflow, dependabot)
│   ├── workflows/
│   │   └── deploy.yml          # Workflow deploy otomatis
│   └── dependabot.yml          # Auto-update dependensi
├── src/                        # Kode sumber utama
│   └── components/             # Komponen React (.tsx)
├── public/                     # File statis
├── database/                   # Skema dan data database
├── package.json                # Dependensi dan skrip npm
├── package-lock.json           # Lock file dependensi
├── tsconfig.json               # Konfigurasi TypeScript
├── vite.config.ts              # Konfigurasi Vite (bundler)
├── tailwind.config.js          # Konfigurasi Tailwind CSS
├── eslint.config.js            # Konfigurasi ESLint
├── components.json             # Konfigurasi Shadcn UI
├── index.html                  # Halaman utama HTML
├── nginx.conf                  # Konfigurasi Nginx
├── .htaccess                   # Konfigurasi Apache
├── .gitignore                  # File yang diabaikan Git
├── ecosystem.config.js         # Konfigurasi PM2
├── runtime.config.json         # Konfigurasi runtime
├── theme.json                  # Konfigurasi tema
├── spark.meta.json             # Metadata Spark
├── *.sh                        # Skrip otomatisasi
├── *.md                        # Dokumentasi
└── README.md                   # Dokumentasi utama
```

---

## 3. File Konfigurasi

### 3.1 package.json
- **Fungsi**: Mendefinisikan nama proyek, versi, dependensi, dan skrip npm
- **Lokasi**: `/package.json`
- **Skrip penting**:
  - `npm run dev` — Menjalankan server pengembangan lokal
  - `npm run build` — Membuat versi produksi
  - `npm run lint` — Mengecek kualitas kode
  - `npm run preview` — Preview hasil build

### 3.2 tsconfig.json
- **Fungsi**: Mengatur kompilasi TypeScript
- **Lokasi**: `/tsconfig.json`

### 3.3 vite.config.ts
- **Fungsi**: Konfigurasi Vite sebagai bundler
- **Lokasi**: `/vite.config.ts`

### 3.4 tailwind.config.js
- **Fungsi**: Mengatur tema, warna, font Tailwind CSS
- **Lokasi**: `/tailwind.config.js`

### 3.5 eslint.config.js
- **Fungsi**: Aturan pengecekan kode
- **Lokasi**: `/eslint.config.js`

### 3.6 components.json
- **Fungsi**: Konfigurasi Shadcn UI
- **Lokasi**: `/components.json`

### 3.7 ecosystem.config.js
- **Fungsi**: Konfigurasi PM2 untuk server produksi
- **Lokasi**: `/ecosystem.config.js`

### 3.8 nginx.conf
- **Fungsi**: Konfigurasi web server Nginx
- **Lokasi**: `/nginx.conf`

### 3.9 .htaccess
- **Fungsi**: Konfigurasi Apache web server
- **Lokasi**: `/.htaccess`

---

## 4. Kode Sumber (src/)

### 4.1 Komponen React

| Komponen | Fungsi |
|----------|--------|
| **PanelComparison** | Perbandingan panel terjemahan side-by-side |
| **PricePage** | Halaman harga/paket layanan |
| **PricingSuggestionDialog** | Dialog saran harga untuk pengguna |
| **ProjectManagement** | Manajemen proyek terjemahan |
| **TestPanel** | Panel pengujian fitur terjemahan |
| **ThreePanelWorkflow** | Alur kerja 3 panel (sumber, proses, hasil) |
| **TouchGestures** | Dukungan gestur sentuh untuk mobile |

---

## 5. Database

- **Lokasi**: `/database/`
- **Fungsi**: Menyimpan skema tabel dan data awal
- **Kegunaan**: Data terjemahan, pengguna, dan pengaturan

---

## 6. Aset Publik (public/)

- **Lokasi**: `/public/`
- **Fungsi**: File statis yang diakses langsung oleh browser
- **Isi**: Ikon aplikasi, gambar, manifest PWA

---

## 7. GitHub Actions dan CI/CD

### 7.1 Deploy Workflow
- **File**: `.github/workflows/deploy.yml`
- **Pemicu**: Push ke branch `main`/`master`, atau manual
- **Tahapan**:
  1. Install — `npm ci`
  2. Test dan Build — `npm run lint`, `npm run build`
  3. Deploy — SSH + rsync ke server

### 7.2 Dependabot
- **File**: `.github/dependabot.yml`
- **Fungsi**: Otomatis membuat PR untuk update dependensi
- **Jadwal**: Setiap hari

---

## 8. Skrip Otomatisasi

| Skrip | Fungsi |
|-------|--------|
| `deploy.sh` | Deploy manual ke server |
| `deploy-auto.sh` | Deploy otomatis dengan pengecekan |
| `setup-deployment.sh` | Setup awal server |
| `check-deployment.sh` | Verifikasi status deployment |
| `verify-deployment.sh` | Verifikasi lengkap setelah deploy |
| `quick-start.sh` | Jalankan proyek dengan cepat |
| `quick-fix.sh` | Perbaikan cepat error umum |
| `fix-all-errors.sh` | Perbaiki semua error |
| `fix-npm-cache.sh` | Perbaiki cache npm rusak |
| `fix-npm-error.sh` | Perbaiki error npm |
| `master-fix.sh` | Perbaikan utama |
| `cleanup.sh` | Bersihkan file sementara |
| `cleanup-docs.sh` | Bersihkan dokumentasi berlebih |
| `test-all-panels.sh` | Tes semua panel |
| `test-deploy-auto.sh` | Tes deploy otomatis |
| `test-whatsapp-system.sh` | Tes sistem WhatsApp |
| `create-installer-bundle.sh` | Buat paket installer |

---

## 9. Dokumentasi

### 9.1 Panduan Utama
| File | Penjelasan |
|------|------------|
| `README.md` | Dokumentasi utama proyek |
| `CARA-PAKAI.md` | Panduan cara menggunakan aplikasi |
| `CARA-INSTALL-WEB.md` | Cara instalasi web |
| `QUICKSTART.md` | Panduan mulai cepat |
| `COMPLETE-GUIDE.md` | Panduan lengkap |

### 9.2 Panduan Deployment
| File | Penjelasan |
|------|------------|
| `DEPLOY.md` | Panduan deploy |
| `CARA-DEPLOY-SIMPLE.md` | Cara deploy sederhana |
| `PANDUAN-LENGKAP-DEPLOYMENT.md` | Panduan lengkap deployment |
| `DEPLOYMENT-CHECKLIST.md` | Checklist sebelum deploy |
| `FAQ-DEPLOYMENT.md` | Pertanyaan umum deploy |

### 9.3 Keamanan dan Akses
| File | Penjelasan |
|------|------------|
| `SECURITY.md` | Kebijakan keamanan |
| `PANDUAN-AKSES-FOUNDER.md` | Panduan akses founder |
| `CARA-AMAN-BERBAGI-AKSES.md` | Cara aman berbagi akses |
| `ROLE_ACCESS_CONTROL.md` | Kontrol akses berdasarkan peran |

### 9.4 Bisnis dan Strategi
| File | Penjelasan |
|------|------------|
| `BUSINESS-SUMMARY.md` | Ringkasan bisnis |
| `STRATEGY.md` | Strategi bisnis |
| `PITCH-DECK.md` | Presentasi untuk investor |
| `COMPETITIVE-ADVANTAGE.md` | Keunggulan kompetitif |

### 9.5 Testing
| File | Penjelasan |
|------|------------|
| `TESTING-README.md` | Panduan testing |
| `PANEL-TESTING-REPORT.md` | Laporan testing panel |
| `AUTOMATED-TESTING-REPORT.md` | Laporan testing otomatis |

### 9.6 Teknis
| File | Penjelasan |
|------|------------|
| `COMPONENT-ARCHITECTURE.md` | Arsitektur komponen |
| `STRUCTURE-DIAGRAM.md` | Diagram struktur |
| `IMPLEMENTATION-ROADMAP.md` | Peta jalan implementasi |
| `MOBILE-APP-PWA.md` | Panduan aplikasi mobile |

---

## 10. Catatan Versi

| Versi | Tanggal | Perubahan |
|-------|---------|-----------|
| **v1.0.0** | 2026-02-18 | Dokumen awal — struktur folder, daftar file konfigurasi, komponen, skrip, dan dokumentasi |

---

> Dokumen ini akan diperbarui secara bertahap. Versi berikutnya (v1.0.1) akan menambahkan detail lebih lanjut pada section yang sudah ada.