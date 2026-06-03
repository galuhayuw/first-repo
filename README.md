# Customer Segmentation for FundFusion Telemarketing Campaign
Methodology: Unsupervised Machine Learning (K-Means Clustering)
## 1. Executive Summary & Business Problem
FundFusion menghadapi tantangan dalam mengoptimalkan konversi penjualan produk keuangan melalui jalur Telemarketing. Mengingat tingginya biaya operasional per panggilan, strategi pemasaran "satu ukuran untuk semua" (one-size-fits-all approach) terbukti tidak efisien.

**Tujuan Proyek**: Membangun model segmentasi nasabah berbasis data (data-driven customer profiling) menggunakan algoritma Machine Learning. Hasil segmentasi ini akan digunakan oleh tim bisnis untuk merancang strategi penawaran produk yang personal dan tepat sasaran (targeted marketing campaign).

Dataset
<img width="522" height="571" alt="image" src="https://github.com/user-attachments/assets/921161d7-d8d0-4ac8-ab02-134949b25529" />

## 2. Exploratory Data Analysis & Preprocessing
- Penanganan duplikat, outlier, dan data Hilang dengan melakukan imputasi pada variabel Usia yang kosong secara cerdas menggunakan nilai median yang dikelompokkan berdasarkan Status_Perkawinan.
- Membuang variabel yang memiliki multikolinearitas tinggi (korelasi $> 0.7$)
- Melakukan encoding data kategorik dan standarisasi data numerik
## 3. Modelling and Evalluation
  Untuk menemukan struktur klaster yang paling optimal, proyek ini dibagi menjadi 3 skenario eksperimen:
 - Eksperimen 0: Menggunakan seluruh kombinasi variabel (Baseline).
 - Eksperimen 1: Fokus menggunakan variabel Demographics.
 - Eksperimen 2: Fokus menggunakan variabel Financial Related.
   Setiap skenario diuji menggunakan variasi jumlah klaster ($k = 3, 4, 5$) dan dievaluasi menggunakan Silhouette Score.

**Hasil Evaluasi Model :**
Berdasarkan hasil pengujian, Eksperimen 1 dengan $k = 3$ menghasilkan nilai Silhouette Score tertinggi (0.511). Skor ini menandakan bahwa nasabah FundFusion memiliki pola pengelompokan yang paling tegas dan logis berdasarkan karakteristik profil sosial/personal (demografi)
## 4. Analisis Hasil
**1.   Klaster 0**
*   Profil Personal: DidominasiLaki-laki (67%), rata-rata usia matang (41 tahun), memiliki rata-rata 1 anak, dan mayoritas berpendidikan Sarjana
*   Kekuatan Finansial: Memiliki saldo mengendap yang sangat besar (Rata-rata Rp247,5 Juta). Mayoritas merupakan nasabah loyal dengan masa bergabung (Vintage) 2–3 tahun.
*   Geografis: Terkonsentrasi kuat di pusat ekonomi utama, Jakarta (47,5%).
*   Karakteristik Produk: Saat ini rata-rata baru memiliki 3.17 produk di bank.

**2.   Klaster 1**

*   Profil Personal: Didominasi Laki-laki (67,7%) dengan usia senior menjelang masa pensiun (Rata-rata 56,2 tahun), memiliki anak yang mulai beranjak dewasa (1,44), dan berpendidikan Sarjana.
*   Kekuatan Finansial: Memiliki aset yang besar dan stabil (Rata-rata Rp245 Juta) dengan loyalitas tinggi (49,3% berada di bank selama 2–3 tahun).
*   Geografis: Tersebar di kota-kota besar: Jakarta (48%), Bandung (16,6%), dan Surabaya (12,5%).
*   Karakteristik Produk: Rata-rata memiliki 3.02 produk bank.


**3.   Klaster 2**
*   Profil Personal: Kelompok usia paling muda (Rata-rata 28,5 tahun), namun memiliki proporsi keterlibatan nasabah perempuan tertinggi (35,8%). Didominasi lulusan Sarjana (27%) hingga Doktor (10,2%).
*   Kekuatan Finansial: Memiliki rata-rata saldo terbesar mencapai Rp252,3 Juta. Memiliki kelompok nasabah paling loyal lama ($>4$ tahun) sebesar 21,3%.
*   Geografis: Terkonsentrasi di Jakarta (48,4%), Bandung (17,9%), dan Surabaya (12,5%).
*   Karakteristik Produk: Memiliki rata-rata kepemilikan produk tertinggi yaitu 3.29 produk.
## 5. Strategi dan Rekomendasi
Strategi untuk Cluster 0:
- Gaya Komunikasi: Profesional, berbasis data keuntungan, dan langsung pada intinya (straight-to-the-point).
- Penawaran: Fokus pada kestabilan keluarga seperti Asuransi Pendidikan Anak, Asuransi Jiwa, atau program KPR Premium.
- Waktu Kontak: Jam istirahat siang (12:00–13:00) atau sore hari setelah jam kantor selesai.
  
Strategi untuk Cluster 1:
- Gaya Komunikasi: Penuh rasa hormat, menggunakan nada bicara yang tenang, sabar, dan menekankan aspek keamanan dana.
- Penawaran: Tawarkan produk berisiko rendah dengan imbal hasil pasti seperti Deposito Berjangka atau Obligasi Negara untuk jaminan masa tua. Tawarkan juga program nasabah Prioritas (Wealth Management).
- Waktu Kontak: Jam-jam tenang di pagi hari (09:00–11:00) atau siang menjelang sore (14:00–15:30).

Strategi untuk Cluster 2:
- Gaya Komunikasi: Kasual, modern, energik, dan mengedepankan efisiensi digital (fitur instan lewat aplikasi mobile tanpa perlu ke cabang).
- Penawaran: Tawarkan produk investasi menjanjikan dengan resiko yang kecil, Kartu Kredit khusus gaya hidup anak muda (traveling/dining), atau pinjaman modal usaha produktif.
- Waktu Kontak: Menjelang malam hari (18:30–20:00) saat mereka sudah lepas dari kesibukan start-up atau kantor.
## 6. Kesimpulan
Dengan menerapkan model pemisahan berbasis karakteristik demografi ini, FundFusion dapat mengganti strategi cold-calling acak menjadi pemasaran berbasis persona digital. Langkah ini diproyeksikan mampu meningkatkan efisiensi waktu panggilan tim Telemarketing, menurunkan tingkat penolakan telepon, dan secara signifikan menaikkan angka konversi penjualan produk-produk keuangan unggulan.
