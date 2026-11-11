# Dataset Narkotika PN Pontianak

Dataset 50 putusan Pengadilan Negeri Pontianak tahun 2023-2025 untuk **Soal Tugas 2, UTS Temu Kembali Informasi**, Universitas Muhammadiyah Malang.

| Identitas penyusun | Keterangan |
|---|---|
| Nama | Tegar Reski Pratama |
| NIM | 202310370311215 |
| Anggota | 1 mahasiswa |
| Repositori public | [Dataset-Narkotika_215](https://github.com/TegarReskiPratama/Dataset-Narkotika_215) |

> **Status kelengkapan:** berkas dataset, ringkasan 50 putusan, dan dokumentasi telah disiapkan. Syarat tidak menggunakan putusan berkekuatan hukum tetap (BHT) **belum terverifikasi**. Gunakan tautan setiap perkara pada lembar `Sumber` untuk memeriksa status resmi sebelum pengumpulan. Nama PN juga perlu dipastikan tidak digunakan kelompok lain.

## Isi dataset

| Tahun nomor perkara | Jumlah PDF | Lapisan teks dapat diekstrak | Memerlukan OCR gambar |
|---|---:|---:|---:|
| 2023 | 14 | 14 | 0 |
| 2024 | 20 | 9 | 11 |
| 2025 | 16 | 9 | 7 |
| **Total** | **50** | **32** | **18** |

- **Pengadilan:** Pengadilan Negeri Pontianak (`PN Ptk`).
- **Cakupan isi:** perkara narkotika dan psikotropika dalam pidana khusus, meliputi sabu, ekstasi, ganja, serta barang lain yang ditetapkan dalam amar.
- **Bahasa dokumen:** bahasa Indonesia.
- **Sumber:** [Direktori Putusan Mahkamah Agung RI](https://putusan3.mahkamahagung.go.id/). URL detail 50 perkara diambil dari QR yang tercantum pada setiap PDF.
- **Akuisisi:** 50 PDF disediakan oleh penyusun di folder `Putusan PN PONTIANAK`. Isi PDF disimpan utuh; penamaan di dalam ZIP diseragamkan.
- **Tanggal penyusunan paket:** 12 November 2026.

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

Di dalam `Narkotika.zip`:

```text
Narkotika/
├── 2023/   (14 PDF)
├── 2024/   (20 PDF)
└── 2025/   (16 PDF)
```

Nama PDF mengikuti pola `<nomor>_Pid.Sus_<tahun>_PN_Ptk.pdf`, misalnya `507_Pid.Sus_2023_PN_Ptk.pdf`. Pemetaan ke nama asli tercantum dalam `Dokumentasi/Manifest.csv`.

## Ringkasan putusan

Buka [Overview/Overview.xlsx](Overview/Overview.xlsx). Lembar **Overview** berisi tepat satu baris per putusan dan lima kolom sesuai contoh soal:

| Kolom | Isi |
|---|---|
| No | Nomor urut 1-50 |
| No Putusan | Nomor perkara dan pengadilan |
| Lembaga Peradilan | PN Pontianak |
| Barang Bukti | Jenis, jumlah, berat/satuan, dan rincian penting barang bukti dari amar |
| Amar Putusan | Pernyataan kesalahan, pidana, denda dan penggantinya jika ada, penahanan, tindakan atas barang bukti, serta biaya perkara |

Lembar **Sumber** menyediakan berkas PDF, halaman amar, metode ekstraksi, URL resmi, status BHT, kolom bukti status, dan catatan khusus. Lembar ini dipakai untuk mencocokkan ringkasan dengan dokumen sumber. Filter tabel dapat digunakan untuk mencari nomor perkara atau status.

## Cara penyusunan ringkasan

1. Memeriksa jumlah berkas, nomor perkara, tahun, dan kesamaan pengadilan.
2. Mengambil bagian amar akhir setelah judul `MENGADILI`. Tuntutan penuntut umum pada bagian awal putusan dipisahkan dari amar hakim.
3. Mengekstrak lapisan teks pada 32 PDF. Sebanyak 18 PDF gambar dibaca dengan OCR dan pemeriksaan halaman amar.
4. Merapikan spasi, pemisah butir, dan kesalahan pembacaan yang dapat dicocokkan dengan gambar. Daftar yang panjang diringkas dengan mempertahankan jenis barang, angka penting, sanksi, serta tindakan hakim.
5. Menyimpan sumber per baris dan memverifikasi bahwa isi 50 PDF dalam ZIP identik dengan berkas asal melalui SHA-256.

Isi Excel merupakan **ringkasan**, bukan salinan verbatim seluruh putusan. Identitas teknis panjang seperti IMEI dapat disingkat. PDF sumber tetap menjadi acuan untuk rincian lengkap. Pada amar panjang, daftar barang bukti tidak selalu diulang di kedua kolom.

### Catatan yang perlu diperhatikan

- **649/2023:** amar mencantumkan 37 klip sabu dengan beberapa angka sisa yang tidak konsisten dengan berat awal (antara lain 0,5; 0,6; dan 0,4 gram). Angka sumber dipertahankan dan tidak dikoreksi berdasarkan perkiraan. Kolom Barang Bukti memuat pasangan berat awal/sisa per klip.
- **678/2025 dan 679/2025:** terdapat ketidakkonsistenan aritmetika berat pada sumber. Angka tidak dihitung ulang untuk mengganti isi putusan.
- **550/2025 dan 551/2025:** daftar barang bukti dalam amar tidak mencantumkan sabu; barang dari tuntutan atau perkara terkait tidak ditambahkan ke daftar amar perkara ini.
- **657/2024 dan 664/2024:** nomor halaman tercetak berbeda dari indeks halaman PDF. Acuan pada lembar Sumber memakai indeks PDF mulai dari 1.
- **701/2024 dan 702/2024:** ada perbedaan redaksi berat pada rumusan tindak pidana dan daftar barang bukti. Lihat catatan sumber per perkara.
- Keterangan **tetap ditahan** pada amar bukan penetapan status BHT. Ketiadaan kata `inkracht` dalam PDF juga tidak dipakai sebagai bukti status belum BHT.

## Pemeriksaan status BHT

Semua 50 baris mula-mula diberi status **Belum diverifikasi**. Laman resmi yang berhasil terbaca belum menyediakan bukti yang cukup untuk mengesahkan status akhir setiap perkara; sebagian akses detail juga tidak dapat dibaca oleh alat penelusuran.

Sebelum pengumpulan:

1. Buka URL resmi pada lembar Sumber dan cocokkan nomor perkara.
2. Periksa status perkara pada Direktori MA atau [SIPP PN Pontianak](https://sipp.pn-pontianak.go.id/).
3. Simpan tautan atau bukti status pada kolom **Bukti status**; ubah status hanya jika ada bukti yang sesuai.
4. Jika perkara terbukti BHT, ganti PDF tersebut dengan perkara yang memenuhi ketentuan, lalu perbarui ringkasan dan ZIP sehingga tetap berisi 50 putusan.

Status yang belum diketahui tidak dinyatakan sebagai belum BHT. Paket ini belum menyatakan seluruh syarat seleksi status telah terpenuhi.

## Integritas berkas

- Jumlah dokumen dalam arsip: **50 PDF unik**.
- Ukuran arsip: **303.08 MB** (289.04 MiB).
- SHA-256 `Dataset/Narkotika.zip`:

```text
e6c5ad0cd3344951034bf6ed2746d6676e35a572ea7c29cf3073f4ce421cf457
```

Checksum masing-masing PDF, ukuran byte, nama asli, dan lokasi dalam arsip tersedia pada [Manifest.csv](Dokumentasi/Manifest.csv). Pemeriksaan CRC ZIP serta kecocokan SHA-256 tiap PDF telah dijalankan.

## Menggunakan dataset

1. Unduh `Dataset/Narkotika.zip` dan ekstrak arsipnya.
2. Buka `Overview/Overview.xlsx` untuk melihat ringkasan atau gunakan nomor perkara sebagai kunci penghubung ke PDF.
3. Gunakan lembar Sumber atau [Sumber_Putusan.md](Dokumentasi/Sumber_Putusan.md) untuk menelusuri halaman amar dan URL asal.

Dataset dapat digunakan untuk mempelajari metadata dokumen hukum, ekstraksi informasi, dan temu kembali informasi. Ringkasan mengikuti putusan sumber dan tidak menggantikan pembacaan naskah lengkap.

## Berkas besar dan GitHub

Arsip melebihi batas berkas Git biasa **100 MiB**. Berkas `.gitattributes` telah menandai `Dataset/Narkotika.zip` untuk **Git LFS**. Saat mengunggah melalui Git, aktifkan Git LFS sebelum menambahkan berkas. Simpan objek LFS beserta pointer Git-nya agar pengunduh memperoleh arsip asli.

Dokumentasi resmi: [batas berkas GitHub](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-large-files-on-github) dan [Git LFS](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage).

Repositori **public**: [TegarReskiPratama/Dataset-Narkotika_215](https://github.com/TegarReskiPratama/Dataset-Narkotika_215).

Untuk memperoleh arsip asli, buka [Dataset/Narkotika.zip](Dataset/Narkotika.zip) lalu gunakan tombol unduh berkas, atau jalankan `git lfs pull` setelah mengkloning repositori. Jangan menganggap unduhan ZIP kode sumber GitHub otomatis menyertakan objek LFS.

Setelah verifikasi seleksi perkara selesai, kumpulkan hyperlink repositori melalui LMS sesuai ketentuan dosen. Untuk tugas individu, penamaan menggunakan tiga digit akhir satu NIM, yaitu `215`.
