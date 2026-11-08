# Build APK Weatherglass TV untuk Android TV / ZTE B860H

Proyek ini sudah dilengkapi workflow GitHub Actions untuk membangun APK secara online, sehingga tidak perlu memasang Android SDK di HP.

## Cara membuat APK dari HP Android

1. Ekstrak ZIP ini.
2. Buat repository baru di GitHub (misalnya `weatherglass-tv-b860h`).
3. Upload seluruh isi folder proyek hasil ekstrak ke repository tersebut. Pastikan folder `.github/workflows` ikut ter-upload.
4. Buka tab **Actions** pada repository.
5. Pilih **Build Weatherglass TV APK** lalu tekan **Run workflow** (jika workflow belum berjalan otomatis).
6. Tunggu sampai proses selesai dengan status hijau.
7. Buka hasil run, bagian **Artifacts**, lalu unduh `Weatherglass-TV-APK`.
8. Ekstrak file ZIP artifact. Di dalamnya ada `FreeMyTV.apk`.
9. Kirim APK ke ZTE B860H dan instal. Jika diminta, izinkan pemasangan dari sumber tidak dikenal.

## Catatan kompatibilitas

- Minimum Android 9 (API 28), target build Android 13 (API 33).
- Manifest menyediakan kategori Leanback/Android TV dan layar Home.
- Tidak memerlukan root.
- Konfigurasi contoh memakai Bahasa Indonesia otomatis, wilayah ID, suhu Celsius, prayer times, dan Live Weather.
- Koordinat contoh pada `config.example.properties` masih Jakarta. Setelah instalasi, ubah kota/koordinat melalui Settings → Widgets → City agar cuaca dan waktu salat sesuai lokasi.

## Catatan keamanan dan pembaruan

APK ditandatangani dengan keystore debug proyek yang dibuat saat build. Simpan keystore `freemytv.keystore` bila membangun sendiri secara lokal. Jika workflow dijalankan ulang di runner baru, tanda tangan dapat berbeda; Android mungkin menolak pembaruan langsung di atas versi yang sudah terpasang. Untuk instalasi ulang seperti itu, hapus versi lama terlebih dahulu (pengaturan dan data aplikasi dapat hilang).
