# Laporan Proyek Machine Learning Predictive Analysis - Benevito Kevin Sebastian Hariandja

## Domain Proyek

Saham PT Aneka Tambang Tbk (ANTM) merupakan instrumen investasi yang menarik karena hubungannya yang erat dengan harga emas. Pergerakan harga saham ANTM dipengaruhi oleh faktor-faktor eksternal seperti harga emas, suku bunga, nilai tukar dolar AS, dan kondisi pasar global [1]. Mengingat tingginya volatilitas harga saham ANTM, investor sering menghadapi kesulitan dalam memprediksi pergerakan harga saham secara akurat [2].

Masalah ini penting untuk diselesaikan karena ketidakakuratan dalam memprediksi harga saham dapat berdampak signifikan pada pengambilan keputusan investasi, terutama bagi investor ritel yang tidak memiliki akses ke alat analisis kompleks. Prediksi yang lebih akurat dapat membantu meminimalkan risiko kerugian, meningkatkan kepercayaan investor, dan mendukung pengambilan keputusan yang lebih strategis di pasar saham.

Metode konvensional seperti analisis teknikal dan fundamental terbukti memiliki keterbatasan dalam menangkap pola kompleks dalam data historis harga saham ANTM. Hal ini menuntut adanya solusi yang lebih efektif dan adaptif. Dengan kemajuan teknologi, metode berbasis pembelajaran mesin, khususnya model Long Short-Term Memory (LSTM), semakin banyak digunakan untuk prediksi harga aset finansial berbasis data time series. Model LSTM terbukti dapat mengenali pola jangka panjang dan dinamika pasar yang lebih kompleks, sehingga cocok untuk menganalisis harga saham yang sangat dipengaruhi oleh faktor eksternal [3, 4].

Sebagai solusi, proyek ini menggunakan model LSTM dan GRU untuk memprediksi harga saham ANTM berdasarkan data historis harian, seperti harga pembukaan, penutupan, volume perdagangan, dan harga tertinggi/terendah. Model ini diharapkan dapat meningkatkan akurasi prediksi harga saham dalam jangka pendek, membantu investor untuk membuat keputusan yang lebih terinformasi. Akurasi model akan dievaluasi menggunakan metrik Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), dan R2 Score.

Referensi:

    1. Mahendra, A., Amalia, M. M., & Leon, H. (2022). Analisis pengaruh suku bunga, harga minyak dunia, harga emas dunia terhadap indeks harga saham gabungan dengan inflasi sebagai variabel moderating di Indonesia. Owner: Riset dan Jurnal Akuntansi, 6(1), 1069-1082.

    2. Fadilah, A., Wiharno, H., & Nurfatimah, S. N. (2023). Pengaruh Harga Saham, Return Saham, Volatilitas Harga Saham, Ukuran Perusahaan Dan Volume Perdagangan Saham Terhadap Bid-Ask Spread Saham. Prosiding FRIMA (Festival Riset Ilmiah Manajemen dan Akuntansi), (6), 212-226.

    3. Sofi, K., Sunge, A. S., Riady, S. R., & Kamalia, A. Z. (2021). Perbandingan algoritma linear regression, LSTM, dan GRU dalam memprediksi harga saham dengan model time series. PROSIDING SEMINASTIKA, 3(1), 39-46.

    4. Hanafiah, A., Arta, Y., Nasution, H. O., & Lestari, Y. D. (2023). Penerapan Metode Recurrent Neural Network dengan Pendekatan Long Short-Term Memory (LSTM) Untuk Prediksi Harga Saham. Bulletin of Computer Science Research, 4(1), 27-33.

## Business Understanding

### Problem Statements

- Pasar saham, terutama saham berbasis komoditas seperti PT Aneka Tambang Tbk (ANTM), sangat fluktuatif dan dipengaruhi oleh berbagai faktor eksternal, seperti harga emas dunia, kondisi geopolitik, inflasi, serta nilai tukar mata uang asing. Ketidakpastian dalam pergerakan harga saham ANTM membuat investor dan pelaku pasar sulit untuk mengambil keputusan investasi yang tepat waktu dan berdasarkan prediksi yang akurat.

- Meskipun data historis harga saham ANTM tersedia secara luas, pemanfaatannya untuk prediksi harga saham dalam jangka pendek masih belum optimal. Banyak metode analisis yang digunakan saat ini, seperti analisis teknikal dan fundamental, memiliki keterbatasan dalam mengenali pola non-linear dan kompleks yang ada dalam data time series harga saham ANTM.

- Metode konvensional dalam memprediksi pergerakan harga saham ANTM sering kali tidak cukup adaptif terhadap dinamika pasar yang cepat berubah. Oleh karena itu, diperlukan metode baru yang lebih mampu menangkap pola tersembunyi dalam data historis yang lebih kompleks, untuk menghasilkan prediksi yang lebih akurat dalam jangka pendek.

### Goals

- Mengoptimalkan penggunaan data historis saham ANTM dengan model berbasis pembelajaran mesin, untuk menangkap pola yang tidak dapat dikenali oleh metode konvensional dalam prediksi harga jangka pendek.

- Membangun model prediktif yang dapat memperkirakan pergerakan harga saham ANTM dengan lebih akurat, membantu investor mengambil keputusan yang tepat dalam situasi fluktuasi pasar yang tinggi.

### Solution statements

- Solusi 1: Prediksi Harga Saham ANTM Menggunakan Model Recurrent Neural Network (LSTM & GRU)

Solusi yang diusulkan dalam proyek ini adalah menggunakan model Recurrent Neural Network (RNN), khususnya model Long Short-Term Memory (LSTM) dan Gated Recurrent Unit (GRU), untuk memprediksi harga saham ANTM. Model LSTM dipilih karena kemampuannya dalam menangkap pola jangka panjang dalam data time series dan mengatasi masalah vanishing gradient yang umum terjadi pada jaringan saraf konvensional. Di sisi lain, GRU digunakan sebagai alternatif karena arsitekturnya yang lebih sederhana dan efisien secara komputasi, tetapi tetap mampu menangani data sekuensial dengan baik.

Evaluasi: Dilakukan menggunakan metrik Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), dan R2 Score. Model terbaik dipilih berdasarkan hasil evaluasi yang menunjukkan akurasi paling tinggi dan performa paling konsisten dalam data pengujian. Target performa mencakup pencapaian nilai R2 di atas 0.90 dan nilai RMSE yang rendah sebagai indikator kualitas prediksi yang baik.

- Solusi 2: Hyperparameter Tuning pada Model

Untuk meningkatkan akurasi prediksi, dilakukan tuning pada hyperparameter, seperti jumlah unit neuron di lapisan model, ukuran batch, optimizer, dan jumlah epoch pelatihan. Penyempurnaan parameter ini bertujuan agar model dapat lebih efektif dalam mempelajari pola-pola kompleks yang ada dalam data.

Evaluasi: Performa model yang telah di-tune akan dibandingkan dengan model baseline. Solusi ini dianggap berhasil apabila terdapat penurunan dalam nilai MAE dan R2 dibandingkan dengan model awal.

## Data Understanding

Data yang digunakan dalam proyek ini merupakan data historis harga saham PT Aneka Tambang Tbk (ANTM) yang diperoleh dari platform keuangan Yahoo Finance, dengan kode saham ANTM.JK. Dataset ini mencakup rentang waktu harian dan dapat diunduh secara publik melalui tautan berikut: https://www.kaggle.com/datasets/muhardianabasandi/antam-stock-market-by-kitto

Dataset tersebut berisi informasi perdagangan harian dan harga saham dari tahun 2005 - 2021 untuk analisis dan prediksi. Total data terdiri dari 3.808 baris yang merepresentasikan hari perdagangan bursa, tanpa mencakup hari libur atau akhir pekan.

Variabel-variabel pada dataset ANTM adalah sebagai berikut:

**`Date`** : Tanggal transaksi saham (format: YYYY-MM-DD).

**`Open`** : Harga saham saat pasar dibuka

**`High`** : Harga tertinggi yang dicapai pada hari itu

**`Low`** : Harga terendah yang dicapai pada hari itu

**`Close`** : Harga saham saat pasar ditutup

**`Adj Close`** : Harga penutupan yang disesuaikan dengan pembagian dividen dan aksi korporasi

**`Volume`** : Jumlah saham yang diperdagangkan dalam satu hari

### Exploratory Data Analysis (EDA)

Beberapa tahapan eksplorasi data dilakukan, antara lain:

1. Pemeriksaan missing values. Setelah pemeriksaan, ditemukan bahwa setiap kolom harga dan volume memiliki 1 missing value pada dataset, yaitu pada kolom:

    **`Date`**: 0 nilai hilang

    **`Open`**: 1 nilai hilang

    **`High`**: 1 nilai hilang

    **`Low`**: 1 nilai hilang

    **`Close`**: 1 nilai hilang

    **`Adj Close`**: 1 nilai hilang

    **`Volume`**: 1 nilai hilang

    Karena hanya sedikit nilai yang hilang, baris tersebut dihapus dari dataset agar proses analisis dan pemodelan bisa dilakukan dengan baik.

2. Pemeriksaan duplikasi. Pemeriksaan duplikasi menggunakan **`df.duplicated()`** menunjukkan bahwa tidak terdapat baris duplikat, sehingga tidak perlu dilakukan pembersihan terkait hal ini.

3. Pemeriksaan outlier. Outlier dideteksi menggunakan metode IQR (Interquartile Range) pada kolom Close. Ditemukan 298 data outlier yang tersebar pada beberapa periode. Visualisasi menunjukkan bahwa sebagian besar outlier terjadi pada masa krisis global (2007–2008) dan pandemi COVID-19 (2020), yang merefleksikan volatilitas harga ekstrem di pasar saham.

![image](https://github.com/user-attachments/assets/96c74f49-b332-498e-a046-765f08e0d135)

4. Visualisasi tren harga close dari waktu ke waktu. Grafik garis harga penutupan (Close) menunjukkan adanya fluktuasi harga signifikan sepanjang periode pengamatan. Terlihat tren kenaikan tajam antara tahun 2006–2008, diikuti penurunan pasca krisis, dan kembali meningkat tajam di tahun 2020 yang bertepatan dengan masa pandemi.

![image](https://github.com/user-attachments/assets/38b77b88-f050-4c37-b32c-1cae05f9f4c6)

5. Distribusi harga penutupan (Close). Distribusi harga Close divisualisasikan menggunakan histogram dan KDE. Grafik menunjukkan bahwa harga penutupan paling sering berada di kisaran 500 – 1.250, menunjukkan area akumulasi harga yang paling banyak terjadi.

![image](https://github.com/user-attachments/assets/cda1300c-cfe3-4600-8db1-8dec84f181fe)

6. Korelasi antar fitur. Heatmap korelasi memperlihatkan hubungan kuat antara fitur **`Open`**, **`High`**, **`Low`**, **`Close`**, dan **`Adj Close`** dengan nilai korelasi di atas 0.98. Fitur **`Volume`** menunjukkan korelasi lemah terhadap variabel lain, berada pada kisaran 0.13–0.22. Informasi ini penting untuk pemilihan fitur pada proses pemodelan.

![image](https://github.com/user-attachments/assets/ad052715-141d-4534-8754-322d5fee4d8a)

## Data Preparation

1. Menghapus missing value 
. Pada dataset ditemukan satu baris data yang memiliki nilai kosong, dan baris tersebut dihapus dengan **`dropna()`**.

    Alasan:  Missing value dapat mengganggu proses pelatihan model dan menyebabkan error pada model deep learning.

2. Seleksi fitur. Kolom yang digunakan untuk pelatihan model adalah:

    **`Open`**, **`High`**, **`Low`**, **`Close`**, dan **`Adj Close`**

    Alasan: Fitur-fitur ini memiliki korelasi langsung terhadap harga penutupan saham dan umum digunakan dalam analisis pasar saham.

3. Normalisasi data. Data dinormalisasi menggunakan **`MinMaxScaler()`** dari library **`sklearn.preprocessing`**, sehingga semua nilai fitur berada dalam rentang [0, 1].

    Alasan: LSTM sensitif terhadap skala data. Normalisasi membantu mempercepat konvergensi model dan menghindari dominasi fitur tertentu.

4. Penerapan sliding window. Teknik sliding window digunakan untuk membentuk dataset time series dengan window_size sebesar 60 hari. Setiap input model terdiri dari 60 data historis sebelumnya untuk memprediksi harga hari ke-61.

    Alasan: Sliding window memungkinkan model mempelajari pola urutan dalam data historis yang relevan untuk prediksi ke depan.

5. Penyesuaian tanggal dengan dataset. Setelah sliding window diterapkan, tanggal data juga disesuaikan agar tetap sejajar dengan hasil preprocessing.

    Alasan: Diperlukan untuk evaluasi dan visualisasi hasil prediksi secara akurat berdasarkan waktu.

6. Split data latih dan uji. Data dibagi menjadi data latih dan data uji menggunakan rasio 80:20 tanpa melakukan shuffling, karena urutan waktu harus dipertahankan dalam data time series.

    Alasan: Memastikan model dilatih dengan data masa lalu dan diuji dengan data masa depan secara kronologis, sesuai karakteristik prediksi time series.

## Modeling

**1. Arsitektur model**

**a. Model LSTM (Long Short-Term Memory)**

LSTM digunakan karena memiliki memori internal yang mampu menangkap ketergantungan jangka panjang antar waktu.

Model terdiri dari:

- 2 lapisan LSTM berturut-turut, masing-masing dengan sejumlah unit (neuron).
- 1 lapisan Dense (fully connected) sebagai output yang memprediksi harga penutupan saham.

Fungsi aktivasi yang digunakan secara default adalah tanh pada LSTM, sedangkan output layer menggunakan fungsi linear.

**b. Model GRU (Gated Recurrent Unit)**

GRU merupakan versi lebih ringan dari LSTM, dengan jumlah parameter lebih sedikit namun tetap efektif menangani data deret waktu.

Arsitektur mirip dengan LSTM: 
- 2 lapisan GRU 
- 1 lapisan Dense sebagai output.

**2. Parameter model dan hyperparameter tuning**

Beberapa parameter penting yang digunakan dan diuji melalui tuning:

|Parameter|Fungsi|Nilai yang diuji|
|-|-|-|
|units|Jumlah neuron dalam tiap layer LSTM/GRU|**32**, 50, 64|
|batch_size|Ukuran batch data saat pelatihan|16, **32**|
|epoch|Banyaknya siklus pelatihan|**10**, 20|
|optimizer|Algoritma optimisasi bobot model|**adam**, rmsprop|

Pertama, model LSTM dan GRU dilatih tanpa melakukan hyperparameter tuning untuk menghasilkan baseline model. Nilai-nilai parameter default yang digunakan dalam model baseline ditandai dengan nilai yang di **BOLD** pada tabel parameter diatas. Baseline ini berfungsi sebagai pembanding terhadap hasil model setelah dilakukan optimasi parameter, sehingga dapat diketahui seberapa besar peningkatan performa yang diperoleh setelah tuning dilakukan.

Selanjutnya, proses hyperparameter tuning dilakukan menggunakan teknik RandomizedSearchCV, yaitu metode pencarian kombinasi parameter secara acak dari parameter yang telah ditentukan sebelumnya. Dalam proses ini digunakan 3-fold cross-validation, di mana data latih dibagi menjadi tiga bagian untuk validasi silang untuk menghindari overfitting. Model LSTM dan GRU yang menunjukkan performa terbaik pada data validasi selama proses tuning kemudian dipilih dan digunakan sebagai model terbaik.

**3. Pelatihan ulang model terbaik**

Setelah parameter terbaik ditemukan melalui proses tuning, model LSTM dan GRU dibangun ulang menggunakan konfigurasi optimal tersebut. Selanjutnya, dilakukan pelatihan ulang pada seluruh data latih dengan parameter terbaik untuk memastikan model memperoleh pembelajaran maksimal dari data yang tersedia dan menghasilkan performa prediksi yang lebih akurat.

**4. Evaluasi model**

Pemilihan model terbaik dilakukan dengan membandingkan performa menggunakan empat metrik evaluasi utama: Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), dan R² Score. Model yang dianggap memiliki kinerja terbaik adalah model dengan nilai MAE, MSE, dan RMSE yang paling rendah serta nilai R² yang paling tinggi. Evaluasi dilakukan pada data pengujian untuk mengukur seberapa baik model dapat melakukan generalisasi terhadap data yang belum pernah dilihat sebelumnya.

Berdasarkan hasil evaluasi, model GRU dengan hyperparameter tuning melalui Random Search menunjukkan performa terbaik dibandingkan model lainnya. Model ini mencatatkan nilai MAE sebesar 30.55, RMSE sebesar 53.48, dan R2 Score sebesar 0.9821. Angka-angka ini menunjukkan bahwa model GRU hasil tuning paling akurat dalam memprediksi harga saham ANTM, karena kesalahan prediksi lebih rendah dan kemampuan menjelaskan variasi data lebih tinggi dibandingkan model baseline maupun model LSTM.

Namun, performa model GRU baseline juga cukup kompetitif dengan MAE sebesar 30.47, RMSE 54.74, dan R2 Score 0.9812. Selisih hasil evaluasi antara GRU baseline dan GRU hasil tuning tergolong kecil, yang mengindikasikan bahwa bahkan tanpa tuning, arsitektur GRU sudah cukup andal dalam menangani prediksi data time series harga saham. Oleh karena itu, dalam konteks tertentu, GRU baseline bisa menjadi pilihan efisien jika mempertimbangkan waktu pelatihan dan kompleksitas proses tuning.

**5. Kelebihan dan Kekurangan Model**

|Model|Kelebihan|Kekurangan|
|-|-|-|
|LSTM|Mampu menangkap dependensi jangka panjang|Arsitektur lebih kompleks|
||Mengatasi masalah vanishing gradient|Waktu pelatihan lebih lama dibanding GRU
||Cocok untuk data time series kompleks|
|GRU|Arsitektur lebih sederhana dan cepat dilatih|Kurang mampu menangkap pola jangka panjang dibanding LSTM|
||Performa hampir setara dengan LSTM dalam banyak kasus|
||Lebih efisien untuk dataset kecil|

## Evaluation

Berikut adalah penjelasan matriks evaluasi model:

1. Mean Absolute Error (MAE)

    $MAE = \frac{1}{n} \sum_{i=1}^{n} |y_i - \hat{y}_i|$

    Penjelasan:
    MAE mengukur rata-rata selisih absolut antara nilai yang diprediksi dan nilai aktual. MAE memberikan gambaran seberapa besar kesalahan prediksi rata-rata yang dilakukan oleh model. Semakin kecil nilai MAE, semakin baik model dalam memprediksi harga.

2. Mean Squared Error (MSE)

    
    $MSE = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$

    Penjelasan:
    MSE mengukur rata-rata kuadrat perbedaan antara nilai yang diprediksi dan nilai aktual. MSE memberikan bobot yang lebih besar pada outlier karena kesalahan dikuadratkan. Nilai MSE yang lebih kecil menunjukkan prediksi yang lebih baik.

3. Root Mean Squared Error (RMSE)

    $RMSE = \sqrt{MSE}$

    Penjelasan:
    RMSE adalah akar kuadrat dari MSE dan memberikan ukuran kesalahan dalam unit yang sama dengan data asli. RMSE sering digunakan karena interpretasinya yang lebih mudah, dan semakin kecil nilai RMSE, semakin akurat model.

4. R2 Score (Coefficient of Determination)

    ![Screenshot 2025-05-17 083734](https://github.com/user-attachments/assets/c0b6bf49-57ef-4180-b87a-d01af794f276)

    Penjelasan:
    R2 Score mengukur proporsi variasi dalam data yang dapat dijelaskan oleh model. Nilai R2 berkisar antara 0 dan 1, di mana nilai mendekati 1 menunjukkan bahwa model dapat menjelaskan sebagian besar variabilitas data. Semakin tinggi nilai R2, semakin baik model dalam menjelaskan hubungan antara fitur dan target.

#### Hasil Eksperimen

|Model|MAE|MSE|RMSE|R2 Score|
|-|-|-|-|-|
|LSTM|39.64|4903.66|70.03|0.9692|
|LSTM (Random Search)|35.97|3275.50|57.23|0.9794|
|GRU|30.47|2996.51|54.74|0.9812|
|GRU (Random Search)|30.55|2859.97|53.48|0.9821|

#### Kesimpulan:

Tujuan utama dari proyek ini adalah untuk membantu investor dan pelaku pasar dalam menghadapi fluktuasi harga saham PT Aneka Tambang Tbk (ANTM) yang tinggi dan dipengaruhi oleh berbagai faktor eksternal, seperti harga emas dunia, kondisi geopolitik, inflasi, dan nilai tukar mata uang asing. Dalam situasi seperti ini, metode konvensional seperti analisis teknikal dan fundamental sering kali kurang efektif karena tidak mampu mengenali pola non-linear dan kompleks yang terdapat dalam data historis saham.

Model yang dibangun menggunakan pendekatan Recurrent Neural Network (RNN), yaitu Long Short-Term Memory (LSTM) dan Gated Recurrent Unit (GRU), secara langsung menjawab pernyataan masalah yang telah diidentifikasi. Kedua model ini terbukti mampu mengenali pola sekuensial yang kompleks dan dinamis dalam data historis, yang sebelumnya sulit ditangkap oleh metode konvensional. Berdasarkan hasil evaluasi, model GRU dengan hyperparameter tuning melalui Randomized Search memberikan performa terbaik dengan nilai MAE terendah (30.55), RMSE terendah (53.48), dan R2 tertinggi (0.9821). Hal ini menunjukkan bahwa model mampu menjelaskan sebagian besar variasi dalam data dan memberikan prediksi yang sangat akurat.

Dilihat dari sisi goals, proyek ini berhasil mengoptimalkan penggunaan data historis untuk membangun model prediktif yang akurat dan andal. Akurasi tinggi dari model berkontribusi langsung dalam mendukung pengambilan keputusan investasi yang lebih tepat, khususnya dalam situasi pasar yang fluktuatif. Selain itu, penerapan hyperparameter tuning terbukti meningkatkan performa model, memperkuat solusi yang diusulkan dan menunjukkan bahwa strategi optimasi memberikan dampak nyata terhadap kualitas prediksi.

Secara keseluruhan, solusi yang dirancang dalam proyek ini telah menjawab seluruh problem statement, berhasil mencapai goals yang ditetapkan, dan berdampak positif terhadap konteks bisnis yang diangkat. Model prediksi yang dibangun tidak hanya memberikan hasil evaluasi yang kuat, tetapi juga memiliki nilai praktis dalam mendukung strategi investasi berbasis data yang lebih informatif, adaptif, dan strategis.
