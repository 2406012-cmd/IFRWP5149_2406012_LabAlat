<!-- Use Case Description -->
<!-- A. SIA-UC03_Mengajukan_KRS -->
|Komponen             |                                 Deskripsi                                  |
|---------------------|----------------------------------------------------------------------------|
|Tujuan               |Menghasilkan pengajuan KRS yang tersimpan dengan status menunggu persetujuan|
|Aktor utama          |                                 Mahasiswa                                  |
|Sumber kebutuhan     |                            SIA-R03 dan SIA-R04                             |
|Pemicu               |                   Mahasiswa memilih fungsi pengajuan KRS                   |
|Prasyarat            |       Mahasiswa terautentikasi; data mata kuliah dan jadwal tersedia       |
|Pascakondisi berhasil|   Pengajuan KRS tersimpan dengan status Menunggu persetujuan dosen wali    |
|Pascakondisi gagal   |            Pengajuan KRS tidak tersimpan karena validasi gagal             |
|Include              |                          SIA-UC04 — Validasi KRS                           |
|Extension point      |             "Bukti pengajuan tersedia, pada tahap konfirmasi"              |
|Extend               |                  SIA-UC05 jika [mahasiswa memilih unduh]                   |

<!-- Alur Utama dan Alternatif SIA-UC03-->
Alur Utama:
1. Mahasiswa membuka menu pengajuan KRS. Sistem menampilkan formulir KRS.
2. Mahasiswa memilih mata kuliah yang akan diambil. Sistem menampung pilihan mata kuliah.
3. Mahasiswa mengirimkan pengajuan. Sistem memeriksa kelengkapan data.
4. Sistem menjalankan SIA-UC04 (Validasi KRS).
5. Jika validasi berhasil, sistem menyimpan pengajuan KRS dengan status Menunggu persetujuan.
6. Sistem menampilkan konfirmasi penyimpanan dan mencapai extension point.
7. Mahasiswa mengakhiri proses pengajuan.

Alur Alternatif / Pengecualian:
1. 4a. Validasi gagal (kelengkapan tidak lengkap, prasyarat belum terpenuhi, atau bentrok jadwal):
2. Sistem menolak penyimpanan pengajuan KRS.
3. Sistem menampilkan pesan kesalahan validasi.
4. Pengajuan berakhir tanpa tersimpan (kembali ke langkah 2).

<!--  B. SIA-UC04_Validasi_KRS -->
|Komponen             |                               Deskripsi                               |
|---------------------|-----------------------------------------------------------------------|
|Tujuan               |"Memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal KRS"|
|Aktor utama          |                   Sistem (Dipanggil oleh SIA-UC03)                    |
|Sumber kebutuhan     |                                SIA-R04                                |
|Pemicu               |             Pengiriman data pengajuan KRS oleh mahasiswa              |
|Prasyarat            |            Data pilihan mata kuliah dan prasyarat tersedia            |
|Pascakondisi berhasil|    Validasi dinyatakan lolos (tanpa konflik prasyarat dan jadwal)     |
|Pascakondisi gagal   |          Validasi gagal ditemukan adanya pelanggaran aturan           |

<!--  C. SIA-UC05_Unduh_Bukti_Pengajuan_KRS -->
|Komponen             |                                Deskripsi                                |
|---------------------|-------------------------------------------------------------------------|
|Tujuan               |Menyediakan berkas bukti pengajuan KRS yang dapat diunduh oleh mahasiswa |
|Aktor utama          |                                Mahasiswa                                |
|Sumber kebutuhan     |                                 SIA-R05                                 |
|Pemicu               |         Mahasiswa memilih opsi unduh pada konfirmasi pengajuan          |
|Prasyarat            |Pengajuan KRS telah berhasil tersimpan (SIA-UC03 mencapai titik ekstensi)|
|Pascakondisi berhasil|         Berkas bukti pengajuan terunduh ke perangkat mahasiswa          |
|Pascakondisi gagal   |                      Proses unduh batal dilakukan                       |

 
<!--  D. SIA-UC06_Proses_Keputusan_KRS -->
|Komponen             |                                           Deskripsi                                            |
|---------------------|------------------------------------------------------------------------------------------------|
|Tujuan               |Menetapkan status persetujuan atau penolakan terhadap pengajuan KRS mahasiswa beserta catatannya|
|Aktor utama          |                                           Dosen wali                                           |
|Sumber kebutuhan     |                                            SIA-R06                                             |
|Pemicu               |                  Dosen wali memilih daftar pengajuan KRS mahasiswa bimbingan                   |
|Prasyarat            |                     Terdapat pengajuan KRS berstatus Menunggu persetujuan                      |
|Pascakondisi berhasil|          Status KRS berubah menjadi Disetujui atau Ditolak beserta catatan keputusan           |
|Pascakondisi gagal   |                                    Keputusan gagal disimpan                                    |

<!-- Alur Utama -->
1. Dosen wali membuka daftar pengajuan KRS mahasiswa. Sistem menampilkan daftar KRS berstatus menunggu.
2. Dosen wali memilih salah satu pengajuan untuk ditinjau. Sistem menampilkan detail KRS.
3. Dosen wali memberikan keputusan (menyetujui/menolak) serta mengisi catatan keputusan.
4. Dosen wali menyimpan keputusan. Sistem memperbarui status KRS dan mencatat keputusan.
5. Sistem menampilkan konfirmasi keberhasilan pemrosesan keputusan.