<!-- Use Case Description -->
- SIA-UC08 Input Nilai Mata Kuliah
|Komponen             |                              SIA-UC08 : Input Nilai Mata Kuliah                              |
|---------------------|----------------------------------------------------------------------------------------------|
|ID dan Nama          |                              SIA-UC08: Input Nilai Mata Kuliah.                              |
|Generalization       |                                              -                                               |
|Collaboration        |                             SIA-CO01 : Input Nilai Mata Kuliah.                              |
|Sumber Kebutuhan     |                                           SIA-R08.                                           |
|Tujuan               |    Menyimpan nilai mahasiswa untuk mata kuliah yang diampu oleh dosen yang bersangkutan.     |
|Aktor Utama          |                                            Dosen.                                            |
|Pemicu               |            Dosen memilih menu input nilai dan memilih mata kuliah yang diampunya.            |
|Prasyarat            |Dosen terautentikasi; masa input nilai dibuka; dosen adalah pengampu sah mata kuliah tersebut.|
|Pascakondisi Berhasil|        Nilai mahasiswa tersimpan dan tercatat pada sistem untuk mata kuliah terkait.         |
|Pascakondisi Gagal   |            Tidak ada nilai baru yang tersimpan; data nilai tetap seperti semula.             |

<!-- Alur Utama dan Alternatif -->
- Alur utama
1. Dosen memilih menu input nilai. Sistem menampilkan daftar mata kuliah yang diampu.

2. Dosen memilih mata kuliah dan kelas. Sistem menampilkan daftar mahasiswa peserta kuliah.

3. Dosen memasukkan atau memperbarui nilai mahasiswa. Sistem menampung masukan nilai.

4. Dosen menyimpan data nilai. Sistem memvalidasi rentang nilai dan hak pengampu.

5. Sistem menyimpan nilai dan menampilkan konfirmasi keberhasilan

- Alur Alternatif atau Pengecualian
1. A1 (Nilai di luar sah): Sistem menolak penyimpanan dan menampilkan pesan kesalahan format/rentang nilai; data tidak disimpan.

2. A2 (Bukan dosen pengampu): Sistem menolak akses input nilai karena dosen tidak terdaftar mengampu mata kuliah tersebut.

- SIA-UC09 Lihat KRS
|Komponen             |                                      SIA-UC09 : Lihat KRS                                     |
|---------------------|-----------------------------------------------------------------------------------------------|
|ID dan Nama          |                                      SIA-UC09: Lihat KHS                                      |
|Collaboration        |                                      SIA-CO02: Lihat KHS                                      |
|Sumber Kebutuhan     |                                            SIA-R09                                            |
|Tujuan               |Menampilkan Kartu Hasil Studi (KHS) mahasiswa untuk semester yang nilainya sudah dipublikasikan|
|Aktor Utama          |                                           Mahasiswa                                           |
|Prasyarat            |       Mahasiswa terautentikasi; terdapat nilai semester yang telah resmi dipublikasikan       |
|Pascakondisi Berhasil|                          KHS semester ditampilkan ke layar mahasiswa                          |
                    
<!-- Uji Konsistensi -->
| Situasi Uji |                             Hasil Evaluasi Konsistensi Diagram & deskripsi                                     |
| ----------- | -------------------------------------------------------------------------------------------------------------- |
| Situasi A : Mahasiswa melihat kalender akademik tanpa asosiasi langsung | Konsistensi : Mahasiswa mewarisi asosiasi ke SIA-UC07 (Lihat Kalender Akademik) melalui hubungan generalization dari aktor umum Civitas Akademika. Tidak diperlukan garis asosiasi terpisah dari Mahasiswa. |
| Situasi B: Dosen yang bukan pengampu mencoba menginput nilai | Konsistensi : Sesuai prasyarat dan alur alternatif deskripsi SIA-UC08, sistem akan menolak akses atau penyimpanan karena dosen tersebut tidak memiliki hak akses sebagai pengampu sah mata kuliah terkait. |
| Situasi C: Admin Akademik menghapus data mahasiswa yang masih aktif | Konsistensi : Sesuai aturan dan pascakondisi gagal, sistem menolak penghapusan data mahasiswa apabila masih terdapat rekam jejak atau data akademik aktif yang terikat. |

