# Tugas 3 – Visualisasi Data Teks

**Analisis Kualitas Korpus dan Visualisasi Aduan Masyarakat**

## 1. Project Description

Proyek ini merupakan bagian dari Tugas 3 mata kuliah Visualisasi Data Teks. Penelitian ini bertujuan untuk melakukan audit kualitas korpus serta menganalisis pola permasalahan yang terdapat dalam data aduan masyarakat.

Analisis dilakukan terhadap dataset simulasi aduan masyarakat yang mencakup periode September 2025 hingga Agustus 2026. Pendekatan berbasis aturan kata kunci digunakan untuk mengidentifikasi topik permasalahan berdasarkan isi teks aduan, kemudian hasilnya dianalisis menggunakan visualisasi data.

## 2. Project Objectives

Proyek ini memiliki beberapa tujuan utama:

- Melakukan audit kualitas korpus teks, termasuk pemeriksaan data kosong, duplikasi, normalisasi teks, informasi pribadi, serta kualitas pemrosesan teks.
- Mengidentifikasi topik permasalahan berdasarkan isi aduan masyarakat.
- Menghitung distribusi dan proporsi setiap topik permasalahan.
- Menganalisis perubahan jumlah aduan setiap topik dari waktu ke waktu.
- Menghasilkan visualisasi yang membantu memahami karakteristik dan pola aduan masyarakat.
- Memastikan seluruh proses analisis dapat dijalankan kembali secara reproducible.

## 3. Dataset Description

Dataset yang digunakan merupakan dataset simulasi aduan masyarakat wilayah Sukaraya.

**Dataset Information:**

| Attribute | Description |
|---|---|
| Dataset type | Simulated municipal complaints |
| Total records | 5,049 complaints |
| Time period | September 2025 – August 2026 |
| Data format | CSV |
| Main text field | `isi_aduan` |
| Date field | `tanggal` |
| Category field | `kategori_dilaporkan` |

Dataset mencakup informasi seperti ID aduan, tanggal, kanal pelaporan, kelurahan, kategori yang dilaporkan, isi aduan, koordinat lokasi, dan status penanganan.

The dataset is synthetic and does not represent actual personal complaint records.

## 4. Analysis Workflow

### A. Corpus Quality Audit

Audit kualitas korpus dilakukan untuk mengevaluasi kelayakan data teks sebelum analisis lebih lanjut.

Tahapan yang dilakukan meliputi:

- Pemeriksaan data kosong dan duplikasi.
- Analisis karakteristik panjang teks dan jumlah kata.
- Pemeriksaan serta penyamaran informasi pribadi.
- Pemeriksaan konsistensi kategori dengan isi aduan.
- Normalisasi teks dan penanganan variasi penulisan.
- Evaluasi stopwords dan stemming, termasuk potensi kesalahan perubahan makna.

### B. Complaint Topic Analysis

#### B.1 Topic Identification

Topik permasalahan diidentifikasi berdasarkan isi teks aduan menggunakan pendekatan rule-based keyword classification yang dilengkapi pemeriksaan manual terhadap kasus yang belum teridentifikasi.

Topik yang dianalisis meliputi:

1. Jalan Rusak
2. Penerangan Jalan
3. Sampah
4. Drainase dan Banjir
5. Ketertiban Umum
6. Air Bersih
7. Fasilitas Umum
8. Lain-lain

Aduan yang tidak memiliki informasi masalah yang dapat diidentifikasi dipisahkan ke dalam kategori tidak dapat diklasifikasikan.

#### B.2 Temporal Trend Analysis

Analisis tren dilakukan dengan mengelompokkan jumlah aduan berdasarkan topik dan bulan.

Analisis meliputi:

- Perubahan jumlah aduan setiap bulan.
- Perubahan proporsi setiap topik terhadap seluruh aduan bulanan.
- Perbandingan rata-rata tiga bulan pertama dan tiga bulan terakhir.
- Identifikasi topik dengan peningkatan jumlah aduan paling menonjol.

## 5. Key Findings

### B.1 Distribution of Complaint Topics

Tiga topik dengan jumlah aduan tertinggi adalah:

| Complaint Topic | Total | Percentage |
|---|---:|---:|
| Jalan Rusak | 1,129 | 22.36% |
| Penerangan Jalan | 947 | 18.76% |
| Sampah | 834 | 16.52% |

Ketiga topik tersebut mencakup sekitar 57.64% dari seluruh aduan.

### B.2 Temporal Trend Findings

Air Bersih menunjukkan peningkatan rata-rata jumlah aduan paling menonjol ketika membandingkan tiga bulan pertama dan tiga bulan terakhir.

- Rata-rata tiga bulan pertama: 28.67 aduan per bulan.
- Rata-rata tiga bulan terakhir: 46 aduan per bulan.
- Perubahan rata-rata: meningkat 60.47%.
- Jumlah aduan Agustus 2026: 76 aduan.

Peningkatan tersebut terutama terlihat pada Agustus 2026. Oleh karena itu, temuan ini diinterpretasikan sebagai lonjakan aduan pada bulan tersebut, bukan sebagai tren peningkatan yang konsisten sepanjang periode pengamatan.

## 6. Repository Structure

```text
Tugas3-Visualisasi-Data-Teks/
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
│   └── Tugas3_Teks_203012510036_Dewa_Putu_Fajar_W.ipynb
│
├── outputs/
│   ├── figures/
│   ├── tables/
│   └── reports/
│
├── .gitignore
└── README.md
```

**Folder Description:**

- `data/raw/`: Menyimpan dataset mentah dalam format ZIP.
- `data/processed/`: Menyimpan hasil ekstraksi dan data hasil pemrosesan.
- `notebooks/`: Berisi notebook utama untuk seluruh proses analisis.
- `outputs/figures/`: Menyimpan hasil visualisasi.
- `outputs/tables/`: Menyimpan tabel hasil audit dan analisis.
- `outputs/reports/`: Menyimpan hasil laporan.

## 7. Requirements

Notebook menggunakan Python dan beberapa library berikut:

- pandas
- numpy
- matplotlib
- seaborn
- re
- html
- zipfile

Library tambahan yang diperlukan akan diimpor atau diinstal melalui notebook apabila dibutuhkan.

## 8. How to Run the Notebook

Notebook dapat dijalankan menggunakan Google Colab tanpa memerlukan konfigurasi lingkungan lokal.

**Steps:**

1. Buka repository GitHub ini.
2. Buka folder `notebooks/`.
3. Pilih notebook utama.
4. Buka notebook menggunakan Google Colab.
5. Pilih **Runtime → Run all**.
6. Notebook akan mengambil dataset ZIP dari repository, melakukan ekstraksi otomatis, dan menjalankan seluruh tahapan analisis.

Dataset tidak perlu diunggah secara manual ke Google Colab selama file ZIP tersedia di repository.

## 9. Reproducibility

Reproducibility menjadi salah satu aspek penting dalam proyek ini.

Notebook telah diuji menggunakan runtime Google Colab yang baru dengan menjalankan seluruh cell dari awal hingga akhir.

Pengujian juga dilakukan pada lingkungan Google Colab pengguna lain untuk memastikan bahwa proses pemuatan dataset, ekstraksi, preprocessing, analisis, dan visualisasi dapat dijalankan kembali tanpa bergantung pada variabel dari sesi sebelumnya.

## 10. Author

**Dewa Putu Fajar Wijayakusuma**

Student ID: 203012510036

Course: Visualisasi Data Teks

Repository: [Tugas3-Visualisasi-Data-Teks](https://github.com/dewaputufajar308/Tugas3-Visualisasi-Data-Teks)
