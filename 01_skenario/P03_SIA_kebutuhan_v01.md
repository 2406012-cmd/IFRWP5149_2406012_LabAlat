<!-- Skenario Tugas -->
Mahasiswa mengajukan KRS dengan memilih mata kuliah. Setiap
pengajuan menjalankan validasi KRS yang memeriksa kelengkapan,
prasyarat mata kuliah, dan benturan jadwal. Jika validasi berhasil,
sistem menyimpan pengajuan berstatus menunggu persetujuan dosen
wali. Pada konfirmasi penyimpanan, mahasiswa dapat memilih
mengunduh bukti pengajuan. Dosen wali menyetujui atau menolak KRS
dan memberikan catatan keputusan.

<!-- Tabel Kebutuhan -->
|ID     |                            Kebutuhan_tugas                             |
|-------|------------------------------------------------------------------------|
|SIA-R01|                 Mahasiswa dapat melihat jadwal kuliah                  |
|SIA-R02|              Admin akademik dapat mengelola jadwal kuliah              |
|SIA-R03|                     Mahasiswa dapat mengajukan KRS                     |
|SIA-R04|            Sistem memvalidasi KRS sebagai bagian pengajuan             |
|SIA-R05|Mahasiswa dapat mengunduh bukti jika memilihnya pada konfirmasipengajuan|
|SIA-R06|       Dosen wali dapat memproses persetujuan atau penolakan KRS        |

<!-- Batas Sistem dan Asumsi -->
• Pengguna telah terautentikasi.
• Data mata kuliah, prasyarat, dan jadwal tersedia.
• Validasi gagal menyebabkan pengajuan belum berhasil tersimpan.
• Unduh bukti tidak menjadi syarat keberhasilan pengajuan.
• KRS tersimpan belum berarti disetujui.
• Pembayaran, pengisian nilai, dan implementasi basis data berada di luar tugas.

<!-- Tabel Identifikasi Aktor -->
|           Aktor           |                             Tujuan Terhadap Sistem                      |
| --------------------------| ----------------------------------------------------------------------- |
| Mahasiswa                 | Melihat jadwal kuliah, mengajukan KRS, dan mengunduh bukti pengajuan KRS|
| Dosen Wali                | Memproses Persetujuan atau Penolakan KRS                                |
| Admin Akademik            | Mengelola Jadwal Kuliah                                                 |

<!-- Tabel Katalog Use Case -->
|    ID    |       Nama use case           |         Peran dalam model        | 
| -------- | ----------------------------- | -------------------------------- | 
| SIA-UC01 | Melihat Jadwal Kuliah         | Fungsi utama mahasiswa           | 
| SIA-UC02 | Mengelola Jadwal Kuliah       | Fungsi utama Admin Akademik      | 
| SIA-UC03 | Ajukan KRS                    | Fungsi utama mahasiswa           | 
| SIA-UC04 | Validasi KRS                  | Perilaku yang disertakan SIA-UC03| 
| SIA-UC05 | Mengunduh Bukti Pengajuan KRS | Tambahan bersyarat pada SIA-UC03 | 
| SIA-UC06 | Proses Keputusan KRS          | Fungsi utama Dosen Wali          | 

<!-- Relasi Include -->
SIA-UC03 «include» SIA-UC04
Alasan : Memeriksa Kelengkapan, Prasyarat, dan benturan jadwal wajib dijalankan sebagai bagian tak terpisahkan dari proses pengajuan validasi KRS

<!-- Relasi Extend -->
SIA-UC05 «extend» SIA-UC03
Extension Point : Bukti Pengajuan Tersedia, pada konfirmasi penyimpanan.
Kondisi : [Mahsasiswa Memilih Mengunduh Bukti Pengajuan]
Alasan : Pengajuan KRS tetap berhasil disimpan meskipun mahasiswa tidak memilih mengunduh bukti.

