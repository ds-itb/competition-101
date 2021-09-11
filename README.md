# Data Science Competition 101
Artikel ini bakal ngebahas tentang gambaran besar lomba data science pada umumnya. Keep in mind kalau mayoritas hal yang dibahas di sini akan diutamakan dan ditujukan untuk perlombaan ds, jadi mungkin bukan best practice untuk hal-hal seperti pekerjaan di dunia nyata hehe.

# Introduction
## Lomba DS itu ngapain?
Biasanya kalian bakal dikasih sebuah dataset dalam bentuk file `.csv` dan data tersebut punya banyak kolom atau istilah kerennya feature (fitur). Feature yang ada akan kalian gunakan untuk memprediksi sebuah target feature. Contohnya:  

> Dataset Penyakit Jantung  
> 
> Kolom / Feature: umur, gender, kadar_gula_darah, tekanan_darah  
> Target Feature: penyakit_jantung (bernilai 0 jika tidak punya penyakit jantung, dan 1 jika punya penyakit jantung)  

Kalian bisa melatih sebuah model machine learning yang bakal dipakai untuk memprediksi si target feature tersebut. Jadi dari contoh di atas, bisa dibuat soal seperti:  

>  Buatlah sebuah model machine learning yang dapat memprediksi apakah seseorang menderita penyakit jantung dengan data pribadi seperti umur, gender, kadar gula darah, dan tekanan darah  

Penilaiannya gimana? Kalian bakal dinilai dari nilai akurasi kalian (sesuai jenis soal yang didapat). Tiap jenis soal bakal beda-beda metrik penilaiannya. Contohnya untuk soal klasifikasi, skor kalian bakal berada di angka 0-1. Skor ini menunjukkan berapa persen label yang kalian prediksi dengan benar, misalnya 0.758 berarti kalian memprediksi 75,8% data dengan benar. Untuk soal regresi, metrik yang digunakan misalnya seperti MSE, RMSE (hal berbau garis-garis matematika).

Selain dari skor prediksi, kalian bakal dinilai biasanya dari laporan (untuk penyisihan) dan presentasi (untuk final), dan ini yang rada bikin mager wkwk. Skor prediksi bobotnya umumnya 60% dan yang lain 40%.

**TLDR**; Prediksi sesuatu hal dari data yang sudah ada seakurat mungkin

## Jenis soal

![](https://www.enjoyalgorithms.com/static/classification-vs-regression-in-machine-learning-cover-5b46145641e023c293296d48f052e012.png) 
Di lomba DS biasanya paling sering muncul 2 tipe soal berikut:
- Klasifikasi  
Target yang harus kalian prediksi berupa kategori / label / nilai diskrit. Contohnya jenis kelamin, credit card fraud, apakah seseorang tertarik untuk membeli sebuah barang (Yes/No Question). Di lomba ds, umumnya klasifikasi yang dipakai antara 2 jenis ini, binary classification (hanya memprediksi 2 jenis kategori contohnya prediksi apakah sebuah email adalah spam atau bukan) dan multi-class classification (ada >2 kategori contohnya prediksi jenis hewan apakah kucing, anjing, burung, atau ikan). Untuk tipe-tipe klasifikasi yang lain, bisa kalian baca di [sini](https://machinelearningmastery.com/types-of-classification-in-machine-learning/).
- Regresi  
Target yang harus kalian prediksi biasanya berupa nilai kontinu. Contohnya harga rumah, tinggi badan.

Secara tipe soal, klasifikasi lebih sering dilombakan dibandingkan dengan regresi. Untuk soal-soal kyk image recognition, NLP, dan lain-lain jarang ditemukan kecuali di lomba skala gede.

**TLDR**; Prediksi data kategorikal atau angka kontinu

## Kelengkapan data
Biasanya panitia akan memberikan 3 file yaitu:
- `train.csv`: berisi data latih yang udah diketahui target fiturnya sehingga bisa kalian pakai untuk melatih dan memvalidasi model.
- `test.csv` : berisi data uji yang belum diketahui target fiturnya sehingga kalian harus memprediksinya dengan model yang udah dilatih dengan data train tadi. Data test inilah yang bakal dipakai untuk menilai akurasi jawaban kalian.
- `sample_submission.csv` : format jawaban yang dikumpulkan, biasanya ada 2 kolom yaitu id dan hasil prediksi.

## Platform lomba
Hampir semua lomba diadakan di Kaggle (https://www.kaggle.com/). Kalian akan diminta untuk submit hasil prediksi yang telah kalian produksi dengan model kalian. Submisi bisa dilakukan tergantung jumlah yang diset panitia, biasanya per hari. Dari sekian banyak submisi, biasanya untuk submisi final kalian akan disuruh pilih 2 aja (ini bakal jadi nilai akhir). Hasil kalian bakal dibandingin dengan jawaban asli dari panitia lomba. Semakin akurat prediksi kalian maka semakin bagus.  

![](https://lh3.googleusercontent.com/4IWRQx5munaM7OjDxHecuxHxjaL8YJz_2v3nGw_PX1h-vrhvC0f_cmlQI0hOuQ2rBQWlwVYR-SJd6PAcepi4lgzIN1mgaLS5QhqqUKnsix8vmCRvi6ZOILgd0haPbYhlXgLerNKl)

Di Kaggle sendiri ada istilah LB atau leaderboard. Leaderboard tipenya ada 2, [public dan private](https://www.quora.com/What-is-the-difference-between-public-and-private-leaderboard-in-Kaggle). Selama lomba berlangsung, kalian bisa ngeliat skor, tapi skornya adalah skor sementara dan ngeliatnya di public leaderboard. Skor akhir bakal ditampilin setelah lomba selesai di private LB. Hal ini karena biasanya panitia ngesplit jumlah data yang dipakai untuk melihat skor kalian. Contohnya kyk gini:
> Total data: 1000 data  
> Public leaderboard 30%, Private Leaderboard 70%  
> Artinya skor di public leaderboard akan dinilai hanya dengan 300 data yang ada (dipilih secara acak). Skor "asli" atau final kalian akan bisa dilihat setelah lomba berakhir di private leaderboard. Private leaderboard akan menampilkan penilaian dengan seluruh  data yang ada yaitu 1000 data.  

Kasus konkritnya misalnya:
> Prediksi kalian: 1,0,1,0,1,0,0,0,1,1  
> Jawaban panitia: 1,0,1,1,1,1,1,1,0,0  
> 
> Public Leaderboard 30% dan Private Leaderboard 70% data  
> 
> Di public LB untuk menghitung skor akan digunakan 3 data pertama kalian yaitu 1,0,1 dan 3 data pertama panitia yaitu 1,0,1.  
> Skor yang kalian dapat adalah 1 (100%)  
> Tapi pas private LB dibuka, skor kalian turun menjadi 0.4 karena ternyata dari seluruh total data, kalian cuma bisa memprediksi 40% dengan benar.  

**TLDR**; Di Kaggle, kalian submit prediksi dalam bentuk .csv dan dinilai dari seberapa akurat prediksi kalian dibanding jawaban panitia.

## Tools yang diperlukan
![](https://i.imgur.com/ag4fraf.png)

Di DS, work environment yang bakal kalian pake buat ngoding dan ngerjain soal disebut dengan notebook (notebook ini sama kyk yang kalian pakai di pengkom seperti Jupyter Notebook .ipynb). Untuk nge-run notebook, sebenernya bisa di komputer / laptop local kalian masing-masing, tapi biasanya buat ngedapetin computing power yang lebih gede dengan gratis, kalian bisa pakai notebook online seperti [Kaggle Notebook](https://www.kaggle.com/code) dan [Google Colab](https://colab.research.google.com/). Dari segi tools yang digunakan akan tergantung dengan jenis permasalahan atau soal yang kalian dapatkan.  
Hampir selalu dipakai di lomba-lomba tingkat mahasiswa:
- Python
- Pandas (Manipulasi data)
- Matplotlib dan Seaborn (Visualisasi data)
- Sklearn (Machine learning)

Biasanya dipakai di lomba besar dengan topik-topik yang lebih advanced:
- Tensorflow dan Keras (Deep learning)
- Tableau (Visualisasi dan analisis data)

# Workflow
## Cara legal
Pada umumnya, kalian bakal ngelakuin 5 proses utama di lomba yang berbau data science:
1. Exploratory Data Analysis (EDA)
2. Data Preprocessing
3. Feature Engineering
4. Modeling
5. Validation

Disclaimer: Workflow bisa berbeda-beda tergantung sumber  

### Exploratory Data Analysis
Di proses ini, kalian bakal ngelakuin eksplorasi pada dataset yang diberikan misalnya dengan:
- Visualisasi data
- Cek outlier (data pencilan)
- Cek missing value (baris / kolom data yang datanya gaada)
- Cek korelasi antar fitur

Beberapa plot yang umumnya digunakan untuk visualisasi data:  
- Box plot: outlier
- Hist plot: distribusi jumlah data untuk sebuah fitur numerikal
- Count plot: distribusi jumlah data untuk sebuah fitur kategorikal
- KDE plot: perbandingan distribusi antar fitur
- Correlation matrix: matriks korelasi antar setiap fitur yang ada di dataset

Note: Ada beberapa sumber juga yang menyatakan kalau EDA ini bakal dilakuin setelah data preprocessing.

Tools yang biasanya digunakan adalah Pandas untuk manipulasi data dan Matplotlib / Seaborn untuk visualisasi data.

### Data Preprocessing
Setelah kalian tau dan mengenal data yang diberikan seperti apa, sekarang kalian bakal memproses data agar bisa digunakan untuk melatih model nantinya. Pemrosesan ini bakal tergantung dari hasil EDA yang kalian dapatkan, misalnya:
- Menghilangkan baris yang memiliki missing value
- Melakukan normalisasi data
- Menghapus sebuah kolom / fitur yang missing valuenya kebanyakan
- Encoding data. Misalnya ada data gender yang punya value 'Pria' dan 'Wanita', beberapa model machine learning gabisa nerima input string. Oleh karena itu value yang ada harus dikodekan. Misalnya 0 untuk 'Pria' dan 1 untuk 'Wanita'. Tools yang biasanya digunakan adalah Pandas 

### Feature Engineering
Dengan data yang udah kalian bersihkan dan proses sebelumnya, di tahap ini kalian akan mencoba ngide untuk menghasilkan kolom / fitur baru dari kolom-kolom yang sudah ada. Fitur baru ini nantinya diharapkan bisa digunakan untuk menambah akurasi model kalian. Contohnya:
- Kalian punya fitur tinggi dan berat badan. Dari sini kalian bisa membuat fitur baru yaitu Body Mass Index (BMI) dengan melakukan kalkulasi pada tinggi dan berat badan tersebut.
- Kalian punya fitur nama orang, asumsikan nama orang diakhiri oleh nama keluarga / marga. Dari nama orang tersebut, kalian bisa mengekstraksi nama belakangnya untuk mendapatkan nama keluarga. Dari sini, kalian bisa tau mana orang-orang yang sekeluarga di dataset kalian. 

Tools yang biasanya digunakan adalah Pandas 

### Modeling
Ini adalah tahap yang kedengerannya paling keren karena kalian bakal melatih model machine learning dari data yang sudah kalian olah sedemikian rupa untuk melakukan prediksi fitur target. Model machine learning ini jenisnya ada banyak dan semuanya digunakan tergantung kasus atau soal yang kalian dapat. Contohnya decision tree biasa digunakan untuk klasifikasi, logistic regression digunakan untuk persoalan regresi.  

![](https://i.stack.imgur.com/3tHZF.png)

Sebelum kalian melatih model, data yang udah ada biasanya bakal dibagi ke dalam data train (80% total data) dan validation (20% total data) atau ada jg yang nyebut data train dan test. Data train akan dipakai untuk melatih model kalian, dan data validation akan digunakan untuk memvalidasi model kalian. Kenapa model harus divalidasi? Biar ga terjadi [overfitting / underfitting](https://towardsdatascience.com/what-are-overfitting-and-underfitting-in-machine-learning-a96b30864690) (Bisa coba dibaca tentang ini hehe). Dari data train dan test tersebut, masing-masing bakal dipisah lagi jadi X dan y. Seperti di matematika, X itu dipakai untuk memprediksi y. Penjelasannya:
- `X_train` = berisi fitur-fitur yang digunakan untuk melatih model
- `y_train` = berisi fitur target untuk melatih model
- `X_test` = berisi fitur-fitur yang digunakan untuk melakukan validasi
- `y_test` = berisi fitur target untuk memvalidasi model

Sebenarnya agak susah untuk dideskripsikan dengan kata-kata. Biar lebih jelas, flownya bakal seperti ini:  
1. `X_train` dan `y_train` dipakai untuk melatih model. Model akan belajar untuk memprediksi target di `y_train` dari fitur-fitur yang ada di `X_train`.
2. Model selesai belajar dan dapat dipakai untuk memprediksi
3. Model digunakan untuk memprediksi `X_test` dan hasil prediksinya akan dibandingkan dengan `y_test` untuk mendapatkan hasil akurasi (Validasi)

Dari segi kode, basic modeling itu ga ribet. Intinya:
```
# Ini pseudocode ngasal ya wkwk
import model
model.fit(X_train, y_train) 		# Ngelatih model
y_pred = model.predict(X_test) 		# Validasi
```
Setelah kalian ngelatih model, kalian bisa membuat prediksi dari data test yang diberikan oleh panitia (biasanya namanya `test.csv`) dan hasil prediksinya bisa kalian kumpulkan.

Tools yang biasanya digunakan adalah Scikit-Learn (sklearn). Fungsi yang penting seperti train_test_split (pemisahan dataset) dan model-model sklearn yang bisa kalian eksplor.
 
### Validation
Validasi penting untuk mencegah overfitting atau underfitting. Intinya kedua hal tersebut bakal mengakibatkan kasus seperti: Skor public LB kalian 0.9829 dan kalian di peringkat 1 tapi setelah private LB dibuka, skor kalian jadi 0.5123 dan peringkat kalian turun.

![](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190523171258/overfitting_2.png)

Proses validasi ini digunakan untuk meraba-raba skor kalian di leaderboard, dengan harapan biar pas private LB dibuka, nilai kalian gabakal beda jauh dengan yang di public LB. Jenis validasi ada banyak, tapi yang biasa digunakan namanya adalah K-Fold Cross Validation.

Tools yang biasanya digunakan adalah Pandas dan Scikit-Learn (sklearn). Fungsi yang penting seperti metrik-metrik validasi kyk accuracy_score, f1_score, classification_report, confusion_matrix, roc dan auc, dll.

### TLDR
Eksplorasi dan visualisasi data -> Bersihin dan encoding data -> Buat fitur baru -> Latih model -> Validasi akurasi model

## Cara ilegal

Cara ini adalah cara tidak sehat yang bisa dipakai untuk mendapatkan skor tinggi dengan low effort terutama untuk awal-awal lomba. Cara ini bakal ngeskip proses EDA dan feature engineering. Soalnya EDA dan feature engineering memakan waktu yang lama banget dan ujung-ujungnya gapengaruh banyak sama skor, bahkan ada beberapa kasus dimana skor akurasi kalian turun (tapi gasemua yaa). Tapi tentunya kalo kalian jago dengan feature engineering dan manipulasi data, bisa jadi nilai plus banget. Nah, jadi langkah yang perlu kalian lakukan tinggal:
1. Data Preprocessing
2. Modeling
3. Validation

Untuk di bagian data preprocessing, kalian tinggal ngutak-ngatik data yang ada biar bisa di fit ke model, kebanyakan sih encoding value string yang ada di contoh atas tadi. Setelah itu kalian tinggal nge-fit / ngelatih data ke model pilihan kalian.  

# How to boost your score
## Hyperparameter tuning
[Hyperparameter tuning](https://machinelearningmastery.com/hyperparameter-optimization-with-random-search-and-grid-search/) hampir selalu dipake pada tahap modeling. Intinya setiap model itu punya konfigurasi, dan untuk model yang sama, perbedaan konfigurasi akan menyebabkan perbedaan skor juga. Tujuan kalian adalah konfigurasi yang menghasilkan performa terbaik bagi model. Caranya adalah dengan mencoba-coba semua kemungkinan konfigurasi bagi model dan mengambil konfigurasi yang memiliki nilai akurasi terbaik. Beberapa metode yang bisa digunakan yaitu [Grid Search Cross Validation (GSCV)](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)  dan [Randomized Search Cross Validation (RSCV)](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html).

## Model sakti
Usahain selalu nyoba model tipe boosting untuk submisi karena biasanya sangat overpowered terutama buat di lomba-lomba:
- XGBoost
- CatBoost
- RandomForest

## Ensembling
Setelah itu, kalian juga bisa menggabungkan model, nama konsepnya adalah Ensembling. Biasanya kalo pake ensembling, skor kalian hampir dijamin bakal naik wkwk. Ensembling yang sering dan paling gampang dipake biasanya Voting. Sesuai namanya, Voting bakal ngambil mayoritas hasil prediksi dari beberapa model yang kalian masukkin. Info lebih lanjut [VotingClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.VotingClassifier.html).

## Imbalanced data
Banyak kasus dimana distribusi target label yang ada pada dataset tidak seimbang. Misalnya untuk data berlabel 0 totalnya ada 1000 data, sedangkan untuk data berlabel 1 totalnya hanya 10 data. Dengan kondisi seperti ini, model kita akan cenderung untuk memprediksi label 0 karena kurangnya pengetahuan akan label 1. Di beberapa lomba, kalian bisa mendapatkan performa hasil yang signifikan jika kalian melakukan resampling data. Resampling ini tujuannya untuk membuat data yang tidak seimbang itu menjadi seimbang. Resampling ada 2 jenis, oversampling dan undersampling. Kalau oversampling, berarti label yang lebih sedikit (dalam contoh ini label 1) akan dinaikkan jumlah datanya dengan men-generate data baru dengan algoritma tertentu sehingga hasil akhirnya misalnya label 0 totalnya 1000 data dan label 1 juga totalnya 1000 data. Undersampling adalah keablikannya dimana data yang berlabel lebih tinggi justru akan dieliminasi hingga jumlahnya serupa dengan data yang jumlahnya lebih sedikit. Banyak banget metode yang bisa kalian pakai tapi yang bisa dibilang paling oke berdasarkan pengalaman adalah [SMOTEENN](https://imbalanced-learn.org/stable/references/generated/imblearn.combine.SMOTEENN.html).

## Data leakage
Jika beneran ada data leakage di lomba yang kalian ikuti, data leakage ini dijamin bisa ngeboost skor akurasi kalian bahkan hingga 1 (100% prediksi benar tanpa salah). Sederhananya, data leakage itu terjadi ketika data test yang diberikan oleh panitia punya kesamaan dengan data train. Kesamaan ini bisa kalian cek misalnya dengan membandingkan apakah ada id yang sama di data train dan test. Contohnya:

> ID di data train: 1,2,3,4,5  
> ID di data test: 2,3,4,7,9  
> Di sini ada data leak pada ID 2,3,4. Hal ini karena data dengan ID tersebut sudah ada di data train, artinya kita udah tau label dari data-data tersebut. Jadi bahkan tanpa perlu melatih model, kita udah bisa tau label data di data test dan bisa langsung ngesubmit.

Idealnya, semua data yang ada di data train gaboleh dimasukkan sedikit pun ke data test. Ini contoh yang benar:

> ID di data train: 1,2,3,4,5  
> ID di data test: 6,7,8,9,10  
> Di sini ga ada data leak sama sekali karena ID yang digunakan di data train dan test tidak ada yang overlap.

Kalau di leaderboard lomba yang kalian ikuti ada tim yang mencapai skor 1, maka patut dicurigai kalau ada data leakage di dataset lomba tersebut.

# Other important concepts
Beberapa hal penting yang kalian bisa tambahkan ke laporan dan presentasi  
- [Correlation Matrix](https://www.displayr.com/what-is-a-correlation-matrix/): Melihat korelasi keseluruhan antar kolom / fitur di dataset
- [Kernel Density Estimation Plot](https://www.geeksforgeeks.org/kde-plot-visualization-with-pandas-and-seaborn/): Melihat korelasi antara distribusi beberapa fitur
- [Confusion Matrix](https://www.analyticsvidhya.com/blog/2020/04/confusion-matrix-machine-learning/): Salah satu metode validasi yang wajib kalian lampirkan
- [Feature Importance](https://towardsdatascience.com/explaining-feature-importance-by-example-of-a-random-forest-d9166011959e): Mengetahui fitur mana yang paling berpengaruh terhadap prediksi model (biasanya di pakai untuk model Random Forest) 

# Additional tips
 1. Biasanya lomba yang organizernya dari universitas, soal-soalnya bakal pake data yang udah pernah dilombain. Jadi untuk ~~mencuri~~ mencari ide, kalian bisa searching aja terutama di Kaggle untuk menemukan perlombaan atau data yang mirip atau bahkan sama persis. Dari situ, tinggal baca" notebook dan liat" metode yang dilakukan orang lain (Biasanya ada yang ngeshare notebook gitu). ~~Atau kalau data yang dipake sama persis, bisa comot notebooknya dan langsung ngerun dan submit.~~
 2. Habisin jatah submisi di Kaggle setiap hari dan coba cara-cara yang beragam saat ngerjain soal.
 3. Bikin sheet buat nyatet model apa aja yang udah pernah kalian coba, skor validasinya berapa, skor leaderboardnya berapa.
 4. Ada beberapa lomba yang minta submit notebook, jadi usahakan untuk coding dengan rapi (walaupun kyknya ga dicek sih hehe)
 5. Jangan lupa sesuaiin format submisi dengan format yang diminta. Biasanya sering kelupaan drop index pas ngesave hasil prediksi jadi `.csv`.
 6. Have fun!

#### Terima kasih dan selamat mencoba!
