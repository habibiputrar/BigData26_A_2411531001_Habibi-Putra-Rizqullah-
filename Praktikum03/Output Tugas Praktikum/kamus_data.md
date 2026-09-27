# Kamus Data - Tugas Praktikum Big Data 3

| Nama kolom | Tipe aktual | Satuan | Sumber | Definisi | Aturan validitas | Penanganan nilai hilang |
|---|---|---|---|---|---|---|
| tpep_pickup_datetime | timestamp[us] | waktu lokal | NYC TLC | Waktu penjemputan | Harus berada dalam periode partisi | Baris di luar periode dibuang |
| tpep_dropoff_datetime | timestamp[us] | waktu lokal | NYC TLC | Waktu penurunan | Harus sesudah waktu pickup | Baris dengan durasi tidak valid dibuang |
| passenger_count | double | orang | NYC TLC | Jumlah penumpang | Nilai numerik dan tidak kosong setelah proses | Median per jam lalu median global |
| passenger_count_diimputasi | int8 | 0/1 | Turunan | Penanda passenger_count hasil imputasi | Hanya 0 atau 1 | Tidak boleh kosong |
| trip_distance | double | mil | NYC TLC | Jarak perjalanan asli | Rentang analitis 0,01-100 | Baris di luar rentang dibuang |
| trip_distance_capped | double | mil | Turunan | Jarak setelah pembatasan persentil 99,5 | Tidak melebihi batas persentil bulan | Dihitung dari trip_distance |
| durasi_menit | double | menit | Turunan | Durasi pickup sampai dropoff | Rentang analitis 1-180 | Baris di luar rentang dibuang |
| PULocationID | int64 | kode | NYC TLC | Kode zona penjemputan | Diharapkan ada pada tabel zona | Atribut zona diberi Unknown bila tidak cocok |
| DOLocationID | int64 | kode | NYC TLC | Kode zona penurunan | Bilangan bulat | Dipertahankan apa adanya |
| payment_type | int64 | kode | NYC TLC | Kode metode pembayaran | Diharapkan 1-6 | Label diberi Tidak diketahui bila tidak cocok |
| fare_amount | double | USD | NYC TLC | Tarif dasar | Numerik | Tidak diimputasi |
| tip_amount | double | USD | NYC TLC | Jumlah tip | Numerik; nilai negatif perlu ditinjau | Tidak diimputasi |
| total_amount | double | USD | NYC TLC | Total pembayaran | Harus lebih besar dari nol pada data bersih | Baris tidak valid dibuang |
| tarif_ekstrem | int8 | 0/1 | Turunan | Penanda total_amount di atas batas IQR | Hanya 0 atau 1 | Tidak boleh kosong |
| zona_naik | string | kategori | Taxi Zone Lookup | Nama zona penjemputan | Satu label per LocationID | Diisi Tidak diketahui |
| borough_naik | string | kategori | Taxi Zone Lookup | Borough lokasi penjemputan | Satu label per LocationID | Diisi Unknown |
| service_zone | string | kategori | Taxi Zone Lookup | Jenis wilayah layanan taksi | Satu label per LocationID | Diisi Tidak diketahui |
| nama_pembayaran | string | kategori | Referensi internal | Label metode pembayaran | Satu label per payment_type | Diisi Tidak diketahui |
| kena_biaya_admin | int8 | 0/1 | Referensi internal | Penanda metode dengan biaya admin | Hanya 0 atau 1 | Diisi 0 bila kode tidak dikenal |
| jam_mulai | timestamp[us] | waktu lokal | Turunan | Waktu pickup dibulatkan per jam | Presisi satu jam | Dihitung dari pickup |
| suhu_c | double | derajat Celsius | Open-Meteo | Suhu udara pada jam pickup | Numerik | Tidak diimputasi; ditandai cuaca_tersedia |
| hujan_mm | double | mm | Open-Meteo | Presipitasi pada jam pickup | Diharapkan >= 0 | Tidak diimputasi; ditandai cuaca_tersedia |
| cuaca_tersedia | bool | Boolean | Turunan | Penanda kelengkapan join cuaca | True atau False | Tidak boleh kosong |
| hujan | int8 | 0/1 | Turunan | Penanda presipitasi > 0,1 mm | 0, 1, atau kosong jika cuaca tidak tersedia | Dibiarkan kosong bila join cuaca gagal |
| tanggal | timestamp[us] | tanggal | Turunan | Tanggal pickup tanpa komponen jam | Harus sesuai periode | Dihitung dari pickup |
| nama_libur | string | kategori | Nager.Date API | Nama hari libur nasional | Satu label gabungan per tanggal | Diisi Bukan hari libur |
| libur_nasional | int8 | 0/1 | Nager.Date API | Penanda hari libur nasional AS | Hanya 0 atau 1 | Diisi 0 bila tanggal tidak cocok |
| hari_minggu | int8 | indeks | Turunan | Nomor hari Senin=0 sampai Minggu=6 | Rentang 0-6 | Dihitung dari pickup |
| akhir_pekan | int8 | 0/1 | Turunan | Penanda Sabtu atau Minggu | Hanya 0 atau 1 | Dihitung dari hari_minggu |
| kecepatan_mph | double | mil/jam | Turunan | Kecepatan rata-rata perjalanan | Dihitung pada durasi dan jarak valid | Tidak diimputasi |
| tarif_per_mil | double | USD/mil | Turunan | Total pembayaran per mil | Dihitung pada jarak > 0 | Tidak diimputasi |
| periode | string | YYYY-MM | Parameter pipeline | Partisi bulan data | Harus sama dengan bulan pickup | Tidak boleh kosong |