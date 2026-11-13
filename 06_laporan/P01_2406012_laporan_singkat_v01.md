# Laporan Pertemuan 1: Pengenalan Lingkungan Praktikum dan Kakas Pemodelan UML

## A. Tujuan Pembelajaran

Setelah mengikuti praktikum ini, mahasiswa mampu:

1. Menyiapkan *workspace* dan struktur direktori proyek praktikum dengan tertib sesuai standar operasional prosedur (SOP) yang ditetapkan.

2. Memahami perbedaan antara bahasa pemodelan (UML) dengan kakas pemodelan (*UML tools* seperti draw.io, Visual Paradigm, atau StarUML).

3. Mengoperasikan fitur dasar kakas UML, meliputi pembuatan kanvas baru, pemilihan pustaka bentuk (*shapes*), penempatan elemen, penarikan garis penghubung berarah, dan pelabelan.

4. Menyimpan berkas sumber diagram (`.drawio`), mengekspor hasil ke format gambar (`.png`), serta menguji kembali berkas sumber untuk memastikan diagram tetap dapat disunting.

5. Menyusun dokumentasi pendukung berupa `README.md`, *template* metadata artefak, catatan orientasi skenario, dan *logbook* praktikum.

## B. Teori Dasar Praktikum

*Unified Modeling Language* (UML) adalah bahasa pemodelan visual standar untuk menspesifikasikan dan mendokumentasikan sistem berorientasi objek, sedangkan aplikasi seperti **draw.io**, **Visual Paradigm**, atau **StarUML** merupakan kakas (*tools*) yang digunakan untuk menggambar model tersebut. Penguasaan fitur dasar kakas menjadi langkah awal sebelum masuk ke analisis kebutuhan sistem secara mendalam.

Dalam pengelolaan artefak pemodelan, diterapkan beberapa prinsip kerja utama:

* **Pemisahan Berkas Sumber dan Ekspor:** Berkas sumber (seperti `.drawio`) menyimpan struktur objek diagram agar dapat dibuka dan disunting kembali di kemudian hari, sedangkan berkas ekspor (`.png` atau `.svg`) digunakan untuk keperluan peninjauan visual. Keduanya wajib memiliki nama dasar dan nomor versi yang sama (`v01`).

* **Struktur Workspace Terstandar:** Seluruh artefak proyek disimpan dalam satu folder induk (`IFRWP5149_<NIM>_LabAlat`) yang terbagi ke dalam subfolder terpisah (`00_administrasi`, `01_skenario`, `02_template`, `03_latihan_tools`, `04_model_analisis`, `05_model_desain`, dan `06_laporan`) agar berkas latihan awal tidak tercampur dengan model analisis yang telah divalidasi.

## C. Hasil Praktikum

### 1. Setup Workspace dan Dokumentasi Awal

Pada tahap persiapan lingkungan kerja, dilakukan pembuatan struktur proyek untuk studi kasus *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*:

* **Pembuatan Struktur Direktori:** Membuat folder induk `IFRWP5149_<NIM>_LabAlat` beserta seluruh subfoldernya. Folder `04_model_analisis` dan `05_model_desain` dibiarkan kosong sesuai ketentuan karena pada pertemuan ini belum dihasilkan model tervalidasi.

* **Pengisian Berkas Administrasi dan Template:**

  * Membuat berkas `README.md` di direktori utama yang memuat identitas mahasiswa, nama studi kasus, kakas yang digunakan, daftar isi folder, serta status pekerjaan Pertemuan 1.

  * Menyimpan *template* metadata kosong pada `02_template/template_metadata_artefak_v01.md` sebagai standar identitas artefak untuk pertemuan-pertemuan selanjutnya.

  * Mencatat ruang lingkup awal skenario orientasi `S-ORI-01` beserta batasan dan pertanyaan terbuka ke dalam berkas `01_skenario/S-ORI-01_orientasi_kasus_v01.md`.

  * Merekam seluruh tahapan pengerjaan, hasil pemeriksaan, dan kendala pada `00_administrasi/P01_<NIM>_logbook_v01.md`.

### 2. Latihan Operasional Kakas UML (S-ORI-01)

Sebagai uji operasional kakas menggunakan **draw.io**, dibuat sebuah diagram aktivitas sederhana berdasarkan skenario orientasi `S-ORI-01` (*mahasiswa membuka daftar peralatan dan melihat informasi ketersediaan*):

* **Penyusunan Elemen Diagram:** Menempatkan empat elemen secara berurutan pada kanvas berjudul *Latihan kakas S-ORI-01*, yaitu *initial node* $\rightarrow$ *action* **"Buka daftar peralatan"** $\rightarrow$ *action* **"Lihat informasi ketersediaan"** $\rightarrow$ *activity final node*, yang dihubungkan dengan tiga garis *control flow* berarah.

* **Pelabelan Status:** Menambahkan catatan status **"Belum divalidasi sebagai model proses"** pada kanvas serta memastikan tidak ada aturan bisnis tambahan (seperti persetujuan atau denda) yang dikarang di luar skenario.

* **Penyimpanan, Ekspor, dan Uji Buka Ulang:** Menyimpan berkas sumber sebagai `P01_<NIM>_latihan_activity_v01.drawio` di dalam folder `03_latihan_tools/` dan mengekspornya menjadi `P01_<NIM>_latihan_activity_v01.png`. Selanjutnya dilakukan pengujian dengan menutup aplikasi, membuka kembali berkas `.drawio`, menggeser posisi elemen untuk membuktikan file tetap dapat disunting, lalu menyimpan dan mengekspor ulang agar kedua berkas sinkron.

## D. Kesimpulan

Melalui praktikum Pertemuan 1 ini, mahasiswa telah berhasil menyiapkan lingkungan kerja (*workspace*) yang terstruktur rapi dan memahami cara mengoperasikan fitur dasar kakas pemodelan UML. Kedisiplinan dalam memisahkan folder latihan dari folder model tervalidasi, menjaga konsistensi penamaan versi berkas sumber dan ekspor, serta membiasakan pengujian buka-ulang berkas sumber menjadi fondasi penting agar seluruh artefak pemodelan pada pertemuan berikutnya dapat dikelola dan ditelusuri dengan baik.