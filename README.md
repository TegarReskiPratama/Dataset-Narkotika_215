# Dataset Narkotika PN Pontianak

Paket **Soal Tugas 2, UTS Temu Kembali Informasi** berisi 50 putusan Pengadilan Negeri Pontianak tahun 2023-2025 beserta tabel barang bukti dan amar putusan.

| Identitas | Keterangan |
|---|---|
| Nama | Tegar Reski Pratama |
| NIM | 202310370311215 |
| Anggota | 1 mahasiswa |
| Repositori public | [Dataset-Narkotika_215](https://github.com/TegarReskiPratama/Dataset-Narkotika_215) |

## Isi paket

| Tahun | Jumlah PDF |
|---|---:|
| 2023 | 14 |
| 2024 | 20 |
| 2025 | 16 |
| **Total** | **50** |

- Pengadilan: **Pengadilan Negeri Pontianak** (`PN Ptk`).
- Cakupan isi: pidana khusus, narkotika dan psikotropika.
- Bahasa: Indonesia.
- Revisi tabel: 12 November 2026.
- Akuisisi: 50 PDF disediakan oleh penyusun; isi PDF disimpan utuh. Penamaan berkas di dalam arsip diseragamkan.

## Struktur repositori

```text
Dataset-Narkotika_215/
├── Dataset/
│   └── Narkotika.zip
├── Overview/
│   └── Overview.xlsx
├── Dokumentasi/
│   ├── Manifest.csv
│   └── Sumber_Putusan.md
├── .gitattributes
├── .gitignore
└── README.md
```

`Narkotika.zip` memuat folder `Narkotika/2023`, `Narkotika/2024`, dan `Narkotika/2025`. Nama berkas mengikuti pola `<nomor>_Pid.Sus_<tahun>_PN_Ptk.pdf`. Manifest mencatat pemetaan nama asli, lokasi dalam arsip, ukuran, dan checksum setiap PDF.

## Tabel Overview

Buka [Overview.xlsx](Overview/Overview.xlsx). Lembar **Overview** memuat 50 entri bernomor 1-50 dengan susunan sesuai contoh soal:

| Kolom | Isi |
|---|---|
| No | Nomor urut putusan |
| No Putusan | Nomor perkara lengkap |
| Lembaga Peradilan | PN Pontianak |
| Barang Bukti | Rincian barang bukti yang ditetapkan dalam amar akhir |
| Amar Putusan | Seluruh butir amar akhir, termasuk pidana, denda, pidana pengganti, penahanan, tindakan atas barang bukti, dan biaya perkara |

Tampilan menggunakan **Times New Roman**, latar putih, garis tabel hitam, judul kolom tebal di tengah, dan isi rata atas. Tinggi tabel menyesuaikan panjang teks agar daftar barang bukti dan amar terbaca lengkap.

Lembar **Sumber** memuat lokasi PDF dalam arsip, halaman amar, metode pencocokan, URL sumber, dan catatan isi per perkara.

## Sumber dan pengolahan

1. Dokumen sumber: [Direktori Putusan Mahkamah Agung RI](https://putusan3.mahkamahagung.go.id/). URL setiap perkara diekstrak dari QR pada PDF.
2. Teks PDF diekstrak langsung untuk 32 berkas; 18 berkas gambar dibaca menggunakan OCR.
3. Amar akhir 50 perkara dicocokkan melalui [SIPP PN Pontianak](https://sipp.pn-pontianak.go.id/) menggunakan nomor putusan yang sesuai.
4. Kolom Barang Bukti diambil dari daftar dalam amar hakim, sehingga tidak mencampurkan barang pada tuntutan atau perkara lain.
5. Spasi dan pemisah paragraf dirapikan. Rincian daftar barang bukti serta butir amar dipertahankan; daftar panjang tetap disertakan.

PDF sumber tetap menjadi acuan naskah lengkap. Ketidakkonsistenan angka atau redaksi yang memang terdapat pada sumber tidak diganti berdasarkan perkiraan. Catatan per perkara tersedia di [Sumber_Putusan.md](Dokumentasi/Sumber_Putusan.md).

## Integritas arsip

- Jumlah: **50 PDF unik**.
- Ukuran: **303.08 MB**.
- Pemeriksaan CRC arsip dan kecocokan SHA-256 tiap PDF dengan dokumen asal telah dilakukan.
- SHA-256 `Dataset/Narkotika.zip`:

```text
e6c5ad0cd3344951034bf6ed2746d6676e35a572ea7c29cf3073f4ce421cf457
```

## Cara mengunduh

1. Buka [Dataset/Narkotika.zip](Dataset/Narkotika.zip) dan gunakan tombol unduh berkas untuk memperoleh arsip PDF asli.
2. Ekstrak arsip, lalu cocokkan nomor perkara dengan tabel Excel.
3. Gunakan tautan dan halaman pada lembar Sumber untuk menelusuri dokumen asal.

Arsip PDF menggunakan **Git LFS** karena ukurannya melebihi batas berkas Git biasa. Jika mengkloning repositori, jalankan `git lfs pull`. Unduhan ZIP kode sumber yang dibuat GitHub tidak selalu menyertakan objek LFS.

Dokumentasi: [Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage).

## Pengumpulan

Hyperlink repositori: https://github.com/TegarReskiPratama/Dataset-Narkotika_215

Nama repositori menggunakan tiga digit terakhir NIM penyusun, yaitu `215`. Gunakan hyperlink repositori untuk pengumpulan melalui LMS sesuai arahan dosen.
