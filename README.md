# FitBot - Asisten Kebugaran & Nutrisi Virtual

FitBot adalah aplikasi web interaktif yang berfungsi sebagai pelatih kebugaran virtual dan ahli gizi pribadi. FitBot dirancang untuk membantu pengguna merancang rencana latihan, mendapatkan panduan nutrisi, dan mempertahankan motivasi hidup sehat secara aman dan personal.

Aplikasi ini dilengkapi dengan alur onboarding interaktif yang mengumpulkan profil fisik dan kesehatan pengguna untuk menghasilkan rekomendasi kebugaran yang sangat terpersonalisasi dan disesuaikan dengan kelompok usia masing-masing.


## Fitur Utama

- **Premium UI Flow**: Tampilan antarmuka modern yang terdiri dari halaman Login, Splash Screen ("Get Healthier"), dan Chat Dashboard yang responsif.
- **Smart Onboarding System**: Kuesioner interaktif langkah-demi-langkah untuk mengumpulkan data penting pengguna secara alami:
  - Nama & Usia
  - Jenis Kelamin
  - Berat Badan (kg) & Tinggi Badan (cm)
  - Riwayat Penyakit / Cedera
  - Peralatan Olahraga yang Tersedia
  - Tingkat Aktivitas Harian
  - Komitmen Waktu Mingguan
  - Tujuan Kebugaran Utama
- **Kalkulator BMI Otomatis**: Menghitung Body Mass Index (BMI) secara langsung dari tinggi/berat badan dan menentukan kategorinya (*Kurang berat badan*, *Normal*, *Kelebihan berat badan*, atau *Obesitas*).
- **Rekomendasi Berbasis Usia (Age-Specific Tuning)**: AI menyesuaikan rencana latihan berdasarkan kelompok usia pengguna demi keamanan:
  - **Remaja (< 18 tahun)**: Latihan pertumbuhan menggunakan berat badan sendiri, menghindari beban berat berlebih.
  - **Dewasa Prima (18-45 tahun)**: Rencana latihan komprehensif (kekuatan, kardio, dan fleksibilitas).
  - **Dewasa Menengah (45-60 tahun)**: Fokus menjaga massa otot, kekuatan tulang, latihan jantung rendah benturan, dan kelenturan sendi.
  - **Lansia (> 60 tahun)**: Fokus latihan keseimbangan fungsional, mobilitas sendi, low-impact, dan ramah sendi.
- **Integrasi Gemini 2.5 Flash**: Menggunakan model AI mutakhir dari Google untuk respons chat yang cepat, terstruktur, cerdas, dan suportif.
- **Batasan Keamanan (Safety Guardrails)**: FitBot diprogram untuk menolak pertanyaan di luar topik kesehatan/kebugaran secara sopan dan tidak akan memberikan saran medis/klinis (mengarahkan pengguna ke profesional medis jika diperlukan).


## Teknologi yang Digunakan

### Backend (Server)
- **Node.js** & **Express** — Framework server web
- **@google/generative-ai** — SDK resmi untuk integrasi dengan Gemini AI
- **dotenv** — Pengelolaan environment variables secara aman
- **cors** — Mengizinkan komunikasi lintas asal (*Cross-Origin Resource Sharing*)

### Frontend (Klien)
- **HTML5** — Struktur halaman web semantik
- **Vanilla CSS3** — Desain UI modern dengan efek transisi, ikonografi, dan layout responsif
- **Vanilla JavaScript** — Logika onboarding state machine, validasi input klien, kalkulasi BMI, dan integrasi API
- **Font Awesome 6** — Pustaka ikon modern


## Struktur Proyek

```text
fittbottt-main/
├── server.js          # Entrypoint server Express & integrasi Gemini AI API
├── index.html         # Struktur utama UI (Login, Splash, Chat Box)
├── style.css          # Desain stylesheet premium dan responsif
├── script.js          # Logika frontend, Onboarding State Machine, & Pemanggilan API
├── package.json       # Manajer dependensi proyek dan script run
├── package-lock.json  # File kunci versi dependensi
├── .env.example       # Template konfigurasi environment variables
└── README.md          # Dokumentasi proyek (File ini)
```


## Panduan Instalasi & Pengoperasian

Ikuti langkah-langkah berikut untuk menjalankan FitBot secara lokal di komputer Anda:

### 1. Prasyarat
Pastikan Anda sudah menginstal [Node.js](https://nodejs.org/) (versi 16 atau lebih baru) di perangkat Anda.

### 2. Kloning atau Unduh Repositori
Ekstrak berkas proyek ini ke direktori kerja Anda.

### 3. Instal Dependensi
Buka terminal/command prompt pada folder proyek dan jalankan perintah:
```bash
npm install
```

### 4. Konfigurasi Environment Variables
Salin file `.env.example` menjadi `.env`:
```bash
cp .env.example .env
```
Buka file `.env` yang baru dibuat dan isi kunci API Gemini Anda:
```env
GEMINI_API_KEY=isi_dengan_api_key_gemini_anda
PORT=3000
```
> **Catatan**: Anda bisa mendapatkan API Key gratis melalui [Google AI Studio](https://aistudio.google.com/).

### 5. Jalankan Server
Anda dapat menjalankan server menggunakan script npm yang sudah dikonfigurasi:

**Mode Produksi / Standar:**
```bash
npm start
```

**Mode Pengembangan:**
```bash
npm run dev
```

Setelah server berjalan, buka peramban (browser) Anda dan akses:
**[http://localhost:3000](http://localhost:3000)**

