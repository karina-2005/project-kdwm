# 📊 Estimasi Jumlah Penghuni Ruangan Menggunakan Data Mining

Studi kasus penerapan **Data Mining** untuk mengestimasi jumlah penghuni ruangan (*room occupancy*) secara otomatis berdasarkan data sensor lingkungan, menggunakan metodologi **CRISP-DM** (Cross Industry Standard Process for Data Mining).

🔗 **Portofolio:** [ https://sites.google.com/global.ac.id/portofolio-khanza/beranda ]
🎥 **Video Demo/Penjelasan:** [https://youtu.be/s20NCNk7ySQ?si=9v7xtqPsrRQ5s3OO]

---

## 📌 Deskripsi Proyek

Sebuah gedung perkantoran memasang berbagai sensor lingkungan (suhu, cahaya, suara, CO₂, dan PIR/*Passive Infrared Sensor*) di setiap ruangan, dengan data yang disimpan secara berkala dalam *data warehouse*. Proyek ini membangun model *data mining* untuk memprediksi jumlah penghuni ruangan secara otomatis dari data sensor tersebut, tanpa perlu penghitungan manual — mendukung konsep **smart building**, efisiensi energi, dan keamanan.

**Target/Label:** `Room_Occupancy_Count`
**Algoritma:** `Linear Regression` (scikit-learn)

---

## 🗂️ Dataset

| Item | Keterangan |
|---|---|
| Nama file | `Occupancy_Estimation.csv` |
| Jumlah observasi | 10.129 baris |
| Jumlah atribut | 19 kolom |
| Missing value / duplikat | Tidak ditemukan |

**Atribut sensor yang digunakan:**

| Kategori | Kolom |
|---|---|
| Waktu | `Date`, `Time` |
| Suhu | `S1_Temp`, `S2_Temp`, `S3_Temp`, `S4_Temp` |
| Cahaya | `S1_Light`, `S2_Light`, `S3_Light`, `S4_Light` |
| Suara | `S1_Sound`, `S2_Sound`, `S3_Sound`, `S4_Sound` |
| CO₂ | `S5_CO2`, `S5_CO2_Slope` |
| Gerak (PIR) | `S6_PIR`, `S7_PIR` |
| **Target** | `Room_Occupancy_Count` |

> Kolom `Date` dan `Time` tidak digunakan dalam pemodelan karena tidak berpengaruh langsung terhadap estimasi jumlah penghuni.

---

## 🔁 Tahapan CRISP-DM (Struktur Notebook)

| Fase | Isi |
|---|---|
| **1. Business Understanding** | Latar belakang, permasalahan bisnis, tujuan bisnis & data mining, kriteria keberhasilan, manfaat penelitian |
| **2. Data Understanding** | Load dataset, info & statistik deskriptif, cek missing value/duplikat, analisis korelasi Pearson, heatmap korelasi, scatter plot & histogram distribusi sensor, insight awal |
| **3. Data Preparation** | Pemilihan atribut (drop `Date`, `Time`), pembagian data *train/test* (80:20), normalisasi data dengan `StandardScaler` |
| **4. Modeling** | Membangun & melatih model `LinearRegression`, prediksi data uji, perbandingan aktual vs prediksi |
| **5. Evaluation** | Evaluasi performa model dengan MAE, MSE, RMSE, R² Score, visualisasi aktual vs prediksi |
| **6. Deployment** | Kesimpulan akhir dan saran pengembangan lanjutan |

---

## ⚙️ Library yang Digunakan

```
pandas
numpy
matplotlib
seaborn
scikit-learn   # LinearRegression, train_test_split, StandardScaler,
               # mean_absolute_error, mean_squared_error, r2_score
```

Instalasi:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

---

## ▶️ Cara Menjalankan

1. Pastikan file dataset **`Occupancy_Estimation.csv`** berada pada direktori yang sama dengan notebook.
2. Install dependency (lihat bagian di atas) atau jalankan di environment yang sudah memiliki library tersebut.
3. Jalankan Jupyter Notebook:
   ```bash
   jupyter notebook "estimasi - room occupancy.ipynb"
   ```
4. Eksekusi setiap *cell* secara berurutan dari **Phase 1** hingga **Phase 6**.

---

## 📈 Hasil Evaluasi Model

| Metrik | Nilai |
|---|---|
| Data Training | 8.103 baris |
| Data Testing | 2.026 baris |
| Mean Absolute Error (MAE) | 0,1637 |
| Mean Squared Error (MSE) | 0,0920 |
| Root Mean Square Error (RMSE) | 0,3034 |
| **R² Score** | **0,8878 (88,78%)** |

Model **Linear Regression** mampu menjelaskan ±88,78% variasi jumlah penghuni ruangan berdasarkan atribut sensor, dengan tingkat kesalahan prediksi yang relatif kecil — menunjukkan performa yang **sangat baik**.

---

## ✅ Kesimpulan

Model *data mining* berbasis Linear Regression berhasil dibangun untuk mengestimasi jumlah penghuni ruangan menggunakan data sensor suhu, cahaya, suara, CO₂, dan gerak. Hasil ini dapat dimanfaatkan sebagai dasar sistem monitoring otomatis pada konsep **smart building**.

## 💡 Saran Pengembangan

- Membandingkan performa dengan algoritma lain seperti **Random Forest**, **Decision Tree**, atau **XGBoost**.
- Menambah jumlah data observasi dan jenis atribut sensor untuk meningkatkan akurasi model.

---

## 👤 Informasi Tambahan

- **Metodologi:** CRISP-DM
- **Bahasa & Tools:** Python (Jupyter Notebook)
- **Jenis Model:** Regresi (Supervised Learning)
