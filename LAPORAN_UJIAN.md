# Laporan UTS Web Software Tools

**Nama:**
**Nomor Induk Mahasiswa:**
**Kelas:**
**Tanggal:**

## A. Bukti pemeriksaan masalah
| Masalah | Alat yang digunakan | Bukti pemeriksaan | Perkiraan penyebab | Perbaikan | Hasil setelah perbaikan |
|---|---|---|---|---|---|
| Produk | Network + Console (DevTools), pemeriksaan kode (app.js vs server.mjs)|app.js:56 Gagal mengambil daftar produk: Error: Permintaan gagal
    at loadProducts (app.js:49:29)| URL fetch di public/app.js salah (/api/barang), api tidak cocok dengan rute server |Ubah fetch("/api/barang") menjadi fetch("/api/products"). | Network /api/products → 200 berisi 4 produk; daftar produk tampil dan status "4 produk tersedia"; Console bersih. |

| Tombol keranjang |Elements + Console (DevTools), pemeriksaan kode, style.css | Markup tombol memakai class="add-button" (app.js:24), tetapi listener dipasang ke querySelectorAll(".add-to-cart") (app.js:27). Console: document.querySelectorAll(".add-to-cart").length = 0. .add-button ditata di style.css:24.|Selector di JavaScript tidak cocok dengan kelas yang dirender, sehingga tidak ada listener terpasang | Ganti selector menjadi querySelectorAll(".add-button").| Klik tombol menambah barang; jumlah keranjang, daftar item, dan total berubah dengan sesuai.|

| Total belanja npm run test:once, npm run quality:check, pemeriksaan kode|✖ satu jenis barang dengan jumlah dua (6.9211ms)
  AssertionError [ERR_ASSERTION]: Expected values to be strictly equal: calculateTotal menjumlah item.price tanpa quantity; ada var discount tidak terpakai.| calculateTotal tidak mengalikan harga dengan jumlah barang. |cart.reduce((total, item) => total + item.price * item.quantity, 0);dan hapus var discount = 0;. | npm run test:once ℹ tests 7 ℹ suites 0 ℹ pass 7 ℹ fail 0 |

## B. Hasil pengujian
- Jumlah pengujian sebelum perbaikan:
- Jumlah pengujian berhasil setelah perbaikan:
- Catatan perubahan pada fungsi yang diperiksa:

## C. Kualitas kode
- Temuan sebelum perbaikan:
- Perbaikan yang dilakukan:
- Hasil pemeriksaan ulang:

## D. Git
- Branch (jika membuat):
- Ringkasan commit:
- Hasil pemeriksaan `git status`:

## E. Pemakaian kecerdasan buatan (jika digunakan)
- Nama alat:
- Pertanyaan/instruksi yang diberikan:
- Bagian jawaban yang diterapkan:
- Cara memeriksa apakah saran tersebut benar:

## F. Refleksi singkat
- Satu pelajaran paling penting dari ujian ini:
