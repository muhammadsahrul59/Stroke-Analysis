# Stroke Prediction - Predictive Analysis🏥

## Domain Proyek
Domain yang dipilih untuk dilakukan prediksi adalah domain kesehatan, yang berfokus pada penyakit stroke.

Menurut *World Stroke Organization* (WSO), 13 juta orang terserang stroke setiap tahunnya, dan sekitar 5,5 juta orang akan meninggal dunia. Stroke merupakan penyebab utama kematian dan disabilitas di seluruh dunia, dan itulah sebabnya mengapa dampaknya sangat serius dalam semua aspek kesehatan. Stroke tidak hanya memengaruhi pasien, tetapi juga memengaruhi lingkungan sosial, keluarga, dan tempat kerja pasien. Selain itu, berlawanan dengan kepercayaan masyarakat, stroke dapat terjadi pada siapa saja, pada usia berapa pun, tanpa memandang jenis kelamin atau kondisi fisik.

Stroke didefinisikan sebagai gangguan neurologis akut pada pembuluh darah di otak yang terjadi ketika suplai darah ke suatu area otak terhenti dan sel-sel otak kekurangan oksigen. Stroke dibagi menjadi iskemik dan hemoragik. Stroke iskemik bisa ringan hingga sangat parah dengan kerusakan sementara hingga permanen. Perdarahan jarang terjadi dan melibatkan pecahnya pembuluh darah yang mengakibatkan pendarahan otak. Stroke Iskemik, yang merupakan stroke yang paling umum, melibatkan terhentinya aliran darah ke suatu area otak akibat penyempitan atau penyumbatan arteri.

## Business Understanding
Pada bagian _Business Understanding_ akan dijelaskan mengenai permasalahan yang akan diselesaikan (*problem statements*), tujuan (*goal*), dan solusi yang diajukan (*solution statements*).

### Problem Statements
Bagaimana mengetahui pasien memiliki penyakit stroke berdasarkan riwayat dari variabel-variabel kesehatan yang ada?

### Goals
Untuk menyelesaikan permasalahan yang telah disampaikan pada bagian *Problem Statement*, maka dibuat model yang digunakan untuk memprediksi apakah seseorang memiliki penyakit stroke berdasarkan riwayat kesehatannya.

### Solution statements
Solusi pembuatan model yang dilakukan adalah dengan menerapkan 3 algoritma machine learning, terbatas pada **_K-NN_**, **_Random Forest_**, dan **_AdaBoost_**. Diterapkannya 3 algoritma tersebut bertujuan untuk mengkomparasi dan mendapatkan model atau algoritma yang memiliki tingkat _error_ yang paling kecil, sehingga prediksi penyakit jantung memiliki akurasi yang tinggi.

-  **_K-NN_** Algoritma _K-Nearest Neighbor_ (K-NN) adalah algoritma _machine learning_ yang sederhana dan mudah diterapkan, yang mana umumnya digunakan untuk menyelesaikan masalah klasifikasi dan regresi. Algoritma ini termasuk dalam _supervised learning_. Tujuan dari algortima K-NN adalah untuk mengidentifikasi _nearest neighbor_ dari titik yang diberikan, sehingga dapat menetapkan label prediksi ke titik tersebut.

-  **_Random Forest_** _Random forest_ adalah kombinasi dari masing – masing _tree_ atau pohon, yang kemudian dikombinasikan ke dalam satu model. _Random Forest_ bergantung pada sebuah nilai vector acak dengan distribusi yang sama pada semua pohon yang masing masing _tree_ memiliki kedalaman yang maksimal.

-  **_AdaBoost_** _AdaBoost_ atau _Adaptive Boost_ merupakan algoritma yang memanfaatkan _bagging_ dan _boosting_ untuk meningkatkan akurasi. Sama seperti algoritma _random forest_, algoritma _AdaBoost_ juga menggunakan beberapa _decision tree_ untuk melakukan prediksi.

## Data Understanding
Dataset yang digunakan pada proyek machine learning ini merupakan **5110 data observasi** yang didapat dari situs kaggle [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset). Terdapat 11 fitur yang dapat digunakan untuk memprediksi kemungkinan penyakit stroke.

**Attribute Information**
1) id: unique identifier
2) gender: "Male", "Female" or "Other
3) age: age of the patient
4) hypertension: 0 if the patient doesn't have hypertension, 1 if the patient has hypertension
5) heart_disease: 0 if the patient doesn't have any heart diseases, 1 if the patient has a heart disease
6) ever_married: "No" or "Yes"
7) work_type: "children", "Govt_jov", "Never_worked", "Private" or "Self-employed"
8) Residence_type: "Rural" or "Urban"
9) avg_glucose_level: average glucose level in blood
10) bmi: body mass index
11) smoking_status: "formerly smoked", "never smoked", "smokes" or "Unknown"*
12) stroke: 1 if the patient had a stroke or 0 if not

*Note: "Unknown" in smoking_status means that the information is unavailable for this patient

## Explanatory Data Analysis
### Univariate Analysis - Categorical Feature

1. Riwayat Perokok dan Stroke

![riwayatperokok_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/riwayatperokok_stroke.png?raw=true)

Plot diatas memberikan gambaran bahwa status merokok seseorang dapat berhubungan dengan kejadian stroke, namun jumlah kejadian stroke tertinggi justru ditemukan pada individu yang tidak pernah merokok. Hal ini mungkin disebabkan oleh faktor lain yang tidak terlihat dalam data, atau bisa juga menunjukkan bahwa ada variabel perancu (confounding variables) yang mempengaruhi hubungan antara merokok dan stroke.

2. Status Pernikahan dan Stroke

![statuspernikahan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/statuspernikahan_stroke.png?raw=true)
Plot diatas memberikan gambaran bahwa status status perkawinan seseorang dapat berhubungan dengan kejadian stroke, yang dimana seseorang yang sudah menikah cenderung memiliki penyakit stroke dibanding yang belum menikah.

3. Jenis Pekerjaan dan Stroke
![jenispekerjaan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/jenispekerjaan_stroke.png?raw=true)
Plot diatas memberikan gambaran bahwa jenis pekerjaan seseorang dapat berhubungan dengan kejadian stroke. Jumlah kejadian stroke tertinggi ditemukan pada **individu yang bekerja di sektor swasta**, diikuti oleh mereka yang bekerja sendiri, dan kemudian mereka yang bekerja di sektor pemerintah. Jumlah kejadian stroke pada anak-anak sangat rendah, yang bisa diharapkan mengingat prevalensi stroke pada usia muda umumnya lebih rendah dibandingkan dengan orang dewasa.

4. Hipertensi dan Stroke
![jenispekerjaan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/hipertensi_stroke.png?raw=true)
Plot ini memberikan gambaran bahwa meskipun hipertensi dikenal sebagai faktor risiko utama untuk stroke, jumlah kejadian stroke lebih banyak ditemukan pada individu yang tidak memiliki hipertensi.

5. Heatmap of Data
![heatmap_of_data](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/heatmap_of_data.png?raw=true)

**Hasil Pengamatan**:
Pengamatan:
1) Tidak ada korelasi yang kuat antar fitur.
2) Korelasi tertinggi dapat diamati antara indeks massa tubuh (BMI) dan usia.
3) Korelasi terendah dapat diamati antara heart_disease dan hyper_tension (patut dipertanyakan).

### Analysis of Categorical Variables
![analysis_of_categorical_variables](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/analysis_of_categorical_variables.png?raw=true)
Hasil Pengamatan:
1) Jumlah perempuan lebih banyak daripada laki-laki dalam penyakit stroke.
2) Jumlah orang yang sudah menikah jauh lebih banyak menderika penyakit stroke daripada yang belum menikah (masuk akal karena distribusinya antara 0 dan 60)
3) Jumlah yang bekerja di perusahaan swasta memiliki penyakit stroke terbanyak.
4) Tidak ada perbedaan antara populasi di daerah perkotaan dan pedesaan.
5) Jumlah orang yang tidak merokok memiliki penyakit stroke terbanyak.

### Analysing Categorical Variables with Stroke
![analysing_categorical_variables_with_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/analysis_categorical_with_stroke.png?raw=true)
Hasil Pengamatan:
1) Jumlah pria dan wanita yang mengalami stroke sama jumlahnya.
2) Jumlah orang yang tidak memiliki hipertensi juga menunjukkan tanda-tanda tidak ada stroke. Dan orang yang memiliki hipertensi juga tidak menunjukkan tanda-tanda lebih banyak orang yang terkena stroke.
3) Orang dengan penyakit jantung juga menunjukkan tanda-tanda stroke (seperti yang diharapkan).
4) Orang yang menikah menunjukkan tanda-tanda stroke lebih banyak daripada orang yang belum menikah (sesuai dugaan).
5) Karyawan swasta tampaknya lebih banyak mengalami stroke daripada jenis pekerjaan lainnya (mungkin karena tekanan kerja). Orang wiraswasta memang menunjukkan tanda-tanda stroke (mungkin karena alasan seperti penyakit jantung, tekanan tinggi, dll).
6) Tidak ada perbedaan antara orang yang tinggal di daerah perkotaan dan pedesaan dalam hal kejadian stroke.
7) Orang yang sebelumnya merokok dan yang merokok (gabungan) menunjukkan tanda-tanda stroke jauh lebih banyak daripada orang yang tidak pernah merokok (mengingat ukuran sampel orang yang tidak pernah merokok dan orang yang dulu merokok dan merokok sekarang).

### Univariate Analysis - Numerical Feature
![numerical_feature](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/numerical_features.png?raw=true)
![heatmap_numerical_feature](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/heatmap_of_numerical_variables.png?raw=true)
![pairplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/pairplot.png?raw=true)

## Data Preparation
1. Melakukan Label Encoder: Melakukan proses encoding terhadap  `categorical_feature`. Hal ini dilakukan karena fitur-fitur kategorikal perlu dirubah agar dapat digunakan pada tahap  _modeling_.
2. Melakukan Splitting: membagi data menjadi  _training_  dan  _testing_  untuk  _modeling_. Dalam melakukan  _splitting_, digunakan rasio 80:20, yang berarti 80% data training, dan 20% data testing.
3.  Standarisasi: membantu membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. Dalam standarisasi, digunakan  _module_  `StandarScaler`  yang dapat ditemukan pada  _library_  `sklearn`.

## Modelling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Proses ini dilakukan dengan menggunakan tiga algoritma, yakni KNN, RandomForest, dan AdaBoost. Hasil akhirnya adalah untuk mencari algoritma yang memiliki performa paling baik dari ketiga algoritma yang digunakan. Dapat dilihat dari _bar chart_ yang menunjukkan tiga model algoritma yang digunakan. Diketahui bahwa algoritma KNN merupakan algoritma yang memiliki error yang paling kecil dibanding model lainnya.

![pairplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/evaluasi_model.png?raw=true)

Dari _plot_ yang disajikan di atas, dapat diketahui bahwa model Random Forest memberikan nilai error yang paling kecil. Sehingga, model Random Forest lah yang dipilih sebagai model terbaik untuk melakukan klasifikasi penyakit jantung.

## Evaluation
Evaluasi metrik yang digunakan untuk mengukur kinerja model adalah metrik mse (Mean Squared Error). Pemilihan matrik ini disebabkan karena kasus atau domain proyek yang dipilih adalah klasifikasi. Matrik MSE, pada dasarnya akan mengukur kuadrat rerata error dari prediksi yang dilakukan. MSE juga akan menghitung selisih kuadrat antara prediksi dan target, yang kemudian melakukan perhitungan rata-rata terhadap nilai-nilai tersebut.

Semakin tinggi nilai yang diperoleh MSE, semakin buruk juga modelnya. Nilai MSE tidak pernah negatif, tetapi akan menjadi NOL untuk model yang sempurna.

Rumus perhitungan matrik MSE: 
![alt](https://www.gstatic.com/education/formulas2/472522532/en/mean_squared_error.svg)

ket:

$\mathrm{MSE}$	=	mean squared error

${n}$	=	_number of data points_

$Y_{i}$	=	_observed values_ atau _ground truth_ dari nilai sebenarnya, dalam kasus ini nilai yang digunakan adalah nilai dari variabel `HeartDisease`

$\hat{Y}_{i}$	=	_predicted values_ atau _estimated target values_, dalam kasus ini nilai yang digunakan adalah nilai prediksi model terhadap variabel `HeartDisease`

Hasil dari _modeling_ dapat dilihat pada tabel di bawah ini. Tabel memberikan informasi detail terkait hasil _training_ dan _testing_

|		            | train	    |	test        |
|---------------|-----------|-------------|
|KNN		        | 0.041012  |	0.154174    |
|AdaBoost	      | 0.153882  |	0.173916    |
|RandomForest	  | 0.007169  |	0.088335    |

Hasil prediksi yang diberikan oleh model Random Forest adalah benar, dikarenakan mendekati nilai y_true.

|		 | y_true |	prediksi_KNN | prediksi_RandomForest | prediksi_Boosting |
|----|--------|--------------|-----------------------|-------------------|
|3936| 0      | 0.0          | 0.1                   | 0.1               |


Referensi:

[1] [Stroke Risk Prediction with Machine Learning Techniques](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9268898/)

[2]: [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)


