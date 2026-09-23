# Sales Performance & Regional Target Achievement Analysis

## Business Problem

Management ingin memahami performa penjualan dari berbagai sudut — tren revenue, pencapaian target per region, efektivitas channel penjualan, dan kontribusi produk — untuk mengidentifikasi area yang tumbuh baik maupun area yang memerlukan perhatian lebih lanjut.

## Business Questions

**Revenue Trend**
1. Bagaimana perkembangan revenue perusahaan dari waktu ke waktu — apakah tumbuh, stagnan, atau melambat?
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

- `sales_dataset.csv` — data transaksi (±12.500 baris, Januari 2023 – Juni 2026)
- `sales_target.csv` — target penjualan bulanan per region

Dataset dummy dibuat menggunakan Python, mensimulasikan transaksi penjualan FMCG (12 produk, 6 region, 4 sales channel) di Indonesia.

## Approach

Seluruh analisis, visualisasi, dan insight dikerjakan di Excel (PivotTable, formula, conditional formatting), tersimpan dalam workbook **`Sales Performance & Regional Target Achievement Analysis.csv`** di Sheet **Performance Analysis**. Tahapan yang dilakukan:

1. Data cleaning & validasi (konsistensi revenue, cost, harga per produk, kalibrasi target)
2. Analisis tren revenue — bulanan, kuartalan (QoQ & YoY), dan tahunan
3. Perhitungan Achievement % (Actual vs Target) per region per bulan
4. Analisis kontribusi produk & kategori terhadap revenue
5. Analisis performa channel (revenue, margin, AOV, discount)

## Key Findings

### 1. Revenue Trend

| Analisis | Kegunaan | Temuan |
|---|---|---|
| Trend Bulanan | Deteksi anomali jangka pendek | Revenue bulanan cukup fluktuatif di luar pola musiman (contoh: Mei 2025 turun 41.3%) |
| Trend per Region per Tahun | Menentukan apakah masalah bersifat lokal atau menyeluruh | Perlambatan growth (31%→4% YoY) terjadi merata di hampir semua region, bukan disebabkan 1 region tertentu |
| Trend Kuartalan (QoQ) | Konfirmasi pola musiman untuk perencanaan stok/campaign | Pola musiman konsisten tiap tahun: revenue naik di kuartal yang mengandung Maret/April dan Desember |
| Trend Kuartalan (YoY) | Melihat growth riil bebas gangguan musiman, menunjuk waktu spesifik | **Q2 2025 adalah satu-satunya kuartal dengan growth YoY negatif (-13%)** — layak jadi fokus investigasi lanjutan |

**Insight utama:** Analisis dari berbagai level (bulanan, kuartalan, tahunan, regional) secara konsisten menunjukkan perlambatan pertumbuhan bisnis sejak 2024 ke 2025. Pola musiman tetap konsisten sepanjang periode, sehingga tetap bisa diandalkan untuk perencanaan meski tren pertumbuhan jangka panjang perlu perhatian.

### 2. Sales Achievement per Region

| Region | Temuan | Insight | Saran |
|---|---|---|---|
| Jawa Barat | Pencapaian target terbaik (missed 17%), tapi revenue riil justru menurun (-7% di 2025) | Baik dari sisi target, namun tren penjualan aktualnya melemah — kemungkinan target belum mencerminkan kondisi terkini | Perlu ditelusuri penyebab penurunan revenue, dan target ke depan bisa disesuaikan dengan tren aktual |
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

**Insight utama:** Ketergantungan bisnis cukup tinggi pada kategori Food dan dua produk utama. Frekuensi pembelian antar produk relatif merata — perbedaan kontribusi pendapatan lebih disebabkan oleh harga jual, bukan popularitas produk. Ini membuka peluang strategi bundling untuk mendorong nilai transaksi secara lebih merata.

### 4. Channel Performance

**Insight:** Direct dan Distributor adalah dua channel dengan kontribusi terbesar terhadap revenue dan profit. Direct unggul dari sisi skala (revenue & profit tertinggi), sementara Distributor sedikit lebih efisien dari sisi margin. Modern Trade dan Online berkontribusi lebih kecil, dengan Online menunjukkan margin terendah akibat kombinasi discount rata-rata tertinggi dan AOV yang justru paling besar — mengindikasikan strategi diskon di channel ini layak ditinjau kembali.

**Saran:** Direct dan Distributor tetap menjadi dua channel dengan kontribusi terbesar dan layak menjadi prioritas perhatian ke depan. Untuk Online, ada baiknya ditelusuri lebih lanjut efektivitas discount terhadap margin — apakah diskon besar benar-benar mendorong volume secara signifikan, atau justru menekan profitabilitas tanpa hasil yang sepadan.

## Overall Recommendations

1. Prioritaskan investigasi lanjutan pada periode April–Juni 2025 untuk memahami faktor spesifik di balik penurunan revenue pada kuartal tersebut
2. Tinjau kembali metode penetapan target per region, mengingat ditemukan beberapa region dengan pencapaian target dan tren revenue riil yang bertolak belakang (Jawa Barat, Sulawesi)
3. Mulai eksplorasi penguatan kategori di luar Food untuk mengurangi risiko konsentrasi pendapatan
4. Telusuri efektivitas strategi discount pada channel Online terhadap margin

## Limitations

- Growth 2026 tidak dibandingkan langsung dengan tahun-tahun sebelumnya karena data baru mencakup Januari–Juni (partial year)
- Analisis kontribusi produk/region bersifat ringkasan sepanjang periode observasi; breakdown yang lebih granular per segmen dari waktu ke waktu berada di luar cakupan analisis ini
- Beberapa insight bersifat hipotesis awal berdasarkan pola dalam data dummy, dan memerlukan data tambahan (misal data distribusi, aktivitas kompetitor) untuk validasi lebih lanjut
- Tipe channel dan tipe customer (Retail/Wholesale) di-generate secara independen dalam dataset, sehingga pola AOV per channel mungkin tidak sepenuhnya merefleksikan dinamika bisnis riil

## Tools
Excel (PivotTable, formula, conditional formatting)

## File
- **`Sales Performance & Regional Target Achievement Analysis.csv`** — seluruh hasil analisis, visualisasi, dan insight
