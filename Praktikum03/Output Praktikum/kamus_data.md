# Kamus Data Tabel Analitik Pricing

| Kolom | Tipe/Satuan | Definisi dan cara penghitungan |
|---|---|---|
| borough_naik | kategori | Borough lokasi penjemputan dari join PULocationID dengan taxi zone lookup. |
| jam_mulai | datetime, jam lokal New York | Waktu penjemputan yang dibulatkan ke awal jam. |
| jumlah_perjalanan | perjalanan | Jumlah baris perjalanan pada borough dan jam yang sama. Hanya kelompok dengan minimal 30 perjalanan yang disimpan. |
| rata_tarif_per_mil | USD/mil | Median total_amount dibagi trip_distance pada kelompok. Nama kolom dipertahankan mengikuti kebutuhan tim, tetapi statistik yang dipakai adalah median. |
| rata_kecepatan | mil/jam | Median trip_distance dibagi durasi perjalanan dalam jam. |
| suhu_c | derajat Celsius | Nilai suhu pertama pada jam yang sama dari Open-Meteo. |
| hujan | 0 atau 1 | Bernilai 1 apabila hujan_mm pada jam tersebut lebih dari 0,1 mm; selain itu 0. |

## Sumber

NYC TLC Yellow Taxi Trip Records Januari 2023, NYC Taxi Zone Lookup, referensi payment_type, dan Open-Meteo Archive API.
