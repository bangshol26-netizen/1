# RUANGDIGITAL190 — Enhanced Digital Store

Versi pengembangan dari kode asli RUANGDIGITAL190. Identitas visual dan katalog produk dipertahankan; fitur belanja ditingkatkan dengan inspirasi pengalaman PremkuyStore.

## Yang dipertahankan
- 12 produk asli: 10 aplikasi dan 2 game.
- 25 varian Mobile Legends dan 23 varian Free Fire (20 diamond + 3 membership/BP Card).
- Seluruh harga, nama varian, deskripsi, dan status awal dari kode sumber tidak diubah.
- Logo RUANGDIGITAL190 dan seluruh logo produk dari unggahan ditanam langsung sebagai data URI di dalam `index.html`.
- Spotify dan YouTube memakai SVG inline lokal karena file logonya tidak termasuk gambar unggahan.
- Warna navy gelap, cyan, ungu, pink, dan gaya visual RUANGDIGITAL190 tetap dipertahankan.

## Fitur yang berfungsi langsung di GitHub Pages
- Katalog pilihan, pencarian, filter kategori, kategori cepat, pengurutan produk, detail produk, petunjuk pemesanan, dan pencarian varian.
- Tombol beli sekarang, kuantitas, keranjang, tambah/kurangi/hapus item, dan subtotal.
- Checkout tamu melalui WhatsApp dengan ringkasan produk, varian, harga, kuantitas, dan data game.
- Invoice lokal, riwayat pesanan pada browser yang sama, dan pencarian invoice lokal.
- Profil kontak lokal untuk mempercepat checkout (bukan akun online).
- Notifikasi lokal.
- FAQ yang dapat dicari.
- Pengajuan refund/garansi yang disiapkan untuk dikirim ke admin melalui WhatsApp.
- WhatsApp mengambang yang dapat digeser, navigasi responsif, dan tombol kembali ke atas.
- Ulasan tidak dipalsukan; area ulasan menjelaskan bahwa ulasan terverifikasi menunggu backend.

## Batasan teknis yang harus diketahui
GitHub Pages adalah hosting statis. Karena belum ada kredensial backend dan payment gateway, paket ini **tidak mengaktifkan** login/password online, saldo pelanggan, pembayaran QRIS otomatis, webhook, sinkronisasi riwayat lintas perangkat, upload bukti, moderasi ulasan online, maupun dashboard admin terlindungi. Tidak ada QRIS palsu atau status pembayaran palsu. Pesanan saat ini dikirim ke WhatsApp untuk konfirmasi manual dan invoice tersimpan lokal pada browser pengunjung.

Untuk mengaktifkan fitur tersebut dibutuhkan backend seperti Supabase (Auth, PostgreSQL, Storage, Edge Functions) serta akun payment gateway (misalnya Midtrans/Xendit), konfigurasi domain, secret server-side, SQL/RLS, dan webhook. Jangan menaruh secret key di HTML/JavaScript publik.

## Cara deploy
1. Unduh ZIP project dan ekstrak.
2. Unggah `index.html` dan `README.md` ke root repository `RuangDigital19` (file HTML ini sudah berdiri sendiri; tidak ada folder aset gambar yang wajib diunggah).
3. Commit ke branch `main`.
4. Pastikan GitHub Pages aktif melalui **Settings → Pages → Deploy from a branch → main → /(root)**.
5. Buka URL GitHub Pages setelah deployment selesai.

## Pengaturan toko
Di `index.html`, cari `STORE_CONFIG`. Ubah nomor WhatsApp hanya jika nomor admin memang berubah. Format nomor: kode negara tanpa tanda `+`, spasi, atau tanda hubung.

## Mengubah katalog
Cari `const PRODUCTS = [...]`. Data produk dan varian adalah sumber data utama. Harga `null` akan ditampilkan sebagai harga yang perlu dikonfirmasi admin, bukan Rp0. Untuk mengubah harga/stok, edit objek varian yang sesuai. Logo sudah tertanam pada `EMBEDDED_LOGOS`; tidak perlu mengunggah folder gambar.

## Pemeriksaan
- Sintaks JavaScript diperiksa dengan Node.js.
- Pemeriksaan HTML, jumlah produk/varian, referensi elemen, dan pemuatan gambar data URI dilakukan sebelum penyerahan.
- Pengujian browser dilakukan pada viewport desktop dan mobile.
- Integrasi backend/payment gateway tidak diklaim sudah diuji atau aktif.
