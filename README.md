# Praktikum Big Data

Kumpulan notebook, tugas, dan laporan praktikum mata kuliah **Big Data**. Materi mencakup pengolahan data, pembersihan dan integrasi data, penyusunan pipeline, serta perbandingan model penyimpanan menggunakan Python.

| Identitas | Keterangan |
| --- | --- |
| Nama | Habibi Putra Rizqullah |
| NIM | 2411531001 |
| Kelas | A |
| Repository | [BigData26_A_2411531001_Habibi-Putra-Rizqullah-](https://github.com/habibiputrar/BigData26_A_2411531001_Habibi-Putra-Rizqullah-) |

## Daftar Praktikum

| Praktikum | Fokus Materi | Implementasi |
| --- | --- | --- |
| [01](Praktikum01/) | Pengolahan data dan pengukuran kinerja | Membaca data NYC Yellow Taxi, membandingkan CSV dan Parquet, memilih kolom, membaca data bertahap, melakukan agregasi dengan pandas dan PySpark, serta mengukur waktu dan penggunaan memori. |
| [02](Praktikum02/) | Akuisisi dan pembersihan data | Membuat data transaksi sintetis dengan Faker, menangani nilai hilang dan duplikat, menyeragamkan teks, memperbaiki tipe data, serta mengekspor dataset bersih. |
| [03](Praktikum03/) | Integrasi data dan pipeline pra-pemrosesan | Menggabungkan data perjalanan, referensi zona, cuaca, dan hari libur; memeriksa kualitas data; melakukan rekayasa fitur; serta menyusun pipeline dengan pencatatan lineage dan pengujian idempotensi. |
| [04](Praktikum04/) | NoSQL dan pemodelan data | Membandingkan tabel, key-value, document, penyimpanan kolom, graph, dan indeks spasial; dilanjutkan dengan versi data, time travel, serta schema enforcement pada Delta Lake. |

## Notebook dan Laporan

Pilih notebook untuk melihat kode beserta output yang tersimpan, atau buka laporan PDF untuk membaca pembahasan hasil praktikum.

| Praktikum | Notebook Praktikum | Notebook Tugas / Latihan | Laporan |
| --- | --- | --- | --- |
| 01 | [Buka notebook](Praktikum01/BD_A_P01_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Buka tugas](Praktikum01/BD_A_TugasP01_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Laporan PDF](Praktikum01/BD_A_Laporan%20Praktikum%2001_2411531001_Habibi%20Putra%20Rizqullah%20%281%29.pdf) |
| 02 | [Buka notebook](Praktikum02/BD_KelasA_P02_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Buka latihan](Praktikum02/BD_KelasA_LatihanP02_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Laporan PDF](Praktikum02/BD_A_Laporan%20Praktikum%2002_2411531001_Habibi%20Putra%20Rizqullah%20%281%29.pdf) |
| 03 | [Buka notebook](Praktikum03/BD_A_P03_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Buka tugas](Praktikum03/BD_A_TugasP03_2411531001_Habibi_Putra_Rizqullah_%281%29.ipynb) | [Laporan PDF](Praktikum03/BD_A_Laporan%20Praktikum%2003_2411531001_Habibi%20Putra%20Rizqullah.pdf) |
| 04 | [Buka notebook](Praktikum04/BD_A_P04_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Buka tugas](Praktikum04/BD_A_TugasP04_2411531001_Habibi_Putra_Rizqullah.ipynb) | [Laporan PDF](Praktikum04/BD_A_Laporan_Praktikum_04_2411531001_Habibi_Putra_Rizqullah.pdf) |

## Struktur Repository

```text
.
├── Praktikum01/
│   ├── Notebook praktikum (.ipynb)
│   ├── Notebook tugas (.ipynb)
│   └── Laporan praktikum (.pdf)
├── Praktikum02/
│   ├── Notebook praktikum (.ipynb)
│   ├── Notebook latihan (.ipynb)
│   └── Laporan praktikum (.pdf)
├── Praktikum03/
│   ├── Notebook praktikum dan tugas (.ipynb)
│   ├── Laporan praktikum (.pdf)
│   ├── Output Praktikum/
│   └── Output Tugas Praktikum/
├── Praktikum04/
│   ├── Notebook praktikum (.ipynb)
│   ├── Notebook tugas (.ipynb)
│   └── Laporan praktikum (.pdf)
└── README.md
```

Nama berkas lengkap tersedia melalui tautan pada tabel notebook dan laporan.

## Teknologi yang Digunakan

| Kebutuhan | Teknologi |
| --- | --- |
| Lingkungan kerja | Python, Jupyter Notebook, Google Colab |
| Pengolahan data | pandas, NumPy, PyArrow, PySpark |
| Data sintetis dan akuisisi | Faker, requests |
| Visualisasi dan pengukuran | Matplotlib, psutil, time |
| Pra-pemrosesan fitur | scikit-learn |
| Query dan basis data | SQLite, SQLAlchemy, DuckDB |
| Document, graph, dan spasial | TinyDB, NetworkX, Shapely |
| Penyimpanan dengan versi | Delta Lake melalui pustaka deltalake |

Pustaka yang digunakan berbeda pada setiap notebook. Ikuti sel instalasi dan import pada notebook yang dipilih.

## Menjalankan Notebook

Notebook terutama disusun untuk **Google Colab**. Beberapa notebook memakai Google Drive dan path `/content/drive/MyDrive/BigData/` untuk membaca data serta menyimpan hasil.

1. Buka [Google Colab](https://colab.research.google.com/).
2. Pada pilihan untuk membuka notebook, gunakan tab **GitHub**, lalu masukkan URL repository ini.
3. Pilih notebook praktikum atau tugas yang ingin dijalankan.
4. Gunakan runtime Python 3 dan jalankan sel secara berurutan dari atas.
5. Jalankan sel instalasi dependensi dan hubungkan Google Drive jika notebook memerlukannya.
6. Periksa path input, folder output, serta ketersediaan data sebelum melanjutkan ke sel pengolahan.

Beberapa notebook tugas membaca hasil notebook praktikum sebelumnya. Jalankan notebook praktikum terlebih dahulu dan pastikan berkas yang dibutuhkan sudah tersedia di folder yang ditentukan.

Khusus alur antarpertemuan, **Praktikum 04 menggunakan data bersih dari Praktikum 03**. Siapkan `trips_bersih.zip` atau folder `trips_bersih` sesuai path input notebook. Tugas Praktikum 04 juga membaca `benchmark_nosql.csv` yang dihasilkan notebook praktikumnya.

Untuk menjalankan melalui Jupyter di komputer lokal, unduh repository:

```bash
git clone https://github.com/habibiputrar/BigData26_A_2411531001_Habibi-Putra-Rizqullah-.git
cd BigData26_A_2411531001_Habibi-Putra-Rizqullah-
```

Buka file `.ipynb` melalui Jupyter atau editor yang mendukung notebook. Sesuaikan bagian Google Drive, path `/content/`, dan dependensi dengan lingkungan lokal; notebook yang menggunakan PySpark juga memerlukan lingkungan Java yang sesuai.

## Data dan Hasil Pengolahan

Data yang digunakan meliputi perjalanan **NYC TLC Yellow Taxi** Januari dan Juli 2023, referensi zona taksi, cuaca dari **Open-Meteo**, hari libur dari **Nager.Date**, serta transaksi sintetis dari **Faker**. Pemakaiannya mengikuti kebutuhan setiap notebook.

Repository menyertakan notebook dengan output tersimpan, laporan PDF, dan sebagian hasil pengolahan berbentuk CSV, Markdown, serta diagram PDF. Dataset mentah, dataset bersih Parquet, dan arsip hasil pipeline tidak disertakan dalam repository ini; siapkan melalui langkah pada notebook atau folder penyimpanan yang digunakan saat praktikum.

| Hasil yang Tersedia | Lokasi |
| --- | --- |
| Kamus data, laporan kualitas, dan lineage hasil praktikum | [Output Praktikum](Praktikum03/Output%20Praktikum/) |
| Kamus data, laporan kualitas gabungan dan per bulan, serta lineage hasil tugas | [Output Tugas Praktikum](Praktikum03/Output%20Tugas%20Praktikum/) |
| Diagram alur lineage | [diagram_lineage.pdf](Praktikum03/Output%20Tugas%20Praktikum/diagram_lineage.pdf) |

Waktu eksekusi dan penggunaan memori dapat berbeda sesuai runtime, ukuran data, serta kondisi cache. Pembahasan dan hasil eksperimen masing-masing tersedia pada notebook dan laporan terkait.
