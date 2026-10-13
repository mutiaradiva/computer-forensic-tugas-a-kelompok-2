# Computer Forensic - Linux Disk Image | Kelompok 2

## 1. Informasi Tugas

- **Kelompok pembuat image:** Kelompok 2
- **Sistem operasi:** Ubuntu Server 24.04 LTS
- **Virtualisasi:** Oracle VirtualBox
- **Format disk image:** RAW (`.img`)
- **Nama image:** `CF-Linux-Kel2.img`

Image ini disediakan untuk dianalisis oleh kelompok pasangan sesuai pembagian tugas dari dosen.

## 2. Spesifikasi Virtual Machine

| Komponen | Spesifikasi |
|---|---|
| Nama VM | `CF-Linux-Kel2` |
| Sistem Operasi | Ubuntu Server 24.04 LTS |
| RAM | 4096 MB |
| CPU | 2 core |
| Kapasitas virtual disk | 12 GB |
| Username Linux | `kelompokdua` |
| Format image akhir | RAW (`.img`) |

## 3. Unduh Disk Image

**Link disk image:** https://drive.google.com/file/d/1GcD4v8gGeG8yEtceU6wS_rEoqRN4FNGU/view?usp=sharing

Pastikan file image sudah diunduh sepenuhnya sebelum memulai analisis. Simpan salinan asli sebagai bukti awal dan lakukan pemeriksaan pada salinan kerja agar file sumber tetap terjaga.

## 4. Verifikasi Integritas Image

Disk image dikonversi dari virtual disk VirtualBox (`.vdi`) ke format RAW menggunakan `VBoxManage`.

- **Ukuran file:** 12.884.901.888 byte
- **Algoritma hash:** SHA-256

Nilai hash acuan:

```text
5CC32C430C9FF8730B2FD8D180968F8B91F857853E964A922DF89AFE88BDE6F7
```

Untuk memeriksa integritas file yang telah diunduh, jalankan PowerShell:

```powershell
Get-FileHash ".\CF-Linux-Kel2.img" -Algorithm SHA256
```

Bandingkan hasilnya dengan hash acuan di atas. Jika berbeda, periksa kembali file yang diunduh sebelum melakukan analisis.

## 5. Tujuan Analisis

Kelompok penerima diminta melakukan investigasi forensik terhadap disk image Linux untuk menjawab pertanyaan berikut:

1. **Identifikasi file target.** Temukan file yang relevan dengan tantangan, termasuk kemungkinan file tersembunyi, terhapus, atau termodifikasi.
2. **Identifikasi credential atau username.** Tentukan akun yang terkait dengan aktivitas terhadap file target berdasarkan bukti yang tersedia.
3. **Tentukan waktu kejadian.** Telusuri timestamp yang relevan dan jelaskan jenis timestamp yang digunakan, seperti waktu modifikasi konten atau perubahan metadata.
4. **Kumpulkan bukti pendukung.** Periksa metadata filesystem, permission, struktur direktori, log audit, dan artefak lain yang relevan jika tersedia.
5. **Susun kesimpulan.** Jelaskan temuan berdasarkan bukti yang ditemukan serta keterbatasan analisis.

Tidak semua aktivitas dijamin tercatat dalam log. Kesimpulan harus didasarkan pada bukti yang benar-benar tersedia di dalam image.

## 6. Panduan Umum Analisis

Gunakan perangkat dan metode forensik yang sesuai untuk memeriksa disk image RAW. Analisis dapat mencakup:

- Pemeriksaan struktur filesystem dan direktori tersembunyi.
- Pencarian file berdasarkan nama, ekstensi, metadata, dan isi.
- Pemeriksaan pemilik file serta permission.
- Pemeriksaan timestamp filesystem.
- Analisis log audit dan artefak sistem yang relevan.
- Pemeriksaan kemungkinan file terhapus atau perubahan yang masih dapat dibuktikan.

Catat setiap perintah, tools, hasil pemeriksaan, dan alasan yang mendukung kesimpulan. Hindari mengubah image asli selama proses analisis.

**Kelompok 2 — Computer Forensic**
