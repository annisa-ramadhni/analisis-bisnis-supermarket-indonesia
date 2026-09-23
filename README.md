# Analisis Bisnis Supermarket Indonesia

## Overview

Proyek ini merupakan analisis bisnis pada dataset supermarket Indonesia yang bertujuan untuk memahami pola penjualan, performa bisnis, serta membuat analisis prediktif terhadap keuntungan.

Proyek mencakup proses pengolahan data, analisis bisnis, visualisasi melalui dashboard, dan pemodelan prediktif menggunakan beberapa metode machine learning.

> **Catatan:** Dataset yang digunakan merupakan dataset sintetis.

## Objectives

Proyek ini dilakukan untuk:

- Membersihkan dan mempersiapkan data sebelum analisis.
- Menganalisis performa penjualan berdasarkan beberapa aspek bisnis.
- Mengidentifikasi pola dan insight dari data penjualan.
- Menyajikan hasil analisis dalam dashboard interaktif.
- Membangun model machine learning untuk memprediksi keuntungan.
- Membandingkan performa model berdasarkan hasil evaluasi.

## Tools

- **Google Sheets** — data cleaning dan business analysis
- **Looker Studio** — dashboard dan visualisasi
- **Orange Data Mining** — predictive analysis dan machine learning

## Dataset

Dataset yang digunakan adalah:

`synthetic_store_indonesia.xlsx`

Dataset berisi informasi transaksi supermarket, termasuk data terkait:

- Order
- Customer
- Produk
- Penjualan
- Kuantitas
- Diskon
- Keuntungan
- Wilayah
- Segmen
- Kategori produk
- Sub-kategori produk
- Metode pengiriman
- Kota

Dataset tersedia pada folder [`data/`](data/).

## Data Preparation

Tahapan persiapan data dilakukan untuk memastikan data dapat digunakan dalam proses analisis.

Beberapa proses yang dilakukan meliputi:

- Pemeriksaan struktur dan kualitas data.
- Penanganan data yang perlu dibersihkan.
- Pembuatan kolom hasil cleaning untuk beberapa atribut.
- Persiapan data untuk analisis bisnis.
- Persiapan fitur yang digunakan dalam predictive analysis.

## Business Analysis

Analisis bisnis dilakukan menggunakan Google Sheets untuk melihat berbagai aspek performa penjualan.

Beberapa analisis yang dilakukan meliputi:

- Tren penjualan dari tahun 2014–2017.
- Proporsi jumlah order berdasarkan wilayah.
- Penjualan berdasarkan kategori produk.
- Kota dengan penjualan tertinggi.
- Performa metode pengiriman.
- Tren penjualan bulanan.

Hasil analisis kemudian divisualisasikan dalam dashboard menggunakan Looker Studio.

## Dashboard

Dashboard dibuat menggunakan Looker Studio dan terdiri dari dua halaman.

### Dashboard 1

Menampilkan:

- Tren penjualan 2014–2017.
- Proporsi order berdasarkan wilayah.
- Penjualan berdasarkan kategori produk.
- KPI utama.
- Insight hasil analisis.

### Dashboard 2

Menampilkan:

- Kota dengan penjualan tertinggi.
- Distribusi berdasarkan metode pengiriman.
- Tren penjualan bulanan.
- KPI utama.

Dokumentasi dashboard tersedia pada folder [`images/`](images/), sedangkan versi PDF tersedia pada folder [`dashboard/`](dashboard/).

## Predictive Analysis

Analisis prediktif dilakukan menggunakan Orange Data Mining dengan tujuan memprediksi **keuntungan (`keuntungan`)**.

Model yang digunakan:

- Linear Regression
- Random Forest

### Features

Fitur yang digunakan dalam pemodelan meliputi:

- `penjualan`
- `kuantitas`
- `diskon`
- `metode_pengiriman`
- `segmen`
- `wilayah`
- `kategori`
- `sub_kategori`
- `clean_kota`

Target yang digunakan:

- `keuntungan`

### Model Evaluation

Evaluasi dilakukan menggunakan **5-fold cross-validation**.

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | 900,339.269 | 2,904,034.595 | 0.316 |
| Random Forest | 301,020.806 | 1,752,168.554 | 0.751 |

Berdasarkan hasil evaluasi 5-fold cross-validation, Random Forest menghasilkan nilai MAE dan RMSE yang lebih rendah serta R² yang lebih tinggi dibandingkan Linear Regression pada eksperimen ini.

Workflow Orange tersedia pada folder [`orange/`](orange/).

## Project Structure

```text
analisis-bisnis-supermarket-indonesia/
│
├── data/
│   ├── README.md
│   └── synthetic_store_indonesia.xlsx
│
├── dashboard/
│   └── informasi_penjualan_super_market_indonesia.pdf
│
├── images/
│   ├── Dashboard_Analisis_Penjualan_Supermarket_Indonesia (1)_page-0001.jpeg
│   ├── Dashboard_Analisis_Penjualan_Supermarket_Indonesia (2)_page-0001.jpeg
│   └── Screenshot 2026-09-23 at 10.15.44.png
│
├── orange/
│   └── analisis-prediktif-supermarket.ows
│
└── README.md
