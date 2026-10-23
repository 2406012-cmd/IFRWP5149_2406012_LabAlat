<!-- Tabel Kebutuhan -->
|  ID Kebutuhan   |                                             Deskripsi                                               |
| --------------- | --------------------------------------------------------------------------------------------------- |
| SIA-R01-SIA-R06 | Kebutuhan Pertemuan 2 dan Pertemuan 3 tetap sama (Jadwal Kuliah, Pengajuan KRS, Validasi, Unduh Bukti, dan Proses Keputusan KRS). |
| SIA-R07         | Mahasiswa dan Dosen, sebagai Civitas Akademika, dapat melihat kalender akademik.                    |
| SIA-R08         | Dosen dapat menginput nilai mata kuliah yang diampunya. |
| SIA-R09         | Mahasiswa dapat melihat KHS untuk semester yang nilainya sudah dipublikasikan.                      |
| SIA-R10         | Admin Akademik dapat mengelola data mahasiswa.                                                      |
| SIA-R11         | Pengelolaan data mahasiswa terdiri dari tiga bentuk khusus: tambah, ubah, dan hapus data mahasiswa. |
| SIA-R12         | Model menunjukkan collaboration yang merealisasikan Input Nilai Mata Kuliah dan Lihat KHS.          |
  
<!-- Batas Sistem dan Asumsi -->
1. Kode kebutuhan dimulai dari `SIA-R07` agar tidak bertumbukan dengan identitas kebutuhan Pertemuan 2 dan 3.
2. Pengguna telah terautentikasi dan memiliki hak akses sesuai perannya.
3. Kalender akademik adalah agenda resmi institusi (awal semester, batas KRS, masa ujian); tidak disamakan dengan jadwal kuliah.
4. Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut, dan KHS hanya menampilkan nilai yang sudah dipublikasikan resmi.
5. Hapus Data Mahasiswa hanya dapat dilakukan untuk mahasiswa yang tidak memiliki data akademik aktif.

<!-- Tabel Aktor -->
| Aktor             |                        Kedudukan                               |          Tujuan Terhadap Sistem          |
| ----------------- | -------------------------------------------------------------- | ---------------------------------------- |
| Civitas Akademika | Umum (General), baru pada Pertemuan 4 | Peran umum bagi sivitas akademik; mewariskan fungsinya kepada Mahasiswa dan Dosen. |
| Mahasiswa         | Khusus dari Civitas Akademika, tetap dari Pertemuan sebelumnya | Melihat kalender akademik (diwarisi), mengajukan KRS, melihat jadwal, dan melihat KHS (serta unduh bukti KRS). |
| Dosen             | Khusus dari Civitas Akademika, baru pada Pertemuan 4           | Melihat kalender akademik (diwarisi) dan menginput nilai mata kuliah yang diampunya. |
| Admin Akademik    | Tetap dari Pertemuan 2                                         | Mengelola jadwal kuliah dan mengelola data mahasiswa. |
| Dosen Wali        | Tetap dari Pertemuan 3                                         | Memproses persetujuan atau penolakan KRS mahasiswa bimbingan. |

<!-- Tabel Use Case -->
| ID Use Case | Nama Use Case | Peran dalam Model | Sumber Kebutuhan |
| ------      | ----------------------- | --- | --- |
| SIA-UC01    | Lihat Jadwal Kuliah | Tetap dari Pertemuan 2 | SIA-R01 |
| SIA-UC02    | Kelola Jadwal Kuliah | Tetap dari Pertemuan 2 | SIA-R02 |
| SIA-UC03    | Ajukan KRS | Tetap dari Pertemuan 3 (menyertakan SIA-UC04) | SIA-R03 |
| SIA-UC04    | Validasi KRS | Tetap dari Pertemuan 3 (perilaku diserta SIA-UC03) | SIA-R04 |
| SIA-UC05    | Unduh Bukti Pengajuan KRS | Tetap dari Pertemuan 3 (extend ke SIA-UC03) | SIA-R05 |
| SIA-UC06    | Proses Keputusan KRS | Tetap dari Pertemuan 3 (fungsi Dosen Wali) | SIA-R06 |
| SIA-UC07    | Lihat Kalender Akademik | Baru P4; fungsi aktor umum Civitas Akademika | SIA-R07 |
| SIA-UC08    | Input Nilai Mata Kuliah | Baru P4; fungsi utama Dosen; direalisasikan SIA-CO01 | SIA-R08 |
| SIA-UC09    | Lihat KHS | Baru P4; fungsi utama Mahasiswa; direalisasikan SIA-CO02 | SIA-R09 |
| SIA-UC10 | Kelola Data Mahasiswa | Baru P4; use case UMUM bagi SIA-UC11, SIA-UC12, SIA-UC13 | SIA-R10, SIA-R11 |
| SIA-UC11 | Tambah Data Mahasiswa | Baru P4; use case KHUSUS dari SIA-UC10 | SIA-R11 |
| SIA-UC12 | Ubah Data Mahasiswa | Baru P4; use case KHUSUS dari SIA-UC10 | SIA-R11 |
| SIA-UC13 | Hapus Data Mahasiswa | Baru P4; use case KHUSUS dari SIA-UC10 | SIA-R11 |

<!-- Generalization Actor dan Use Case -->
- Generalization Actor
Aktor Umum : Civitas Akademika (dibuat khusus pada Pertemuan 4 sebagai peran umum yang mencakup civitas akademik).   
Aktor Khusus : Mahasiswa dan Dosen 
Fungsi yang Diwarisi : Karena Mahasiswa dan Dosen sama-sama dapat melihat kalender akademik (SIA-UC07), fungsi ini ditempatkan dan dihubungkan satu kali saja dari aktor umum Civitas Akademika.

- Generalization Use Case
SIA-UC10 (Kelola Data Mahasiswa) : Adalah use case umum.
SIA-UC11 (Tambah Data Mahasiswa) : Menghasilkan data mahasiswa baru yang tersimpan di sistem.
SIA-UC12 (Ubah Data Mahasiswa)   : Menghasilkan perubahan pada data mahasiswa yang sudah ada.
SIA-UC13 (Hapus Data Mahasiswa)  : Menghapus data mahasiswa dari sistem dengan syarat tidak memiliki data akademik aktif.

<!-- Collaboration dan Realization -->
| ID       | Nama Collaboration                               | Use case yang direalisasikan           |
| -------- | -------------------------------------------------|----------------------------------------|
| SIA-CO01 | Input Nilai Mata Kuliah                          | SIA-UC08 : Input Nilai Mata Kulia      |
| SIA-CO02 | Melihat KRS                                      | SIA-UC09 : Lihat KRS                   |