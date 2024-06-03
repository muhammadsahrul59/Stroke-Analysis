# Stroke Prediction - Predictive Analysis🏥

## Domain Proyek
Domain yang dipilih untuk dilakukan prediksi adalah domain kesehatan, yang berfokus pada penyakit stroke.

Menurut *World Stroke Organization* (WSO), 13 juta orang terserang stroke setiap tahunnya, dan sekitar 5,5 juta orang akan meninggal dunia. Stroke merupakan penyebab utama kematian dan disabilitas di seluruh dunia, dan itulah sebabnya mengapa dampaknya sangat serius dalam semua aspek kesehatan. Stroke tidak hanya memengaruhi pasien, tetapi juga memengaruhi lingkungan sosial, keluarga, dan tempat kerja pasien. Selain itu, berlawanan dengan kepercayaan masyarakat, stroke dapat terjadi pada siapa saja, pada usia berapa pun, tanpa memandang jenis kelamin atau kondisi fisik[1].

Stroke didefinisikan sebagai gangguan neurologis akut pada pembuluh darah di otak yang terjadi ketika suplai darah ke suatu area otak terhenti dan sel-sel otak kekurangan oksigen. Stroke dibagi menjadi iskemik dan hemoragik. Stroke iskemik bisa ringan hingga sangat parah dengan kerusakan sementara hingga permanen. Perdarahan jarang terjadi dan melibatkan pecahnya pembuluh darah yang mengakibatkan pendarahan otak. Stroke Iskemik, yang merupakan stroke yang paling umum, melibatkan terhentinya aliran darah ke suatu area otak akibat penyempitan atau penyumbatan arteri[1].

Permasalahan stroke yang signifikan ini memiliki kaitan erat dengan machine learning, yang dapat digunakan untuk mendeteksi, mendiagnosis, dan memprediksi risiko stroke secara lebih akurat dan cepat. Dengan menggunakan dataset yang mencakup berbagai faktor risiko seperti usia, tekanan darah, riwayat medis, gaya hidup, dan hasil pemeriksaan klinis, algoritma machine learning dapat dilatih untuk mengenali pola dan korelasi yang mungkin tidak terlihat oleh manusia[1].

Kontribusi dari penerapan machine learning dalam dunia kesehatan khususnya stroke sangatlah besar. Dengan model prediksi yang akurat, tenaga medis dapat mengidentifikasi pasien berisiko tinggi lebih awal dan mengambil tindakan pencegahan yang tepat, seperti perubahan gaya hidup atau terapi medis. Hal ini dapat mengurangi jumlah kasus stroke, menurunkan angka kematian, dan mengurangi beban disabilitas yang seringkali menyertai pasien stroke. Selain itu, kemampuan prediksi yang ditingkatkan juga dapat membantu dalam merancang strategi kesehatan masyarakat yang lebih efektif, mengoptimalkan sumber daya kesehatan, dan memberikan perawatan yang lebih personal dan tepat sasaran[1].

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
Dataset yang digunakan pada proyek machine learning ini merupakan **5110 data observasi** yang didapat dan didownload dari situs [kaggle](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) [2]. Terdapat 11 fitur yang dapat digunakan untuk memprediksi kemungkinan penyakit stroke.

**Variabel-variabel pada Stroke Prediction Dataset adalah sebaggai berikut:**

1. id: pengenal identitas

2. gender: Jenis Kelamin pasian
    - Pria "Male",
    - Wanita "Female",
    - Lainnya "Other"

3. age: usia pasien, dalam tahun (years)

4. hypertension: 0 jika pasien tidak memiliki hipertensi, 1 jika pasien memiliki hipertensi

5. heart_disease: 0 jika pasien tidak memiliki penyakit jantung, 1 jika pasien memiliki penyakit jantung

6. ever_married: Status Pernikahan,
    - Belum Menikah "No",
    - Sudah Menikah "Yes"

7. work_type: Jenis Pekerjaan
    - Masih anak kecil "children",
    - Pemerintahan "Govt_jov",
    - Tidak bekerja "Never_worked",
    - Swasta "Private",
    - Wiraswasta "Self-employed"

8. Residence_type: Jenis Tempat Tinggal
    - Perdesaan "Rural",
    - Perkotaan"Urban"

9. avg_glucose_level: kadar glukosa rata-rata dalam darah

10. bmi: indeks massa tubuh "body max index"

11. smoking_status: Status perokok
    - Sebelumnya perokok "formerly smoked",
    - Tidak pernah merokok "never smoked",
    - Perokok "smokes"
    - Tidak diketahui "Unknown"*

12. stroke: 1 jika pasien mengalami stroke atau 0 jika tidak

*Note: "Unknown" dalam status_smoking berarti informasi tersebut tidak tersedia untuk pasien ini

## Explanatory Data Analysis
### Univariate Analysis - Categorical Feature

1. Riwayat Perokok dan Stroke

![riwayatperokok_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/riwayatperokok_stroke.jpg?raw=true)

Gambar 1. Riwayat Perokok dan Stroke

Pada Gambar 1, plot diatas memberikan gambaran bahwa status merokok seseorang dapat berhubungan dengan kejadian stroke, namun jumlah kejadian stroke tertinggi justru ditemukan pada individu yang tidak pernah merokok. Hal ini mungkin disebabkan oleh faktor lain yang tidak terlihat dalam data, atau bisa juga menunjukkan bahwa ada variabel perancu (confounding variables) yang mempengaruhi hubungan antara merokok dan stroke.

2. Status Pernikahan dan Stroke

![statuspernikahan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/statuspernikahan_stroke.jpg?raw=true)

Gambar 2. Status Pernikahan dan Stroke

Pada Gambar 2, plot diatas memberikan gambaran bahwa status status perkawinan seseorang dapat berhubungan dengan kejadian stroke, yang dimana seseorang yang sudah menikah cenderung memiliki penyakit stroke dibanding yang belum menikah.

3. Jenis Pekerjaan dan Stroke

![jenispekerjaan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/jenispekerjaan_stroke.jpg?raw=true)

Gambar 3. Jenis Pekejaan dan Stroke

Pada Gambar 3, plot diatas memberikan gambaran bahwa jenis pekerjaan seseorang dapat berhubungan dengan kejadian stroke. Jumlah kejadian stroke tertinggi ditemukan pada **individu yang bekerja di sektor swasta**, diikuti oleh mereka yang bekerja sendiri, dan kemudian mereka yang bekerja di sektor pemerintah. Jumlah kejadian stroke pada anak-anak sangat rendah, yang bisa diharapkan mengingat prevalensi stroke pada usia muda umumnya lebih rendah dibandingkan dengan orang dewasa.

4. Hipertensi dan Stroke
![jenispekerjaan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/hipertensi_stroke.jpg?raw=true)

Gambar 4. Hipertensi dan Stroke

Pada Gambar 4, plot ini memberikan gambaran bahwa meskipun hipertensi dikenal sebagai faktor risiko utama untuk stroke, jumlah kejadian stroke lebih banyak ditemukan pada individu yang tidak memiliki hipertensi.

### Analysis of Categorical Variables
![analysis_of_categorical_variables](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/analysis_of_categorical_variables.png?raw=true)

Gambar 5. Analysis of Categorical Variables 

Pada Gambar 5, mendapatkan hasil pengamatan yaitu:
- Jumlah perempuan lebih banyak daripada laki-laki dalam penyakit stroke.
- Jumlah orang yang sudah menikah jauh lebih banyak menderika penyakit stroke daripada yang belum menikah (masuk akal karena distribusinya antara 0 dan 60)
- Jumlah yang bekerja di perusahaan swasta memiliki penyakit stroke terbanyak.
- Tidak ada perbedaan antara populasi di daerah perkotaan dan pedesaan.
- Jumlah orang yang tidak merokok memiliki penyakit stroke terbanyak.

### Analysing Categorical Variables with Stroke
![analysing_categorical_variables_with_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/analysis_categorical_with_stroke.png?raw=true)

Gambar 6. Analysing Categorical Variables with Stroke

Pada Gambar 6, mendapatkan hasil pengamatan yaitu:
- Jumlah pria dan wanita yang mengalami stroke sama jumlahnya.
- Jumlah orang yang tidak memiliki hipertensi juga menunjukkan tanda-tanda tidak ada stroke. Dan orang yang memiliki hipertensi juga tidak menunjukkan tanda-tanda lebih banyak orang yang terkena stroke.
- Orang dengan penyakit jantung juga menunjukkan tanda-tanda stroke (seperti yang diharapkan).
- Orang yang menikah menunjukkan tanda-tanda stroke lebih banyak daripada orang yang belum menikah (sesuai dugaan).
- Karyawan swasta tampaknya lebih banyak mengalami stroke daripada jenis pekerjaan lainnya (mungkin karena tekanan kerja). Orang wiraswasta memang menunjukkan tanda-tanda stroke (mungkin karena alasan seperti penyakit jantung, tekanan tinggi, dll).
- Tidak ada perbedaan antara orang yang tinggal di daerah perkotaan dan pedesaan dalam hal kejadian stroke.
- Orang yang sebelumnya merokok dan yang merokok (gabungan) menunjukkan tanda-tanda stroke jauh lebih banyak daripada orang yang tidak pernah merokok (mengingat ukuran sampel orang yang tidak pernah merokok dan orang yang dulu merokok dan merokok sekarang).

### Univariate Analysis - Numerical Feature
![numerical_feature](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/numerical_features.png?raw=true)

Gambar 7. Histogram Fitur Numerical

Pada Gambar 7, plot diatas melihatkan histogram masing-masing fitur _numerical_ yaitu age, avg_glucose_level, dan bmi

![pairplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/pairplot.png?raw=true)

Gambar 8. Korelasi Fitur Numerical

Pada Gambar 8, plot diatas melihatkan observasi korelasi antara fitur numerical dengan fitur target

## Data Preparation
1. Seleksi Data: Menyeleksi data apakah data tersebut ada yang kosong atau tidak, jika ada data kosong maka akan diisi dengan mean menggunakan `fillna()`. Pada `stroke_prediction` terdapat data missing 201 pada bmi. Hal ini dibuktikan dari pengecekan menggunakan `isnull().sum()`.

![pairplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/boxplot.jpg?raw=true)

Gambar 9. Boxplot Fitur Numerical

2. Menangani Outlier: melakukan pengecekan apakah data stroke prediction memiliki data outlier. Apabila terdapat data outlier, maka akan dihapus. Untuk mengetahui data outlier yang dimiliki oleh stroke prediction dataset, maka digunakanlah boxplot yang memperlihatkan langsung keseluruhan dataset. Dapat dilihat bahwa terdapat beberapa outlier, khususnya pada fitur BMI yang memiliki outlier paling banyak. Dapat dilihat pada Gambar 9, bahwa outlier ditemukan pada `age`, `avg_glucose_level`, dan `bmi`. Untuk mengetasi outlier maka digunakan metode IQR. Hasil akhir data dari outlier yang telah dihapuskan dapat dilihat dengan shape.
3. Melakukan Label Encoder: Melakukan proses encoding terhadap  `categorical_feature`. Hal ini dilakukan karena fitur-fitur kategorikal perlu dirubah agar dapat digunakan pada tahap  _modeling_.
4. Melakukan Splitting: membagi data menjadi  _training_  dan  _testing_  untuk  _modeling_. Dalam melakukan  _splitting_, digunakan rasio 80:20, yang berarti 80% data training, dan 20% data testing.
5. Standarisasi: membantu membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. Dalam standarisasi, digunakan  _module_  `StandarScaler`  yang dapat ditemukan pada  _library_  `sklearn`. Menggunakan `StandarScaler` dibanding teknik/metode lainnya adalah untuk beberapa algoritma optimasi, data yang berskala standar bisa membantu dalam mencapai konvergensi lebih cepat dan stabil.

## Modelling
Tahapan ini membahas mengenai model machine learning yang digunakan untuk menyelesaikan permasalahan. Proses ini dilakukan dengan menggunakan tiga algoritma, yakni KNN, RandomForest, dan AdaBoost. Hasil akhirnya adalah untuk mencari algoritma yang memiliki performa paling baik dari ketiga algoritma yang digunakan. Dapat dilihat dari _bar chart_ yang menunjukkan tiga model algoritma yang digunakan. Diketahui bahwa algoritma KNN merupakan algoritma yang memiliki error yang paling kecil dibanding model lainnya.

![evaluasi_model](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/evaluasi_model.jpg?raw=true)

Gambar 10. Evaluasi Model

Pada Gambar 10, _plot_ yang disajikan di atas, dapat diketahui bahwa model Random Forest memberikan nilai error yang paling kecil. Sehingga, model Random Forest lah yang dipilih sebagai model terbaik untuk melakukan klasifikasi penyakit jantung.

- Dalam membangun model KNN, digunakan module KNeighborsRegressor dari library sklearn. Digunakan parameter n_neighbors = 10 untuk membangun model. Untuk melakukan training, maka digunakan .fit(Xtrain, ytrain) untuk fitting. Kemudian, untuk melakukan melakukan prediksi, digunakan .predict(Xtrain).
- Dalam membangun model RandomForest, digunakan module RandomForestRegressor dari library sklearn. Digunakan parameter n_estimators=100, max_depth=16, random_state=55, n_jobs=-1 untuk membangun model. Untuk melakukan training, maka digunakan .fit(Xtrain, ytrain) untuk fitting. Kemudian, untuk melakukan melakukan prediksi, digunakan .predict(Xtrain).
- Dalam membangun model AdaBoost, digunakan module AdaBoostRegressor dari library sklearn. Digunakan parameter learning_rate=0.2, random_state=55 untuk membangun model. Untuk melakukan training, maka digunakan .fit(Xtrain, ytrain) untuk fitting. Kemudian, untuk melakukan melakukan prediksi, digunakan .predict(Xtrain).

## Evaluation
Evaluasi metrik yang digunakan untuk mengukur kinerja model adalah metrik mse (Mean Squared Error). Pemilihan matrik ini disebabkan karena kasus atau domain proyek yang dipilih adalah klasifikasi. Matrik MSE, pada dasarnya akan mengukur kuadrat rerata error dari prediksi yang dilakukan. MSE juga akan menghitung selisih kuadrat antara prediksi dan target, yang kemudian melakukan perhitungan rata-rata terhadap nilai-nilai tersebut.

Semakin tinggi nilai yang diperoleh MSE, semakin buruk juga modelnya. Nilai MSE tidak pernah negatif, tetapi akan menjadi NOL untuk model yang sempurna.

Rumus perhitungan matrik MSE: 
![alt](https://www.gstatic.com/education/formulas2/472522532/en/mean_squared_error.svg)

ket:

$\mathrm{MSE}$	=	mean squared error

${n}$	=	_number of data points_

$Y_{i}$	=	_observed values_ atau _ground truth_ dari nilai sebenarnya, dalam kasus ini nilai yang digunakan adalah nilai dari variabel `Stroke Prediction`

$\hat{Y}_{i}$	=	_predicted values_ atau _estimated target values_, dalam kasus ini nilai yang digunakan adalah nilai prediksi model terhadap variabel `Stroke Prediction`

Tabel 1. Hasil Evaluasi Model
|		            | train	    |	test        |
|---------------|-----------|-------------|
|KNN		        | 0.000039	|	0.000048    |
|AdaBoost	      | 0.000007  |	0.000046    |
|RandomForest	  | 0.000056  |	0.000063    |

Hasil dari _modeling_ dapat dilihat pada Tabel 1. Tabel diatas memberikan informasi detail terkait hasil _training_ dan _testing_

Tabel 2. Hasil Prediksi

|		 | y_true |	prediksi_KNN | prediksi_AdaBoost     | prediksi_RandomForest |
|----|--------|--------------|-----------------------|-----------------------|
|32  | 1      | 0.2          | 0.2                   | 0.4                   |
|4187| 0      | 0.0          | 0.0                   | 0.1                   |
|1812| 0      | 0.0          | 0.0                   | 0.0                   |
|4315| 0      | 0.0          | 0.0                   | 0.0                   |
|2478| 0      | 0.0          | 0.0                   | 0.0                   |
|4568| 0      | 0.0          | 0.0                   | 0.0                   |
|2234| 0      | 0.0          | 0.0                   | 0.0                   |
|4472| 0      | 0.0          | 0.0                   | 0.0                   |
|38  | 1      | 0.0          | 0.0                   | 0.2                   |
|1199| 0      | 0.1          | 0.0                   | 0.2                   |

Pada Tabel 2, disajikan informasi hasil prediksi dari model yang digunakan. Dari tabel yang disajikan dapat dilihat bahwa prediksi menggunakan AdaBoost, memiliki hasil paling sesuai dengan data aslinya `y_true`, dibandingkan kedua model lainnya. Hasil prediksi yang diberikan oleh model AdaBoost adalah benar, dibandingkan dengan prediksi KNN dan RandomForest. Maka dapat diketahui bahwa model AdaBoost memberikan nilai error yang paling kecil. Sehingga, model AdaBoost lah yang dipilih sebagai model terbaik untuk melakukan klasifikasi penyakit jantung.

Referensi:

[1] [Stroke Risk Prediction with Machine Learning Techniques](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9268898/)

[2]: [Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)


