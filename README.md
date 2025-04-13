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
Dalam proyek ini, digunakan dataset Pima Indians Diabetes yang tersedia secara publik melalui [Kaggle](https://www.kaggle.com/datasets/nancyalaswad90/review). Dataset ini dikumpulkan oleh National Institute of Diabetes and Digestive and Kidney Diseases dan bertujuan untuk memprediksi apakah seorang pasien menderita diabetes berdasarkan sejumlah pengukuran diagnostik.
Dataset ini terdiri dari 768 entri data dengan 8 fitur input dan 1 target output, di mana target Outcome bernilai:
- 0 jika pasien tidak menderita diabetes, dan
- 1 jika pasien menderita diabetes.

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
1. Pregnancies	Jumlah kehamilan yang pernah dialami pasien
2. Glucose	Kadar glukosa dalam plasma darah
3. BloodPressure	Tekanan darah diastolik (mm Hg)
4. SkinThickness	Ketebalan lipatan kulit triceps (mm)
5. Insulin	Kadar insulin serum 2 jam setelah makan (mu U/ml)
6. BMI	Indeks massa tubuh (berat badan dalam kg / (tinggi badan dalam m)^2)
7. DiabetesPedigreeFunction	Fungsi riwayat diabetes secara genetik
8. Age	Usia pasien (dalam tahun)
9. Outcome	Label (0 = negatif diabetes, 1 = positif diabetes)

Selanjutnya untuk melakukan analisis data lanjutan langkah awal yang dilakukan adalah mendefinisikan pertanyaan terlebih dahulu. Pertanyaan yang didefinisikan yaitu:
1. Berapa banyak entri dalam dataset dan berapa proporsi dari masing-masing nilai Outcome (0 dan 1)?
2. Bagaimana Korelasi tiap Variabel?
3. Variabel apa yang memiliki korelasi paling tinggi dengan outcome?

![image](https://github.com/user-attachments/assets/1d446357-16d1-471a-a1b6-ffd353bd37d7) \
Berdasarkan gambar diatas, sebaran data pasien yang terkena diabetes yaitu 31% dan yang tidak yaitu sebesar 69% dari data yang ada. 
Kemudian untuk melihat bagaimana korelasi setiap variabel/fitur, maka visualisasi menggunakan heatmap seperti dibawah ini dilakukan.
![image](https://github.com/user-attachments/assets/c07353bf-a17c-41cd-b4f2-9c50b08f5421) \
Berdasarkan kedua visualisasi tersebut, didapatkan kesimpulan dan saran sebagai berikut \
**Kesimpulan**
1. Variabel yang memiliki korelasi paling tinggi dengan Outcome (Hasil akhir, di mana 1 menunjukkan pasien menderita diabetes dan 0 menunjukkan pasien tidak menderita diabetes) adalah Glucose (kadar gula darah) dalam pasien.
2. Dan yang memiliki Korelasi paling rendah adalah SkinThickness: Ketebalan lipatan kulit triceps (mm).\

**Saran**
1. Penting untuk mempertimbangkan apakah SkinThickness akan digunakan atau tidak
2. Penambahan data dalam dataset bila akurasi yang didapatkan cukup rendah


## Data Preparation
Tahapan data preparation sangat penting dalam proses pemodelan, karena kualitas data yang baik akan meningkatkan performa model machine learning dan deep learning yang digunakan. Pada proyek ini, dilakukan beberapa tahapan persiapan data untuk memastikan bahwa dataset layak digunakan dalam proses pelatihan model.

1. Menangani Nilai yang Tidak Logis (Zero Replacement)
   Beberapa fitur dalam dataset memiliki nilai 0 yang tidak realistis atau secara medis tidak mungkin bernilai nol, seperti pada kolom Glucose, BloodPressure, SkinThickness, Insulin, dan BMI. Nilai nol ini sebenarnya merepresentasikan data yang hilang (missing values) dan perlu ditangani. Mengganti nilai 0 dengan rata-rata (mean) dari kolom masing-masing, kecuali kolom Pregnancies yang secara medis bisa bernilai 0.
2. Split Data: Training dan Testing
   Untuk mengevaluasi performa model secara objektif, data dibagi menjadi dua bagian:
   - 80% data untuk pelatihan (training)
   - 20% data untuk pengujian (testing)
   - Stratifikasi digunakan agar distribusi kelas tetap seimbang.
3. Standarisasi Fitur (Feature Scaling)
   Beberapa algoritma machine learning seperti K-Nearest Neighbors dan Logistic Regression sensitif terhadap skala fitur. Oleh karena itu, dilakukan standarisasi data agar semua fitur memiliki skala yang seragam. StandardScaler dari sklearn.preprocessing, yang mengubah setiap fitur agar memiliki mean 0 dan standar deviasi 1.

## Modeling
Untuk menyelesaikan permasalahan klasifikasi dalam mendeteksi potensi diabetes, beberapa algoritma machine learning telah digunakan dan dibandingkan performanya. Algoritma yang dipilih meliputi Logistic Regression, Decision Tree, Random Forest, dan K-Nearest Neighbors (KNN). Masing-masing algoritma diuji berdasarkan akurasi, precision, recall, dan f1-score untuk mengetahui model mana yang paling optimal dalam mengklasifikasikan data pasien.
1. Logistic Regression digunakan sebagai model baseline karena kesederhanaannya dan kemampuannya untuk memberikan interpretasi yang jelas. Namun, model ini kurang mampu menangani hubungan non-linear antara fitur.
2. Decision Tree menawarkan kemampuan menangkap hubungan kompleks antar fitur tanpa perlu standarisasi data, tetapi rentan terhadap overfitting.
3. Random Forest digunakan sebagai metode ensemble yang menggabungkan banyak pohon keputusan, sehingga lebih stabil dan mampu memberikan performa lebih baik dari Decision Tree tunggal.
4. K-Nearest Neighbors (KNN) merupakan algoritma berbasis jarak yang sederhana namun sangat bergantung pada pemilihan parameter dan preprocessing, terutama scaling.
5. Model Deep learning juga digunakan untuk melihat apakah akan memiliki perbedaan yang signifikan. Model deeplearning yang digunakan, menggunakan arsitektur seperti gambar dibawah.\
![image](https://github.com/user-attachments/assets/8f40cde2-3c7b-4fb0-80cb-2d390f74fbb1)


 
## Evaluation
 Metrik Evaluasi yang digunakan untuk melihat performa dari tiap model yaitu Confusion matrix. [Confusion matrix](https://ieeexplore.ieee.org/document/10396931) adalah informasi yang disimpan dalam bentuk matriks untuk mengetahui performansi model Machine learning maupun Deep learning yang dipakai, dan dapat digunakan sebagai tumpuan dari performansi klasifikasi algoritma yang dipakai pada tahap evaluasi. Confusion matrix merupakan sebuah pengukuran performa yang sering digunakan pada masalah klasifikasi di mana output dapat terdiri dari dua kelas atau lebih. Terdapat empat atribut yang merupakan kombinasi dari nilai yang diprediksi (predicted) dan nilai yang sebenarnya (actual) yaitu True Positif (TP), True Negatif (TN), False Positif (FP), dan False Negatif (FN).
1. Accuracy, menggambarkan akurasi dari sebuah model dalam mengklasifikasikan dengan benar.\
   Accuracy =(TP+TN)/(TP+TN+FP+FN) 					
2. Precision, memberitahu seberapa banyak sampel positif yang diprediksi secara benar untuk semua sampel yang diprediksi positif.\
   Precision=TP/(TP+FP) 						
3. Recall, memberitahu seberapa banyak sampel yang diprediksi secara benar untuk semua sampel nilai aktual yang positif.\
    Recall=TP/(TP+FN) 			
4. F1-score merupakan hasil kombinasi dari rumus precision dan recall. Nilai F1-score adalah nilai rata-rata dari precision dan recall yang memiliki sebuah nilai maksimal ketika precision dan recall setara.\
    F1-score = 2 ((Precision*Recall)/(Precision+Recall))

Hasil  perbandingan setiap model bisa dilihat pada gambar berikut\
![image](https://github.com/user-attachments/assets/08de89e7-f41c-4844-804d-c90e822aea5c)

Berdasarkan hasil evaluasi, model KNN menunjukkan performa terbaik dengan akurasi sekitar 78%. Model ini sangat baik dalam mendeteksi pasien tanpa diabetes (class 0), namun performanya dalam mendeteksi pasien yang positif diabetes (class 1) masih bisa ditingkatkan. Oleh karena itu, dilakukan proses hyperparameter tuning menggunakan GridSearchCV untuk mengoptimalkan parameter seperti n_neighbors, weights, dan metric. Hasil tuning menunjukkan bahwa pengaturan parameter yang optimal mampu meningkatkan nilai recall dan f1-score untuk class 1, yang sangat penting dalam konteks medis agar model tidak melewatkan pasien yang berpotensi terkena diabetes. Hasil tunning bisa dilihat pada gambar dibawah ini.\
![image](https://github.com/user-attachments/assets/e5efcbf9-bda8-4e9d-8ac8-296e7ed999c9)

Proses tuning juga divisualisasikan untuk menunjukkan bagaimana perubahan jumlah tetangga (n_neighbors) memengaruhi akurasi model. Hasil tuning ini menghasilkan model KNN yang lebih seimbang dan dapat diandalkan dalam konteks klasifikasi biner untuk diagnosis awal diabetes. Dengan mempertimbangkan keseimbangan metrik, kemudahan implementasi, dan performa setelah tuning, maka model K-Nearest Neighbors dipilih sebagai model terbaik dalam proyek ini. Proses tunning pemilihan parameter terbaik dapat dilihat pada gambar berikut\
![image](https://github.com/user-attachments/assets/329afcc1-cc46-4533-85ec-1bd89a098587)

Selain menggunakan model machine learning konvensional, proyek ini juga mengimplementasikan pendekatan deep learning sebagai pembanding untuk melihat sejauh mana peningkatan performa dapat dicapai dengan arsitektur jaringan saraf yang lebih kompleks. Model deep learning yang digunakan adalah model feedforward neural network (FNN) yang terdiri dari beberapa lapisan tersembunyi (hidden layers) dan telah dilengkapi dengan teknik regularisasi untuk menghindari overfitting. Arsitektur model terdiri dari tiga lapisan tersembunyi: layer pertama dengan 128 neuron, layer kedua dengan 64 neuron, dan layer ketiga dengan 32 neuron, semuanya menggunakan fungsi aktivasi ReLU. Untuk output, digunakan satu neuron dengan fungsi aktivasi sigmoid karena permasalahan bersifat klasifikasi biner. Model ini juga dilengkapi dengan dropout layer sebesar 0.3 dan 0.2 di antara lapisan-lapisan tersembunyi sebagai upaya untuk mengurangi overfitting.

Model ini dilatih menggunakan binary cross-entropy sebagai loss function dan optimasi menggunakan Adam optimizer. Selama proses training, model dipantau berdasarkan akurasi dan loss pada data training dan validation set. Hasil pelatihan menunjukkan bahwa meskipun akurasi model relatif tinggi, terdapat indikasi awal overfitting—dimana model memiliki performa sangat baik pada data pelatihan namun tidak terlalu baik dalam generalisasi ke data uji. Hal ini merupakan salah satu kelemahan umum dari deep learning ketika digunakan pada dataset yang relatif kecil seperti dataset Pima Indian Diabetes, yang hanya memiliki sekitar 768 data.

Kelebihan dari model deep learning adalah kemampuannya untuk menangkap hubungan non-linear dan kompleks antar fitur secara otomatis tanpa perlu rekayasa fitur eksplisit. Selain itu, model ini juga fleksibel dan dapat ditingkatkan skalanya dengan menambahkan lebih banyak lapisan atau unit neuron jika tersedia data dalam jumlah besar. Namun, kelemahannya adalah membutuhkan lebih banyak waktu pelatihan, sumber daya komputasi yang lebih tinggi, serta lebih rentan terhadap overfitting terutama jika data tidak cukup besar atau tidak dilakukan regularisasi dengan baik.

hasil dari model deep learning itu sendiri bisa dilihat pada gambar dibawah ini. Penggunaan model deep learninh hanya mendapat akurasi sebesar 75%, dalam konteks proyek ini model K-Nearest Neighbors (KNN) tetap menjadi model terbaik berdasarkan keseimbangan performa, kesederhanaan, dan interpretabilitas. Namun demikian, pendekatan deep learning tetap menjadi alternatif yang menjanjikan, khususnya jika di masa depan tersedia dataset yang lebih besar dan beragam.\
![image](https://github.com/user-attachments/assets/147d39bd-1b7e-42f3-83c5-b138c7ed9589)


