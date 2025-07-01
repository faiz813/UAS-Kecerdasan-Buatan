# UAS-Kecerdasan-Buatan

Penjelasan langkah pengerjaan 

1. Business Understanding (Pemahaman Masalah)
•	Masalah Nyata: Perubahan iklim menyulitkan prediksi cuaca dengan metode konvensional.
•	Tujuan Proyek: Membangun sistem prediksi cuaca dengan machine learning untuk meningkatkan akurasi.
•	Pengguna Sistem: BMKG, aplikasi cuaca, petani, nelayan, operator transportasi.
•	Manfaat AI: Prediksi lebih cepat dan akurat, meningkatkan kesiapsiagaan terhadap cuaca ekstrem.
________________________________________
2. Data Understanding (Pemahaman Data)
•	Sumber Data: Dataset “Weather History” dari Kaggle.
•	Deskripsi Fitur: Berisi atribut seperti suhu, kelembapan, tekanan, visibilitas, dan cuaca (summary).
•	Target Klasifikasi: Summary dikategorikan menjadi tiga:
o	Clear
o	Cloudy
o	Rain
•	Ukuran Data: 96.453 baris dan 11 kolom, format CSV.
________________________________________
3. Exploratory Data Analysis (EDA)
•	Distribusi Data:
o	Suhu dan suhu terasa mengikuti distribusi normal.
o	Kelembapan dan kecepatan angin condong ke kanan (positif skew).
o	Beberapa fitur seperti Cloud Cover tidak berguna karena konstan.
•	Korelasi:
o	Suhu dan suhu terasa berkorelasi sangat tinggi (0.99).
o	Suhu vs kelembapan = korelasi negatif kuat (-0.63).
o	Tekanan tidak berkorelasi signifikan.
•	Data Tidak Seimbang:
o	Kelas Rain jauh lebih dominan dari Snow.
________________________________________
4. Data Preparation (Persiapan Data)
•	Missing Values:
o	Fitur Precip Type memiliki missing value dan diisi dengan “No Precipitation”.
•	Encoding:
o	Fitur kategorikal (misalnya Precip Type) diubah menjadi numerik (0/1).
•	Normalisasi:
o	Tidak diperlukan karena Random Forest tahan terhadap skala fitur.
•	Split Data:
o	Data dibagi menjadi 80% training dan 20% testing.
________________________________________
5. Modeling (Pemodelan)
•	Algoritma: Random Forest (metode bagging dengan banyak decision tree).
•	Alasan Pemilihan:
o	Akurasi tinggi, tahan terhadap noise, bisa menilai pentingnya fitur.
•	Implementasi:
o	Training model dengan data yang sudah diproses.
o	Visualisasi Confusion Matrix.
•	Evaluasi Model:
o	Akurasi: 100%
o	Precision, Recall, F1-Score: Semua 1.0 (sempurna)
o	Tidak ada kesalahan klasifikasi (semua prediksi benar)
________________________________________
6. Evaluation (Evaluasi)
•	Confusion Matrix:
o	Semua prediksi benar → menunjukkan performa sempurna.
•	Analisis Metrik Evaluasi:
o	Model sangat akurat berkat fitur yang sangat informatif (seperti suhu dan visibilitas).
o	Tidak ada False Positive maupun False Negative.
•	Catatan Kritis:
o	Walau 100% akurat, tetap perlu diuji ulang dengan data baru untuk hindari overfitting.
________________________________________
7. Kesimpulan & Rekomendasi
•	Kesimpulan:
o	Model sangat baik, tidak overfit, fitur cuaca sangat relevan.
•	Rekomendasi:
o	Tambah data historis (lebih panjang).
o	Gunakan cross-validation untuk kestabilan.
o	Eksplorasi model lain seperti XGBoost atau LSTM untuk data time series.
o	Kembangkan sistem prakiraan otomatis.
o	Gabungkan dengan citra satelit untuk akurasi lebih tinggi.

