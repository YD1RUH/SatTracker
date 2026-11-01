# SatTracker

<p align="center">
  <img src="https://github.com/YD1RUH/SatTracker/blob/main/image.png?raw=true" width="50%" alt="Tampilan SatTracker">
</p>

<p align="center">
  <a href="https://github.com/YD1RUH/SatTracker/releases"><img src="https://img.shields.io/github/v/release/YD1RUH/SatTracker?include_prereleases&label=release" alt="Release"></a>
  <img src="https://img.shields.io/badge/status-beta-orange" alt="Status: beta">
  <img src="https://img.shields.io/badge/Android-7.0%2B%20(API%2024)-3DDC84?logo=android&logoColor=white" alt="Android 7.0+">
  <img src="https://img.shields.io/badge/target%20SDK-34-3DDC84?logo=android&logoColor=white" alt="Target SDK 34">
  <img src="https://img.shields.io/badge/ABI-arm64--v8a%20%7C%20armeabi--v7a%20%7C%20x86__64-informational" alt="ABI">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/C%2B%2B-17-00599C?logo=cplusplus&logoColor=white" alt="C++17">
  <img src="https://img.shields.io/badge/Java-11-ED8B00?logo=openjdk&logoColor=white" alt="Java 11">
  <img src="https://img.shields.io/badge/Android%20NDK-NativeActivity-3DDC84?logo=android&logoColor=white" alt="Android NDK">
  <img src="https://img.shields.io/badge/OpenGL%20ES-3.0-5586A4?logo=opengl&logoColor=white" alt="OpenGL ES 3.0">
  <img src="https://img.shields.io/badge/Dear%20ImGui-1.93.0-0B7BC1" alt="Dear ImGui 1.93.0">
  <img src="https://img.shields.io/badge/SGP4-Vallado-blueviolet" alt="SGP4">
  <img src="https://img.shields.io/badge/CMake-3.22.1-064F8C?logo=cmake&logoColor=white" alt="CMake 3.22.1">
  <img src="https://img.shields.io/badge/Gradle-8.9-02303A?logo=gradle&logoColor=white" alt="Gradle 8.9">
  <img src="https://img.shields.io/badge/Android%20Gradle%20Plugin-8.7.3-3DDC84?logo=android&logoColor=white" alt="AGP 8.7.3">
  <img src="https://img.shields.io/badge/Android%20Studio-project-3DDC84?logo=androidstudio&logoColor=white" alt="Android Studio">
</p>

Aplikasi Android pelacak satelit dengan **overlay augmented reality (AR)** di kamera. Arahkan ponsel ke langit, dan SatTracker menampilkan posisi satelit, lintasannya, serta waktu **AOS** dan **LOS** secara realtime.

> Produk hasil penelitian dan pengembangan (litbang) tim **AMSAT-ID** — <https://amsat-id.org/>

**[⬇ Unduh APK (Beta V1.0.0)](https://github.com/YD1RUH/SatTracker/releases/download/Beta-V1.0.0/SatTracker.apk)**

## Fitur

- **Kamera utama + data GPS** — tombol **Start** membuka kamera belakang dan menampilkan latitude, longitude, dan altitude dari GPS di layar.
- **Import TLE dari file** — muat file TLE (format 2 baris atau 3 baris) lewat `Menu > Import TLE (file)`.
- **Import TLE dari URL** — lewat `Menu > Import TLE dari URL...`, ketik atau **Tempel** alamat `https://` file TLE, lalu tekan **Unduh**. Hasil unduhan disimpan di ponsel sehingga tetap bisa dipakai tanpa internet.
- **URL default tersimpan** — URL terakhir yang berhasil dipakai mengunduh menjadi URL default dan terisi otomatis saat dialog dibuka lagi. Bawaan awal: `https://amsat-id.org/tle.txt`. Tombol **Reset default** mengembalikan ke alamat bawaan.
- **Perbarui TLE satu ketukan** — `Menu > Perbarui TLE (URL tersimpan)` mengunduh ulang TLE dari URL default.
- **TLE terakhir diingat** — TLE yang terakhir dimuat (dari file maupun URL) dimuat otomatis saat aplikasi dibuka kembali.
- **Satelit terpilih diingat** — satelit yang dicentang disimpan otomatis dan dicentang kembali saat aplikasi dibuka lagi, juga setelah TLE diperbarui (selama satelitnya masih ada di file TLE). Tombol **Clear** menghapus pilihan yang tersimpan.
- **Layout 3/4 kamera : 1/4 daftar satelit** setelah TLE dimuat, baik portrait maupun landscape.
- **Overlay satelit dinamis** untuk satelit yang dicentang: nama, AOS, LOS, titik satelit (merah), dan lintasan di langit (hijau stabilo).
- **Beberapa satelit sekaligus** (maksimal 12) — informasi nama, AOS, dan LOS tampil bergantian.
- **Lock** — saat satelit melintas, tampilan terkunci ke satelit itu sampai LOS. Jika satelit di luar layar, panah penunjuk arah muncul di tepi layar.
- **Pencarian satelit** berdasarkan nama atau nomor katalog.
- **Countdown lintasan** — geser daftar satelit ke kiri untuk melihat hitung mundur AOS/LOS satelit yang dicentang; geser ke kanan untuk kembali.
- **Space Object** — `Menu > Space Object` membuka window checklist untuk mengaktifkan overlay benda langit selain satelit:
  - **Solar System** — Matahari, Bulan (dengan persentase fase), Merkurius, Venus, Mars, Jupiter, Saturnus, Uranus, Neptunus, plus garis ekliptika.
  - **Comet** — beberapa komet periodik (Halley, Encke, Pons-Brooks, Giacobini-Zinner, Wirtanen, Churyumov-Gerasimenko, Swift-Tuttle) beserta jarak ke Matahari.
  - **Rasi Bintang** — garis dan bintang utama 14 rasi (Orion, Beruang Besar/Kecil, Kasiopeia, Angsa, Lyra, Kalajengking, Gubug Penceng, Singa, Gemini, Taurus, Anjing Besar, Elang, Pegasus). Pilihan checklist diingat saat aplikasi dibuka lagi.
- **Auto rotate** — mengikuti rotasi ponsel.
- **Crosshair** di pusat kamera dengan bacaan Az/El arah bidikan, dan **label nama satelit** yang menempel pada lintasan hijaunya.
- **HUD info** menempel pada objek overlay: untuk satelit menampilkan lintang/bujur titik sub-satelit, ketinggian (km), dan kecepatan orbit (km/s); untuk Space Object menampilkan Az/El, lintang/bujur titik di Bumi tempat objek tepat di zenit, jarak, dan kecepatan orbit.
- Penanda arah mata angin (N/E/S/W) dan garis horizon untuk membantu memeriksa keselarasan sensor.

## Instalasi

1. Unduh file APK: [SatTracker.apk](https://github.com/YD1RUH/SatTracker/releases/download/Beta-V1.0.0/SatTracker.apk) (atau dari halaman [Releases](https://github.com/YD1RUH/SatTracker/releases)).
2. Buka file APK di ponsel. Jika diminta, izinkan **Install dari sumber tidak dikenal** untuk aplikasi yang Anda pakai membukanya.
3. Buka **SatTracker**.

## Cara pakai

1. Muat data TLE, pilih salah satu cara:
   - **Dari URL (disarankan):** pilih **Menu > Import TLE dari URL...**, lalu tekan **Unduh**. Kolom sudah terisi URL default `https://amsat-id.org/tle.txt`; Anda bisa menggantinya, misalnya dengan data [CelesTrak](https://celestrak.org/NORAD/elements/) untuk satelit amatir:
     `https://celestrak.org/NORAD/elements/gp.php?GROUP=amateur&FORMAT=tle`
   - **Dari file:** unduh file TLE terlebih dahulu, lalu pilih **Menu > Import TLE (file)** dan pilih file tersebut.
2. Tekan **Start**, izinkan akses kamera dan lokasi, lalu tunggu GPS mendapatkan posisi.
3. Centang satelit pada daftar (bagian bawah layar, atau sisi kanan saat landscape). Gunakan kolom pencarian untuk menemukan satelit tertentu.
4. Arahkan ponsel ke langit mengikuti titik dan lintasan di layar. Untuk menampilkan planet, Bulan, komet, atau rasi bintang, buka **Menu > Space Object** lalu centang yang diinginkan.
5. Lain kali, buka aplikasi: TLE terakhir dan satelit yang Anda pilih langsung tampil kembali. Gunakan **Menu > Perbarui TLE (URL tersimpan)** untuk mengambil data orbit terbaru.

**Tips**
- Kalibrasi kompas dengan menggerakkan ponsel membentuk angka 8, dan jauhkan dari benda logam atau magnet.
- Perbarui TLE secara berkala. Usia TLE ditampilkan di kartu informasi (di atas 14 hari ditandai oranye) karena akurasi prediksi menurun seiring waktu.
- Pastikan jam ponsel diatur otomatis, karena perhitungan memakai waktu sistem.
- Jika layar terasa penuh, matikan checkbox **HUD info** (di bawah tombol Stop) atau hapus centang objek di **Menu > Space Object**.

## Kebutuhan

- Android 7.0 (API 24) atau lebih baru
- OpenGL ES 3.0
- Kamera belakang, GPS, dan sensor rotasi (umumnya ada di semua ponsel modern)
- Koneksi internet hanya diperlukan saat mengunduh TLE dari URL

## Izin yang diminta

| Izin | Kegunaan |
|---|---|
| Kamera | Menampilkan gambar kamera sebagai latar overlay AR |
| Lokasi (GPS) | Menentukan posisi pengamat untuk menghitung AOS/LOS dan arah satelit |
| Internet | Hanya untuk mengunduh file TLE dari URL yang Anda masukkan |

Aplikasi tidak meminta izin penyimpanan; file TLE dibuka lewat pemilih file Android. Aplikasi hanya mengunduh file TLE dari URL yang Anda tentukan dan tidak mengirim data apa pun (lokasi, gambar kamera, dan sebagainya) ke server.

## Data yang disimpan di ponsel

Semua disimpan di penyimpanan privat aplikasi dan terhapus bila aplikasi dihapus:

| Data | Isi |
|---|---|
| TLE terakhir | Salinan file TLE yang terakhir dimuat, untuk pemakaian offline |
| URL default | Alamat TLE yang terakhir dipakai mengunduh |
| Satelit terpilih | Nomor katalog satelit yang dicentang |
| Space Object | Status checklist Solar System, Comet, Rasi Bintang, dan HUD info |

## Batasan

- Ketepatan penempatan overlay bergantung pada sensor ponsel (umumnya beberapa derajat) dan perkiraan sudut pandang kamera.
- Posisi Matahari, Bulan, dan planet cukup teliti untuk overlay AR. Posisi **komet** dihitung dari elemen orbit tanpa gangguan planet sehingga hanya perkiraan kasar, dan sebagian besar komet terlalu redup untuk dilihat mata. Daftar komet bawaan bersifat tetap (tidak diunduh).
- **Jangan mengarahkan kamera atau mata ke Matahari tanpa filter khusus.**
- Unduhan TLE dari URL hanya mendukung alamat `https://`.
- Aplikasi masih berstatus **beta**. Jika menemukan masalah (misalnya arah gambar atau titik satelit tidak sesuai di perangkat tertentu), laporkan lewat **Issues** dengan menyebutkan tipe ponsel dan versi Android.
- Sebagian keyboard dengan saran teks/prediksi kadang tidak mengirim huruf dengan benar ke kolom pencarian atau kolom URL; matikan saran teks atau coba keyboard lain.

## Dibangun dengan

| Komponen | Teknologi | Fungsi |
|---|---|---|
| Bahasa | C++17 dan Java 11 | Logika dan UI di C++ (native), akses kamera/GPS/sensor di Java |
| Platform | Android 7.0+ (API 24), target SDK 34, Android NDK (NativeActivity) | ABI `arm64-v8a`, `armeabi-v7a`, `x86_64` |
| Antarmuka | [Dear ImGui](https://github.com/ocornut/imgui) 1.93.0 | Menu, daftar satelit, HUD, dan overlay |
| Grafik | OpenGL ES 3.0 (EGL) | Menggambar pratinjau kamera dan UI |
| Orbit satelit | SGP4 (kode referensi David Vallado) | Propagasi orbit dari TLE, AOS/LOS, titik sub-satelit |
| Astronomi | Modul sendiri (`astro.cpp`) dengan elemen Keplerian JPL | Posisi Matahari, Bulan, planet, komet, dan rasi bintang |
| Build | CMake 3.22.1, Gradle 8.9, Android Gradle Plugin 8.7.3 | Dibuka lewat Android Studio |

## Kredit

- **AMSAT-ID** — tim litbang pembuat aplikasi: <https://amsat-id.org/>
- [Dear ImGui](https://github.com/ocornut/imgui) — antarmuka (lisensi MIT)
- SGP4 — kode referensi David Vallado untuk propagasi orbit
- Posisi planet: elemen Keplerian JPL (E. M. Standish, 1800–2050); posisi Bulan: deret periodik singkat dari Astronomical Almanac
- Font [Roboto](https://fonts.google.com/specimen/Roboto) (Apache License 2.0)
- Data orbit (TLE): [AMSAT-ID](https://amsat-id.org/tle.txt) (default) dan [CelesTrak](https://celestrak.org/)
