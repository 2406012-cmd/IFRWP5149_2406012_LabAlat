# Laporan Pertemuan 3: Use Case Diagram dan Use Case Description

## A. Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa mampu:

1. Menuliskan batas sistem, aktor, kebutuhan, aturan bisnis, dan asumsi dari skenario yang diberikan.

2. Menentukan *use case* berdasarkan tujuan aktor, bukan berdasarkan nama tombol, tabel, atau langkah teknis.

3. Membuat *use case diagram* yang konsisten dengan daftar kebutuhan dan hubungan aktor-fungsi.

4. Menyusun *use case description* yang memuat pemicu, prasyarat, alur utama, alur alternatif atau pengecualian, dan pascakondisi.

5. Menunjukkan keterlacakan setiap *use case* ke kebutuhan yang mendasarinya.

6. Memperbaiki model berdasarkan *review* dan mendokumentasikan perubahan pada versi berikutnya.

## B. Teori Dasar Praktikum

*Use case diagram* adalah pemodelan UML yang memvisualisasikan fungsionalitas sistem serta interaksi yang terjadi antara pengguna eksternal dengan sistem tersebut.

* **Aktor dan Batas Sistem:** Aktor adalah peran eksternal (manusia atau sistem lain) yang berinteraksi dengan sistem dan digambarkan di luar batas sistem (*system boundary*). *Use case* adalah fungsionalitas bernilai bagi aktor yang ditulis menggunakan kata kerja dan objek, serta diletakkan di dalam batas sistem.

* **Association:** Garis utuh yang menghubungkan aktor dengan *use case* yang dijalankannya.

* **Relasi `<<include>>`:** Menyatakan bahwa perilaku suatu *use case* selalu disertakan sebagai bagian wajib dalam pelaksanaan *use case* lain. Arah panah putus-putus mengarah dari *use case* penyerta menuju *use case* yang disertakan.

* **Relasi `<<extend>>`:** Menambahkan perilaku opsional ke *use case* dasar pada *extension point* tertentu apabila *condition* terpenuhi, di mana *use case* dasar tetap dapat berjalan utuh tanpa perilaku tambahan tersebut. Arah panah putus-putus mengarah dari *use case* tambahan menuju *use case* dasar.

* **Use Case Description:** Dokumentasi tekstual berbentuk tabel yang merinci satu *use case* mulai dari pemicu, prasyarat, alur utama, alur alternatif/pengecualian, hingga pascakondisi berhasil dan gagal.

## C. Hasil Praktikum

### 1. Studi Kasus Terbimbing: Laboratorium (LAB)

Pada studi kasus Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus, dilakukan pemodelan dasar berdasarkan kebutuhan `LAB-R01` sampai `LAB-R06`:

* **Identifikasi Aktor dan Use Case:** Menetapkan tiga aktor di luar batas sistem, yaitu **Mahasiswa**, **Petugas Laboratorium**, dan **Kepala Laboratorium**, beserta tujuh *use case* (`LAB-UC01` hingga `LAB-UC07`) di dalam batas sistem.

* **Pemetaan Relasi:**
  * Mahasiswa berasosiasi dengan *Lihat Ketersediaan Peralatan* (`LAB-UC01`), *Ajukan Peminjaman* (`LAB-UC03`), dan *Cetak Bukti Pengajuan* (`LAB-UC05`).
  * Petugas Laboratorium berasosiasi dengan *Kelola Data Peralatan* (`LAB-UC02`) dan *Proses Keputusan Peminjaman* (`LAB-UC06`).
  * Kepala Laboratorium berasosiasi dengan *Lihat Laporan Peminjaman* (`LAB-UC07`).
  * Menerapkan relasi `<<include>>` dari `LAB-UC03` menuju *Periksa Ketersediaan* (`LAB-UC04`) sebagai tahapan validasi wajib, serta `<<extend>>` dari `LAB-UC05` menuju `LAB-UC03` pada *extension point* `Bukti pengajuan tersedia` dengan kondisi `[mahasiswa memilih cetak]`.

* **Penyusunan Use Case Description:** Menyusun rincian skenario untuk `LAB-UC03 Ajukan Peminjaman` yang mencakup alur utama, skenario kegagalan validasi, serta pascakondisi berhasil dan gagal.

### 2. Tugas Praktik: Sistem Informasi Akademik (SIA)

Sebagai tugas mandiri, disusun model baru untuk proses layanan pengajuan Kartu Rencana Studi (KRS) berdasarkan kebutuhan `SIA-R03` sampai `SIA-R06`:

* **Identifikasi Aktor dan Use Case:** Menetapkan dua aktor yang terlibat langsung dalam skenario, yaitu **Mahasiswa** dan **Dosen Wali** (aktor Admin Akademik tidak dilibatkan karena berada di luar cakupan skenario KRS).

* **Pemetaan Relasi:**
  * Mahasiswa berasosiasi dengan *Ajukan KRS* (`SIA-UC03`), yang memiliki relasi `<<include>>` wajib menuju *Validasi KRS* (`SIA-UC04`) untuk memeriksa kelengkapan data, prasyarat mata kuliah, dan benturan jadwal.
  * Menerapkan relasi `<<extend>>` dari *Unduh Bukti Pengajuan KRS* (`SIA-UC05`) menuju `SIA-UC03` sebagai perilaku tambahan bersyarat setelah pengajuan tersimpan.
  * Dosen Wali berasosiasi dengan *Proses Keputusan KRS* (`SIA-UC06`) untuk menyetujui atau menolak pengajuan KRS beserta catatannya.

* **Penyusunan Deskripsi dan Uji Konsistensi:** Menyusun empat *use case description* lengkap untuk `SIA-UC03` hingga `SIA-UC06`, serta melakukan pengujian konsistensi antara diagram dan deskripsi untuk kondisi validasi berhasil (dengan dan tanpa unduh bukti) maupun validasi gagal.

## D. Kesimpulan

Melalui praktikum Pertemuan 3 ini, mahasiswa dapat memahami cara menerjemahkan deskripsi kebutuhan sistem menjadi *Use Case Diagram* dan *Use Case Description* yang terstruktur dan konsisten. Pemisahan yang tepat antara prasyarat sistem, perilaku wajib (`<<include>>`), dan perilaku tambahan bersyarat (`<<extend>>`) memastikan bahwa batasan fungsionalitas sistem terdefinisi dengan jelas serta mudah ditelusuri pada tahapan pemodelan analisis berikutnya.