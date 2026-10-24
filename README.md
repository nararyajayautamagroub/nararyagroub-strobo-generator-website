# Nararya Groub Strobo Generator Website

Website tools berbasis HTML, CSS, dan JavaScript murni. Tidak membutuhkan framework atau proses build.

## Fitur
- **Strobo Generator:** pola alternate, full screen, quad, pulse, dan split; warna A/B; kecepatan; kecerahan; ukuran panel; glow; label.
- **Image Motion Studio:** unggah PNG/JPG/WebP; preset Zoom In/Out, Pan, Rotasi, Floating, Shake, Fade, dan Ken Burns; pengaturan animasi manual bergaya keyframe (zoom awal/akhir, posisi X/Y, rotasi), transisi masuk/keluar (fade, zoom, slide, rotate), durasi, intensitas, cover/contain, latar, FPS, timeline, ekspor PNG dan WebM.\n- **Running Text Generator:** teks kustom, warna teks/latar/glow, kecepatan, ukuran dan ketebalan font, gaya LED glow/outline/solid/rainbow, bingkai.
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

## Catatan keselamatan
Efek strobo berkedip cepat dapat memicu ketidaknyamanan atau kejang pada orang yang sensitif terhadap cahaya. Jangan gunakan efek ini untuk mengganggu pengguna jalan atau pengendara.

© 2026 Nararya Groub. All rights reserved.


## Build dan pemeriksaan browser
- Repository ini adalah website statis, jadi tidak memerlukan proses kompilasi aplikasi.
- GitHub Actions menjalankan smoke test browser pada setiap push ke `main` dan dapat dijalankan manual dari tab **Actions**.
- Jika tes berhasil, screenshot desktop dan mobile tersedia sebagai artifact bernama `nararya-visual-test-screenshots` pada workflow run.
- Buka **Actions → Build and Visual Smoke Test → run terbaru → Artifacts** untuk mengunduh screenshot hasil tes.
