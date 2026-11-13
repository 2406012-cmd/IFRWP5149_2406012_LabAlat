# Laporan Pertemuan 2: Unified Modelling Language (UML)

## A. Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa mampu:

1. Menempatkan simbol *actor*, *use case*, batas sistem (*system boundary*), dan *association* pada diagram sederhana sesuai contoh yang disediakan.
2. Menggunakan nama aktor dan fungsi secara konsisten dengan skenario latihan.
3. Mengisi identitas artefak melalui *template* metadata yang telah disiapkan pada Pertemuan 1.
4. Menyimpan berkas sumber (`.drawio`) dan ekspor (`.png`) dengan nama, lokasi direktori, serta nomor versi yang konsisten.
5. Memperbaiki kesalahan notasi dan dokumentasi berdasarkan hasil *review*, kemudian mencatat perubahannya.

## B. Teori Dasar Praktikum

*Unified Modeling Language* (UML) merupakan bahasa pemodelan visual standar yang dikembangkan oleh Grady Booch, James Rumbaugh, dan Ivar Jacobson (di bawah standar OMG) untuk menspesifikasikan, memvisualisasikan, dan mendokumentasikan sistem perangkat lunak berorientasi objek.

Dalam konsep dasar UML (*Building Blocks*), terdapat tiga elemen utama yaitu *Things* (seperti *Class*, *Interface*, *Collaboration*, *Use Case*, dan *Node*), *Relationships* (*Dependency*, *Association*, *Generalization*, dan *Realization*), serta berbagai jenis *Diagram*. Pada praktikum Pertemuan 2, fokus latihan dibatasi pada empat notasi dasar *Use Case Diagram*:

* **Actor:** Peran eksternal (manusia atau sistem lain) yang berinteraksi dengan sistem, digambarkan dengan simbol orang (*stick figure*) dan diletakkan **di luar** batas sistem.
* **Use Case:** Fungsionalitas atau layanan sistem yang bernilai bagi aktor, digambarkan dengan bentuk elips berlabel kata kerja dan diletakkan **di dalam** batas sistem.
* **Batas Sistem (*System Boundary*):** Persegi panjang yang membatasi ruang lingkup fungsionalitas sistem yang sedang dimodelkan, dilengkapi judul nama sistem di bagian atas.
* **Association:** Garis utuh tanpa anak panah yang menghubungkan aktor dengan *use case* sebagai tanda partisipasi interaksi (bukan penunjuk urutan alur proses).

*(Catatan: Relasi lanjutan seperti `<<include>>`, `<<extend>>`, dan generalisasi belum diterapkan pada tahap ini agar latihan berfokus pada ketepatan notasi dasar).*

## C. Hasil Praktikum

### 1. Studi Kasus Terbimbing: Laboratorium (LAB)

Pada studi kasus *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*, dilakukan pemodelan dasar berdasarkan kebutuhan `LAB-R01` dan `LAB-R02`:

* **Pembuatan Batas Sistem dan Elemen:** Membuat batas sistem berjudul lengkap, meletakkan dua aktor di luar batas sistem yaitu **Mahasiswa** (sisi kiri) dan **Petugas Laboratorium** (sisi kanan), serta menempatkan dua *use case* berbentuk elips di dalam batas sistem yaitu *Lihat ketersediaan peralatan* dan *Kelola data peralatan*.
* **Penarikan Garis Asosiasi:** Menghubungkan aktor **Mahasiswa** dengan *Lihat ketersediaan peralatan*, serta **Petugas Laboratorium** dengan *Kelola data peralatan* menggunakan garis utuh tanpa anak panah dan tanpa menghubungkan antar-elips.
* **Pengisian Metadata dan Penyimpanan:** Melengkapi metadata artefak (`ID: LAB-P02-UC`, status `LATIHAN NOTASI`) serta menyimpan berkas sumber `P02_<NIM>_LAB_notasi_usecase_v01.drawio` beserta ekspor `.png` pada folder `03_latihan_tools/P02/LAB/`.

### 2. Tugas Praktik: Sistem Informasi Akademik (SIA)

Pada tugas mandiri untuk kasus *Sistem Informasi Akademik* (`SIA-R01` dan `SIA-R02`), dilakukan analisis dan perbaikan terhadap diagram awal (`P02_<NIM>_SIA_perbaikan_notasi_v01.drawio`) yang sengaja memuat empat kesalahan pemodelan:

* **Koreksi Posisi Aktor:** Memindahkan simbol aktor **Mahasiswa** yang sebelumnya berada di dalam kotak batas sistem ke area luar batas sistem.
* **Koreksi Simbol Use Case:** Mengubah bentuk fungsi *Lihat jadwal kuliah* yang semula digambar menggunakan kotak biasa menjadi simbol elips standar UML.
* **Koreksi Hubungan Asosiasi:** Memutus hubungan yang keliru antara Mahasiswa dengan *Kelola jadwal kuliah*, lalu menyesuaikan asosiasi sesuai skenario, yakni **Mahasiswa** terhubung ke *Lihat jadwal kuliah* dan **Admin akademik** terhubung ke *Kelola jadwal kuliah*.
* **Koreksi Identitas Sistem:** Mengubah judul pada batas sistem yang semula tertulis nama sistem laboratorium menjadi **Sistem Informasi Akademik**, lalu menyimpan hasil revisinya sebagai `P02_<NIM>_SIA_notasi_v01.drawio`.

## D. Kesimpulan

Melalui praktikum Pertemuan 2 ini, mahasiswa memahami prinsip dasar pemodelan menggunakan UML serta aturan penempatan notasi fundamental pada *Use Case Diagram*. Pemisahan yang tegas antara posisi aktor di luar batas sistem dan *use case* di dalam batas sistem, penggunaan simbol yang sesuai standar, serta disiplin dalam melakukan *review* dan penamaan versi berkas menjadi fondasi penting sebelum melangkah ke pemodelan relasi *use case* yang lebih kompleks pada pertemuan berikutnya.


| No. | Temuan | Perbaikan yang diperlukan | Alasan |
| :--- | :--- | :--- | :--- |
| 1 | Aktor Mahasiswa ada di dalam batas sistem. | Memindahkan Aktor Mahasiswa ke luar batas sistem. | Aktor adalah entitas yang berinteraksi dengan sistem, sehingga posisinya harus berada di luar kotak batas sistem. |
| 2 | Fungsi "Lihat jadwal kuliah" digambar sebagai kotak biasa. | Mengubah bentuk kotak menjadi bentuk elips. | Sesuai standar UML, notasi untuk sebuah use case (fungsi sistem) digambarkan menggunakan bentuk elips, bukan persegi panjang. |
| 3 | Aktor Mahasiswa dihubungkan dengan fungsi "Kelola jadwal kuliah". | Menghapus garis asosiasi antara Mahasiswa dan "Kelola jadwal kuliah", lalu hubungkan Mahasiswa dengan "Lihat jadwal kuliah" dan Admin akademik dengan "Kelola jadwal kuliah". | Berdasarkan deskripsi skenario, mahasiswa tidak mempunyai hak mengelola jadwal. Hak pengelolaan ada pada Admin Akademik, sedangkan mahasiswa hanya mempunyai hak untuk melihat jadwal. |
| 4 | Identitas diagram menggunakan judul "Sistem Laboratorium". | Mengganti judul identitas diagram dengan judul "Sistem Informasi Akademik". | Konteks skenario latihan ini berfokus pada Sistem Informasi Akademik, sehingga penamaan sistem harus sesuai dengan masalah dan yang dikerjakan. |