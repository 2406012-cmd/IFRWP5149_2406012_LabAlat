<!-- Tabel Model Analisis -->
|Sumber        |Hubungan   | Tujuan |
|--------------|-----------|--------|
|Mahasiswa     |Asosiasi   |SIA-UC01|
|Mahasiswa     |Asosiasi   |SIA-UC03|
|Mahasiswa     |Asosiasi   |SIA-UC05|
|Dosen Wali    |Asosiasi   |SIA-UC06|
|Admin Akademik|Asosiasi   |SIA-UC02|
|SIA-UC03      |<<include>>|SIA-UC04|
|SIA-UC05      |<<extend>> |SIA-UC03|

<!-- Uji Situasi -->
|                    Situasi Uji                         | Hasil Evaluasi Konsistensi Diagram & Deskripsi |
| ------------------------------------------------------ | ---------------------------------------------- |
|Validasi Berhasil dan Mahasiswa Tidak Mengunduh Bukti   | Konsistensi: Sistem menjalankan `SIA-UC03`, memanggil `SIA-UC04` (include) dengan hasil sukses, data tersimpan, namun kondisi ekstensi `SIA-UC05` bernilai false sehingga pencetakan/pengunduhan dilewati dengan baik. |
|Validasi Gagal                                          | Konsistensi: Alur alternatif pada `SIA-UC03` menangani kegagalan dari `SIA-UC04`. Sistem menghentikan proses penyimpanan tanpa memicu proses lanjutan atau perubahan status. |
|Validasi Berhasil dan Mahasiswa Mengunduh Bukti | Konsistensi : `SIA-UC03` berhasil melewati `SIA-UC04`, mencapai *extension point*, dan kondisi `[mahasiswa memilih unduh]` terpenuhi sehingga `SIA-UC05` dijalankan dengan sukses. |