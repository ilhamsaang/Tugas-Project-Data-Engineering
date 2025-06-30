<h1><strong>Tugas Data  Engineer: Web Scraping & Data Lowongan Kerja di Jobstreet</strong></h1>

[![Pre-commit](https://img.shields.io/badge/pre--commit-passing-brightgreen?logo=github)](https://github.com/ilhamsaang/Tugas-Data/actions)   [![Tests](https://img.shields.io/badge/tests-passing-brightgreen?logo=github)](https://github.com/ilhamsaang/Tugas-Data/actions)    [![Documentation](https://img.shields.io/badge/Documentation-file-brightblue?logo=readthedocs)](https://docs.google.com/document/d/16DCU0SObi8ZhqjiYe0Ir8vifVu_H1YO9ENuhEdEjubw/edit?usp=sharing)   [![Dibimbing](https://img.shields.io/badge/Dibimbing-Online%20Bootcamp-Green?logo=bookstack&logoColor=white)](https://dibimbing.id/en)   [![Jobstreet](https://img.shields.io/badge/Jobstreet-Job%20Portal-Purple?logo=workplace&logoColor=white)](https://id.jobstreet.com/)

> Disusun untuk program pelatihan **Data Science Fundamental (DSF) : Data Engineer** di <img src="./asset/Dbimbing Logo.png" alt="Dbimbing" width="10"/> [DBimbing](https://dibimbing.id/en)

> __dibuat Oleh: Mohammad Ilham__

> __Tahun: 2025__

Terima kasih kepada:
<img src="./asset/Dbimbing Logo.png" alt="Dbimbing" width="10"/> [DBimbing](https://dibimbing.id/en) &
<img src="./asset/Jobstreet logo.jpg" alt="Jobstreet" width="15"/> [Jobstreet](https://id.jobstreet.com/)

<h3><strong>📌 Tujuan</strong></h3>
melakukan web scraping lowongan pekerjaan dari situs JobStreet.co.id, memproses datanya, dan menyimpannya dalam format CSV untuk dianalisis lebih lanjut.

<h3><strong> 🛠️ Pembuatan </strong></h3>

1. Memahami website dan data apa saja yang tersedia

2. Memutuskan data apa saja yang akan diambil dan apa saja elementnya

3. Melakukan Check Element pada Website untuk melakukan Data Scraping
<img src="./asset/Check Element.png" alt="check element" width="200"/>

4. mencari tau Library apa saja yang diperlukan berdasarkan element yang ada dan data yang ingin diambil

5. mencoba melakukan data scraping dan menyimpannya sebagai CSV

6. mengolah data yang berhasil didapatkan

7. Membuat Dokumentasi pada dan Repositori pada Github


## 👨‍💻 Peran dalam Proyek
- **Data Engineer**: Menangani pembersihan, parsing, dan transformasi data mentah dari sumber CSV.
- **Data Analyst**: Melakukan analisis eksploratif, statistik deskriptif, dan visualisasi lowongan pekerjaan berbasis lokasi, tipe, dan kisaran gaji.

## 🗂️ Hasil Data Scraping
**Nama file**: `lowongan_jobstreet_lengkap_20250630_120733` 

**Waktu pengambilan data**: pada tanggal 30 Juni 2025, Pukul 12:07:33 WIB

**Jumlah data**: 64 baris 

**Sumber**: JobStreet (scraped/exported data)

### 🔑 Kolom Penting
| Kolom | Deskripsi |
|-------|-----------|
| `Job Position` | Nama posisi pekerjaan |
| `Company` | Nama perusahaan |
| `Location` | Lokasi pekerjaan (misal: Surabaya, Jawa Timur) |
| `Salary` | Informasi gaji (bisa kosong) |
| `Job Type` | Jenis pekerjaan (Full time, Kontrak) |
| `Days_Since_Posted` | Hari sejak posting |
| `Link` | Tautan ke detail pekerjaan |
| `Description` | Deskripsi rinci pekerjaan (multiline) |

## 🛠️ Data Engineering Process

### 1. Parsing CSV dengan format non-standar
- Menggunakan delimiter ';'
- Menangani kolom deskripsi multiline
- Memperbaiki encoding (UTF-8 BOM)
- Mengatasi inkonsistensi jumlah kolom dan missing values

### 2. Pembersihan dan Transformasi
- Drop baris duplikat
- Normalisasi kolom `Salary` ke dalam range numerik (jika memungkinkan)
- Ekstraksi `Provinsi` dari kolom `Location` untuk agregasi data wilayah

## 📈 Data Analysis Process

### Statistik Deskriptif
- Job Type paling umum: **Full time** (79,68%)
- Lokasi terbanyak: **Jakarta Selatan**


### Analisis Visual (dalam notebook)
- Bar chart jumlah lowongan per provinsi
- Pie chart jenis pekerjaan
- Jumlah data gaji tersedia hanya **18 dari 64**

## 💡 Insight & Rekomendasi
- Perluasan scraping untuk memperoleh lebih banyak data `Salary` yang valid
- Data `Description` bisa diolah dengan NLP untuk keyword extraction
- Perusahaan bisa fokus memposting di wilayah-wilayah dengan demand tinggi seperti Jakarta Selatan

## 🧰 Tools
- Python (Pandas, Matplotlib, Seaborn, Selenium, matplotlib, BeautifulSoup)
- Visual Studio Code
- Jupyter Notebook

<h3><strong> 📊 Hasil Data </strong></h3>

<img src="./asset/Jumlah Lowongan yang dibuka 1 bulan ini.png" alt="Hasil1" width="300"/>

<img src="./asset/Jumlah Lowongan Per Provinsi, Distribusi Jenis Pekerjaan, Jumlah Data gaji yang tersedia per provinsi, perusahaan dengan data gaji, 10 perusahaan dengan lowongan terbanyak.png" alt="Hasil2" width="300"/>

💼 1. Jumlah Lowongan per Provinsi
Jakarta Raya mendominasi dengan jumlah lowongan kerja terbanyak.

Diikuti oleh Banten, Jawa Timur, Jawa Barat, dan Sumatera Utara.

Provinsi seperti Kalimantan Timur dan Sulawesi Selatan punya jumlah lowongan yang jauh lebih sedikit.

📌 Interpretasi:

> Konsentrasi lowongan sangat terpusat di wilayah Jabodetabek dan provinsi padat penduduk. Daerah luar Jawa memiliki sedikit lowongan.

🧰 2. Distribusi Jenis Pekerjaan
Hampir seluruh lowongan adalah Full time.

Sedikit yang termasuk kategori Kontrak/Temporer atau Kasual.

📌 Interpretasi:

> Sebagian besar perusahaan menawarkan pekerjaan penuh waktu, menandakan kebutuhan tenaga kerja jangka panjang.

💰 3. Jumlah Data Gaji yang Tersedia per Provinsi
Lagi-lagi, Jakarta Raya dan Banten menempati posisi teratas untuk jumlah data gaji yang diungkapkan.

Provinsi lainnya menunjukkan lebih sedikit transparansi soal gaji.

📌 Interpretasi:

> Wilayah-wilayah industri utama lebih cenderung mencantumkan gaji secara terbuka dibanding daerah lainnya.

🏢 4. Perusahaan dengan Data Gaji 

>  Banyak perusahaan belum mencantumkan data gaji sebab data hanya menunjukan ada 1 perusahaan dengan 2 lowongan menggunakan data gaji dan sisanya hanya ada 16 perusahaan saja dengan masing masing 1 lowongan yang memiliki data gaji

📌 Interpretasi:

> Perusahaan-perusahaan ini bisa dianggap lebih terbuka atau menarik bagi pencari kerja yang mengutamakan kejelasan kompensasi.

🏆 5. 10 Perusahaan dengan Lowongan Terbanyak
Perusahaan yang paling aktif membuka lowongan adalah:

PT Depoguna Bangunan Online

PT Bussan Auto Finance (BAF)

PT Propan Raya Industrial Coating Chemical

📌 Interpretasi:

> Perusahaan yang banyak membuka lowongan juga cenderung lebih terbuka soal gaji, ini positif bagi pencari kerja.


Ikuti dan dukung Dbimbing:
- 🌐 Website: [dbimbing.id](https://dibimbing.id/en)
- 📷 Instagram: [@dbimbing](https://www.instagram.com/dibimbing.id/)
- ▶️ YouTube: [Dbimbing Official](https://www.youtube.com/@dibimbingid)

> Dibuat dengan semangat belajar bersama komunitas Dbimbing 🚀
