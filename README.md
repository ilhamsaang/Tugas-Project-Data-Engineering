<h1><strong>Web Scraping & Data Lowongan Kerja di Jobstreet</strong></h1>

[![Pre-commit](https://img.shields.io/badge/pre--commit-passing-brightgreen?logo=github)](https://github.com/ilhamsaang/Tugas-Data/actions)[![Tests](https://img.shields.io/badge/tests-passing-brightgreen?logo=github)](https://github.com/ilhamsaang/Tugas-Data/actions)

> Disusun untuk program pelatihan **Data Science Fundamental (DSF)** di <img src="./Dbimbing Logo.png" alt="Dbimbing" width="10"/> [DBimbing](https://dibimbing.id/en)

<h3><strong>📌 Tujuan</strong></h3>
melakukan web scraping lowongan pekerjaan dari situs JobStreet.co.id, memproses datanya, dan menyimpannya dalam format CSV untuk dianalisis lebih lanjut.

<h3><strong>🧰 1. Instalasi dan Import Library</strong></h3>

%pip install selenium beautifulsoup4 pandas webdriver-manager
!apt-get update
!apt-get install chromium-browser

<strong>✨ Tujuan:</strong>

Menginstal library yang diperlukan untuk scraping:

selenium: Mengontrol browser secara otomatis

beautifulsoup4: Mengambil dan memproses data HTML

pandas: Untuk menyimpan dan mengolah data

webdriver-manager: Memudahkan setup driver browser

<h3><strong>📚 2. Import Modul Python</strong></h3>

from selenium import webdriver
from selenium.webdriver.chrome.options import Options
from selenium.webdriver.chrome.service import Service
from selenium.webdriver.common.by import By
from webdriver_manager.chrome import ChromeDriverManager
from bs4 import BeautifulSoup
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import time, os, re

<strong>✨ Tujuan:</strong>

Semua library di atas digunakan untuk:

Mengakses dan membaca HTML

Scraping dinamis menggunakan Selenium

Analisis data dan visualisasi dengan pandas, matplotlib, seaborn

Fungsi tambahan seperti regex (re), delay waktu (time), dan file (os)

<h3><strong>🧩 3. Fungsi: Generate Filename</strong></h3>

def generate_unique_filename(base_name, ext=".csv"):
    i = 1
    filename = f"{base_name}{ext}"
    while os.path.exists(filename):
        filename = f"{base_name}({i}){ext}"
        i += 1
    return filename

<strong>✨ Tujuan:</strong>

Agar nama file CSV tidak menimpa file yang sudah ada, fungsi ini akan menambahkan angka di belakang jika nama file sudah digunakan.

<h3><strong>⏳ 4. Fungsi: Konversi Waktu Posting</strong></h3>

def convert_posted_date_to_days(posted_text):
    ...
<strong>✨ Tujuan:</strong>
Mengubah informasi waktu seperti "2 hari yang lalu" atau "1 bulan yang lalu" menjadi angka (int) berupa jumlah hari.

<h3><strong>🌐 5. Setup Selenium dan Masukkan Keyword</strong></h3>
python
Salin
Edit
options = Options()
options.add_argument("--headless")  # Tanpa buka browser
...
driver = webdriver.Chrome(options=options)

<strong>✨ Tujuan:</strong>

Mengatur agar browser berjalan di background

Membuka browser otomatis dengan webdriver.Chrome

<h3><strong>🔍 6. Scraping Data Lowongan Kerja</strong></h3>

base_url = f"https://www.jobstreet.co.id/id/data-analyst-jobs"
...
driver.get(url)
...
soup = BeautifulSoup(driver.page_source, "html.parser")

<strong>✨ Tujuan:</strong>

Mengakses halaman pencarian kerja

Menggunakan BeautifulSoup untuk membaca dan ambil data dari HTML

<strong>✨ 🔎 Data yang diambil:</strong>

Posisi pekerjaan

Nama perusahaan

Lokasi kerja

Gaji (jika tersedia)

Tipe pekerjaan (penuh waktu, kontrak, dll.)

Deskripsi pekerjaan

Link ke lowongan

Umur lowongan (berapa hari yang lalu)

<h3><strong>💾 7. Menyimpan Data ke CSV</strong></h3>

filename = generate_unique_filename("lowongan_jobstreet_lengkap")
df = pd.DataFrame(jobs)
df.to_csv(filename, index=False, encoding='utf-8-sig')

<strong>✨ Tujuan:</strong>

Mengubah list jobs menjadi DataFrame

Menyimpan hasil scraping ke file .csv untuk analisis lebih lanjut

<h3><strong>📥 8. Membaca Data CSV</strong></h3>

data = pd.read_csv('lowongan_jobstreet_lengkap.csv', engine='python')

<strong>✨ Tujuan:</strong>

Membaca kembali data yang sudah disimpan untuk dilakukan analisis statistik atau visualisasi

🖼️ Penjelasan Gambar (Jika Ada)
Jika terdapat grafik atau visualisasi di cell berikutnya (belum dibaca), grafik biasanya akan menunjukkan:

Jumlah lowongan per lokasi

Distribusi gaji

Frekuensi jenis pekerjaan

Saya bisa lanjut membaca dan menjelaskan bagian visualisasi / analisis jika kamu mau. Cukup katakan "lanjutkan" atau "jelaskan analisisnya". 

> dibuat Oleh: Mohammad Ilham  

> Tahun: 2025

Ikuti dan dukung Dbimbing:
- 🌐 Website: [dbimbing.id](https://dibimbing.id/en)
- 📷 Instagram: [@dbimbing](https://www.instagram.com/dibimbing.id/)
- ▶️ YouTube: [Dbimbing Official](https://www.youtube.com/@dibimbingid)

> Dibuat dengan semangat belajar bersama komunitas Dbimbing 🚀
