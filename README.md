# QR Generator 171 — by Tank171 app

Satu aplikasi QR (buat + baca, 100% offline), dua target build:

| Folder | Hasil build |
| --- | --- |
| `android-app/` | APK Android — file hasilnya bernama `QR Generator 171.apk` |
| `pc-app/` | Installer & versi portable Windows (`.exe`) |
| `web/index.html` | Aplikasinya sendiri (satu file, offline) |
| `icons/` | Logo & ikon aplikasi, dipakai otomatis oleh kedua build |

## Cara build (tanpa coding)

1. Buat repo baru di GitHub (gratis), pilih **Public**.
2. Upload **semua isi folder ini** — termasuk `.github`, `web`, `icons`, `android-app`, `pc-app`.
   - Kalau seret folder ditolak, upload file satu per satu lewat **Add file → Upload files** (folder `.github/workflows` harus ikut).
3. Buka tab **Actions** → kalau ada tombol *"I understand my workflows"*, klik.
4. Pilih workflow yang mau dijalankan, lalu **Run workflow**:
   - **Build APK (Android)** → sekitar 5–8 menit
   - **Build EXE (Windows)** → sekitar 5–10 menit
5. Setelah hijau, buka run tersebut → bagian **Artifacts**:
   - `QR-Generator-171-APK` → berisi **`QR Generator 171.apk`**
   - `QR-Generator-171-Windows` → berisi **installer** dan **portable** `.exe`
6. **Android:** kirim APK ke HP → buka → izinkan *"Install unknown apps"* → Install. Ikon di layar HP langsung memakai logo **QR**.
7. **Windows:** jalankan `QR-Generator-171-setup-1.0.0.exe` (terinstall, ada shortcut) atau `QR-Generator-171-portable-1.0.0.exe` (langsung jalan tanpa install).

## Isi aplikasi

- **Buat QR**: teks/link, level koreksi L/M/Q/H, ukuran sampai 1024 px, warna + tukar, unduh PNG & SVG, salin gambar.
- **Baca QR**: scan kamera, ambil dari galeri, seret-lepas gambar, atau tempel (Ctrl+V). Hasil bisa disalin atau dipakai untuk membuat QR baru.
- **Splash selamat datang** dengan logo QR + nama aplikasi + brand *by Tank171 app*.
- Tombol **?** di kanan atas berisi brand dan versi aplikasi.
- **Bahasa**: tombol **ID / EN** di kanan atas; pilihan diingat di perangkat itu.
- Tanpa iklan, tanpa akun, tanpa koneksi internet.

## Buka di mana saja

- `web/index.html` adalah satu file mandiri: tidak butuh internet, server, atau instalasi apa pun.
  Dobel-klik di Windows/Mac/Linux, kirim ke HP, atau host gratis (GitHub Pages, Netlify, Cloudflare Pages)
  — hasilnya sama.
- Sudah diuji di Chrome. Dirancang netral browser: jalan juga di Edge, Firefox, dan Safari (iOS/macOS),
  tanpa API khusus Chrome.
- **Kamera** hanya aktif kalau halaman dibuka lewat **https** atau sebagai file lokal; di alamat `http://`
  browser memblokirnya. Tombol **Ambil dari galeri** tetap jalan di semua kondisi.
- Kalau di-host di GitHub Pages: buat repo, upload isi folder ini, lalu **Settings → Pages → Deploy from branch**
  (folder `/root`) dan buka `https://nama-akun.github.io/nama-repo/web/`.

## Catatan

- **Kamera di Android**: izin `CAMERA` ditambahkan otomatis oleh workflow. Kalau kamera tetap tidak muncul di HP tertentu, pakai **Ambil dari galeri** — hasil bacanya sama.
- **Kamera di Windows**: Electron sudah mengizinkan akses media.
- APK memakai **tanda tangan debug** — cukup untuk dipakai sendiri dan dibagikan langsung. Untuk Play Store perlu signing key tersendiri.
- EXE belum ditandatangani, jadi Windows bisa menampilkan SmartScreen → **More info → Run anyway**.
- Mau ubah aplikasi? Edit `web/index.html`, commit, lalu jalankan workflow lagi — ikon dan nama aplikasi tetap.
