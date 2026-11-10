# Analisis-Deret-Waktu-A
Forecasting PDB Industri Makanan dan Minuman Indonesia
Johanes Efata Putra Diaz Prasetiyo (24083010016)

Proyek ini merupakan bagian dari tugas Ujian Akhir Semester (UAS) mata kuliah Analisis Data Waktu (ADW).

Penelitian ini bertujuan untuk menganalisis karakteristik data Produk Domestik Bruto (PDB) Industri Makanan dan Minuman Indonesia serta membandingkan metode forecasting RegARIMA (regresi dengan error ARIMA) dan Holt-Winters Exponential Smoothing.

1. Latar Belakang

Subsektor Industri Makanan dan Minuman merupakan kontributor terbesar pada PDB Industri Pengolahan Non-Migas di Indonesia dengan rata-rata pangsa sekitar 34,04% (mencapai 39,08% pada periode terbaru). Peramalan kinerja subsektor ini penting untuk memantau pertumbuhan riil manufaktur dan mendukung perencanaan kebijakan industri.

Dari sisi deret waktu, data ini memiliki tiga karakteristik utama:

Tidak stasioner: Nilai produksi riil tumbuh lebih dari tiga kali lipat dari Rp85.184,0 Miliar (2010-Q1) menjadi Rp261.225,3 Miliar (2026-Q3), disertai fluktuasi kuartalan yang makin melebar.
Musiman kuartalan: Produksi cenderung meningkat pada pertengahan tahun (Q2–Q3) dan melandai pada akhir maupun awal tahun (Q4–Q1).
Efek pergeseran hari raya: Periode Ramadan dan Idul Fitri maju sekitar 11 hari setiap tahun (dari Q3 di 2010–2013, ke Q2 di 2017–2022, hingga masuk ke Q1 pada 2025–2026), serta terdapat perubahan kemiringan tren pasca-pandemi COVID-19.
2. Dataset
Sumber: Badan Pusat Statistik (BPS) melalui Pusat Data dan Informasi (Pusdatin) Kementerian Perindustrian
File: data/pdb_industri_makanan_minuman_bps.csv
Periode: 2010 Q1 – 2026 Q3
Frekuensi: Triwulanan
Jumlah observasi: 67 (tanpa missing value maupun duplikasi)
Variabel target: PDB Industri Makanan dan Minuman ADHK 2010 (Miliar Rupiah)
Kolom	Deskripsi Singkat
periode, tanggal, tahun, triwulan	Penanda waktu kuartalan (2010-Q1 s.d. 2026-Q3)
pdb_mamin_adhk_miliar_rp	Variabel target: PDB Industri Makanan & Minuman Harga Konstan 2010 (Miliar Rupiah)
pdb_mamin_adhb_miliar_rp	PDB Industri Makanan & Minuman Harga Berlaku (Miliar Rupiah), pembanding nominal
pdb_industri_nonmigas_adhk_miliar_rp	Total PDB Industri Pengolahan Non-Migas ADHK 2010 (Miliar Rupiah)
hari_ramadan_idul_fitri	Jumlah hari Ramadan dan Idul Fitri yang jatuh pada triwulan terkait
3. Metode Penelitian
RegARIMA (metode utama): model ARIMA/SARIMA dengan regressor variabel kalender hari raya (hari_ramadan_idul_fitri) untuk menangkap efek pergeseran Ramadan dan Idul Fitri.
Holt-Winters Exponential Smoothing (metode pembanding): pemulusan eksponensial dengan komponen level, tren, dan musiman.

Kedua metode dibandingkan menggunakan ukuran akurasi RMSE, MAE, MAPE, dan sMAPE pada data uji.

4. Tahapan Penelitian
Data Collection
Data Preprocessing
Exploratory Data Analysis (EDA)
Stationarity Analysis
RegARIMA Modeling
Holt-Winters Modeling
Model Evaluation
Forecasting and Comparison
5. Struktur Repository
.
├── data/
│   └── pdb_industri_makanan_minuman_bps.csv
├── notebooks/
│   └── Forcast_Industri_ADW.ipynb
├── images/
├── requirements.txt
└── README.md
data/: Dataset penelitian.
notebooks/: Notebook analisis dan pemodelan (Forcast_Industri_ADW.ipynb).
images/: Visualisasi hasil analisis.
6. Cara Menjalankan
bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter lab notebooks/Forcast_Industri_ADW.ipynb
7. Status Pengerjaan
 Pemilihan dataset
 Penentuan metode
 Data preprocessing
 Exploratory Data Analysis
 Modeling
 Evaluasi model
 Forecasting
