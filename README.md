# Nararya Groub Strobo Generator Website

Website tools berbasis HTML, CSS, dan JavaScript murni. Tidak membutuhkan framework atau proses build.

## Fitur
- **Strobo Generator:** pola alternate, full screen, quad, pulse, dan split; warna A/B; kecepatan; kecerahan; ukuran panel; glow; label.
- **Image Motion Studio:** unggah PNG/JPG/WebP; preset Zoom In/Out, Pan, Rotasi, Floating, Shake, Fade, dan Ken Burns; pengaturan animasi manual bergaya keyframe (zoom awal/akhir, posisi X/Y, rotasi), transisi masuk/keluar (fade, zoom, slide, rotate), durasi, intensitas, cover/contain, latar, FPS, timeline, ekspor PNG dan WebM.\n- **Running Text Generator:** teks kustom, warna teks/latar/glow, kecepatan, ukuran dan ketebalan font, gaya LED glow/outline/solid/rainbow, bingkai.
- Pengaturan tersimpan otomatis di browser saat kontrol berubah; proyek juga bisa diekspor/impor sebagai JSON.
- Ukuran canvas kustom, preset rasio, ekspor batch PNG, dan mode terang/gelap.
- Asisten prompt lokal berbasis aturan untuk menerapkan preset animasi. Ini bukan model AI generatif dan tidak mengklaim data cloud real-time.
- Preview canvas secara langsung.
- Ekspor preview menjadi PNG.
- Rekam animasi menjadi WebM di browser yang mendukung Canvas Capture Stream dan MediaRecorder.
- Responsive untuk HP dan desktop.

## Struktur
```
.
├── index.html
├── strobo.html
├── running-text.html
├── image-motion.html
├── assets/
│   ├── style.css
│   ├── strobo.js
│   └── running-text.js
└── README.md
```

## Menjalankan lokal
Buka `index.html` di browser. Untuk pengalaman terbaik, jalankan lewat GitHub Pages atau server statis sederhana.

## GitHub Pages
Di repository, buka **Settings → Pages**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu simpan. Setelah proses deployment selesai, website dapat dibuka lewat URL GitHub Pages yang ditampilkan di halaman tersebut.

## Batasan yang perlu diketahui
- Website saat ini statis dan berjalan di browser. Belum ada backend/database, layanan AI generatif, pembayaran QRIS sungguhan, verifikasi pembayaran, atau konfirmasi WhatsApp.
- Autosave hanya tersimpan di browser/perangkat yang digunakan; tidak disinkronkan lintas perangkat.
- Perubahan kode masuk ke repository melalui commit GitHub; workflow otomatis menguji perubahan setelah push, tetapi tidak menciptakan fitur baru sendiri.

## Catatan keselamatan
Efek strobo berkedip cepat dapat memicu ketidaknyamanan atau kejang pada orang yang sensitif terhadap cahaya. Jangan gunakan efek ini untuk mengganggu pengguna jalan atau pengendara.

© 2026 Nararya Groub. All rights reserved.


## Build dan pemeriksaan browser
- Repository ini adalah website statis, jadi tidak memerlukan proses kompilasi aplikasi.
- GitHub Actions menjalankan smoke test browser pada setiap push ke `main`, pull request ke `main`, dan dapat dijalankan manual dari tab **Actions**.
- Jika tes berhasil, screenshot desktop dan mobile tersedia sebagai artifact bernama `nararya-visual-test-screenshots` pada workflow run.
- Buka **Actions → Build and Visual Smoke Test → run terbaru → Artifacts** untuk mengunduh screenshot hasil tes.


## Otomasi, verifikasi, dan integrasi data

- GitHub Actions menjalankan pengujian browser saat ada push ke `main`, pull request, atau pemicu manual. Hasil sukses/gagal terlihat pada tab **Actions**; workflow tidak membuat fitur baru secara mandiri.
- Tes browser memeriksa homepage, generator strobo, running text, Image Motion Studio, kontrol animasi, autosave lokal, manifest PWA, ikon aplikasi, dan registrasi service worker. Screenshot tes diunggah sebagai artifact bila dihasilkan.
- **Scraper tidak dipasang secara membabi buta.** Generator strobo, running text, dan animasi gambar bekerja dari input pengguna di browser, sehingga tidak membutuhkan data eksternal/API. Mengambil data dari 10 situs tanpa kebutuhan sumber yang jelas tidak meningkatkan akurasi fitur ini.
- Jika kelak ada fitur yang benar-benar membutuhkan data eksternal, gunakan adapter sumber yang terpisah, timeout, validasi skema, cache dengan waktu pembaruan, batas percobaan, pencatatan sumber, dan fallback ke sumber lain. Sepuluh adapter hanya masuk akal jika ada sepuluh sumber relevan yang diizinkan dan dapat diuji.
- **Fallback bukan berarti mengganti scraper dengan AI secara otomatis.** Model AI harus dikonfigurasi melalui backend/proxy yang aman dengan API key tersimpan sebagai GitHub Actions secret atau secret penyedia hosting. Jangan menaruh API key di HTML/JavaScript publik. Hasil AI perlu ditandai sebagai hasil model, bukan data terverifikasi.
- Data real-time dan akurasi 100% tidak dapat dijamin secara universal. Status sumber, timestamp, validasi, dan kegagalan koneksi harus ditampilkan secara jujur. Saat ini aplikasi tidak memiliki backend, API eksternal, scraper aktif, atau layanan AI generatif.
