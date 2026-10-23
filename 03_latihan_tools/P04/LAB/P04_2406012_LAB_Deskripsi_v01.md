<!-- Use Case Description -->
|Elemen               |                               LAB-UC11: Catat Pengembalian Peralatan                                |
|---------------------|-----------------------------------------------------------------------------------------------------|
|ID dan nama          |                               LAB-UC11: Catat Pengembalian Peralatan                                |
|Sumber kebutuhan     |                                         LAB-R09 dan LAB-R10                                         |
|Tujuan               |            Pengembalian tercatat dan status peminjaman serta kondisi peralatan terbarui             |
|Aktor utama          |                                        Petugas Laboratorium                                         |
|Pemicu               |   Petugas memilih fungsi pencatatan pengembalian danmenentukan peminjaman yang akan dikembalikan    |
|Prasyarat            |                Petugas telah terautentikasi; peminjaman terpilih berstatus Dipinjam                 |
|Pascakondisi berhasil|Pengembalian tercatat dengan tanggal kembali dan kondisi peralatan; status peminjaman menjadi Selesai|
|Pascakondisi gagal   |             Tidak ada pengembalian baru yang tercatat; status peminjaman tidak berubah              |
|Include              |                                LAB-UC12 : Periksa Kondisi Peralatan                                 |
|Collaboration        |                               LAB-CO02 : Catat Pengembalian Peralatan                               |

<!-- Alur Utama dan Alternatif -->
- Alur utama
|Langkah|Tindakan petugas                             |                                Respons sistem                                 |
|-------|---------------------------------------------|-------------------------------------------------------------------------------|
|1      |Memilih peminjaman yang akan dikembalikan    |              Menampilkan data peminjaman terpilih dan statusnya               |
|2      |Mengonfirmasi alat yang kembali dan jumlahnya|                         Menampung konfirmasi petugas                          |
|3      |Tidak ada                                    |                  Memeriksa status peminjaman harus Dipinjam                   |
|4      |Tidak ada                                    |          Jalankan LAB-UC12: memeriksa dan mencatat kondisi peralatan          |
|5      |Menyimpan pencatatan pengembalian            |Menyimpan tanggal kembali dakondisi; mengubah status peminjaman menjadi Selesai|
|6      |Melihat konfirmasi                           |                      Menampilkan ringkasan pengembalian                       |

- Alur Alternatif atau Pengecualian
• A1: Status bukan Dipinjam (pada langkah 3): sistem menolak pencatatandan menampilkan status peminjaman saat ini. Pascakondisi gagal berlaku; tidak ada data yang disimpan.
• A2: Kondisi Rusak Ringan atau Rusak Berat (pada langkah 4): sistem tetap
menyimpan pencatatan, menandai kondisi tersebut pada data peralatan,dan pengembalian tetap tercatat. Kerusakan tidak otomatis menimbulkan denda pada model ini.
• A3: Jumlah alat yang kembali tidak sesuai (pada langkah 2): sistem meminta petugas memeriksa kembali isian sebelum penyimpanan;
pencatatan tidak disimpan sampai jumlah sesuai atau dikoreksi
