# RUANGDIGITAL190 — Website Siap GitHub Pages

Semua logo yang dikirim sudah dimasukkan ke project. Website menggunakan versi WebP teroptimasi agar halaman lebih ringan, sementara file logo asli tetap disertakan di `assets/source-logos/`.

## Isi folder
- `index.html` — website utama.
- `assets/brand/` — logo RUANGDIGITAL190 dan favicon.
- `assets/logos/` — logo produk yang dipakai website (lokal, tidak bergantung pada CDN gambar).
- `assets/source-logos/` — salinan asli logo unggahan untuk arsip.

Logo unggahan yang dipakai: Netflix, Alight Motion, QuillBot, Canva, ChatGPT, Free Fire, Gemini, Grammarly, Mobile Legends, dan CapCut. Spotify dan YouTube memakai ikon SVG lokal karena file logo terpisahnya tidak ada di antara gambar yang diunggah.

## Cara upload
1. Download dan ekstrak ZIP.
2. Buka repository GitHub `RuangDigital19`.
3. Upload **semua isi folder ini** ke root repository. Pastikan `index.html` berada sejajar dengan folder `assets`.
4. Commit perubahan.
5. Pastikan GitHub Pages aktif melalui **Settings → Pages → Deploy from a branch → main → /(root)**.

## Edit produk
Di `index.html`, cari `STORE_CONFIG` untuk mengubah nomor WhatsApp dan informasi toko. Cari `PRODUCTS` untuk mengubah nama produk, harga, paket, dan status stok. Jangan menghapus folder `assets` karena semua logo website dibaca dari sana.

## Catatan sistem
Paket ini mempertahankan website katalog statis dan pemesanan via WhatsApp. Login pelanggan, saldo, checkout, QRIS otomatis, refund, dan dashboard admin berbasis database belum diaktifkan sebagai transaksi nyata.
