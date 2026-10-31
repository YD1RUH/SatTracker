# SatTracker

<p align="center">
  <img src="https://github.com/YD1RUH/SatTracker/blob/main/image.png?raw=true" width="50%" alt="Tampilan SatTracker">
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
- **Auto rotate** — mengikuti rotasi ponsel.
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
4. Arahkan ponsel ke langit mengikuti titik dan lintasan di layar.
5. Lain kali, buka aplikasi: TLE terakhir dan satelit yang Anda pilih langsung tampil kembali. Gunakan **Menu > Perbarui TLE (URL tersimpan)** untuk mengambil data orbit terbaru.

**Tips**
- Kalibrasi kompas dengan menggerakkan ponsel membentuk angka 8, dan jauhkan dari benda logam atau magnet.
- Perbarui TLE secara berkala. Usia TLE ditampilkan di kartu informasi (di atas 14 hari ditandai oranye) karena akurasi prediksi menurun seiring waktu.
- Pastikan jam ponsel diatur otomatis, karena perhitungan memakai waktu sistem.

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

## Batasan

- Ketepatan penempatan overlay bergantung pada sensor ponsel (umumnya beberapa derajat) dan perkiraan sudut pandang kamera.
- Unduhan TLE dari URL hanya mendukung alamat `https://`.
- Aplikasi masih berstatus **beta**. Jika menemukan masalah (misalnya arah gambar atau titik satelit tidak sesuai di perangkat tertentu), laporkan lewat **Issues** dengan menyebutkan tipe ponsel dan versi Android.
- Sebagian keyboard dengan saran teks/prediksi kadang tidak mengirim huruf dengan benar ke kolom pencarian atau kolom URL; matikan saran teks atau coba keyboard lain.

## Kredit

- **AMSAT-ID** — tim litbang pembuat aplikasi: <https://amsat-id.org/>
- [Dear ImGui](https://github.com/ocornut/imgui) — antarmuka (lisensi MIT)
- SGP4 — kode referensi David Vallado untuk propagasi orbit
- Font [Roboto](https://fonts.google.com/specimen/Roboto) (Apache License 2.0)
- Data orbit (TLE): [AMSAT-ID](https://amsat-id.org/tle.txt) (default) dan [CelesTrak](https://celestrak.org/)
