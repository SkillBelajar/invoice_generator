# Invoice Generator

Invoice generator satu file HTML. Tanpa build, tanpa dependency, tanpa install.

## Pakai

Buka `index.html` di browser. Isi form, klik **Print / Save PDF** untuk cetak atau simpan sebagai PDF (dialog print → "Save as PDF").

Atau serve lokal:

```bash
python3 -m http.server 8080
# buka http://localhost:8080
```

## Fitur

- Header nomor, tanggal, jatuh tempo (default hari ini + 14 hari), mata uang
- Data "Dari" dan "Ditagihkan ke"
- Item dinamis: deskripsi, qty, harga, jumlah otomatis
- Subtotal, pajak persen, diskon, total
- Hitung otomatis saat mengetik
- Draft simpan/muat via `localStorage`
- CSS print: toolbar dan tombol hapus disembunyikan, input jadi teks polos

## Batasan

- Satu invoice per draft (key `invoice-generator-draft`). Multi-invoice butuh perubahan skema storage.
- Format angka `id-ID`. Ubah locale di `fmt()` untuk format lain.
- Tanpa backend — data tidak keluar dari browser.
