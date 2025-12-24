# **Minda – Aplikasi Jurnal Harian Offline**

---

![Kotlin](https://img.shields.io/badge/Kotlin-100%25-7F52FF?style=for-the-badge&logo=kotlin)
![Jetpack Compose](https://img.shields.io/badge/Jetpack_Compose-Declarative_UI-4285F4?style=for-the-badge&logo=jetpackcompose)
![Android SDK](https://img.shields.io/badge/Min_SDK-24_(Android_7.0)-3DDC84?style=for-the-badge&logo=android)
![Database](https://img.shields.io/badge/Database-Room_(SQLite_Offline)-EF6C00?style=for-the-badge&logo=sqlite)

---

## 👨‍💻 Kontributor

| Nama | Peran |
|------|--------|
| **Muhammad Riduwan (230104040080)** | Pengembang & Penyusun Dokumentasi |
| **Muhayat, M.IT** | Dosen Pembimbing |
🏫 **Universitas Islam Negeri Antasari – Fakultas Teknologi Informasi**

---

> **Minda** adalah aplikasi jurnal harian berbasis **Kotlin** dan **Jetpack Compose** yang bekerja sepenuhnya secara *offline*.  
> Semua data disimpan menggunakan **Room (SQLite)** tanpa koneksi internet.  
> Proyek ini dikembangkan sebagai implementasi **Modul Praktikum #6 Mobile Programming 20251 – “Menggunakan Database Lokal”** di bawah bimbingan **Muhayat, M.IT**.

---

## 🎯 Tujuan Proyek

- Mengembangkan aplikasi Android modern dengan arsitektur **Jetpack Compose + Room ORM**  
- Menerapkan fungsionalitas **CRUD (Create, Read, Update, Delete)** di database lokal  
- Menyimpan preferensi pengguna (nama & status onboarding) dengan **DataStore Preferences**  
- Menggunakan **Navigation Compose** untuk navigasi antar-screen  
- Membangun **alur onboarding 4 langkah** yang hanya tampil saat pertama kali  
- Menerapkan prinsip *privacy-by-design* — semua data disimpan di perangkat pengguna  

---

## ⚙️ Tumpukan Teknologi

| Lapisan | Teknologi |
|----------|------------|
| **Bahasa Pemrograman** | Kotlin (100%) |
| **UI Framework** | Jetpack Compose + Material Design 3 |
| **Database Lokal** | Room ORM (SQLite) |
| **Penyimpanan Preferensi** | DataStore Preferences |
| **Arsitektur** | MVVM + Repository Pattern |
| **Navigasi** | Navigation Compose |
| **Asinkronisasi** | Kotlin Coroutines + Flow |
| **Build System** | Gradle Kotlin DSL (KSP) |
| **Minimum SDK** | Android 7.0 (API 24) |
| **Target SDK** | Android 14 (API 34) |

---

## ✨ Fitur Utama

- ✅ **Onboarding 4 langkah:** Welcome → Name → Hello → Start Journaling  
- 💾 **CRUD Lengkap:** Tambah, baca, edit, hapus catatan  
- 🔒 **100% Offline:** Data tersimpan di database lokal Room  
- 🗓️ **Kalender Dinamis:** Lihat catatan per tanggal dengan indikator dot  
- 📊 **Insights:** Statistik jumlah catatan dan mood pengguna  
- 🧭 **Navigasi Modern:** Menggunakan NavHost Compose + FAB  
- 🎨 **Material 3 Theme:** Desain minimalis, responsif, dan modern  
- 🔔 **Adaptive Launcher Icon**  

---

## 🗂️ Struktur Proyek

```
app/
└── src/main/
    ├── AndroidManifest.xml
    ├── java/id/antasari/p6minda_<nim>/
    │   ├── MainActivity.kt              // Scaffold, FAB, BottomNav, NavHost
    │   ├── MindaTheme.kt                // Tema Material 3
    │   ├── data/
    │   │   ├── DiaryEntry.kt            // Entity Room
    │   │   ├── DiaryDao.kt              // CRUD Interface
    │   │   ├── MindaDatabase.kt         // Definisi Database
    │   │   ├── DiaryRepository.kt       // Repository Pattern
    │   │   └── UserPrefsRepository.kt   // DataStore Preferences
    │   ├── ui.theme/
    │   │   ├── BottomNav.kt             // Bottom Navigation
    │   │   ├── OnboardingScreens.kt     // Welcome – Name – Hello – Start
    │   │   ├── HomeScreen.kt            // Daftar catatan + FAB
    │   │   ├── NewEntryScreen.kt        // Tambah catatan
    │   │   ├── EditEntryScreen.kt       // Edit catatan
    │   │   ├── NoteDetailScreen.kt      // Detail catatan
    │   │   ├── calendar/
    │   │   │   ├── CalendarScreen.kt    // Tampilan kalender
    │   │   │   └── CalendarViewModel.kt // Logika data kalender
    │   │   ├── ExtraScreens.kt          // Insights + Settings
    │   │   └── navigation/
    │   │       ├── AppNavHost.kt        // Rangka navigasi utama
    │   │       └── Routes.kt            // Konstanta route
    │   └── util/
    │       └── DateFormatter.kt         // Format tanggal
    └── res/
        ├── drawable/
        │   └── banner_diary.jpg         // Banner tampilan
        └── xml/
            └── backup_rules.xml         // Pengecualian DataStore dari backup
```

---

## ⚙️ Instalasi & Menjalankan Aplikasi

### Prasyarat
1. **Android Studio:** Narwhal (2025.1.1) atau lebih baru  
2. **Java:** JDK 17  
3. **SDK:** Android API 34  
4. **Perangkat:** Emulator / fisik (Min SDK 24)

### Langkah Menjalankan
```bash
# 1. Clone repositori
git clone https://github.com/husinnafarin/p6minda_2301040400XX.git
cd p6minda_2301040400XX

# 2. Buka di Android Studio
# 3. (Windows) Buat folder untuk Room
mkdir C:\temp\sqlite

# 4. Sync Gradle, Clean & Rebuild
# 5. Jalankan aplikasi (Shift + F10)
```

---

## 🔧 Arsitektur Aplikasi

```
UI (Jetpack Compose)
        ↓
ViewModel (State & Logic)
        ↓
Repository (Abstraksi Data)
        ↓
Room DAO (CRUD SQLite)
        ↓
Database Lokal (minda.db)
```

---

## 🧭 Alur Onboarding & DataStore

1. Welcome → pengenalan aplikasi  
2. What’s your name? → input nama  
3. Hello {nama}! → sapaan personal  
4. Start Journaling → simpan `onboarding_completed = true`  
5. Saat dibuka kembali → langsung ke Home tanpa onboarding ulang  

---

## 🧾 Lisensi

Proyek ini dikembangkan untuk kepentingan akademik sebagai bagian dari Praktikum Mobile Programming 20251 di **Universitas Islam Negeri Antasari**.

```
© 2025 Muhammad Riduwan  
Dosen Pembimbing: Muhayat, M.IT
```
