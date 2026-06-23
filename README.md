<p align="center">

![Nama](https://img.shields.io/badge/Nama-Muhammad%20Said%20Abimanyu-0A66C2?style=for-the-badge&logo=github&logoColor=white)
![NIM](https://img.shields.io/badge/NIM-312410145-blueviolet?style=for-the-badge)
![Kelas](https://img.shields.io/badge/Kelas-TI%2024%20A1-1ABC9C?style=for-the-badge)
![Matakuliah](https://img.shields.io/badge/Matakuliah-Pemrograman%20Mobile%202-FF6F00?style=for-the-badge&logo=android&logoColor=white)

</p>

<h1 align="center">💰 CatatUang</h1>

<p align="center">
<b>Catat Uang, Atur Masa Depan.</b>
</p>

<p align="center">
Aplikasi Android modern untuk membantu pengguna mengelola keuangan pribadi, mencatat transaksi, memindai struk menggunakan OCR berbasis AI, membuat target tabungan, hingga memperoleh saran keuangan melalui Artificial Intelligence.
</p>

---

# 📖 Tentang Proyek

CatatUang merupakan aplikasi Android yang dikembangkan sebagai proyek **Ujian Akhir Semester (UAS)** Mata Kuliah **Pemrograman Mobile 2**.

Aplikasi ini dirancang untuk membantu pengguna dalam mengelola kondisi keuangan sehari-hari dengan menyediakan fitur pencatatan pemasukan, pengeluaran, target tabungan, laporan keuangan, pemindaian struk menggunakan Google ML Kit OCR, serta asisten keuangan berbasis AI menggunakan Groq API.

---

# 🎯 Tujuan Aplikasi

Aplikasi ini dibuat untuk:

- Membantu pengguna mencatat pemasukan dan pengeluaran.
- Memudahkan pengelolaan keuangan pribadi.
- Mengurangi kesalahan input transaksi menggunakan OCR.
- Memberikan rekomendasi finansial berbasis AI.
- Menyediakan laporan keuangan dalam format PDF.

---

# ✨ Fitur Utama

## 💵 Manajemen Keuangan

- Tambah pemasukan
- Tambah pengeluaran
- Kategori transaksi
- Deskripsi transaksi
- Riwayat transaksi
- Perhitungan saldo otomatis

---

## 🎯 Target Tabungan

- Membuat target tabungan
- Mengatur nominal target
- Monitoring progres tabungan
- Menampilkan persentase pencapaian

---

## 🧾 OCR Scan Struk

- Scan menggunakan kamera
- Import gambar dari galeri
- OCR menggunakan Google ML Kit
- AI membaca isi struk
- Konversi hasil OCR menjadi data transaksi

---

## 🤖 AI Financial Assistant

- Analisis pemasukan
- Analisis pengeluaran
- Analisis target tabungan
- Memberikan saran pengelolaan keuangan
- Menjawab pertanyaan pengguna berdasarkan data keuangan

---

## 📄 Export PDF

- Generate laporan transaksi
- Laporan siap dibagikan
- Format profesional

---

## 📈 Statistik

- Total pemasukan
- Total pengeluaran
- Saldo
- Status surplus/defisit

---

## 🎨 Modern UI

- Material Design 3
- Jetpack Compose
- Responsive Layout
- Dark Mode
- Floating AI Chat Bubble

---

# 🏗 Arsitektur

Aplikasi menggunakan pola arsitektur **MVVM (Model - View - ViewModel)**.

```
User
   │
   ▼
Jetpack Compose
   │
ViewModel
   │
Repository
   │
SharedPreferences
   │
Groq API
Google ML Kit
```

---

# 🚀 Tech Stack

| Teknologi | Digunakan |
|------------|-----------|
| Kotlin | ✅ |
| Jetpack Compose | ✅ |
| Material 3 | ✅ |
| MVVM | ✅ |
| Retrofit | ✅ |
| Gson | ✅ |
| Kotlin Coroutines | ✅ |
| Flow | ✅ |
| CameraX | ✅ |
| Google ML Kit OCR | ✅ |
| Groq API | ✅ |
| SharedPreferences | ✅ |
| PdfDocument | ✅ |

---

# 📱 Preview Aplikasi

<p align="center">
  <img src="https://github.com/user-attachments/assets/9a5d1ed2-7347-4e5c-a65e-3a142effb6a4" width="220"/>
  <img src="https://github.com/user-attachments/assets/9b1a066b-c40a-4b6e-a620-f67b1586114f" width="220"/>
  <img src="https://github.com/user-attachments/assets/029c16d7-d03e-4c84-b81e-650faf73e703" width="220"/>
</p>

<p align="center">
🏠 Dashboard &nbsp;&nbsp;&nbsp;
🧾 Scan Struk &nbsp;&nbsp;&nbsp;
🤖 AI Assistant
</p>

---

# ⚙️ Persyaratan

- Android Studio Hedgehog atau terbaru
- JDK 11+
- Android SDK 34
- Minimum SDK 24
- Internet
- Groq API Key

---

# 🔧 Instalasi

## Clone Repository

```bash
git clone https://github.com/username/CatatUang.git
```

Masuk ke folder project

```bash
cd CatatUang
```

---

## Konfigurasi API Key

Buat file

```
secrets.properties
```

Isi

```properties
GROQ_API_KEY=YOUR_API_KEY
```

---

## BuildConfig

Aktifkan

```kotlin
buildFeatures {
    buildConfig = true
}
```

Tambahkan

```kotlin
buildConfigField(
"String",
"GROQ_API_KEY",
"\"${secretsProperties.getProperty("GROQ_API_KEY")}\""
)
```

---

## Permission

```xml
<uses-permission android:name="android.permission.CAMERA"/>

<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE"/>

<uses-permission
android:name="android.permission.WRITE_EXTERNAL_STORAGE"
android:maxSdkVersion="28"/>
```

---

## File Provider

```xml
<provider
android:name="androidx.core.content.FileProvider"
android:authorities="${applicationId}.fileprovider"
android:grantUriPermissions="true"
android:exported="false">

<meta-data
android:name="android.support.FILE_PROVIDER_PATHS"
android:resource="@xml/file_paths"/>

</provider>
```

file_paths.xml

```xml
<paths>
    <cache-path
        name="cache"
        path="/"/>
</paths>
```

---

# ▶️ Menjalankan Aplikasi

1. Hubungkan perangkat Android atau Emulator.
2. Klik **Sync Gradle**.
3. Tekan tombol **Run**.
4. Aplikasi siap digunakan.

---

# 🤖 Cara Kerja AI

## OCR

```
Foto Struk
      │
      ▼
Google ML Kit OCR
      │
      ▼
Ekstraksi Teks
      │
      ▼
Groq AI
      │
      ▼
JSON
      │
      ▼
Data Transaksi
```

---

## AI Assistant

```
Riwayat Transaksi
        │
Target Tabungan
        │
Saldo
        │
        ▼
Groq AI
        │
        ▼
Analisis Keuangan
        │
        ▼
Rekomendasi Finansial
```

---

# 📂 Struktur Project

```
app
│
├── ui
│   ├── components
│   ├── screens
│   └── theme
│
├── data
│
├── model
│
├── network
│   └── GroqClient.kt
│
├── helper
│   └── ReceiptScannerHelper.kt
│
├── storage
│   └── AppPrefs.kt
│
├── pdf
│   └── PdfGenerator.kt
│
├── MainActivity.kt
│
└── BuildConfig
```

---

# 📊 Hasil Implementasi

✅ CRUD transaksi

✅ OCR Google ML Kit

✅ AI Chat

✅ Target Tabungan

✅ Export PDF

✅ Statistik Keuangan

✅ Material Design 3

✅ Jetpack Compose

---

# 🔮 Roadmap

- [ ] Login Google
- [ ] Firebase Authentication
- [ ] Firebase Firestore
- [ ] Cloud Sync
- [ ] Backup & Restore
- [ ] Export Excel
- [ ] Export CSV
- [ ] Grafik Interaktif
- [ ] Multi Currency
- [ ] Notifikasi Pengingat

---

# 👨‍💻 Penyusun

**Muhammad Said Abimanyu**

**NIM** : 312410145

**Kelas** : TI.24.A1

**Mata Kuliah** : Pemrograman Mobile 2

---

# 📜 Lisensi

Proyek ini dikembangkan sebagai bagian dari **Ujian Akhir Semester (UAS) Mata Kuliah Pemrograman Mobile 2**.

Hak Cipta © 2026 Muhammad Said Abimanyu.

Proyek ini diperuntukkan untuk keperluan pendidikan. Penggunaan, modifikasi, dan distribusi diperbolehkan dengan tetap mencantumkan kredit kepada pengembang.

---
