# Implementasi ETL Pipeline Asynchronous dan OLAP pada Data Skor Perguruan Tinggi Amerika Serikat Menggunakan PostgreSQL dan Atoti

## Deskripsi Proyek
Proyek ini membangun workflow Data Warehouse untuk menganalisis data pendidikan tinggi Amerika Serikat (College Scorecard 2017-2018) menggunakan ETL pipeline asynchronous (aiohttp & asyncio) dan PostgreSQL berbasis cloud (Supabase). Data 6.322 institusi ditransformasi menjadi 12.644 baris, lalu dianalisis secara multidimensi menggunakan Atoti melalui operasi OLAP (roll-up, slice, dice, drill-down). Hasil menunjukkan kenaikan rata-rata completion rate nasional dari 0,474 menjadi 0,500 serta kenaikan biaya kuliah sekitar 3,1%.

## Tujuan
- Membangun pipeline ETL lengkap dari API College Scorecard ke PostgreSQL cloud.
- Mengimplementasikan asynchronous extraction untuk efisiensi pengambilan data.
- Menerapkan operasi OLAP multidimensi menggunakan Atoti.
- Menganalisis tren pendidikan tinggi Amerika Serikat 2017-2018.

## Tools & Library
- Python
- aiohttp, asyncio (asynchronous extraction)
- Pandas, NumPy (data manipulation)
- SQLAlchemy, psycopg2 (PostgreSQL connection)
- Supabase (cloud PostgreSQL)
- Atoti (OLAP cube & dashboard)
- Matplotlib, Seaborn (visualisasi)
- Ngrok (publikasi dashboard)
- Google Colab

## Tahapan Proyek
1. **Extract** - Pengambilan data dari API College Scorecard (64 halaman) secara paralel dengan aiohttp & asyncio
2. **Transform** - Reshape wide-to-long (6.322 → 12.644 baris), imputasi median, standardisasi teks
3. **Load** - Pemuatan ke PostgreSQL cloud (Supabase) via SQLAlchemy, dilengkapi index & materialized view
4. **OLAP Analysis** - Roll-up, slice, dice, drill-down menggunakan Atoti
5. **Visualisasi** - Dashboard interaktif Atoti dipublikasikan via Ngrok

## Hasil
- **Completion rate** nasional naik dari 0,474 (2017) menjadi 0,500 (2018).
- **Biaya kuliah** naik ~3,1% (dari $12.756 ke $13.150).
- **California** memiliki institusi terbanyak dengan biaya kuliah di bawah rata-rata nasional.
- **New York** memiliki completion rate tertinggi (0,555), sedangkan **Texas** memiliki biaya kuliah terendah di antara 5 negara bagian terbesar.
- Korelasi positif antara biaya kuliah dan completion rate per negara bagian.

## File Terkait
- 📓 [Notebook ETL & OLAP](./notebook/etl_olap_college_scorecard.ipynb)
- 📁 Dataset: College Scorecard (data.gov)<br>(https://catalog.data.gov/dataset/college-scorecard)

## Author
**Fauziah Roikhana Wardah** (dan tim)
- Program Studi S1 Sains Data, Universitas Negeri Surabaya
- Email: fauziahroikhana@gmail.com
