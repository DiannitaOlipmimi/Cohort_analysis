# COHORT ANALYSIS

## 📌Table of contents
- [Definisi](https://github.com/DiannitaOlipmimi/cohort_analysis#definisi)
- [Study Case](https://github.com/DiannitaOlipmimi/cohort_analysis#study-case)
- [Step by Step analysis](https://github.com/DiannitaOlipmimi/cohort_analysis#step-by-step-analysis)
- [Result](https://github.com/DiannitaOlipmimi/cohort_analysis#result)
- [Dataset](https://github.com/DiannitaOlipmimi/cohort_analysis#dataset)
- [Links](https://github.com/DiannitaOlipmimi/cohort_analysis#links)

## 📌**Definisi**
### 📒Cohort
cohort analysis adalah proses analisis yang bertujuan memahami perubahan *user engagement* dari waktu ke waktu

## 📌**Study Case**
### **User Retention Analysis for a Mobile App**

### 📒 Deskripsi Masalah:
sebuah perusahaan E-Commerce di UK ingin memahami pola retention [kemampuan perusahaan untuk membuat pelanggan kembali membeli atau menggunakan layanannya] konsumen dan mengidentifikasi strategi yang dapat menaikan *user engagement* serta *retention rate*. untuk mengetahuinya, maka perusahaan melakukan *cohort analysis* untuk menganalisa perilaku konsumen dan menemukan *key factors* yang dapat membantu menaikan *user retention* kedepannya

### 📒 Data dan Variabel:
perusahaan ini telah mengumpulkan dataset yang berisi kumpulan data transnasional yang berisi semua transaksi yang terjadi antara 01/12/2010 dan 09/12/2011 untuk ritel online non-toko yang berbasis di Inggris dan terdaftar. Perusahaan ini terutama menjual hadiah unik untuk semua acara. Banyak pelanggan perusahaan adalah grosir. dataset ini memiliki variabel:
- **InvoiceNo**: angka unik pada setiap pembelian 
- **StockCode**: angka unik pada stock toko
- **Description**: deskripsi jenis produk yang dibeli
- **Quantity**: jumlah barang yang dibeli
- **InvoiceDate**: tanggal pembelian
- **UnitPrice**: harga satu unit produk
- **CustomerID**: ID konsumen
- **Country**: negara asal toko

### 📒 Tujuan:
melakukan *cohort analysis* untuk mengetahui *user retention rate*, mengidentifikasi pola konsumen, dan membuat rekomendasi untuk menaikan *user retention*

### 📒 Langkah Analisis:
✅ *Exploratory Data Analysis* (EDA):
1. Memuat dataset
2. Melakukan pengecekan dimensi data seperti jumlah baris dan jumlah kolom
3. Melakukan pengecekan pada 5 data teratas serta melakukan statistik deskriptif

✅ Cohort Creation:
1. Identify the cohort definition based on a specific event or timeframe (e.g., the month of user registration).
2. Assign users to their respective cohorts based on the defined criteria.
3. Calculate the cohort sizes to understand the distribution of users across cohorts.

✅Cohort Retention Analysis:
1. Calculate the retention rate for each cohort over time.
2. Create a retention matrix or retention curve to visualize the retention rates across different cohorts.
3. Identify any significant differences in retention rates among cohorts and investigate potential reasons for these differences.

✅Behavioral Analysis:
1. Analyze user behavior within each cohort, such as the number of app sessions, time spent in the app, or specific actions taken.
2. Compare the behavior patterns of retained users versus churned users within each cohort.
3. Identify any specific actions or behaviors that are strongly correlated with higher retention rates.

✅Time-Based Analysis:
1. Analyze user engagement and retention over time since registration within each cohort.
2. Calculate metrics such as average session frequency, average time spent, or the likelihood of churn at different time intervals.
3. Identify any critical time periods where user engagement or retention tends to drop.

✅Segment Analysis:
1. Segment the cohorts based on user demographics or other relevant variables.
2. Compare the retention rates and behavioral patterns among different segments.
3. Identify any specific segments that exhibit higher retention rates or unique behaviors.

✅Insights and Recommendations:
1. Summarize the key findings from the cohort analysis, including retention rates, behavioral patterns, and time-based trends.
2. Identify the key factors that contribute to long-term user retention.
3. Provide recommendations on strategies to improve user engagement and retention, such as personalized onboarding, targeted marketing campaigns, or feature enhancements based on the identified patterns.
4. By conducting a comprehensive cohort analysis, the mobile app company can gain insights into user retention patterns, identify areas for improvement, and develop data-driven strategies to enhance user engagement and increase long-term user retention.

## 📌**Step by step analysis**
### 📒 **menggunakan Excel**

### 📒 **menggunakan R/RStudio**

### 📒**menggunakan Python**
```python
data['cohort'] = data.apply(lambda row: (row['year'] * 100) + (row['month']), axis=1)
# 2010 * 100 = 201000
# aug -> 201000 + 08 = 201008

cohorts = data.groupby('CustomerID')['cohort'].min().reset_index()
cohorts.columns = ['CustomerID', 'first_cohort']

data = data.merge(cohorts, on='CustomerID', how='left')
```

## 📌**Result**
### 📒**menggunakan Excel**

### 📒**menggunakan R/RStudio**

### 📒**menggunakan Python**


## 📌**Dataset**
### **E-Commerce UK (5 data teratas)**
| |InvoiceNo|StockCode|Description|Quantity|InvoiceDate|UnitPrice|CustomerID|Country|
|:----|:----|:----|:----|:----|:----|:----|:----|:----|
|0|536365|85123A|WHITE HANGING HEART T-LIGHT HOLDER|6|12/1/2010 8:26|2.55|17850.0|United Kingdom|
|1|536365|71053|WHITE METAL LANTERN|6|12/1/2010 8:26|3.39|17850.0|United Kingdom|
|2|536365|84406B|CREAM CUPID HEARTS COAT HANGER|8|12/1/2010 8:26|2.75|17850.0|United Kingdom|
|3|536365|84029G|KNITTED UNION FLAG HOT WATER BOTTLE|6|12/1/2010 8:26|3.39|17850.0|United Kingdom|
|4|536365|84029E|RED WOOLLY HOTTIE WHITE HEART.|6|12/1/2010 8:26|3.39|17850.0|United Kingdom|


## 📌**Links**
https://www.kaggle.com/datasets/carrie1/ecommerce-data

https://colab.research.google.com/drive/1Q2xO-MIBwe4W_QGszL9FDW9DbJbeB2aY

https://medium.com/@myskill.id/cohort-and-retention-analysis-practice-dd43c6f5a771

https://medium.com/@myskill.id/cohort-and-retention-analysis-57249d6718dc