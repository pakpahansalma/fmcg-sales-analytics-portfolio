# 01. Sales Performance & Regional Target Achievement Analysis using Microsoft Excel & SQL

## Business Problem

Management ingin memahami performa penjualan dari berbagai sudut - tren revenue, pencapaian target per region, efektivitas channel penjualan, dan kontribusi produk - untuk mengidentifikasi area yang tumbuh baik maupun area yang memerlukan perhatian lebih lanjut.

## Business Questions

**Revenue Trend**
1. Bagaimana perkembangan revenue perusahaan dari waktu ke waktu. Apakah tumbuh, stagnan, atau melambat?
2. Apakah ada pola musiman yang bisa dimanfaatkan untuk perencanaan bisnis?
3. Pada periode mana pertumbuhan revenue mulai melambat atau melemah?

**Sales Achievement per Region**
4. Region mana yang paling konsisten mencapai target penjualan, dan mana yang paling sering meleset?
5. Apakah pencapaian target sejalan dengan tren pertumbuhan revenue riil di masing-masing region?

**Kontribusi Produk & Kategori**
6. Produk atau kategori mana yang paling berkontribusi terhadap total revenue?
7. Apakah ada risiko konsentrasi pendapatan pada segelintir produk/kategori tertentu?

**Channel Performance**
8. Channel mana yang paling berkontribusi terhadap revenue dan profit perusahaan?
9. Bagaimana pengaruh discount terhadap margin di masing-masing channel?

## Data

- **`sales_dataset.csv`** - Data transaksi historis (±12.500 baris, Januari 2023 – Juni 2026). [Lihat Dataset Transaksi](./sales_dataset.csv)
- **`sales_target.csv`** - Data target penjualan bulanan per region. [Lihat Target Penjualan](./sales_target.csv)

Dataset dummy dibuat menggunakan Python, mensimulasikan transaksi penjualan FMCG (12 produk, 6 region, 4 sales channel) di Indonesia.

## Approach

Seluruh analisis, visualisasi, dan insight dikerjakan di Excel (PivotTable, formula, conditional formatting), tersimpan dalam workbook - - **`Sales Performance & Regional Target Achievement Analysis.xlsx`** — [Unduh atau Lihat File](./01.%20Sales%20Performance%20Anallysis/Sales%20Performance%20%26%20Regional%20Target%20Achievement%20Analysis.xlsx) di Sheet **Performance Analysis**. Tahapan yang dilakukan:

1. Data cleaning & validasi (konsistensi revenue, cost, harga per produk, kalibrasi target)
2. Analisis tren revenue - bulanan, kuartalan (QoQ & YoY), dan tahunan
3. Perhitungan Achievement % (Actual vs Target) per region per bulan
4. Analisis kontribusi produk & kategori terhadap revenue
5. Analisis performa channel (revenue, margin, AOV, discount)

## Key Findings

### 1. Revenue Trend

| Analisis | Kegunaan | Temuan |
|---|---|---|
| Trend Bulanan | Deteksi anomali jangka pendek | Revenue bulanan cukup fluktuatif di luar pola musiman (contoh: Mei 2025 turun 41.3%) |
| Trend per Region per Tahun | Menentukan apakah masalah bersifat lokal atau menyeluruh | Perlambatan growth (31%→4% YoY) terjadi merata di hampir semua region, bukan disebabkan 1 region tertentu |
| Trend Kuartalan (QoQ) | Konfirmasi pola musiman untuk perencanaan stok/campaign | Pola musiman konsisten tiap tahun: revenue naik di kuartal pada bulan Maret/April dan Desember |
| Trend Kuartalan (YoY) | Melihat growth riil bebas gangguan musiman, menunjuk waktu spesifik | **Q2 2025 adalah satu-satunya kuartal dengan growth YoY negatif (-13%)** - Bisa menjadi fokus investigasi lanjutan |

**Insight utama:** Analisis dari berbagai level (bulanan, kuartalan, tahunan, regional) secara konsisten menunjukkan perlambatan pertumbuhan bisnis sejak 2024 ke 2025. Pola musiman tetap konsisten sepanjang periode, sehingga tetap bisa diandalkan untuk perencanaan meski tren pertumbuhan jangka panjang perlu perhatian.

### 2. Sales Achievement per Region

| Region | Temuan | Insight | Saran |
|---|---|---|---|
| Jawa Barat | Pencapaian target terbaik (missed 17%), tapi revenue riil justru menurun (-7% di 2025) | Baik dari sisi target, namun tren penjualan aktualnya melemah. Kemungkinan target belum mencerminkan kondisi terkini | Perlu ditelusuri penyebab penurunan revenue, dan target ke depan bisa disesuaikan dengan tren aktual |
| Sulawesi | Paling sering gagal target (40%), tapi revenue-nya tumbuh paling stabil di antara semua region | Target yang ditetapkan kemungkinan kurang sejalan dengan kapasitas pertumbuhan aktual region ini | Target Sulawesi bisa ditinjau kembali agar lebih realistis |
| Sumatera | Rata-rata pencapaian tertinggi (123%), tapi fluktuatif dan growth-nya melambat tajam | Rata-rata yang tinggi menutupi ketidakstabilan performa dari bulan ke bulan | Ada baiknya ditelusuri apa yang membedakan bulan-bulan kuat dan lemahnya |
| Jawa Tengah | Rata-rata pencapaian terendah (107%), namun revenue riil relatif terjaga | Terlihat lemah dari sisi target, tapi performa penjualan sebenarnya tidak seburuk itu | Target Jawa Tengah mungkin perlu dievaluasi kembali |
| Jawa Timur | Jarang gagal parah, meski cukup sering di zona mendekati target | Performa cukup solid dan sejalan dengan tren umum perusahaan | Sedikit dorongan tambahan berpotensi mengangkat pencapaian ke level lebih baik |
| Jabodetabek | Pencapaian stabil dan konsisten, sejalan dengan tren umum | Performa yang cukup baik, tidak menunjukkan tanda bermasalah | Pendekatan saat ini sudah berjalan baik |

**Insight utama:** Pencapaian target dan pertumbuhan revenue riil tidak selalu sejalan. Jawa Barat unggul dalam pencapaian target namun penjualannya justru menurun, sementara Sulawesi sering meleset dari target meski penjualannya tumbuh paling stabil. Ini mengindikasikan target di beberapa region mungkin perlu disesuaikan agar lebih mencerminkan tren pertumbuhan yang sebenarnya.

### 3. Kontribusi Produk & Kategori

| Temuan | Insight | Saran |
|---|---|---|
| Kategori Food menyumbang 47.7% dari total revenue — jauh di atas kategori lain | Bisnis cukup bergantung pada satu kategori. Gangguan pada kategori Food berpotensi berdampak besar ke keseluruhan bisnis | Ada baiknya mulai dilihat peluang penguatan kategori lain untuk mengurangi ketergantungan secara bertahap |
| Dua produk (Beras Premium & Minyak Goreng) menyumbang 37.3% dari total revenue | Sebagian kecil produk menopang porsi besar pendapatan, sekaligus menandakan risiko yang cukup terkonsentrasi | Ketersediaan stok dan kestabilan harga dua produk ini layak jadi perhatian khusus |
| Frekuensi transaksi antar produk relatif merata, namun kontribusi revenue bervariasi jauh (1.9%-22.7%) | Perbedaan pendapatan antar produk lebih dipengaruhi oleh harga jual, bukan seberapa sering produk dibeli | Ada peluang mendorong nilai transaksi lewat strategi bundling produk kontribusi kecil dengan produk andalan |
| Sabun Mandi Batang terjual cukup banyak namun kontribusi revenue paling kecil (1.9%) | Demand stabil, namun nilai kontribusinya terbatas karena berada di segmen harga rendah | Bisa dipertimbangkan sebagai kandidat produk bundling, mengingat demand-nya yang konsisten |

**Insight utama:** Ketergantungan bisnis cukup tinggi pada kategori Food dan dua produk utama. Frekuensi pembelian antar produk relatif merata - perbedaan kontribusi pendapatan lebih disebabkan oleh harga jual, bukan popularitas produk. Ini membuka peluang strategi bundling untuk mendorong nilai transaksi secara lebih merata.

### 4. Channel Performance

**Insight:** Direct dan Distributor adalah dua channel dengan kontribusi terbesar terhadap revenue dan profit. Direct unggul dari sisi skala (revenue & profit tertinggi), sementara Distributor sedikit lebih efisien dari sisi margin. Modern Trade dan Online berkontribusi lebih kecil, dengan Online menunjukkan margin terendah akibat kombinasi discount rata-rata tertinggi dan AOV yang justru paling besar - mengindikasikan strategi diskon di channel ini layak ditinjau kembali.

**Saran:** Direct dan Distributor tetap menjadi dua channel dengan kontribusi terbesar dan layak menjadi prioritas perhatian ke depan. Untuk Online, ada baiknya ditelusuri lebih lanjut efektivitas discount terhadap margin  apakah diskon besar benar-benar mendorong volume secara signifikan, atau justru menekan profitabilitas tanpa hasil yang sepadan.

## Overall Recommendations

1. Prioritaskan investigasi lanjutan pada periode April-Juni 2025 untuk memahami faktor spesifik di balik penurunan revenue pada kuartal tersebut
2. Tinjau kembali metode penetapan target per region, mengingat ditemukan beberapa region dengan pencapaian target dan tren revenue riil yang bertolak belakang (Jawa Barat, Sulawesi)
3. Mulai eksplorasi penguatan kategori di luar Food untuk mengurangi risiko konsentrasi pendapatan
4. Telusuri efektivitas strategi discount pada channel Online terhadap margin

## Limitations

- Growth 2026 tidak dibandingkan langsung dengan tahun-tahun sebelumnya karena data baru mencakup Januari-Juni (partial year)
- Analisis kontribusi produk/region bersifat ringkasan sepanjang periode observasi; breakdown yang lebih granular per segmen dari waktu ke waktu berada di luar cakupan analisis ini
- Beberapa insight bersifat hipotesis awal berdasarkan pola dalam data dummy, dan memerlukan data tambahan (misal data distribusi, aktivitas kompetitor) untuk validasi lebih lanjut
- Tipe channel dan tipe customer (Retail/Wholesale) di-generate secara independen dalam dataset, sehingga pola AOV per channel mungkin tidak sepenuhnya merefleksikan dinamika bisnis riil

## Tools
Excel (PivotTable, formula, conditional formatting) dan SQL (SQLite)

## Catatan
Seluruh analisis dikerjakan di Excel terlebih dahulu, kemudian direplikasi 
menggunakan SQL untuk validasi hasil dan latihan penguasaan kedua tools. 
Hasil dari kedua pendekatan konsisten satu sama lain.

## File
- **`Sales Performance Analysis using Microsoft Excel`** — [Lihat File Excel](./01.%20Sales%20Performance%20Anallysis/Sales%20Performance%20%26%20Regional%20Target%20Achievement%20Analysis.xlsx)
- **`Sales Performance Analysis using SQL`** — [Lihat File SQL](./01.%20Sales%20Performance%20Anallysis/using.sql.db)



# 02. Customer Segmentation & Retention Analysis

> 🚧 **Status: Sedang dikerjakan.** README ini mencerminkan progress analisis sejauh ini dan akan terus diperbarui.

## Business Problem

Management ingin memahami perilaku pembelian customer — seberapa aktif mereka bertransaksi, segmen mana yang paling berkontribusi terhadap revenue, dan seberapa besar risiko kehilangan customer bernilai tinggi — untuk mendukung strategi retensi yang lebih terarah.

## Business Questions

**Customer Acquisition**
1. Berapa banyak customer baru bertransaksi di tiap periode? Apakah jumlahnya bertambah atau stagnan dari waktu ke waktu?

**Customer Segmentation (RFM-based)**

2. Bagaimana sebaran customer berdasarkan tingkat keaktifan transaksinya (Recency)?
3. Segmen customer mana yang memberikan kontribusi revenue terbesar?
4. Apakah ada segmen customer yang berpotensi berisiko terhadap kontribusi revenue ke depan?

**Repurchase Interval Analysis** *(sedang dikerjakan)*

5. Berapa siklus wajar customer melakukan pembelian ulang, berdasarkan pola aktual di data?
6. Berapa banyak customer yang pola pembeliannya masih sesuai siklus wajar, dan berapa yang mulai melambat?

## Data

Menggunakan dataset yang sama dengan Project 1: `sales_dataset.csv`, fokus pada kolom `Customer ID`, `Transaction Date`, dan `Revenue`.

## Approach

1. Menghitung metrik dasar per customer: **Recency** (jarak waktu sejak transaksi terakhir), **Frequency** (jumlah transaksi), **Monetary** (total nilai transaksi) — dikenal sebagai analisis RFM
2. Mengelompokkan customer ke dalam segmen berdasarkan Recency, dengan threshold yang ditentukan dari distribusi data aktual (bukan asumsi umum)
3. Menganalisis interval pembelian ulang untuk memahami siklus beli yang wajar, sebagai dasar identifikasi customer yang mulai melambat dari kebiasaannya

## Key Findings (sejauh ini)

### 1. Customer Acquisition Trend

| Temuan | Catatan |
|---|---|
| Customer baru menurun tajam dari 249 (Januari 2023) menjadi hampir nol sejak 2024 | Pola ini merupakan konsekuensi dari desain dataset simulasi (pool customer tetap sejak awal periode), bukan mencerminkan tren akuisisi bisnis riil. Metrik ini tidak dijadikan dasar rekomendasi bisnis. |

### 2. Customer Segmentation

Threshold segmentasi ditentukan berdasarkan distribusi Recency aktual pada data (bukan angka baku umum), sehingga mencerminkan pola nyata pelanggan dalam dataset ini.

| Segmen | Kriteria (sejak transaksi terakhir) | Jumlah Customer | % Customer | Revenue (Juta) | % Revenue |
|---|---|---|---|---|---|
| Active | ≤ 90 hari | 453 | 57% | 2,081 | 66% |
| At Risk | 91–270 hari | 168 | 21% | 631 | 20% |
| Dormant | 271–500 hari | 48 | 6% | 91 | 3% |
| Lost | > 500 hari | 131 | 16% | 348 | 11% |
| **Total** | | **800** | | **3,151** | |

**Insight utama:** Sebagian besar revenue perusahaan (66%) masih ditopang oleh customer yang aktif bertransaksi, namun sekitar sepertiga revenue (34%) berasal dari customer yang mulai jarang atau sudah tidak aktif. Pola ini juga menunjukkan bahwa customer cenderung berpindah cukup cepat dari mulai jarang menjadi berhenti total, dibanding menurun secara bertahap — terlihat dari kecilnya proporsi segmen Dormant (6%) dibanding Lost (16%).

| Temuan | Insight | Saran |
|---|---|---|
| Segmen Active (57% customer) menyumbang 66% revenue, sementara segmen At Risk, Dormant, dan Lost (43% customer) menyumbang 34% revenue | Revenue cukup terpusat pada customer yang masih aktif, namun porsi revenue dari customer yang mulai tidak aktif masih cukup signifikan | Segmen non-aktif ini bisa menjadi perhatian khusus, mengingat kontribusinya terhadap revenue masih cukup besar |
| Segmen At Risk (21% customer, 20% revenue) memiliki proporsi kontribusi yang seimbang dengan proporsi jumlahnya | Segmen ini masih berkontribusi wajar terhadap revenue, namun sudah menunjukkan tanda mulai jarang bertransaksi | Ada baiknya segmen ini ditelusuri lebih lanjut, mengingat statusnya berada di antara aktif dan berisiko hilang |
| Segmen Dormant relatif kecil (6%), namun segmen Lost jauh lebih besar (16%, 348 juta revenue) | Customer yang mulai jarang bertransaksi tampak cenderung berpindah cepat menuju berhenti total, bukan menurun bertahap | Perlu ditelusuri lebih lanjut pada rentang waktu mana penurunan aktivitas customer biasanya mulai terjadi |

### 3. Repurchase Interval Analysis *(in progress)*

Analisis pendahuluan terhadap jarak waktu antar transaksi (di seluruh customer) menunjukkan:

| Statistik | Nilai |
|---|---|
| Rata-rata interval | 68.8 hari (~2.3 bulan) |
| Median interval | 47 hari (~1.5 bulan) |
| P75 (75% customer beli ulang dalam) | 93 hari (~3 bulan) |
| P90 (90% customer beli ulang dalam) | 157 hari (~5 bulan) |

Statistik ini akan digunakan sebagai dasar penentuan threshold untuk mengklasifikasikan customer ke dalam kategori "On-Time" (pola beli sesuai siklus wajar) vs "Melambat" (interval pembelian melebihi siklus wajar). Analisis lanjutan (klasifikasi per customer dan ringkasan kontribusi revenue tiap kategori) masih dalam pengerjaan.

## Limitations (sejauh ini)

- Analisis Customer Acquisition Trend tidak dapat dijadikan indikator tren bisnis riil karena keterbatasan desain dataset (pool customer tetap)
- Threshold segmentasi dan interval pembelian ditentukan berdasarkan pola dalam data dummy ini; penerapan pada data riil memerlukan validasi ulang terhadap distribusi datanya masing-masing

## Tools

Excel (PivotTable, formula, conditional formatting)

## Next Steps

- Menyelesaikan analisis Repurchase Interval (klasifikasi On-Time vs Melambat per customer)
- Dormant/At-Risk Customer Deep Dive — mengidentifikasi customer bernilai tinggi yang berpotensi berisiko
- Replikasi analisis menggunakan SQL
