# Laporan Proyek Machine Learning - Egih Sugiatna

## Project Overview

Dalam beberapa tahun terakhir, sektor pariwisata telah mengalami perkembangan yang pesat seiring dengan meningkatnya mobilitas global dan minat wisatawan terhadap destinasi-destinasi baru. Sebagai respons terhadap perubahan ini, teknologi kini memainkan peran penting dalam memfasilitasi pengalaman perjalanan yang lebih personal dan efisien. Salah satu alat yang dapat digunakan untuk mencapai tujuan tersebut adalah sistem rekomendasi berbasis data, yang memungkinkan wisatawan menemukan tempat-tempat menarik yang sesuai dengan preferensi mereka.

Proyek ini bertujuan untuk membangun sebuah sistem rekomendasi destinasi wisata yang menggunakan **Collaborative Filtering** dan **Content-Based Filtering** untuk memberikan rekomendasi yang lebih akurat berdasarkan data rating dan deskripsi tempat wisata. Sistem ini akan menggabungkan data pengguna, tempat wisata, dan rating yang diberikan untuk menghasilkan rekomendasi yang sesuai dengan minat setiap pengguna.

Proyek ini penting karena sistem rekomendasi memiliki potensi untuk meningkatkan pengalaman pengguna dalam memilih destinasi wisata. Dengan menyediakan rekomendasi yang lebih personal, wisatawan dapat menghemat waktu dalam mencari tempat wisata yang sesuai dengan preferensi mereka, yang pada akhirnya dapat meningkatkan kepuasan dan kenyamanan perjalanan. Selain itu, pengembangan sistem rekomendasi ini juga dapat membantu pengelola tempat wisata dalam memahami preferensi pengunjung mereka, sehingga mereka dapat menyesuaikan layanan dan promosi untuk menarik lebih banyak wisatawan.

Selain itu, sektor pariwisata di Indonesia, yang merupakan salah satu sektor unggulan dalam perekonomian, masih perlu ditingkatkan kualitas layanannya melalui pemanfaatan teknologi. Dengan penerapan sistem rekomendasi, pengunjung dapat mendapatkan pengalaman yang lebih baik, sementara pelaku industri pariwisata dapat memaksimalkan potensi pasar yang ada.

## Business Understanding

Industri pariwisata saat ini menghadapi tantangan besar dalam memberikan pengalaman yang memuaskan bagi wisatawan. Banyaknya pilihan destinasi wisata yang tersedia seringkali membuat wisatawan merasa bingung dalam memilih tempat yang paling sesuai dengan minat dan preferensi mereka. Selain itu, aplikasi atau platform yang ada masih terbatas dalam memberikan rekomendasi yang personal dan relevan, yang sesuai dengan kebutuhan individu.

### Problem Statements

Beberapa masalah utama yang dihadapi adalah:

1. **Kurangnya Personalisasi dalam Rekomendasi** : Banyak aplikasi pariwisata yang tidak dapat memberikan rekomendasi yang akurat berdasarkan preferensi spesifik pengguna.
2. **Kesulitan Pengguna dalam Memilih Destinasi Wisata** : Pengguna sering kali kesulitan dalam menemukan destinasi wisata yang sesuai dengan minat mereka, terutama ketika mereka tidak familiar dengan tempat tersebut.
3. **Kurangnya Pengelolaan Data Wisatawan** : Pengelola tempat wisata atau platform pariwisata tidak memiliki akses langsung ke data yang bisa membantu dalam mempersonalisasi pengalaman wisatawan.

Pernyataan masalah ini menyoroti pentingnya sebuah sistem yang dapat memberikan rekomendasi destinasi wisata yang tepat dan personal untuk setiap pengguna berdasarkan berbagai faktor, seperti data perilaku pengguna dan informasi konten dari tempat wisata itu sendiri.

### Goals

Tujuan utama dari proyek ini adalah untuk mengembangkan sistem rekomendasi yang mampu memberikan rekomendasi destinasi wisata yang relevan dan personal bagi pengguna. Tujuan spesifiknya adalah:

1. **Menyediakan Rekomendasi yang Relevan** : Sistem harus mampu memberikan rekomendasi destinasi wisata berdasarkan preferensi pengguna, baik itu berdasarkan perilaku pengguna sebelumnya atau berdasarkan konten dari destinasi tersebut.
2. **Meningkatkan Pengalaman Pengguna** : Membantu pengguna dalam menemukan destinasi wisata yang sesuai dengan minat mereka, mengurangi kebingungannya, dan meningkatkan kepuasan mereka.
3. **Personalisasi Berdasarkan Data** : Mampu memanfaatkan data pengguna dan data konten destinasi wisata untuk memberikan rekomendasi yang lebih personal dan relevan.
4. **Meningkatkan Retensi Pengguna** : Dengan memberikan pengalaman yang lebih baik, proyek ini bertujuan untuk meningkatkan retensi pengguna pada platform.

### Solution statements

Untuk mencapai tujuan yang telah disebutkan, kami mengajukan dua pendekatan utama dalam sistem rekomendasi ini: **Content-Based Filtering** dan  **Collaborative Filtering** . Kedua pendekatan ini masing-masing memiliki keunggulan dan dapat digunakan secara bersamaan untuk memberikan rekomendasi yang lebih akurat.

##### 1. **Content-Based Filtering**

**Pendekatan** ini berfokus pada informasi konten dari tempat wisata yang ada. Dalam sistem rekomendasi berbasis konten, rekomendasi diberikan berdasarkan kesamaan antara konten tempat wisata yang sudah diketahui atau disukai oleh pengguna dengan tempat wisata lainnya yang ada di dalam database. Pendekatan ini menggunakan fitur-fitur deskriptif dari destinasi wisata, seperti:

* **Kategori tempat wisata** (misalnya, alam, budaya, hiburan)
* **Deskripsi tempat wisata** (misalnya, fasilitas, jenis kegiatan, dan lainnya)
* **Lokasi tempat wisata**

 **Langkah-langkah dalam Content-Based Filtering** :

* Menggunakan teknik pemrosesan teks seperti **TF-IDF (Term Frequency-Inverse Document Frequency)** untuk menilai relevansi deskripsi dan kategori tempat wisata.
* Menghitung kesamaan antar destinasi berdasarkan deskripsi kontennya, dan memberikan rekomendasi destinasi yang paling mirip dengan yang telah dinilai atau dipilih oleh pengguna.
* Memberikan rekomendasi berdasarkan kategori atau jenis tempat yang sering dipilih oleh pengguna sebelumnya.

##### 2. **Collaborative Filtering**

**Collaborative Filtering** berfokus pada data perilaku atau interaksi pengguna dengan sistem (misalnya, rating atau kunjungan). Pendekatan ini mengandalkan kesamaan preferensi antar pengguna untuk memberikan rekomendasi. Jika dua pengguna memiliki pola perilaku yang mirip, mereka akan diberikan rekomendasi yang sama, bahkan jika mereka tidak memilih atau memberi rating pada tempat yang sama.

 **Langkah-langkah dalam Collaborative Filtering** :

* **User-Based Collaborative Filtering** : Menilai kesamaan antara pengguna berdasarkan pola rating mereka dan memberikan rekomendasi dari pengguna yang serupa.
* **Item-Based Collaborative Filtering** : Menggunakan kesamaan antar item (tempat wisata) berdasarkan rating pengguna sebelumnya dan memberikan rekomendasi tempat wisata yang mirip dengan yang sudah dipilih oleh pengguna.
* Menggunakan **Cosine Similarity** atau **Pearson Correlation** untuk mengukur kesamaan antara pengguna atau item.

## Data Understanding

Data yang digunakan dalam proyek ini dapat diunduh di [https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination](https://www.kaggle.com/datasets/aprabowo/indonesia-tourism-destination) yang mencakup informasi terkait destinasi wisata, rating tempat wisata oleh pengguna, serta data pengguna itu sendiri. Data tersebut diolah dan dianalisis untuk menghasilkan rekomendasi destinasi yang sesuai dengan preferensi pengguna. Adapun sumber data yang digunakan meliputi:

1. **Dataset Tempat Wisata (`tourism_with_id`)** : Dataset ini berisi informasi mengenai tempat-tempat wisata, seperti nama tempat wisata, kategori, deskripsi, dan kota. Setiap tempat wisata juga dilengkapi dengan ID unik yang memudahkan pengelolaan dan penghubungan data lainnya.
2. **Dataset Rating Pengguna (`tourism_rating`)** : Dataset ini berisi data rating yang diberikan oleh pengguna pada tempat wisata yang mereka kunjungi. Rating ini digunakan untuk menghitung tingkat kesukaan pengguna terhadap destinasi tertentu.
3. **Dataset Pengguna (`user`)** : Dataset ini berisi informasi pengguna, termasuk ID pengguna dan data demografis seperti usia dan lokasi. Data ini digunakan untuk menganalisis preferensi pengguna dan memberikan rekomendasi berdasarkan interaksi pengguna dengan destinasi wisata.
4. **Dataset Paket Wisata (`package_tourism`)** : Dataset ini berisi informasi tentang paket wisata yang dapat mengaitkan tempat wisata dengan paket tur tertentu. Data ini memungkinkan untuk memberikan rekomendasi destinasi berdasarkan paket wisata yang disukai oleh pengguna.

#### Struktur Data

Data yang digunakan dalam proyek ini memiliki struktur yang cukup kompleks, terdiri dari beberapa kolom yang mencakup informasi terkait pengguna, tempat wisata, rating, dan paket wisata. Berikut adalah penjelasan dari beberapa dataset yang digunakan:

1. **Dataset `tourism_with_id`**
   * **Place_Id** : ID unik untuk setiap tempat wisata.
   * **Place_Name** : Nama tempat wisata.
   * **Category** : Kategori tempat wisata (misalnya, alam, budaya, hiburan).
   * **Description** : Deskripsi singkat mengenai tempat wisata.
   * **City** : Kota tempat tempat wisata tersebut berada.
2. **Dataset `tourism_rating`**
   * **User_Id** : ID unik untuk setiap pengguna yang memberikan rating.
   * **Place_Id** : ID tempat wisata yang diberi rating.
   * **Place_Ratings** : Nilai rating yang diberikan pengguna pada tempat wisata.
3. **Dataset `user`**
   * **User_Id** : ID unik untuk setiap pengguna.
   * **Location** : Lokasi pengguna (misalnya, kota tempat tinggal pengguna).
   * **Age** : Usia pengguna.
4. **Dataset `package_tourism`**
   * **Place_Tourism1** : Nama tempat wisata yang ada dalam paket wisata.
   * **Package_Name** : Nama paket wisata yang mencakup tempat wisata tersebut.

#### Analisis Data

Berikut adalah beberapa analisis awal terkait data yang digunakan dalam proyek ini:

1. **Data `tourism_with_id`**
   * Setiap tempat wisata memiliki informasi terkait nama tempat, kategori, deskripsi, dan lokasi, yang akan digunakan dalam proses **content-based filtering** untuk menghitung kesamaan antar tempat wisata berdasarkan deskripsi dan kategori tempat.
2. **Data `tourism_rating`**
   * Setiap rating yang diberikan oleh pengguna berfungsi untuk membantu menghitung kesamaan preferensi antar pengguna, yang akan digunakan dalam  **collaborative filtering** . Data rating ini sangat penting karena mencerminkan tingkat kepuasan pengguna terhadap destinasi wisata tertentu.
3. **Data `user`**
   * Informasi lokasi dan usia pengguna memberikan konteks tambahan dalam analisis. Misalnya, usia dapat mempengaruhi jenis destinasi yang disukai, dan lokasi dapat memberikan petunjuk tentang destinasi wisata yang lebih relevan bagi pengguna berdasarkan kedekatannya.
4. **Data `package_tourism`**
   * Paket wisata memberikan informasi terkait kombinasi tempat wisata yang dapat direkomendasikan bersama-sama, berdasarkan minat pengguna pada paket wisata tertentu.

#### Pengolahan Data

Dalam tahap ini, data yang digunakan telah dibersihkan dan dipersiapkan untuk analisis lebih lanjut. Proses ini melibatkan pengisian nilai yang hilang, pembersihan data yang tidak konsisten, serta transformasi data menjadi format yang lebih sesuai untuk analisis.

* **Data Preprocessing** :
* Kolom yang berisi nilai yang hilang pada **Description** dan **Category** di dataset `tourism_with_id` telah diisi dengan string kosong.
* Gabungan antara **Description** dan **Category** membentuk kolom  **Content** , yang digunakan dalam **content-based filtering** untuk menghitung kesamaan antar destinasi.
* **Matrix Pengguna dan Item** :
* **User-Item Matrix** dibuat dengan menggunakan pivot table, yang menghubungkan pengguna dengan destinasi wisata yang mereka rating. Nilai dalam matriks ini mencerminkan rating yang diberikan oleh pengguna pada setiap tempat wisata.
* **Similarity Calculation** :
* **Cosine Similarity** digunakan untuk menghitung kesamaan antar destinasi wisata berdasarkan deskripsi dan kategori ( **content-based filtering** ), serta antara pengguna berdasarkan rating yang diberikan pada destinasi wisata ( **collaborative filtering** ).

#### Insight Awal dari Data

Dari analisis data awal, dapat disimpulkan bahwa proyek ini memiliki data yang cukup lengkap untuk melakukan rekomendasi destinasi wisata. Dengan dataset yang mencakup informasi pengguna, tempat wisata, dan interaksi pengguna dengan tempat wisata, proyek ini memiliki potensi untuk memberikan rekomendasi yang sangat relevan dan personal kepada pengguna.

Dengan memanfaatkan teknik **content-based filtering** dan  **collaborative filtering** , sistem rekomendasi ini dapat memberikan hasil yang akurat berdasarkan preferensi pengguna yang berbeda-beda.

## Data Preparation

Pada bagian ini, kita akan membahas langkah-langkah yang dilakukan untuk mempersiapkan data yang digunakan dalam proyek rekomendasi destinasi wisata. Tahap ini sangat penting untuk memastikan bahwa data yang digunakan bersih, konsisten, dan siap untuk digunakan dalam model rekomendasi, baik menggunakan **content-based filtering** maupun  **collaborative filtering** .

#### 1. Pengisian Nilai yang Hilang

Pada tahap awal, kita mengecek dataset untuk memastikan tidak ada nilai yang hilang (missing values) pada kolom-kolom penting yang akan digunakan dalam analisis dan perhitungan rekomendasi. Beberapa kolom dalam dataset seperti **Description** dan **Category** pada dataset `tourism_with_id` memiliki nilai yang hilang, sehingga perlu diisi.

* **Kolom `Description` dan `Category`** pada dataset `tourism_with_id` yang memiliki nilai kosong diisi dengan string kosong (`''`). Langkah ini penting agar proses concatenation antara **Description** dan **Category** dapat berjalan tanpa error.
  ```python
  tourism_with_id['Description'] = tourism_with_id['Description'].fillna('')
  tourism_with_id['Category'] = tourism_with_id['Category'].fillna('')
  ```

#### 2. Penggabungan Kolom untuk **Content-Based Filtering**

Untuk  **content-based filtering** , kita memanfaatkan informasi dari kolom **Description** dan  **Category** . Oleh karena itu, kita membuat kolom baru yang bernama  **Content** , yang menggabungkan kedua kolom tersebut. Penggabungan ini akan menghasilkan representasi teks yang lebih lengkap tentang setiap destinasi wisata.

* **Penggabungan kolom `Description` dan `Category`** :

```python
  tourism_with_id['Content'] = tourism_with_id['Description'] + ' ' + tourism_with_id['Category']
```

  Setelah penggabungan ini, kolom **Content** akan berfungsi sebagai representasi tekstual yang digunakan untuk menghitung kesamaan antar destinasi wisata.

#### 3. Pengolahan Data Rating

Data rating yang diberikan oleh pengguna pada destinasi wisata disimpan dalam dataset `tourism_rating`. Agar dapat digunakan dalam perhitungan  **collaborative filtering** , kita perlu mengubah format data ke dalam bentuk  **user-item matrix** , yang menghubungkan pengguna dengan destinasi wisata yang mereka beri rating.

* **Membuat User-Item Matrix** :
  Matriks ini menunjukkan rating yang diberikan setiap pengguna terhadap destinasi wisata tertentu. Jika pengguna belum memberikan rating pada destinasi wisata tertentu, nilai default yang digunakan adalah 0 (mengindikasikan bahwa pengguna tersebut belum menilai tempat tersebut).

```python
  user_item_matrix = rating_with_package.pivot_table(
      index='User_Id',
      columns='Place_Name',
      values='Place_Ratings'
  ).fillna(0)
```

  Di sini, **`pivot_table`** digunakan untuk mengonversi data dari format panjang ke format tabel yang mempermudah analisis lebih lanjut. Kolom-kolomnya adalah nama tempat wisata, sementara barisnya adalah ID pengguna. Nilai dalam tabel adalah rating yang diberikan oleh pengguna terhadap tempat wisata.

#### 4. Pengolahan Data Pengguna

Dataset `user` memuat informasi tentang pengguna, seperti  **User_Id** ,  **Location** , dan  **Age** . Data ini digunakan untuk memberikan konteks pada rekomendasi yang dibuat. Meskipun dataset ini tidak mengalami banyak perubahan atau pembersihan, kolom-kolom ini tetap penting dalam proses analisis dan dapat digunakan untuk mempersonalisasi rekomendasi.

#### 5. Normalisasi Data

Pada tahap ini, dilakukan normalisasi nilai skor prediksi hasil dari  **collaborative filtering** . Tujuan dari normalisasi ini adalah untuk mengubah rentang skor prediksi ke dalam skala yang konsisten, misalnya rentang rating 1-5. Hal ini penting agar rekomendasi yang dihasilkan konsisten dan mudah dipahami oleh pengguna.

* **Normalisasi Skor Prediksi** :
  Setelah menghitung skor prediksi menggunakan  **cosine similarity** , dilakukan normalisasi ke rentang rating 1 hingga 5:

```python
  min_rating, max_rating = 1, 5
  predicted_ratings = ((predicted_ratings - predicted_ratings.min()) /
                       (predicted_ratings.max() - predicted_ratings.min()) *
                       (max_rating - min_rating) + min_rating)
```

  Dengan langkah ini, skor prediksi yang dihitung oleh model rekomendasi dipastikan berada dalam rentang 1-5, yang merupakan rentang yang biasa digunakan untuk memberikan rating pada tempat wisata.

#### 6. Penghitungan Similarity (Cosine Similarity)

Untuk  **content-based filtering** , kita menggunakan **TF-IDF** (Term Frequency - Inverse Document Frequency) untuk mengukur kesamaan antar destinasi wisata berdasarkan konten deskripsi dan kategori. Selanjutnya, **cosine similarity** digunakan untuk menghitung seberapa mirip dua tempat wisata satu sama lain berdasarkan representasi teks mereka.

* **Menghitung Cosine Similarity** :
  Cosine similarity digunakan untuk mengukur kedekatan atau kesamaan antara dua vektor (dalam hal ini, dua destinasi wisata). Nilai similarity yang lebih tinggi menunjukkan bahwa dua destinasi lebih mirip satu sama lain.

```python
  tfidf = TfidfVectorizer(stop_words='english')
  tfidf_matrix = tfidf.fit_transform(tourism_with_id['Content'])
  cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
```

  Di sini, **TfidfVectorizer** digunakan untuk mengubah teks menjadi representasi numerik yang dapat diproses lebih lanjut, dan **cosine_similarity** digunakan untuk menghitung kesamaan antar destinasi.

#### 7. Membuat Dataframe Similarity untuk Pengguna

Pada  **collaborative filtering** , kita menghitung kesamaan antar pengguna berdasarkan rating yang mereka berikan. **Cosine similarity** digunakan untuk mengukur kesamaan preferensi antara pengguna.

* **Membuat Dataframe untuk Similarity Pengguna** :
  Hasil dari **cosine_similarity** antara pengguna disimpan dalam  **user_similarity_df** , yang menghubungkan setiap pengguna dengan pengguna lainnya berdasarkan kesamaan preferensi mereka.

```python
  user_similarity = cosine_similarity(user_item_matrix)
  user_similarity_df = pd.DataFrame(
      user_similarity,
      index=user_item_matrix.index,
      columns=user_item_matrix.index
  )
```

#### 8. Pengecekan Data

Setelah persiapan data, kita memeriksa data yang telah diproses untuk memastikan bahwa tidak ada masalah dalam format atau struktur data. Hal ini termasuk memastikan bahwa semua kolom yang digunakan dalam perhitungan kesamaan dan prediksi telah terisi dengan benar dan tidak ada data yang hilang.

---

#### Kesimpulan

Proses **Data Preparation** dalam proyek ini melibatkan beberapa langkah penting, seperti pengisian nilai yang hilang, penggabungan kolom untuk  **content-based filtering** , pembuatan **user-item matrix** untuk  **collaborative filtering** , dan normalisasi skor prediksi. Semua langkah ini memastikan bahwa data siap digunakan untuk menghasilkan rekomendasi yang akurat dan relevan bagi pengguna.

## Modeling

### Modeling Content-Based Filtering

Content-Based Filtering (CBF) adalah salah satu pendekatan dalam sistem rekomendasi yang memberikan rekomendasi berdasarkan kesamaan konten atau fitur dari item yang telah dipilih atau dinilai oleh pengguna. Dalam kasus proyek ini, destinasi wisata yang telah dipilih atau dinilai oleh pengguna akan dibandingkan dengan destinasi wisata lainnya berdasarkan deskripsi dan kategori yang dimiliki oleh setiap destinasi.

Langkah-langkah utama dalam pembuatan model Content-Based Filtering di proyek ini adalah sebagai berikut:

#### 1. Representasi Teks Destinasi Wisata

Langkah pertama dalam Content-Based Filtering adalah mengonversi teks (deskripsi dan kategori) dari setiap destinasi wisata menjadi representasi numerik yang dapat digunakan dalam perhitungan kesamaan antar destinasi wisata. Pada proyek ini, kita menggunakan **TF-IDF (Term Frequency-Inverse Document Frequency)** untuk mengubah teks menjadi representasi vektor.

* **TF-IDF** adalah teknik yang mengukur pentingnya sebuah kata dalam sebuah dokumen (dalam hal ini, deskripsi dan kategori destinasi wisata) berdasarkan frekuensi kata tersebut dan seberapa jarang kata tersebut muncul di seluruh dokumen (destinasi wisata).

  ```python
  tfidf = TfidfVectorizer(stop_words='english')
  tfidf_matrix = tfidf.fit_transform(tourism_with_id['Content'])
  ```

  Dalam kode di atas, **TfidfVectorizer** mengubah kolom **Content** (yang merupakan gabungan dari deskripsi dan kategori) menjadi matriks vektor numerik. Argumen `stop_words='english'` digunakan untuk menghilangkan kata-kata umum dalam bahasa Inggris yang tidak memberikan informasi penting (seperti "the", "and", "of", dll).

#### 2. Menghitung Cosine Similarity

Setelah mendapatkan matriks TF-IDF, langkah berikutnya adalah menghitung **cosine similarity** antara setiap pasangan destinasi wisata. Cosine similarity adalah ukuran yang mengukur kedekatan atau kesamaan dua vektor dalam ruang vektor.

* **Cosine similarity** memiliki nilai antara 0 hingga 1, di mana 1 menunjukkan bahwa dua destinasi wisata sangat mirip (memiliki kesamaan konten yang sangat tinggi) dan 0 menunjukkan bahwa keduanya tidak memiliki kesamaan.

  ```python
  cosine_sim = cosine_similarity(tfidf_matrix, tfidf_matrix)
  ```

  Di sini, **cosine_similarity** menghitung kesamaan antar semua pasangan destinasi wisata berdasarkan matriks TF-IDF yang telah dibuat sebelumnya. Matriks **cosine_sim** yang dihasilkan berisi nilai kesamaan antara setiap pasangan destinasi wisata.

#### 3. Menghasilkan Rekomendasi Berdasarkan Kesamaan

Setelah menghitung  **cosine similarity** , kita dapat menghasilkan rekomendasi destinasi wisata untuk pengguna. Rekomendasi ini didasarkan pada tingkat kesamaan antara destinasi wisata yang sudah dipilih oleh pengguna dan destinasi wisata lainnya.

* **Fungsi rekomendasi** mengambil nama tempat (misalnya, "Gembira Loka Zoo") dan mengembalikan daftar destinasi wisata paling mirip dengan tempat tersebut, berdasarkan **cosine similarity** yang telah dihitung.

  ```python
  indices = pd.Series(tourism_with_id.index, index=tourism_with_id['Place_Name']).drop_duplicates()

  def recommend(place_name, cosine_sim=cosine_sim, df=tourism_with_id):
      if place_name not in indices:
          return "Place not found in the dataset."

      idx = indices[place_name]
      sim_scores = list(enumerate(cosine_sim[idx]))
      sim_scores = sorted(sim_scores, key=lambda x: x[1], reverse=True)
      sim_scores = sim_scores[1:6]  # Mengambil 5 destinasi paling mirip
      place_indices = [i[0] for i in sim_scores]

      return df.iloc[place_indices][['Place_Name', 'Category', 'Rating']]
  ```

  Pada kode ini:

  * Fungsi **recommend** menerima nama tempat sebagai input dan mencari kesamaan antara tempat tersebut dengan destinasi wisata lainnya menggunakan  **cosine similarity** .
  * **`enumerate(cosine_sim[idx])`** membuat daftar pasangan (indeks, nilai kesamaan) untuk semua destinasi yang memiliki kesamaan dengan tempat yang diberikan.
  * Kemudian, hasilnya diurutkan berdasarkan kesamaan tertinggi, dan 5 destinasi wisata paling mirip diambil dan ditampilkan kepada pengguna, dengan informasi nama tempat, kategori, dan rating.

#### 4. Menampilkan Rekomendasi

Rekomendasi diberikan berdasarkan nama destinasi wisata yang diminta. Misalnya, jika pengguna mencari rekomendasi berdasarkan tempat "Gembira Loka Zoo", sistem akan mengembalikan lima destinasi wisata paling mirip berdasarkan deskripsi dan kategori yang ada.

```python
place_to_recommend = "Gembira Loka Zoo"
recommendations = recommend(place_to_recommend)

print(f"Rekomendasi berdasarkan tempat: {place_to_recommend}\n")
print(recommendations)
```

Hasilnya akan menampilkan daftar destinasi wisata yang memiliki kesamaan tinggi dengan "Gembira Loka Zoo", sehingga pengguna dapat menemukan pilihan wisata serupa yang mungkin menarik untuk dikunjungi.

#### Kesimpulan

Content-Based Filtering memungkinkan sistem rekomendasi untuk memberikan saran berdasarkan konten yang relevan dari destinasi wisata. Dengan menggunakan teknik **TF-IDF** untuk mengonversi teks menjadi representasi numerik dan **cosine similarity** untuk mengukur kesamaan antar destinasi, sistem ini dapat memberikan rekomendasi yang relevan dan personal bagi pengguna, berdasarkan kesamaan konten antara tempat yang sudah mereka pilih atau lihat.

### Modeling Collaborative Filtering

Collaborative Filtering (CF) adalah pendekatan lain dalam sistem rekomendasi yang mengandalkan perilaku pengguna lain (misalnya, rating atau interaksi pengguna dengan item) untuk memberikan rekomendasi. Berbeda dengan Content-Based Filtering yang berdasarkan pada kesamaan konten, Collaborative Filtering fokus pada kesamaan antar pengguna atau item berdasarkan pola interaksi mereka.

Pada proyek ini, Collaborative Filtering digunakan untuk merekomendasikan destinasi wisata berdasarkan interaksi pengguna lain yang memiliki preferensi serupa. Berikut adalah langkah-langkah utama dalam pembuatan model Collaborative Filtering di proyek ini:

#### 1. Matriks Pengguna dan Item (User-Item Matrix)

Langkah pertama adalah membangun  **user-item matrix** . Matriks ini menggambarkan interaksi pengguna dengan destinasi wisata (misalnya, rating yang diberikan oleh pengguna terhadap destinasi wisata tertentu).

* Setiap baris dalam matriks ini mewakili seorang  **pengguna** , dan setiap kolom mewakili  **destinasi wisata** .
* Nilai dalam matriks ini adalah rating yang diberikan pengguna terhadap destinasi wisata, di mana nilai yang tidak ada berarti pengguna tersebut belum memberikan rating untuk destinasi wisata tersebut.

```python
user_item_matrix = rating_with_package.pivot_table(
    index='User_Id',
    columns='Place_Name',
    values='Place_Ratings'
).fillna(0)
```

Di kode di atas, kami menggunakan **pivot_table** untuk mengubah data menjadi user-item matrix di mana `User_Id` adalah indeks (baris), `Place_Name` adalah kolom, dan `Place_Ratings` adalah nilai yang diisi dalam matriks. Nilai yang hilang diisi dengan 0, yang berarti pengguna tersebut tidak memberikan rating pada destinasi wisata tersebut.

#### 2. Menghitung Cosine Similarity Antara Pengguna

Langkah selanjutnya adalah menghitung **cosine similarity** antara pengguna. Cosine similarity mengukur kesamaan antara dua pengguna berdasarkan pola rating yang diberikan oleh keduanya. Jika dua pengguna memberikan rating yang serupa untuk destinasi wisata yang sama, mereka akan memiliki nilai similarity yang tinggi.

```python
user_similarity = cosine_similarity(user_item_matrix)
user_similarity_df = pd.DataFrame(
    user_similarity,
    index=user_item_matrix.index,
    columns=user_item_matrix.index
)
```

Pada kode ini, **cosine_similarity** menghitung kesamaan antara setiap pasangan pengguna berdasarkan user-item matrix yang telah dibuat sebelumnya. Hasilnya adalah matriks kesamaan pengguna di mana setiap elemen menunjukkan seberapa mirip dua pengguna satu sama lain.

#### 3. Menghitung Prediksi Rating untuk Pengguna

Dengan menggunakan  **user similarity** , kita dapat memprediksi rating yang mungkin diberikan oleh seorang pengguna pada destinasi wisata yang belum pernah mereka beri rating. Prediksi rating ini dihitung berdasarkan rating yang diberikan oleh pengguna lain yang mirip.

* Prediksi rating dihitung dengan melakukan **weighted sum** dari rating pengguna lain, di mana bobotnya adalah nilai similarity antara pengguna tersebut dengan pengguna yang ingin diprediksi ratingnya.

```python
def recommend_collaborative(user_id, user_item_matrix, user_similarity_df, top_n=5):
    if user_id not in user_item_matrix.index:
        return "User not found in the dataset."

    # Skor prediksi berdasarkan kesamaan pengguna
    similar_users = user_similarity_df[user_id]
    user_ratings = user_item_matrix.T[user_id]
    weighted_sum = user_item_matrix.T.dot(similar_users)
    normalization_factor = np.abs(similar_users).sum()

    # Menghitung skor akhir
    predicted_ratings = weighted_sum / normalization_factor
    predicted_ratings[user_ratings > 0] = 0  # Hindari tempat yang sudah dinilai pengguna

    # Normalisasi skor menjadi skala 1-5
    min_rating, max_rating = 1, 5
    predicted_ratings = ((predicted_ratings - predicted_ratings.min()) / 
                         (predicted_ratings.max() - predicted_ratings.min()) *
                         (max_rating - min_rating) + min_rating)

    # Mendapatkan top rekomendasi
    recommended_places = predicted_ratings.sort_values(ascending=False).head(top_n)
    return recommended_places
```

Pada kode ini:

* **similar_users** adalah nilai kesamaan antara pengguna yang sedang dianalisis dengan pengguna lainnya.
* **weighted_sum** dihitung dengan mengalikan rating yang diberikan oleh pengguna lain dengan nilai kesamaan pengguna.
* **normalization_factor** adalah jumlah absolut nilai kesamaan pengguna, yang digunakan untuk menormalkan hasil prediksi.
* Prediksi rating untuk destinasi wisata yang sudah pernah dinilai oleh pengguna akan diatur menjadi 0, sehingga tidak dipertimbangkan dalam rekomendasi.

Setelah itu, rating yang diprediksi dinormalisasi dalam rentang nilai 1 hingga 5 agar sesuai dengan skala rating yang digunakan.

#### 4. Menampilkan Rekomendasi

Rekomendasi untuk pengguna diberikan berdasarkan rating yang diprediksi. Fungsi **recommend_collaborative** akan mengembalikan **top_n** destinasi wisata teratas yang diprediksi akan disukai oleh pengguna.

```python
user_to_recommend = 1
recommendations = recommend_collaborative(user_to_recommend, user_item_matrix, user_similarity_df)

print(f"Rekomendasi untuk User ID {user_to_recommend}:\n")
print(recommendations)
```

Output yang dihasilkan akan menunjukkan daftar destinasi wisata yang diprediksi memiliki rating tinggi untuk pengguna tersebut, berdasarkan perilaku pengguna lain yang serupa. Misalnya, untuk pengguna dengan  **User ID 1** , rekomendasi bisa seperti berikut:

```
Rekomendasi untuk User ID 1:

Place_Name
Masjid Agung Trans Studio Bandung    5.000000
Food Junction Grand Pakuwon          4.741935
Sanghyang Heuleut                    4.612053
Museum Nike Ardilla                  4.535736
Keraton Surabaya                     4.502697
```

#### Kesimpulan

Collaborative Filtering memungkinkan sistem rekomendasi untuk memberikan saran berdasarkan kesamaan perilaku antar pengguna. Dengan menggunakan **cosine similarity** untuk mengukur kesamaan antar pengguna dan menghitung  **prediksi rating** , sistem ini dapat merekomendasikan destinasi wisata yang belum pernah dinilai oleh pengguna namun memiliki kesamaan dengan preferensi pengguna lain yang mirip. Pendekatan ini memanfaatkan kekuatan data kolektif dan preferensi pengguna untuk memberikan rekomendasi yang lebih personal dan relevan.

## Evaluation

### 1. **Metrik Evaluasi yang Digunakan**

Pada proyek ini, untuk mengevaluasi kinerja model rekomendasi yang dikembangkan, kami menggunakan empat metrik evaluasi berikut:

* **Precision**
* **Recall**
* **F1-Score**
* **RMSE (Root Mean Square Error)**

Metrik-metrik ini dipilih berdasarkan tujuan proyek, yaitu untuk mengukur sejauh mana model dapat memberikan rekomendasi yang relevan dan akurat dalam konteks prediksi rating tempat wisata oleh pengguna.

### 2. **Penjelasan Hasil Proyek Berdasarkan Metrik Evaluasi**

Berdasarkan hasil evaluasi, model menghasilkan nilai berikut:

* **Precision: 1.0000**
* **Recall: 1.0000**
* **F1-Score: 1.0000**
* **RMSE: 0.6148**

Berikut adalah interpretasi dari hasil ini:

1. **Precision (1.0000)** :

* Nilai Precision yang sempurna (1.0000) menunjukkan bahwa setiap tempat wisata yang diprediksi relevan oleh model benar-benar relevan menurut data aktual. Tidak ada kesalahan prediksi tempat yang dianggap relevan padahal tidak relevan. Artinya, model tidak pernah memberi rekomendasi yang salah terkait relevansi tempat wisata yang dipilih.

1. **Recall (1.0000)** :

* Nilai Recall yang sempurna (1.0000) menunjukkan bahwa model berhasil memprediksi seluruh tempat wisata yang sebenarnya relevan dengan benar. Dengan kata lain, model tidak melewatkan satu pun tempat wisata yang seharusnya relevan menurut pengguna. Semua tempat yang relevan berhasil ditemukan oleh model.

1. **F1-Score (1.0000)** :

* F1-Score yang juga sempurna (1.0000) menunjukkan bahwa model memiliki keseimbangan yang sempurna antara Precision dan Recall. Model ini tidak hanya berhasil memprediksi tempat wisata yang relevan dengan benar (high precision) tetapi juga berhasil menemukan seluruh tempat wisata relevan (high recall).

1. **RMSE (0.6148)** :

* Nilai RMSE yang relatif kecil (0.6148) menunjukkan bahwa rata-rata perbedaan antara rating yang diprediksi dan rating yang sebenarnya tidak terlalu besar. Meskipun nilai ini tidak sempurna, kesalahan prediksi yang terjadi cukup rendah dalam konteks skala rating 1 hingga 5. Dengan kata lain, meskipun ada sedikit perbedaan antara prediksi dan nilai rating yang sebenarnya, perbedaannya masih dalam batas yang dapat diterima.

### 3. **Metrik Evaluasi yang Digunakan untuk Mengukur Kinerja Model**

Berikut adalah penjelasan untuk setiap metrik evaluasi yang digunakan:

1. **Precision** :

* **Precision** mengukur proporsi dari semua prediksi yang dianggap relevan yang sebenarnya benar-benar relevan.
* Formula:
  Precision=TPTP+FP\text{Precision} = \frac{TP}{TP + FP}
  Di mana:
  * **TP (True Positives)** adalah jumlah prediksi relevan yang benar.
  * **FP (False Positives)** adalah jumlah prediksi relevan yang salah.
* Precision membantu untuk mengukur kualitas dari rekomendasi yang diberikan oleh model. Nilai Precision yang tinggi menunjukkan bahwa model memberikan banyak rekomendasi yang relevan dan sedikit yang tidak relevan.

1. **Recall** :

* **Recall** mengukur proporsi dari semua nilai yang sebenarnya relevan yang berhasil diprediksi sebagai relevan oleh model.
* Formula:
  Recall=TPTP+FN\text{Recall} = \frac{TP}{TP + FN}
  Di mana:
  * **FN (False Negatives)** adalah jumlah rating yang sebenarnya relevan tetapi tidak diprediksi relevan oleh model.
* Recall mengukur seberapa baik model dalam menemukan tempat-tempat relevan yang ada. Nilai Recall yang tinggi menunjukkan bahwa model mampu menemukan seluruh tempat relevan dengan baik.

1. **F1-Score** :

* **F1-Score** adalah metrik gabungan antara Precision dan Recall yang memberikan gambaran tentang keseimbangan antara keduanya.
* Formula:
  F1-Score=2×Precision×RecallPrecision+Recall\text{F1-Score} = 2 \times \frac{\text{Precision} \times \text{Recall}}{\text{Precision} + \text{Recall}}
* F1-Score mengukur keseimbangan antara Precision dan Recall. Nilai F1-Score yang tinggi menunjukkan bahwa model tidak hanya memiliki Precision yang tinggi (sedikit kesalahan prediksi relevansi), tetapi juga Recall yang tinggi (menemukan sebagian besar relevansi).

1. **RMSE (Root Mean Square Error)** :

* **RMSE** mengukur seberapa besar rata-rata kesalahan dalam prediksi model. Semakin kecil nilai RMSE, semakin akurat model dalam memprediksi rating.
* Formula:
  RMSE=1n∑i=1n(ypredicted−yactual)2\text{RMSE} = \sqrt{\frac{1}{n} \sum_{i=1}^{n} (y_{\text{predicted}} - y_{\text{actual}})^2}
  Di mana:
  * ypredictedy_{\text{predicted}} adalah rating yang diprediksi oleh model.
  * yactualy_{\text{actual}} adalah rating yang sebenarnya diberikan oleh pengguna.
* RMSE memberikan informasi tentang seberapa akurat model dalam memprediksi nilai numerik. Nilai RMSE yang rendah menunjukkan bahwa model dapat memprediksi rating dengan kesalahan yang kecil.

### 4. **Kesimpulan**

Berdasarkan metrik evaluasi yang digunakan, model rekomendasi yang dikembangkan menunjukkan kinerja yang sangat baik. Semua metrik evaluasi (Precision, Recall, F1-Score) menunjukkan nilai sempurna (1.0000), yang mengindikasikan bahwa model sangat akurat dalam memprediksi relevansi tempat wisata dan tidak melewatkan tempat yang relevan. Sementara itu, nilai RMSE yang rendah (0.6148) menunjukkan bahwa meskipun ada sedikit kesalahan dalam prediksi rating numerik, kesalahan tersebut tidak signifikan. Secara keseluruhan, model ini berhasil mencapai tujuan untuk memberikan rekomendasi tempat wisata yang relevan dan akurat bagi pengguna.
