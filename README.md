# Stroke Prediction - Predictive Analysis🏥

## Domain Proyek
Domain yang dipilih untuk dilakukan prediksi adalah domain kesehatan, yang berfokus pada penyakit stroke.

Menurut *World Stroke Organization* (WSO), 13 juta orang terserang stroke setiap tahunnya, dan sekitar 5,5 juta orang akan meninggal dunia. Stroke merupakan penyebab utama kematian dan disabilitas di seluruh dunia, dan itulah sebabnya mengapa dampaknya sangat serius dalam semua aspek kesehatan. Stroke tidak hanya memengaruhi pasien, tetapi juga memengaruhi lingkungan sosial, keluarga, dan tempat kerja pasien. Selain itu, berlawanan dengan kepercayaan masyarakat, stroke dapat terjadi pada siapa saja, pada usia berapa pun, tanpa memandang jenis kelamin atau kondisi fisik[1].

Stroke didefinisikan sebagai gangguan neurologis akut pada pembuluh darah di otak yang terjadi ketika suplai darah ke suatu area otak terhenti dan sel-sel otak kekurangan oksigen. Stroke dibagi menjadi iskemik dan hemoragik. Stroke iskemik bisa ringan hingga sangat parah dengan kerusakan sementara hingga permanen. Perdarahan jarang terjadi dan melibatkan pecahnya pembuluh darah yang mengakibatkan pendarahan otak. Stroke Iskemik, yang merupakan stroke yang paling umum, melibatkan terhentinya aliran darah ke suatu area otak akibat penyempitan atau penyumbatan arteri[1].

Permasalahan stroke yang signifikan ini memiliki kaitan erat dengan _machine learning_, yang dapat digunakan untuk mendeteksi, mendiagnosis, dan memprediksi risiko stroke secara lebih akurat dan cepat. Dengan menggunakan dataset yang mencakup berbagai faktor risiko seperti usia, tekanan darah, riwayat medis, gaya hidup, dan hasil pemeriksaan klinis, algoritma _machine learning_ dapat dilatih untuk mengenali pola dan korelasi yang mungkin tidak terlihat oleh manusia[1].

Kontribusi dari penerapan _machine learning_ dalam dunia kesehatan khususnya stroke sangatlah besar. Dengan model prediksi yang akurat, tenaga medis dapat mengidentifikasi pasien berisiko tinggi lebih awal dan mengambil tindakan pencegahan yang tepat, seperti perubahan gaya hidup atau terapi medis. Hal ini dapat mengurangi jumlah kasus stroke, menurunkan angka kematian, dan mengurangi beban disabilitas yang seringkali menyertai pasien stroke. Selain itu, kemampuan prediksi yang ditingkatkan juga dapat membantu dalam merancang strategi kesehatan masyarakat yang lebih efektif, mengoptimalkan sumber daya kesehatan, dan memberikan perawatan yang lebih personal dan tepat sasaran[1].

## Business Understanding
Pada bagian _Business Understanding_ akan dijelaskan mengenai permasalahan yang akan diselesaikan (*problem statements*), tujuan (*goal*), dan solusi yang diajukan (*solution statements*).

### Problem Statements
Bagaimana mengetahui pasien memiliki penyakit stroke berdasarkan riwayat dari variabel-variabel kesehatan yang ada?

### Goals
Untuk menyelesaikan permasalahan yang telah disampaikan pada bagian *Problem Statement*, maka dibuat model yang digunakan untuk memprediksi apakah seseorang memiliki penyakit stroke berdasarkan riwayat kesehatannya.

### Solution statements
Solusi pembuatan model yang dilakukan adalah dengan menerapkan 3 algoritma _machine learning_, terbatas pada **_K-NN_**, **_Random Forest_**, dan **_AdaBoost_**. Diterapkannya 3 algoritma tersebut bertujuan untuk mengkomparasi dan mendapatkan model atau algoritma yang memiliki tingkat _error_ yang paling kecil, sehingga prediksi penyakit stroke memiliki akurasi yang tinggi.

-  **_K-NN_**: Algoritma _K-Nearest Neighbor_ (K-NN) adalah algoritma _machine learning_ yang sederhana dan mudah diterapkan, yang mana umumnya digunakan untuk menyelesaikan masalah klasifikasi dan regresi. Algoritma ini termasuk dalam _supervised learning_. Tujuan dari algortima K-NN adalah untuk mengidentifikasi _nearest neighbor_ dari titik yang diberikan, sehingga dapat menetapkan label prediksi ke titik tersebut.

-  **_Random Forest_**: _Random forest_ adalah kombinasi dari masing – masing _tree_ atau pohon, yang kemudian dikombinasikan ke dalam satu model. _Random Forest_ bergantung pada sebuah nilai vector acak dengan distribusi yang sama pada semua pohon yang masing masing _tree_ memiliki kedalaman yang maksimal.

-  **_AdaBoost_**: _AdaBoost_ atau _Adaptive Boost_ merupakan algoritma yang memanfaatkan _bagging_ dan _boosting_ untuk meningkatkan akurasi. Sama seperti algoritma _random forest_, algoritma _AdaBoost_ juga menggunakan beberapa _decision tree_ untuk melakukan prediksi.

## Data Understanding
Dataset yang digunakan pada proyek _machine learning_ ini merupakan **5110 data observasi** yang didapat dan diunduh dari situs [_kaggle_](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset) [2]. Terdapat 11 fitur yang dapat digunakan untuk memprediksi kemungkinan penyakit stroke.

**Variabel-variabel pada Stroke Prediction Dataset adalah sebaggai berikut:**

1. _id_: pengenal identitas

2. _gender_: Jenis Kelamin pasian
    - Pria "_Male_",
    - Wanita "_Female_",
    - Lainnya "_Other_"

3. _age_: usia pasien, dalam tahun (_years_)

4. _hypertension_: 0 jika pasien tidak memiliki hipertensi, 1 jika pasien memiliki hipertensi

5. _heart_disease_: 0 jika pasien tidak memiliki penyakit jantung, 1 jika pasien memiliki penyakit jantung

6. _ever_married_: Status Pernikahan,
    - Belum Menikah "_No_",
    - Sudah Menikah "_Yes_"

7. _work_type_: Jenis Pekerjaan
    - Masih anak kecil "_children_",
    - Pemerintahan "_Govt_jov_",
    - Tidak bekerja "_Never_worked_",
    - Swasta "_Private_",
    - Wiraswasta "_Self-employed_"

8. _Residence_type_: Jenis Tempat Tinggal
    - Perdesaan "_Rural_",
    - Perkotaan "_Urban_"

9. _avg_glucose_level_: kadar glukosa rata-rata dalam darah

10. _bmi_: indeks massa tubuh "_body max index_"

11. _smoking_status_: Status perokok
    - Sebelumnya perokok "_formerly smoked_",
    - Tidak pernah merokok "_never smoked_",
    - Perokok "_smokes_"
    - Tidak diketahui "_Unknown_"*

12. _stroke_: 1 jika pasien mengalami stroke atau 0 jika tidak

*Catatan: "_Unknown_" dalam _status_smoking_ berarti informasi tersebut tidak tersedia untuk pasien ini

## Explanatory Data Analysis
### Univariate Analysis - Categorical Feature

1. Riwayat Perokok dan Stroke

![riwayatperokok_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/riwayatperokok_stroke.jpg?raw=true)

Gambar 1. Riwayat Perokok dan Stroke

Pada Gambar 1, _plot_ diatas memberikan gambaran bahwa status merokok seseorang dapat berhubungan dengan kejadian stroke, namun jumlah kejadian stroke tertinggi justru ditemukan pada individu yang tidak pernah merokok. Hal ini mungkin disebabkan oleh faktor lain yang tidak terlihat dalam data, atau bisa juga menunjukkan bahwa ada variabel perancu (_confounding variables_) yang mempengaruhi hubungan antara merokok dan stroke.

2. Status Pernikahan dan Stroke

![statuspernikahan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/statuspernikahan_stroke.jpg?raw=true)

Gambar 2. Status Pernikahan dan Stroke

Pada Gambar 2, _plo_t diatas memberikan gambaran bahwa status status perkawinan seseorang dapat berhubungan dengan kejadian stroke, yang dimana seseorang yang sudah menikah cenderung memiliki penyakit stroke dibanding yang belum menikah.

3. Jenis Pekerjaan dan Stroke

![jenispekerjaan_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/jenispekerjaan_stroke.jpg?raw=true)

Gambar 3. Jenis Pekejaan dan Stroke

Pada Gambar 3, _plot_ diatas memberikan gambaran bahwa jenis pekerjaan seseorang dapat berhubungan dengan kejadian stroke. Jumlah kejadian stroke tertinggi ditemukan pada **individu yang bekerja di sektor swasta**, diikuti oleh mereka yang bekerja sendiri, dan kemudian mereka yang bekerja di sektor pemerintah. Jumlah kejadian stroke pada anak-anak sangat rendah, yang bisa diharapkan mengingat prevalensi stroke pada usia muda umumnya lebih rendah dibandingkan dengan orang dewasa.

4. Hipertensi dan Stroke
![hipertensi_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/hipertensi_stroke.jpg?raw=true)

Gambar 4. Hipertensi dan Stroke

Pada Gambar 4, _plot_ ini memberikan gambaran bahwa meskipun hipertensi dikenal sebagai faktor risiko utama untuk stroke, jumlah kejadian stroke lebih banyak ditemukan pada individu yang tidak memiliki hipertensi.

5. Penyakit Jantung dan Stroke
![penyakitjantung_stroke](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/penyakitjantung_stroke.jpg?raw=true)

Gambar 5. Penyakit Jantung dan Stroke

Pada Gambar 5, _plot_ ini menunjukkan bahwa lebih banyak kejadian stroke ditemukan pada individu yang tidak memiliki penyakit jantung dibandingkan dengan mereka yang memiliki penyakit jantung. Meskipun penyakit jantung adalah faktor risiko untuk stroke.

### Analysis of Categorical Variables
![analysis_of_categorical_variables](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/analysis_of_categorical_variables.jpg?raw=true)

Gambar 6. _Analysis of Categorical Variables_ 

Pada Gambar 6, didapatkan hasil pengamatan yaitu:
- Jumlah perempuan lebih banyak daripada laki-laki dalam penyakit stroke.
- Jumlah orang yang sudah menikah jauh lebih banyak menderika penyakit stroke daripada yang belum menikah (masuk akal karena distribusinya antara 0 dan 60)
- Jumlah yang bekerja di perusahaan swasta memiliki penyakit stroke terbanyak.
- Tidak ada perbedaan antara populasi di daerah perkotaan dan pedesaan.
- Jumlah orang yang tidak merokok memiliki penyakit stroke terbanyak.

### Univariate Analysis - Numerical Feature
![numerical_feature](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/numerical_features.jpg?raw=true)

Gambar 7. Histogram Fitur _Numerical_

Pada Gambar 7, plot diatas melihatkan histogram masing-masing fitur _numerical_ yaitu _age_, _avg_glucose_level_, dan _bmi_

![pairplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/pairplot.jpg?raw=true)

Gambar 8. Korelasi Fitur _Numerical_

Pada Gambar 8, _plot_ diatas melihatkan observasi korelasi antara fitur _numerical_ dengan fitur target

## Data Preparation
1. Seleksi Data: Menyeleksi data apakah data tersebut ada yang kosong atau tidak, jika ada data kosong maka akan diisi dengan mean menggunakan _`fillna()`_. Pada _`stroke_prediction`_ terdapat _data missing_ 201 pada _bmi_. Hal ini dibuktikan dari pengecekan menggunakan _`isnull().sum()`_.

![boxplot](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/boxplot.jpg?raw=true)

Gambar 9. _Boxplot_ Fitur _Numerical_

2. Menangani _Outlier_: melakukan pengecekan apakah _data stroke prediction_ memiliki _data outlier_. Apabila terdapat _data outlier_, maka akan dihapus. Untuk mengetahui _data outlier_ yang dimiliki oleh s_troke prediction dataset_, maka digunakanlah _boxplot_ yang memperlihatkan langsung keseluruhan dataset. Dapat dilihat bahwa terdapat beberapa _outlier_, khususnya pada fitur _BMI_ yang memiliki _outlier_ paling banyak. Dapat dilihat pada Gambar 9, bahwa _outlier_ ditemukan pada _`age`_, _`avg_glucose_level`_, dan _`bmi`_. Untuk mengetasi _outlier_ maka digunakan metode _IQR_. Hasil akhir data dari _outlier_ yang telah dihapuskan dapat dilihat dengan _shape_.
3. Melakukan _Label Encoder_: Melakukan proses _encoding_ terhadap  _`categorical_feature`_. Hal ini dilakukan karena fitur-fitur kategorikal perlu dirubah agar dapat digunakan pada tahap  _modeling_.
4. Melakukan_ Data Splitting_: membagi data menjadi  _training_  dan  _testing_  untuk  _modeling_. Dalam melakukan  _splitting_, digunakan rasio 80:20, yang berarti 80% _data training_, dan 20% _data testing_. Pembagian ini cukup ideal untuk dataset yang terbilang kecil.
5. Standarisasi: membantu membuat fitur data menjadi bentuk yang lebih mudah diolah oleh algoritma. Dalam standarisasi, digunakan  _module_  _`StandarScaler_`  yang dapat ditemukan pada  _library_  _`sklearn`_. Menggunakan _`StandarScaler`_ dibanding teknik/metode lainnya adalah untuk beberapa algoritma optimasi, data yang berskala standar bisa membantu dalam mencapai konvergensi lebih cepat dan stabil.

## Modelling
Tahapan ini membahas mengenai model _machine learning_ yang digunakan untuk menyelesaikan permasalahan. Proses ini dilakukan dengan menggunakan tiga algoritma, yakni _KNN_, _RandomForest_, dan _AdaBoost_. Hasil akhirnya adalah untuk mencari algoritma yang memiliki performa paling baik dari ketiga algoritma yang digunakan.

- Dalam membangun model _KNN_, digunakan _module KNeighborsRegressor_ dari _library sklearn_. Digunakan parameter _n_neighbors = 10_ untuk membangun model. Untuk melakukan _training_, maka digunakan _.fit(Xtrain, ytrain)_ untuk _fitting_. Kemudian, untuk melakukan melakukan prediksi, digunakan _.predict(Xtrain)_.
- Dalam membangun model _RandomForest_, digunakan _module RandomForestRegressor_ dari _library sklearn_. Digunakan _parameter n_estimators=100_, _max_depth=16, random_state=55_, _n_jobs=-1_ untuk membangun model. Untuk melakukan _training_, maka digunakan _.fit(Xtrain, ytrain)_ untuk _fitting_. Kemudian, untuk melakukan melakukan prediksi, digunakan _.predict(Xtrain)_.
- Dalam membangun model _AdaBoost_, digunakan _module AdaBoostRegressor_ dari _library sklearn_. Digunakan parameter _learning_rate=0.2_, _random_state=55_ untuk membangun model. Untuk melakukan _training_, maka digunakan _.fit(Xtrain, ytrain)_ untuk _fitting_. Kemudian, untuk melakukan melakukan prediksi, digunakan _.predict(Xtrain)_.

## Evaluation
Evaluasi metrik yang digunakan untuk mengukur kinerja model adalah metrik MSE (_Mean Squared Error_). Pemilihan matrik ini disebabkan karena kasus atau domain proyek yang dipilih adalah klasifikasi. Matrik MSE, pada dasarnya akan mengukur kuadrat rerata error dari prediksi yang dilakukan. MSE juga akan menghitung selisih kuadrat antara prediksi dan target, yang kemudian melakukan perhitungan rata-rata terhadap nilai-nilai tersebut.

Semakin tinggi nilai yang diperoleh MSE, semakin buruk juga modelnya. Nilai MSE tidak pernah negatif, tetapi akan menjadi NOL untuk model yang sempurna.

Rumus perhitungan matrik MSE: 

$$
\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$

ket:

$\mathrm{MSE}$	=	_mean squared error_

${n}$	=	_number of data points_

$Y_{i}$	=	_observed values_ atau _ground truth_ dari nilai sebenarnya, dalam kasus ini nilai yang digunakan adalah nilai dari variabel _`Stroke Prediction`_

$\hat{Y}_{i}$	=	_predicted values_ atau _estimated target values_, dalam kasus ini nilai yang digunakan adalah nilai prediksi model terhadap variabel _`Stroke Prediction`_


![evaluasi_model](https://github.com/muhammadsahrul59/stroke-analysis/blob/main/images/evaluasi_model.jpg?raw=true)

Gambar 10. Evaluasi Model

Pada Gambar 10, _plot_ yang disajikan di atas, dapat diketahui bahwa model _AdaBoost_ memberikan nilai error yang paling kecil. Sehingga, model _AdaBoost_ lah yang dipilih sebagai model terbaik untuk melakukan klasifikasi penyakit stroke.

Tabel 1. Hasil Evaluasi Model
|                 | train	  |	test        |
|-----------------|-----------|-------------|
|KNN		      | 0.000039  |	0.000048    |
|AdaBoost	      | 0.000007  |	0.000046    |
|RandomForest	  | 0.000056  |	0.000063    |

Hasil dari _modeling_ dapat dilihat pada Tabel 1. Tabel diatas memberikan informasi detail terkait hasil _training_ dan _testing_

Tabel 2. Hasil Prediksi

|    | y_true |	prediksi_KNN | prediksi_AdaBoost     | prediksi_RandomForest |
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

Pada Tabel 2, disajikan informasi hasil prediksi dari model yang digunakan. Dari tabel yang disajikan dapat dilihat bahwa prediksi menggunakan _AdaBoost_, memiliki hasil paling sesuai dengan data aslinya _`y_true`_, dibandingkan kedua model lainnya. Hasil prediksi yang diberikan oleh model _AdaBoost_ adalah benar, dibandingkan dengan prediksi _KNN_ dan _RandomForest_. Maka dapat diketahui bahwa model _AdaBoost_ memberikan nilai error yang paling kecil. Sehingga, model _AdaBoost_ lah yang dipilih sebagai model terbaik untuk melakukan klasifikasi penyakit stroke. Dan melihat dari keberhasilan prediksi menggunakan _AdaBoost_ maka proyek ini mampu dan berhasil menyelesaikan _Goals_ yang diinginkan.

Referensi:

[1] E. Dritsas and M. Trigka, “Stroke risk prediction with machine learning techniques,” Sensors, vol. 22, no. 13, p. 4670, Jun. 2022. doi:10.3390/s22134670

[2] Fedesoriano, “Stroke prediction dataset,” Kaggle, https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset. 
