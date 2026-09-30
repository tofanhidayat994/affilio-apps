# Affilio — Pantau Komisi Harian

Aplikasi PWA untuk memantau posting & komisi harian akun Shopee/TikTok/lainnya,
dengan kelola akun dinamis (tambah/hapus akun, deteksi logo otomatis) dan target
harian. Data tersimpan lokal di perangkat (localStorage), jalan offline, dan
bisa dipasang sebagai aplikasi Android.

## Langkah 1 — Deploy ke GitHub Pages

1. Buka https://github.com, login (atau daftar dulu kalau belum punya akun).
2. Klik ikon **+** di kanan atas → **New repository**.
3. Isi:
   - Repository name: `affilio-app`
   - Pilih **Public**
   - JANGAN centang "Add a README file"
   - Klik **Create repository**
4. Di halaman repo baru, klik link **"uploading an existing file"**
   (atau tombol **Add file → Upload files**).
5. Ekstrak/unzip file `affilio-pwa.zip` yang saya kirim, lalu **seret semua isi
   folder `affilio-pwa2`** (index.html, manifest.json, sw.js, icon-192.png,
   icon-512.png, README.md) ke kotak upload GitHub.
6. Scroll ke bawah, klik **Commit changes**.
7. Buka tab **Settings** (menu atas) → **Pages** (sidebar kiri).
8. Di **Build and deployment → Source**: pilih **Deploy from a branch**.
   Branch: **main**, folder **/ (root)** → **Save**.
9. Tunggu 1–2 menit, refresh halaman itu. Akan muncul kotak hijau:
   "Your site is live at `https://<username>.github.io/affilio-app/`"
10. Buka link itu, pastikan aplikasinya tampil dan berfungsi normal.

## Langkah 2 — Bungkus jadi APK dengan PWA Builder

1. Buka https://www.pwabuilder.com
2. Masukkan URL GitHub Pages kamu dari Langkah 1 → klik **Start**.
3. Tunggu PWA Builder membaca `manifest.json` (skor akan muncul, biasanya
   langsung hijau/oke karena manifest & ikon sudah lengkap).
4. Klik **Package for stores → Android**.
5. Pilihan default sudah cukup untuk pemakaian pribadi/sideload:
   - Package ID: biarkan default atau ganti sesuai selera
   - Signing key: biarkan **"Generate new signing key"**
     (⚠️ kalau nanti berniat publish ke Play Store, signing key
     WAJIB sama terus di setiap update — jangan hilangkan filenya)
6. Klik **Generate**, lalu **Download** — kamu akan dapat file `.apk`
   (dan `.aab` kalau suatu saat mau upload ke Play Store).

## Langkah 3 — Pasang APK di HP Android

1. Pindahkan file `.apk` ke HP (kabel USB, Google Drive, WhatsApp ke diri
   sendiri, dll).
2. Buka file `.apk` itu di HP.
3. Kalau muncul peringatan, izinkan **"Install from unknown sources"**
   untuk aplikasi yang kamu pakai membuka file itu (mis. Chrome/Files).
4. Tekan **Install** → selesai, ikon Affilio muncul di app drawer.

## Catatan penting

- Data tersimpan **per perangkat** (localStorage) — tidak otomatis
  sinkron antar HP. Kalau install di 2 HP berbeda, datanya terpisah.
- Simpan file signing key hasil PWA Builder baik-baik kalau berencana
  update aplikasi ini nanti lewat PWA Builder lagi.
- Kalau nanti ada revisi aplikasi (fitur baru dll.), ulangi: update file
  di GitHub (Upload files lagi dengan nama sama → otomatis timpa) →
  GitHub Pages otomatis ter-update dalam ~1 menit → generate ulang APK
  di PWA Builder kalau perlu versi APK terbaru juga.
