# Dompetku – Laporan Keuangan Pribadi

Aplikasi pencatat keuangan pribadi yang nyaman dipakai di HP. Ada dua versi di repository ini:

| Versi | Lokasi | Data disimpan di | Butuh Apps Script? |
|---|---|---|---|
| **Web app (GitHub Pages)** | `index.html` (root) | Browser di perangkat itu | Tidak |
| **Apps Script + Google Sheets** | `apps-script/` | Google Spreadsheet | Ya |

## Fitur

- **Dompet/rekening**: tambah, ubah, arsipkan, atau hapus. Ada saldo awal, ikon, dan warna.
- **Transaksi**: pemasukan, pengeluaran, dan transfer antar dompet. Saldo dihitung otomatis.
- **Kategori**: bisa diatur sendiri, termasuk anggaran bulanan per kategori.
- **Filter transaksi**: per bulan, jenis, dompet, kategori, dan kata kunci.
- **Analisis**:
  - Pemasukan, pengeluaran, rasio tabungan, dan perbandingan dengan bulan lalu.
  - Grafik per kategori, tren 6 bulan, dan pengeluaran harian.
  - Progres anggaran dan komposisi saldo.
  - Insight otomatis: proyeksi akhir bulan, kategori terbesar, dan perkiraan dana darurat.
- **Mode sembunyikan nominal** (👁️).

## 1. Web app (GitHub Pages)

Buka link GitHub Pages repository ini di HP. Di Chrome, pilih menu ⋮ lalu **Tambahkan ke layar utama**. Di Safari, pilih **Bagikan** lalu **Tambah ke Layar Utama**. Setelah dibuka sekali, aplikasi tetap bisa dibuka tanpa internet.

**Penting soal data:**
- Data tersimpan **di browser perangkat itu saja**. Data di HP dan laptop tidak otomatis sama.
- Buat cadangan rutin lewat **Atur → Cadangkan data**. Hasilnya file `.json`.
- Untuk pindah ke perangkat lain, pakai **Atur → Pulihkan dari cadangan** dengan file `.json` tadi.
- **Atur → Ekspor ke CSV** menghasilkan file yang bisa dibuka di Google Sheets atau Excel. Kolomnya sama dengan tab *Transaksi* di spreadsheet "Laporan Keuangan Pribadi".
- Menghapus data browser atau riwayat situs akan ikut menghapus data aplikasi ini. Pastikan sudah dicadangkan.

### Mengaktifkan GitHub Pages

1. Buka **Settings → Pages** di repository.
2. Pada *Source*, pilih **Deploy from a branch**.
3. Pilih branch `main` dan folder `/ (root)`, lalu klik **Save**.
4. Tunggu sekitar 1 menit. Linknya akan berbentuk `https://<username>.github.io/<nama-repo>/`.

## 2. Apps Script + Google Sheets

Versi ini menyimpan data langsung ke Google Spreadsheet. Pakai versi ini jika akun Google-mu mengizinkan Apps Script.

1. Buat Google Spreadsheet baru, lalu buka **Ekstensi → Apps Script**.
2. Tempel isi `apps-script/Code.gs` ke file `Code.gs`.
3. Tambahkan file HTML bernama `Index`, lalu tempel isi `apps-script/Index.html`.
4. Pilih **Terapkan → Deployment baru → Aplikasi web**, dengan *Jalankan sebagai: Saya* dan *Akses: Hanya saya sendiri*.
5. Buka link `/exec` di HP.

Sheet **Dompet**, **Transaksi**, dan **Kategori** dibuat otomatis saat aplikasi pertama kali dibuka.
