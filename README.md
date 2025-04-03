# Prediksi-Risiko-Diabetes

## Dataset
sumber : https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset 

Dataset dimuat menggunakan pd.read_csv(), dan eksplorasi awal dilakukan:
- df.shape: Menampilkan jumlah baris dan kolom.
-  df.head(): Melihat sampel data.
-  df.info() dan df.describe(): Mendapatkan informasi tipe data dan statistik deskriptif.

Data Cleaning:
- Duplikasi: Menghapus duplikasi dengan df.drop_duplicates().
- Nilai Kosong: Mengisi nilai kosong dengan rata-rata menggunakan SimpleImputer.

Menangani Ketidakseimbangan Kelas
- SMOTE: Membuat distribusi kelas menjadi seimbang dengan menghasilkan data sintetis.
- Oversampling/Undersampling: Menambah atau mengurangi sampel untuk kelas minoritas/majoritas.

Analisis dan Transformasi Data
- Analisis Statistik: Menggunakan fungsi khusus untuk menghitung nilai maksimum, minimum, mean, skewness, dll.
- Transformasi Data:
1. Encoding untuk kolom kategorikal seperti Sex dan Smoker.
2. Scaling data numerik menggunakan StandardScaler.
3. Transformasi Yeo-Johnson untuk membuat distribusi lebih normal.

Pemodelan dan Evaluasi
- Model yang Digunakan:
1. KNN (K-Nearest Neighbors).
2. Random Forest Classifier.
3. Decision Tree Classifier.
- Evaluasi: Menggunakan metrik seperti:
1. Precision
2. Recall
3. F1 Score
4. Confusion Matrix.

Menampilkan visualisasi:
- Heatmap korelasi antar fitur.
- Boxplot untuk mendeteksi outlier.
- Distribusi kelas sebelum dan sesudah SMOTE.


# PENJELASAN OUTPUT:
1. Eksplorasi Data
- Tujuan: Memahami ukuran dan isi dataset.
- Hasil: Dataset memiliki banyak baris (data individu) dan kolom (fitur kesehatan). Contohnya, ada data tentang tekanan darah tinggi, kolesterol, aktivitas fisik, dan apakah seseorang menderita diabetes atau tidak.
- Output Tambahan: Informasi tentang tipe data di setiap kolom (angka atau teks), nilai kosong, dan statistik seperti rata-rata atau nilai maksimum dari tiap kolom.

2. Pembersihan Data
Data seringkali tidak sempurna, jadi langkah ini memastikan data bersih:
- Duplikasi: Baris yang sama persis dihapus.
- Nilai Kosong: Nilai yang hilang diisi dengan rata-rata atau metode lain agar dataset tetap lengkap.

3. Distribusi Kelas
Dataset seringkali tidak seimbang, di mana jumlah data pada satu kelompok (contohnya, orang sehat) jauh lebih banyak dibanding kelompok lain (contohnya, penderita diabetes).
- Hasil: Grafik menunjukkan perbedaan besar dalam jumlah kelas.
- Masalah: Ketidakseimbangan ini dapat membuat model tidak akurat karena terlalu fokus pada kelas yang dominan.

4. Transformasi dan Standarisasi Data
Untuk mempersiapkan data:
- Data Kategorikal: Contoh, kolom "Jenis Kelamin" diubah menjadi angka (0 untuk pria, 1 untuk wanita).
- Scaling: Data numerik seperti usia dan pendapatan diubah ke skala standar agar lebih seragam dan mudah diproses oleh model.

5. Analisis Korelasi
Langkah ini mengevaluasi hubungan antar kolom:
- Tujuan: Melihat kolom mana yang paling berpengaruh terhadap risiko diabetes.
- Hasil: Ditampilkan dalam bentuk peta panas (heatmap). Kolom dengan korelasi rendah diabaikan agar model hanya menggunakan informasi yang relevan.

6. Penyeimbangan Data
Karena distribusi kelas tidak seimbang:
- Oversampling: Data sintetis ditambahkan untuk kelas yang kurang, sehingga jumlah tiap kelompok menjadi sama.
- Visualisasi: Grafik menunjukkan distribusi baru yang seimbang setelah proses ini.

7. Deteksi dan Penanganan Outlier
- Outlier: Nilai yang sangat berbeda dari data lainnya (contohnya, seseorang dengan BMI sangat tinggi). Ini dapat mengganggu akurasi model.
- Hasil: Ditampilkan dalam bentuk grafik boxplot. Nilai ekstrem diganti dengan nilai rata-rata untuk menjaga stabilitas model.

8. Seleksi Fitur
Tidak semua kolom data penting untuk model:
- Tujuan: Menentukan fitur (kolom) mana yang paling berpengaruh terhadap prediksi diabetes.
- Hasil: Fitur penting seperti BMI, usia, dan tingkat aktivitas fisik diidentifikasi. Fitur yang tidak relevan dihapus.

9. Pemodelan Machine Learning
Beberapa algoritma pembelajaran mesin digunakan untuk membangun model prediksi, seperti:
- KNN (K-Nearest Neighbors): Menentukan risiko diabetes berdasarkan data individu yang mirip.
- Random Forest: Menggunakan banyak pohon keputusan untuk membuat prediksi yang akurat.
- Decision Tree: Membuat keputusan berdasarkan fitur tertentu, misalnya jika BMI tinggi maka risiko diabetes tinggi.

10. Evaluasi Model
Setelah model dilatih, kinerjanya diuji menggunakan metrik seperti:
- Precision: Seberapa tepat model dalam memprediksi diabetes.
- Recall: Seberapa baik model mendeteksi semua kasus diabetes.
F1 Score: Kombinasi antara precision dan recall.
- Hasil: Model terbaik dipilih berdasarkan kinerja metrik tersebut.

11. Output Akhir
- Laporan: Hasil evaluasi disajikan dalam tabel perbandingan antara model (contohnya, Random Forest mungkin lebih baik daripada KNN).
- Kesimpulan: Algoritma terbaik dapat digunakan untuk memprediksi risiko diabetes pada data baru.
