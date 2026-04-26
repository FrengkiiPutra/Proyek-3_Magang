# Proyek 3 Magang: Cardiovascular Disease Classification
### Sistem Peringatan Dini Penyakit Kardiovaskular Berbasis Machine Learning

Proyek ini merupakan dokumentasi lengkap mengenai pengembangan model klasifikasi risiko penyakit kardiovaskular. Dengan memanfaatkan 70.000 data klinis, fokus utama proyek ini adalah mentransformasi data mentah menjadi sistem pendukung keputusan medis yang presisi, tervalidasi, dan memprioritaskan keselamatan pasien.

# 🛠️ Tech Stack
* **Environment:** Google Colab / Jupyter Notebook
* **Libraries:** * `Pandas` & `NumPy` (Data Manipulation)
    * `Seaborn` & `Matplotlib` (Medical Data Visualization)
    * `Scikit-Learn` (Modeling & Pipeline)
    * `Imbalanced-learn` (Data Distribution)

---

# 📋 Alur Kerja Proyek: Pipeline End-to-End

### A. Data Understanding & Medical Audit
Sebelum modeling, dilakukan audit ketat untuk memastikan kualitas data:
1. **Cleaning Anomali:** Menghapus data medis yang tidak logis (misal: tekanan darah sistolik < diastolik).
2. **Outlier Removal:** Membersihkan data ekstrem pada fitur tinggi dan berat badan untuk menjaga objektivitas model.
3. **Feature Engineering:** Membuat fitur baru `BMI` (Body Mass Index) dan mengonversi usia ke tahun (`age_years`) untuk memperkuat korelasi prediktif.
4. **Hasil:** Dataset final terdiri dari **68.388 data valid** dengan distribusi target seimbang (50:50).

### B. Intelligent Preparation (Preprocessing)
1. **StandardScaler:** Menyamakan skala seluruh fitur (seperti tekanan darah yang bernilai ratusan vs kolesterol yang bernilai satuan) agar model stabil.
2. **Stratified Split (80:20):** Memisahkan data latih dan data uji dengan tetap menjaga proporsi kelas pasien sakit agar evaluasi tetap jujur.

### C. Multi-Model Benchmarking & Optimization
Eksperimen dilakukan untuk membandingkan efektivitas dua algoritma utama:
1. **Logistic Regression:** Digunakan sebagai baseline klasifikasi linear.
2. **Random Forest Classifier:** Algoritma Ensemble (Bagging) yang digunakan untuk menangkap pola non-linear pada variabel medis yang kompleks.
3. **Bayesian Search Optimization:** Teknik optimasi cerdas untuk menemukan hyperparameter terbaik guna menyeimbangkan akurasi dan recall.

---

# 📊 Hasil & Metrik Evaluasi

Berdasarkan hasil pengujian di Google Colab, **Random Forest** terbukti sebagai model paling andal secara klinis:

| Metrik | Logistic Regression | Random Forest (Best Model) |
| :--- | :--- | :--- |
| **Akurasi** | 72.16% | **73.84%** |
| **F1-Score** | 70.47% | **72.13%** |
| **Recall** | 66.86% | **68.44%** |

### 💡 Analisis Profesional: Keunggulan Klinis
Dalam aplikasi medis nyata, **Recall (Sensitivitas)** adalah metrik paling krusial. 
* **Insight:** Random Forest berhasil mengurangi angka *False Negative* (pasien sakit yang terdeteksi sehat) sebesar **~94 kasus** dibandingkan Logistic Regression.
* **Kesimpulan:** Model ini lebih aman secara klinis karena meminimalkan risiko pasien berisiko terlewat dari sistem peringatan dini.

---

# 🚀 Cara Menjalankan
1. **Persiapan Data:** Unduh dataset cardio_train.csv secara manual melalui tautan Kaggle ini, lalu unggah file tersebut ke direktori utama Google Colab. Dengan metode ini, Anda dapat melewati langkah konfigurasi API Kaggle dan langsung menjalankan proses pembersihan serta pemodelan data.
2. **Eksekusi Notebook:** Jalankan blok kode secara berurutan di Google Colab untuk menjaga kesinambungan variabel.
3. **Evaluasi:** Tabel `df_performa` dan *Confusion Matrix* di bagian akhir akan menampilkan perbandingan detail antar model.

---
*💡 Repository ini disusun untuk menunjukkan kemampuan dalam mengolah data kesehatan yang besar menjadi keputusan klinis yang menyelamatkan nyawa melalui integrasi Machine Learning.*

**Disusun oleh:** **Frengki Saputra** | 23SA21A074  
Program Studi Sistem Informasi – Universitas Amikom Purwokerto
