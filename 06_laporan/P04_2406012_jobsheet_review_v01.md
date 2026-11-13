# Laporan Pertemuan 4: Use Case Diagram Lanjutan - Generalization dan Collaboration

## A. Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa mampu:

1. Mengidentifikasi aktor umum dan aktor khusus, lalu menyusun hierarki *generalization aktor* dengan arah panah yang benar (aktor khusus menuju aktor umum) tanpa menggambar ulang asosiasi yang diwarisi.
2. Menyusun *generalization use case* yang memuat satu *use case* umum dan beberapa *use case* khusus, serta menjelaskan perilaku pembedanya.
3. Menempatkan *collaboration* (elips garis putus-putus) yang namanya sama persis dengan *use case* yang direalisasikan, dihubungkan dengan relasi *realization* (garis putus-putus berujung segitiga kosong).
4. Membuat *use case diagram* kumulatif untuk kasus laboratorium dan sistem akademik dengan mempertahankan elemen Pertemuan 3 dan menambahkan elemen baru Pertemuan 4.
5. Menyusun *use case description* lanjutan yang memuat parameter prasyarat, alur alternatif, hingga *pascakondisi*.
6. Menunjukkan keterlacakan elemen baru ke kebutuhan sistem yang mendasarinya (kebutuhan R07 hingga R12).

## B. Teori Dasar Praktikum

Pengembangan model pada pertemuan ini bersifat **kumulatif**. Diagram Pertemuan 3 tidak diganti, melainkan dipertahankan dan ditambahkan elemen baru:

* **Generalization Aktor:** Menyatakan hubungan umum-khusus antar peran. Aktor khusus mewarisi semua asosiasi dari aktor umum. Digambarkan dengan garis utuh berujung segitiga kosong yang menunjuk ke aktor umum.
* **Generalization Use Case:** Menyatakan hubungan jenis *use case*. *Use case* khusus mewarisi tujuan dari *use case* umum namun dengan hasil akhir atau perilaku khusus yang berbeda. Digambarkan dengan panah segitiga kosong menunjuk ke *use case* umum.
* **Collaboration & Realization:** *Collaboration* (elips garis putus-putus) mewujudkan perilaku sebuah *use case*. Namanya sama persis dengan *use case* targetnya. Dihubungkan dengan garis *realization* (putus-putus dengan panah segitiga kosong) mengarah dari *collaboration* ke *use case*.

## C. Hasil Praktikum

### 1. Studi Kasus Laboratorium (LAB)

Pemodelan sistem laboratorium dilakukan secara bertahap dengan memperluas diagram Pertemuan 3:

* **Penerapan Generalization Aktor:** Menambahkan aktor `Peminjam` sebagai aktor umum. `Mahasiswa` dan `Dosen` ditetapkan sebagai aktor khusus yang mewarisi fungsi dari `Peminjam` (melihat ketersediaan dan mengajukan peminjaman). Asosiasi khusus `Cetak Bukti Pengajuan` tetap terhubung langsung hanya ke `Mahasiswa`.
* **Penerapan Generalization Use Case:** `Kelola Data Peralatan` ditetapkan sebagai *use case* umum. Tiga *use case* khusus ditambahkan, yaitu `Tambah Data Peralatan`, `Ubah Data Peralatan`, dan `Hapus Data Peralatan`, yang ketiganya menunjuk ke *use case* umum tersebut.
* **Penambahan Use Case Baru:** Menambahkan `Catat Pengembalian Peralatan` yang dilakukan oleh Petugas Laboratorium, yang memiliki relasi `<<include>>` ke `Periksa Kondisi Peralatan`.
* **Penerapan Collaboration:** Menambahkan *collaboration* `Ajukan Peminjaman` dan `Catat Pengembalian Peralatan` yang merealisasikan *use case* dengan nama yang sama.

### 2. Tugas Sistem Informasi Akademik (SIA)

Untuk tugas mandiri SIA, diagram kumulatif dibangun dengan penambahan elemen-elemen Layanan Hasil Studi berdasarkan skenario fiktif:

* **Penerapan Generalization Aktor:** Menetapkan `Civitas Akademika` sebagai aktor umum yang dapat melakukan `Lihat Kalender Akademik`. `Mahasiswa` dan `Dosen` ditetapkan sebagai aktor khusus dari Civitas Akademika.
* **Penerapan Generalization Use Case:** `Kelola Data Mahasiswa` (dilakukan oleh Admin Akademik) ditetapkan sebagai *use case* umum untuk tiga operasi spesifik: `Tambah Data Mahasiswa`, `Ubah Data Mahasiswa`, dan `Hapus Data Mahasiswa`.
* **Penyusunan Use Case Description:** Menyusun deskripsi untuk `Input Nilai Mata Kuliah` (dilakukan oleh Dosen pengampu) dan `Lihat KHS` (dilakukan oleh Mahasiswa, hanya untuk nilai yang telah dipublikasi).
* **Penerapan Collaboration:** Menambahkan *collaboration* untuk merealisasikan `Input Nilai Mata Kuliah` dan `Lihat KHS`.

## D. Kesimpulan

Praktikum Pertemuan 4 ini memberikan pemahaman mendalam tentang teknik pemodelan UML tingkat lanjut. Melalui penerapan *generalization*, diagram menjadi lebih efisien dan tidak redundan karena asosiasi yang sama cukup ditarik dari elemen umumnya. Penggunaan konsep kumulatif juga melatih kemampuan dalam menjaga integritas desain sistem yang sedang berkembang tanpa merusak spesifikasi (diagram Pertemuan 3) yang sudah ada sebelumnya. Selain itu, penambahan *collaboration* memberikan fondasi yang baik sebagai jembatan menuju perancangan diagram interaksi di tahap selanjutnya.