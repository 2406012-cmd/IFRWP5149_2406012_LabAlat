# Laporan Pertemuan 5: Skenario Use Case - Dari Diagram ke Langkah Kegiatan

## A. Tujuan Pembelajaran
Setelah mengikuti praktikum ini, mahasiswa mampu:
1. Menyusun tabel skenario untuk satu *use case* dengan struktur lengkap (Nama, Aktor, Tujuan, Deskripsi, kolom Kegiatan & Respon sistem, Skenario Normal, Skenario Alternative, dan Skenario Akhir).
2. Menulis langkah skenario secara berurutan dengan pemisahan yang jelas antara aksi aktor dan tanggapan sistem, serta penomoran langkah yang berlanjut dari alur normal ke alternatif.
3. Memetakan relasi *include* menjadi langkah wajib dan relasi *extend* menjadi cabang bersyarat lengkap dengan *condition* dan *extension point*.
4. Menerapkan *generalization aktor* (skenario satu kali atas nama aktor umum) dan *generalization use case* (skenario umum ditambah skenario khusus untuk perilaku pembeda).
5. Menelaah 12 tabel skenario studi kasus laboratorium dan menyusun 7 tabel skenario tugas akademik yang selaras dengan diagram kumulatif Pertemuan 4.

## B. Teori Dasar
Skenario *use case* adalah uraian langkah demi langkah tentang interaksi antara aktor dan sistem untuk satu *use case*. Tabel skenario dibagi menjadi dua kolom utama:
*   **Kegiatan:** Berisi aksi yang dilakukan oleh aktor (manusia/sistem eksternal).
*   **Respon Sistem:** Berisi tanggapan sistem terhadap aksi aktor.

**Aturan Pemetaan Relasi Diagram ke Skenario:**
*   **Include:** Menjadi langkah rujukan langsung di dalam Skenario Normal tanpa menyalin ulang langkahnya.
*   **Extend:** Menjadi cabang bersyarat di Skenario Alternative, dilengkapi dengan *condition* (misal: `[mahasiswa memilih cetak]`) dan *extension point*.
*   **Generalization Aktor:** Skenario ditulis atas nama aktor umum (contoh: Civitas Akademika), dengan catatan khusus jika ada perbedaan antar aktor turunan.
*   **Generalization Use Case:** Memisahkan langkah umum menjadi satu tabel *use case* induk, sementara turunan *use case* lainnya hanya mendeskripsikan langkah pembedanya saja (contoh: Tambah, Ubah, Hapus).

## C. Hasil Praktikum

### 1. Penelaahan Studi Kasus Laboratorium (LAB)
Pada bagian ini, dilakukan penelaahan terhadap 12 tabel skenario *use case* sistem laboratorium berdasarkan diagram kumulatif Pertemuan 4. 
*   Pengecekan meliputi kesesuaian nama aktor, kesesuaian ID *use case*, dan pemetaan relasi. 
*   Sebagai contoh, pada `LAB-UC03 Ajukan Peminjaman`, relasi *include* ke `LAB-UC04` telah dipetakan dengan benar di langkah Skenario Normal, dan *extend* ke `LAB-UC05` dipetakan di Skenario Alternative beserta syaratnya.
*   Pengecekan khusus juga dilakukan pada aktor Kepala Laboratorium (`LAB-UC07 Lihat Laporan Peminjaman`) yang terbukti berdiri sendiri tanpa relasi *include/extend/generalization*. Hasil penelaahan didokumentasikan dalam lembar *checklist*.

### 2. Pengerjaan Tugas Sistem Informasi Akademik (SIA)
Sebagai luaran utama, telah disusun 7 tabel skenario untuk fungsi Layanan Hasil Studi SIA (`SIA-UC07` hingga `SIA-UC13`) dengan menerapkan kaidah penulisan yang ketat:
*   **Penerapan Generalization Aktor (SIA-UC07):** Skenario "Lihat Kalender Akademik" ditulis cukup satu kali atas nama **Civitas Akademika**, yang mana secara implisit mewarisi hak akses untuk Mahasiswa dan Dosen.
*   **Validasi Prasyarat Khusus (SIA-UC08 & SIA-UC09):** Pada Input Nilai Mata Kuliah, ditambahkan validasi bahwa dosen adalah pengampu mata kuliah. Pada Lihat KHS, ditambahkan logika Skenario Alternatif jika nilai semester yang dipilih mahasiswa belum dipublikasikan oleh sistem.
*   **Penerapan Generalization Use Case (SIA-UC10 hingga SIA-UC13):** `SIA-UC10 Kelola Data Mahasiswa` dibuat sebagai tabel skenario umum. Kemudian, `SIA-UC11 (Tambah)`, `SIA-UC12 (Ubah)`, dan `SIA-UC13 (Hapus)` dibuat pada tabel terpisah yang hanya berisi rincian langkah pembedanya, sementara langkah dasarnya merujuk kembali ke tabel UC10.

## D. Kesimpulan
Melalui praktikum Pertemuan 5 ini, penulis berhasil memahami bagaimana menerjemahkan model visual (*Use Case Diagram*) menjadi urutan langkah operasional yang detail (*Skenario Use Case*). Pemetaan relasi diagram ke dalam teks terstruktur (seperti penerapan kondisi *extend* pada skenario alternatif dan integrasi *include* pada skenario normal) sangat krusial untuk memastikan bahwa rancangan alur sistem dapat diuji secara komprehensif, tidak ambigu, dan siap menjadi acuan dasar dalam perancangan *Activity Diagram* pada tahap selanjutnya.