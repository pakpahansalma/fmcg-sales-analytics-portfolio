# Sales Performance & Regional Target Achievement Analysis

## Business Problem

Management ingin memahami performa penjualan lintas produk, region, dan channel 
untuk mengidentifikasi pendorong utama pertumbuhan serta area yang memerlukan 
perhatian, termasuk region mana yang konsisten mencapai target dan mana yang tertinggal.

## Business Questions

1. Bagaimana tren revenue dari waktu ke waktu?
2. Region mana yang paling konsisten mencapai target penjualan?
3. Channel mana yang paling efektif dari sisi revenue dan margin?
4. Produk/kategori mana yang paling berkontribusi terhadap revenue?

## Data

- `sales_dataset_portfolio.csv` — data transaksi (±12.500 baris, Jan 2023 - Jun 2026)
- `sales_target_portfolio.csv` — target penjualan bulanan per region

## Approach

Analisis dilakukan menggunakan Excel (PivotTable & formula), meliputi:
- Data cleaning & validasi konsistensi (revenue, cost, harga per produk)
- Analisis tren revenue bulanan & tahunan
- Perhitungan Achievement % (Actual vs Target) per region per bulan
- Analisis performa channel (revenue, margin, AOV)
- Analisis kontribusi produk & kategori

## Key Findings

**1. Pertumbuhan revenue melambat signifikan**
Growth YoY turun tajam dari 31% (2023→2024) menjadi hanya 4% (2024→2025). 
Setelah dibedah per region, perlambatan ini terjadi **merata di hampir semua region** 
— bukan disebabkan oleh satu region tertentu.

**2. Sulawesi paling tidak konsisten mencapai target**
Sulawesi memiliki tingkat gagal target (missed target rate) tertinggi (40%) dengan 
rentang performa paling lebar (34%-262%) dibanding region lain — menunjukkan 
performa yang sangat fluktuatif dari bulan ke bulan.

**3. Direct & Distributor adalah channel utama**
Direct unggul dari sisi revenue dan profit absolut, sementara Distributor sedikit 
lebih efisien dari sisi margin (16.29% vs 16.13%). Online menunjukkan margin 
terendah (15.47%) dengan rata-rata discount tertinggi.

**4. Ketergantungan tinggi pada kategori Food**
Kategori Food menyumbang 47.7% dari total revenue, dengan 2 produk saja 
(Beras Premium & Minyak Goreng) menyumbang 37.3% dari total revenue perusahaan.

## Recommendations

- Lakukan investigasi lanjutan untuk memahami penyebab perlambatan growth yang 
  terjadi merata di seluruh region (kemungkinan faktor lintas produk/channel, 
  bukan isu lokal per region)
- Lakukan review bulanan khusus untuk Sulawesi guna memahami pola di balik 
  fluktuasi performanya sebelum menetapkan target berikutnya
- Pertahankan fokus investasi pada channel Direct dan Distributor sebagai 
  kontributor utama; evaluasi efektivitas discount pada channel Online
- Karena ketergantungan tinggi pada kategori Food, mulai eksplorasi penguatan 
  kategori lain untuk mengurangi risiko konsentrasi

## Limitations

- Growth 2026 tidak dibandingkan langsung karena data baru mencakup Jan-Jun (partial year)
- Analisis kontribusi produk/region bersifat ringkasan sepanjang periode; 
  breakdown growth per segmen dari waktu ke waktu belum tercakup dalam analisis ini
- Rekomendasi bersifat hipotesis awal yang memerlukan investigasi/data tambahan 
  untuk konfirmasi (misal data distribusi, aktivitas kompetitor)

## Tools
Excel (PivotTable, formula, conditional formatting)

## Status
🚧 Dashboard visual sedang disusun — analisis inti sudah selesai.
