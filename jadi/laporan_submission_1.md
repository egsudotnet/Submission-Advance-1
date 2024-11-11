# Laporan Proyek Machine Learning - Egih Sugiatna

## Domain Proyek

Kanker merupakan salah satu penyakit yang memiliki dampak kesehatan dan finansial signifikan, baik bagi pasien maupun sistem kesehatan secara keseluruhan. Berdasarkan data dari WHO, jumlah kasus kanker global terus meningkat setiap tahunnya, dengan jenis kanker tertentu seperti kanker paru-paru, payudara, dan kolorektal menjadi penyebab kematian utama di banyak negara. Pengobatan kanker, yang meliputi kemoterapi, radioterapi, imunoterapi, dan bedah, sangat kompleks dan membutuhkan perawatan jangka panjang yang mahalnesia, prediksi biaya terapi kanker semakin relevan dengan meningkatnya jumlah kasus kanker serta tekanan finansial yang dirasakan oleh banyak keluarga pasien .

Rumah sakit dan penyedia layanan kesehatan memerlukan solusi yang dapat memprediksi biaya layanan kanker secara lebih akurat. Prediksi biaya yang tepat membantu penyedia layanan mengelola anggaran lebih baik dan memberikan estimasi biaya yang transparan bagi pasien. Teknologi kecerdasan buatan (AI) dan *machine learning* telah terbukti efektif dalam memproses data besar dan kompleks, menjadikannya alat yang potensial dalam mengembangkan model prediksi biaya layanan kesehatan, khususnya untuk terapi kanker .

## Business Understanding

Biaya perawatan kanker yang tinggi dan variatif merupakan tantangan besar, baik bagi pasien maupun penyedia layanan kesehatan. Banyak faktor, seperti jenis terapi, stadium kanker, dan kondisi kesehatan pasien, mempengaruhi besaran biaya tersebut. Ketidakmampuan memprediksi biaya dengan akurat sering kali mengakibatkan ketidakstabilan keuangan bagi pasien dan keluarga serta kesulitan pengelolaan anggaran di rumah sakit. Di sisi penyedia layanan, estimasi yang kurang tepat dapat mengganggu alokasi sumber daya yang optimal, menyebabkan masalah ketersediaan layanan di masa mendatang.

Oleh karena itu, diperlukan model prediksi biaya yang mampu memberikan estimasi yang akurat untuk membantu manajemen rumah sakit dalam merencanakan kebutuhan anggaran dan membantu pasien dalam merencanakan biaya perawatan.

### Problem Statements

Dari penjelasan diaatas maka dapat disimpulkan bahwa permasalahan yang ada saat ini adalah:

* Bagaimana cara memperedikisi biaya pengobatan pasien kanker di rumah sakit?

### Goals

Berdasarkan maslah di atas maka proyek ini mempunyai tujuan yaitu:

* Menegetahui cara memperedikisi biaya perawatan pasien kanker di rumah sakit.

### Solution statements

1. Melakukan proses Exploratory Data Analysis (EDA)
2. Membuat model machine learning dengan beberaa model, yaitu:
   * Random forest
   * Liner regression

## Data Understanding

Data yang digunakan dalam proyek ini berasal dari kaggle dan bisa diunduh di [sini](https://www.kaggle.com/datasets/rishidamarla/costs-for-cancer-treatment "https://www.kaggle.com/datasets/rishidamarla/costs-for-cancer-treatment")

Dataset memiliki 1255 baris data dan memiliki beberapa fitur penting terkait biaya dan kejadian penyakit kanker. Dataset ini terdiri dari beberapa fitur utama yang memberikan informasi terkait biaya perawatan tahunan dan beberapa asumsi dasar dalam menangani pasien kanker.

### **Sample data**

| Cancer Site | Year | Sex        | Age      | Incidence and Survival Assumptions                | Annual Cost Increase (applied to initial and last phases) | Total Costs | Initial Year After Diagnosis Cost | Continuing Phase Cost | Last Year of Life Cost |
| ----------- | ---- | ---------- | -------- | ------------------------------------------------- | --------------------------------------------------------- | ----------- | --------------------------------- | --------------------- | ---------------------- |
| AllSites    | 2010 | Both sexes | All ages | Incidence, Survival at constant rate              | 0%                                                        | 124565.6    | 40463.5                           | 46642.8               | 37459.2                |
| AllSites    | 2010 | Both sexes | All ages | Incidence follows recent trend, Survival constant | 0%                                                        | 122420.8    | 38552.7                           | 46671.9               | 37196.3                |
| AllSites    | 2010 | Both sexes | All ages | Survival follows recent trend, Incidence constant | 0%                                                        | 125397.7    | 40463.5                           | 47136.3               | 37797.9                |
| AllSites    | 2010 | Both sexes | All ages | Incidence, Survival follow recent trends          | 0%                                                        | 123236.3    | 38552.7                           | 47155.7               | 37527.8                |
| AllSites    | 2010 | Both sexes | All ages | Incidence, Survival follow recent trends          | 2%                                                        | 123236.3    | 38552.7                           | 47155.7               | 37527.8                |
| AllSites    | 2010 | Both sexes | All ages | Incidence, Survival follow recent trends          | 5%                                                        | 123236.3    | 38552.7                           | 47155.7               | 37527.8                |
| Bladder     | 2010 | Both sexes | All ages | Incidence, Survival at constant rate              | 0%                                                        | 3980.7      | 978.7                             | 1895.8                | 1106.3                 |

### Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:

Berikut ini adalah penjelasan dari setiap fitur dalam dataset:

* **Cancer Site** : Jenis atau lokasi kanker yang diderita pasien. Faktor ini penting karena berbagai jenis kanker memiliki tingkat kejadian dan biaya perawatan yang berbeda.
* **Year** : Tahun ketika data dikumpulkan atau dianalisis. Fitur ini membantu melihat tren tahunan dalam biaya dan kejadian penyakit.
* **Sex** : Jenis kelamin pasien (pria atau wanita), yang dapat mempengaruhi statistik kejadian kanker dan biaya pengobatan.
* **Age** : Usia pasien. Usia sering kali berkaitan dengan risiko dan jenis kanker tertentu serta memengaruhi kebutuhan biaya perawatan.
* **Incidence and Survival Assumptions** : Asumsi terkait kejadian kanker dan tingkat kelangsungan hidup, yang dapat membantu memperkirakan jumlah pasien dan kemungkinan biaya pengobatan dalam periode tertentu.
* **Annual Cost Increase (applied to initial and last phases)** : Peningkatan biaya tahunan yang diterapkan pada fase awal dan akhir perawatan. Biaya perawatan kanker sering meningkat dari tahun ke tahun, dan fitur ini memungkinkan kita memahami peningkatan biaya selama masa perawatan pasien.
* **Total Costs** : Total biaya perawatan yang dikeluarkan untuk pasien kanker. Fitur ini menjadi variabel target dalam memprediksi biaya perawatan.
* **Initial Year After Diagnosis Cost** : Biaya perawatan pada tahun pertama setelah diagnosis. Ini mencakup biaya besar yang biasanya terjadi pada awal pengobatan.
* **Continuing Phase Cost** : Biaya pada fase lanjutan, yaitu biaya perawatan rutin yang dikeluarkan setelah fase awal dan sebelum fase akhir perawatan.

### Missing Values

Data yang hilang dapat menyebabkan bias dalam analisis dan memengaruhi hasil secara signifikan. Mengidentifikasi kolom atau baris yang memiliki nilai hilang memungkinkan kita untuk memutuskan langkah terbaik, seperti mengisi data yang hilang atau menghapus baris atau kolom yang tidak lengkap.

```
print("Pemeriksaan Missing Values:")
print(data.isnull().sum())
```

Dari hasil pemeriksaan **tidak terdapat missing value** untuk keseluruhan data

| Kolom                                                     | Missing Value |
| --------------------------------------------------------- | ------------- |
| Cancer Site                                               | 0             |
| Year                                                      | 0             |
| Sex                                                       | 0             |
| Age                                                       | 0             |
| Incidence and Survival Assumptions                        | 0             |
| Annual Cost Increase (applied to initial and last phases) | 0             |
| Total Costs                                               | 0             |
| Initial Year After Diagnosis Cost                         | 0             |
| Continuing Phase Cost                                     | 0             |
| Last Year of Life Cost                                    | 0             |

### Duplicate Data

Data duplikat adalah entri yang sama yang muncul lebih dari sekali dalam dataset. Keberadaan duplikat dapat mengubah hasil analisis dengan cara yang tidak akurat. Dengan menghapus duplikat, kita memastikan bahwa data yang dianalisis benar-benar mewakili situasi sebenarnya tanpa kelebihan representasi.

```
print("\nPemeriksaan Duplikat:")
print(f"Jumlah baris duplikat: {data.duplicated().sum()}")
```

Dari hasil pemriksaan tersebut **tidak ditemukan adanya duplicate Data**

### EDA

* Distribusi kasus "Cancer Site"

![1731147190012](image/laporan_submission_1/1731147190012.png)

diagram menunjukan jumlah kasus sama masning 66 kasus.

* Total Costs per "Cancer Site"

![1731147100181](image/laporan_submission_1/1731147100181.png)diagram menunjukan biaya terbesar secara berurut yaitu all sites, other , breast, colorectal, lymphoma

* Total Costs berdasarkan Cancer Site dan Sex

![1731147263523](image/laporan_submission_1/1731147263523.png)

diagram menunjukan yang paling banyak untuk wanita yaitu breast dan yang paling banyak untuk pria yaitu prostat.

## Data Preparation

* **Menghapus simbol '%' pada kolom 'Annual Cost Increase' dan mengonversinya menjadi float**

```
data['Annual Cost Increase (applied to initial and last phases)'] = (
    data['Annual Cost Increase (applied to initial and last phases)']
    .replace('%', '', regex=True)
    .astype(float) / 100
)
```

Penjelasan: Proses ini dilakukan untuk membersihkan dan mengonversi data dari format string ke format numerik (float). Simbol '%' dihapus agar kolom tersebut dapat dikonversi menjadi nilai float dan diubah menjadi bentuk desimal dengan membagi 100.

Alasan Diperlukan: Tahap ini sangat penting untuk memastikan bahwa data dalam kolom ini dapat diolah dengan benar oleh model machine learning. Model hanya dapat menerima data numerik untuk melakukan perhitungan, sehingga data yang awalnya berbentuk string dengan simbol seperti '%' perlu dibersihkan dan diubah menjadi tipe data numerik.

* **One-Hot Encoding untuk kolom kategorikal**

```
data_encoded = pd.get_dummies(data, columns=['Cancer Site','Sex','Age','Incidence and Survival Assumptions'], drop_first=True)
```

Penjelasan: One-Hot Encoding digunakan untuk mengubah data kategorikal menjadi format numerik dengan cara membuat kolom biner (0 dan 1) untuk setiap kategori yang ada.

Alasan Diperlukan: Machine learning model seperti regresi linier, SVM, atau algoritma lain memerlukan input berupa data numerik. One-Hot Encoding memastikan bahwa kolom kategorikal diubah ke format yang dapat diproses oleh model. Proses ini juga membantu model memahami setiap kategori tanpa memperkenalkan hubungan ordinal yang tidak ada.

* **Menentukan fitur dan target**

```
fitur = data_encoded.drop(columns=['Total Costs'])  # Gantilah dengan nama kolom target jika berbedatarget = data_encoded['Total Costs']
```

Penjelasan: Proses ini memisahkan variabel independen (fitur) dari variabel dependen (target) yang akan diprediksi.

Alasan Diperlukan: Pemilihan fitur dan target adalah langkah esensial dalam membangun model machine learning. Memisahkan fitur dari target memungkinkan model mempelajari pola dalam data untuk membuat prediksi yang akurat.

* **Pisahkan data menjadi set pelatihan dan pengujian**

```
X_train, X_test, y_train, y_test = train_test_split(fitur, target, test_size=0.2, random_state=42)
```

Jumlah sampel pelatihan: 1003
Jumlah sampel pengujian: 251

Penjelasan: Data dibagi menjadi set pelatihan (80%) dan set pengujian (20%). random_state=42 digunakan untuk memastikan hasil pembagian yang konsisten di setiap eksekusi.

Alasan Diperlukan: Memisahkan data menjadi set pelatihan dan pengujian penting untuk mengukur performa model secara objektif. Model dilatih pada data pelatihan dan dievaluasi pada data pengujian untuk menghindari overfitting dan memastikan bahwa model dapat menggeneralisasi dengan baik pada data baru.

* **Standarisasi fitur**

```
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
```

Penjelasan: Standarisasi dilakukan untuk menyelaraskan skala fitur-fitur dalam dataset agar memiliki distribusi yang sama (mean 0 dan standar deviasi 1).

Alasan Diperlukan: Standarisasi membantu model machine learning seperti algoritma yang berbasis gradien (contohnya: regresi linier, SVM, jaringan saraf) agar lebih stabil dan cepat dalam proses training. Skala yang tidak selaras antara fitur-fitur dapat mengakibatkan model kesulitan dalam mempelajari hubungan dalam data.

## Modeling

Pada proyek ini menggunakan model random forest dan liner regression

**Random Forest** :

* **Kelebihan** : Mampu menangani data kompleks dan hubungan non-linear dengan baik, robust terhadap overfitting berkat metode ensemble.
* **Kekurangan** : Butuh sumber daya komputasi yang lebih besar dan sulit diinterpretasikan dibandingkan model linier.
* **Proses Improvement** : Dilakukan hyperparameter tuning dengan `GridSearchCV` untuk menemukan kombinasi parameter terbaik. Parameter yang di-tuning meliputi:
  * `n_estimators`: Jumlah pohon dalam hutan.
  * `max_depth`: Kedalaman maksimum setiap pohon.
  * `min_samples_split`: Jumlah sampel minimum yang diperlukan untuk membagi node.
  * `min_samples_leaf`: Jumlah sampel minimum di daun pohon.

**Linear Regression** :

* **Kelebihan** : Mudah diinterpretasikan dan efisien secara komputasi, cocok untuk data dengan hubungan linier.
* **Kekurangan** : Tidak cocok untuk data dengan hubungan non-linear dan rentan terhadap overfitting jika data memiliki fitur multikolinearitas.

Secara keseluruhan, **Random Forest** dipilih karena mampu memenuhi kebutuhan analisis data yang lebih kompleks dan memiliki fleksibilitas yang lebih tinggi dibandingkan  **Linear Regression** , yang cenderung sederhana dan terbatas pada hubungan linier.

## Evaluation

**Hasil Evaluasi Model:**

Evaluasi model machine learning (ML) menggunakan metrik seperti **MSE (Mean Squared Error)**, **RMSE (Root Mean Squared Error)**, dan **R² (Koefisien Determinasi)** penting karena:

1. **MSE** mengukur rata-rata kuadrat perbedaan antara prediksi model dan nilai sebenarnya. Ini memberi penalti yang lebih besar pada kesalahan besar, sehingga model yang memiliki kesalahan besar akan terdeteksi lebih jelas.
2. **RMSE** adalah akar kuadrat dari MSE, sehingga nilainya berada dalam satuan yang sama dengan data asli. Ini membantu dalam menginterpretasi seberapa besar kesalahan prediksi dalam konteks data yang diukur.
3. **R²** mengukur seberapa baik model dalam menjelaskan variabilitas data. Nilai mendekati 1 menunjukkan model yang sangat baik, sementara nilai mendekati 0 menunjukkan model yang tidak lebih baik dari model sederhana.

Kombinasi ketiga metrik ini memberikan gambaran menyeluruh tentang performa model, baik dalam hal akurasi prediksi (MSE, RMSE) dan kemampuan model untuk menjelaskan data (R²).

| Model                   | MSE           | RMSE      | R2      |
| ----------------------- | ------------- | --------- | ------- |
| Random Forest (default) | 469.475,09604 | 685,18253 | 0,99923 |
| Linear Regression       | 0,00345       | 0,05876   | 1,00000 |

Dari hasil evaluasi tersebut, model **Linear Regression** dan **Random Forest** keduanya menunjukkan performa yang sangat tinggi. Namun, jika dilihat dari evaluasi pada set pengujian:

1. **Linear Regression** :

* **MSE: 0.00** ,  **RMSE: 0.06** , **R²: 1.00** menunjukkan bahwa model Linear Regression memiliki kesalahan yang sangat kecil pada set pengujian dan mampu menjelaskan hampir seluruh variabilitas target dengan sempurna. Ini adalah hasil yang sangat baik, tetapi bisa menjadi indikasi **overfitting** jika hasil ini terlalu sempurna dibandingkan dengan set pelatihan.

2. **Random Forest** :

* **MSE: 469475.10** ,  **RMSE: 685.18** , **R²: 1.00** menunjukkan bahwa model Random Forest juga menjelaskan variabilitas target dengan sangat baik (R² = 1.00), tetapi kesalahannya jauh lebih tinggi dibandingkan dengan Linear Regression. Ini bisa jadi karena kompleksitas data atau adanya variabilitas yang ditangkap oleh model.

**Kesimpulan** :

* **Linear Regression** memiliki performa yang luar biasa dengan error yang hampir nol pada set pengujian. Jika Anda yakin bahwa data Anda benar-benar linier dan tidak terlalu kompleks, model ini adalah pilihan yang tepat. Namun, hasil yang terlalu sempurna (R² = 1.00) bisa mengindikasikan bahwa model mungkin overfitting pada data pelatihan, jadi penting untuk memverifikasi performanya pada data baru atau menggunakan validasi silang.
* **Random Forest** memiliki performa yang lebih realistis dalam hal error, tetapi tetap dengan R² yang sangat tinggi. Model ini lebih cocok jika data Anda memiliki kompleksitas tambahan atau hubungan non-linear antar fitur. Meskipun MSE dan RMSE-nya lebih tinggi, model ini dapat menangkap pola yang lebih rumit.

Berdasarkan MSE dan RMSE yang jauh lebih rendah pada Linear Regression, **Linear Regression adalah model yang lebih efektif untuk memprediksi biaya pengobatan** pasien kanker dalam dataset ini. Model ini lebih akurat dalam memprediksi hasil dengan kesalahan yang sangat minimal, membuatnya lebih sesuai untuk aplikasi praktis dalam perencanaan anggaran dan estimasi biaya.
