# Laporan Proyek Machine Learning - ANDREAS DWI PUTRA TURANGAN

## Prediksi Diabetes (Kesehatan)

Karena jumlah penderita diabetes mellitus yang terus meningkat setiap tahunnya, diabetes mellitus adalah salah satu penyakit kronis yang menjadi perhatian global. [World Health Organization (WHO)](https://www.who.int/health-topics/diabetes#tab=tab_1) melaporkan bahwa prevalensi diabetes telah meningkat secara global. Menurut data dari [International Diabetes Federation (IDF)](https://diabetesatlas.org/), pada tahun 2021 tercatat bahwa 1 dari 10 orang dewasa hidup dengan diabetes, dan diperkirakan angka ini akan meningkat menjadi 643 juta pada tahun 2030 Perubahan gaya hidup modern diperkirakan akan menyebabkan peningkatan ini terus berlanjut. Penyakit ini tidak hanya memengaruhi kualitas hidup penderita, tetapi juga menimbulkan tantangan yang signifikan bagi sistem kesehatan, terutama jika tidak ditemukan sejak awal. Salah satu masalah utama dalam pengobatan diabetes adalah diagnosis yang terlambat. Banyak penderita diabetes baru mengetahui bahwa mereka memiliki komplikasi serius. Akibatnya, sangat penting untuk mendeteksi diabetes sejak dini. M
Dalam bidang kesehatan, teknologi kecerdasan buatan (AI) dan pembelajaran mesin telah membuka peluang baru, seperti mendeteksi penyakit kronis seperti diabetes.  Teknik ini memungkinkan sistem untuk membuat prediksi secara otomatis yang sangat akurat dan mengidentifikasi pola dalam data medis yang kompleks.  Studi yang dilakukan oleh [An Dinh](https://bmcmedinformdecismak.biomedcentral.com/articles/10.1186/s12911-019-0918-5) menunjukkan bahwa teknik berbasis pembelajaran mesin dapat membantu diagnosis dini berbagai penyakit, seperti diabetes.
Penelitian ini akan membandingkan beberapa algoritma machine learning konvensional dan algoritma deep learning. Kemudian algoritma terbaik yang dibangun menggunakan base model akan ditingkatkan dengan teknik fine-tunning sesuai dengan algoritma terbaik yang digunakan


## Business Understanding

Diabetes adalah kondisi kronis yang dapat sangat mengganggu kualitas hidup seseorang.  Untuk memastikan bahwa pengobatan atau pencegahan dapat dilakukan segera, deteksi dini sangat penting.  Dalam situasi seperti ini, machine learning dan deep learning sangat potensial untuk membantu memprediksi penyakit diabetes dengan data historis pasien.
Untuk mencapai tujuan ini, pemahaman yang mendalam tentang masalah yang dihadapi diperlukan, serta pendekatan yang dapat digunakan teknologi untuk menjawab masalah tersebut.

### Problem Statements
1. Bagaimana membangun model machine learning yang mampu memprediksi apakah seseorang berpotensi menderita diabetes berdasarkan fitur-fitur medis seperti kadar glukosa, tekanan darah, indeks massa tubuh, dan lainnya?
2. Algoritma mana yang memiliki performa terbaik dalam memprediksi diabetes berdasarkan dataset Pima Indians Diabetes?
3. Bagaimana meningkatkan performa model prediksi agar dapat menangani ketidakseimbangan data serta meminimalkan kesalahan prediksi pada pasien yang positif diabetes?
4. Dapatkah model deep learning memberikan performa yang lebih baik dibandingkan model machine learning konvensional dalam mendeteksi diabetes?


### Goals

1. membangun sistem klasifikasi yang menggunakan data pasien untuk memprediksi kemungkinan diabetes.
2. Memilih model terbaik dengan membandingkan kinerja beberapa algoritma pengajaran mesin, seperti Logistic Regression, Decision Tree, Random Forest, dan K-Nearest Neighbors.
3. Tuning hyperparameter dan metode evaluasi model untuk meningkatkan akurasi dan recall, terutama untuk mengidentifikasi pasien positif diabetes.
4. Untuk mengetahui seberapa baik jaringan saraf dalam klasifikasi data medis, gunakan model deep learning dan bandingkan hasilnya dengan model machine learning.

### Solution statements
- Mengaplikasikan dan membandingkan berbagai algoritma pembelajaran mesin seperti Logistic Regression, Decision Tree, Random Forest, dan K-Nearest Neighbors pada dataset Pima untuk menentukan model terbaik berdasarkan metrik seperti akurasi, precision, recall, dan skor F1.
- Untuk meningkatkan hasil prediksi, terutama recall pada kelas pasien positif diabetes, gunakan hyperparameter tuning (seperti menggunakan GridSearchCV) pada model dengan performa terbaik (seperti K-Nearest Neighbors).
- Untuk menentukan apakah deep learning memberikan keunggulan, arsitektur neural network yang terdiri dari lapisan Dense dan Dropout digunakan. Kemudian, untuk menerapkan model, digunakan metrik yang sama.
- Menggunakan visualisasi seperti heatmap dan confusion matrix untuk membantu memahami hasil tuning dan mengevaluasi kekuatan dan kelemahan model.

## Data Understanding
Dalam proyek ini, digunakan dataset Pima Indians Diabetes yang tersedia secara publik melalui [Kaggle](https://www.kaggle.com/datasets/hassnataslam/pima-indians-diabetes-dataset). Dataset ini dikumpulkan oleh National Institute of Diabetes and Digestive and Kidney Diseases dan bertujuan untuk memprediksi apakah seorang pasien menderita diabetes berdasarkan sejumlah pengukuran diagnostik.
Selanjutnya uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

## Modeling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Anda perlu menjelaskan tahapan dan parameter yang digunakan pada proses pemodelan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan kelebihan dan kekurangan dari setiap algoritma yang digunakan.
- Jika menggunakan satu algoritma pada solution statement, lakukan proses improvement terhadap model dengan hyperparameter tuning. **Jelaskan proses improvement yang dilakukan**.
- Jika menggunakan dua atau lebih algoritma pada solution statement, maka pilih model terbaik sebagai solusi. **Jelaskan mengapa memilih model tersebut sebagai model terbaik**.

## Evaluation
Pada bagian ini anda perlu menyebutkan metrik evaluasi yang digunakan. Lalu anda perlu menjelaskan hasil proyek berdasarkan metrik evaluasi yang digunakan.

Sebagai contoh, Anda memiih kasus klasifikasi dan menggunakan metrik **akurasi, precision, recall, dan F1 score**. Jelaskan mengenai beberapa hal berikut:
- Penjelasan mengenai metrik yang digunakan
- Menjelaskan hasil proyek berdasarkan metrik evaluasi

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
