# Laporan Proyek Machine Learning - Nama Anda

## Domain Proyek

Kanker merupakan salah satu penyakit yang memiliki dampak kesehatan dan finansial signifikan, baik bagi pasien maupun sistem kesehatan secara keseluruhan. Berdasarkan data dari WHO, jumlah kasus kanker global terus meningkat setiap tahunnya, dengan jenis kanker tertentu seperti kanker paru-paru, payudara, dan kolorektal menjadi penyebab kematian utama di banyak negara. Pengobatan kanker, yang meliputi kemoterapi, radioterapi, imunoterapi, dan bedah, sangat kompleks dan membutuhkan perawatan jangka panjang yang mahalnesia, prediksi biaya terapi kanker semakin relevan dengan meningkatnya jumlah kasus kanker serta tekanan finansial yang dirasakan oleh banyak keluarga pasien .

Menghisi ini, rumah sakit dan penyedia layanan kesehatan memerlukan solusi yang dapat memprediksi biaya layanan kanker secara lebih akurat. Prediksi biaya yang tepat membantu penyedia layanan mengelola anggaran lebih baik dan memberikan estimasi biaya yang transparan bagi pasien. Teknologi kecerdasan buatan (AI) dan *machine learning* telah terbukti efektif dalam memproses data besar dan kompleks, menjadikannya alat yang potensial dalam mengembangkan model prediksi biaya layanan kesehatan, khususnya untuk terapi kanker .


Alasanan Masalah ???

Penyelesaian masalah ini penting karena prediksi yang tepat dapat mengurangi ketidakpastian biaya bagi pasien dan keluarganya serta memungkinkan perencanaan anggaran yang lebih efisien bagi rumah sakit. Model prediksi berbasis AI ini dapat memberikan estimasi yang lebih akurat dengan mempertimbangkan data spesifik pasien, seperti jenis kanker, stadium, serta metode terapi yang digunakan. Hal ini akan mengurangi risiko overestimasi atau underestimasi biaya yang dapat berdampak pada pengelolaan sumber daya di rumah sakit dan kemampuan pasien untuk merencanakan keuangan mereka .

Riset Terkait


Penelitian seenunjukkan bahwa algoritma seperti regresi linear,  *random forest* , dan *gradient boosting* efektif dalam memprediksi biaya layanan kesehatan. Misalnya, studi yang dilakukan oleh perusahaan riset McKinsey & Company menunjukkan bahwa pemanfaatan data historis dengan teknik *machine learning* dapat memperbaiki akurasi prediksi hingga 20-30%, terutama dalam konteks layanan kesehatan dengan variabilitas biaya yang tinggi seperti terapi kanker【6†source】. Riset lain dari jurnal medis BMC [GitHub](https://github.com/ilhamAdhim/machine-learning-terapan-dicoding/blob/main/Submission_1_MLT.ipynb)

vices Research mendukung penggunaan data klinis dan algoritma prediksi untuk memberikan gambaran yang lebih jelas mengenai biaya perawatan dan prediksi kebutuhan sumber daya bagi institusi kesehatan【7†source】.

- Format Referensi: [Judul Referensi](https://scholar.google.com/)  XXX

## Business Understanding


### Problem Statements

Biaya perawatan kanker yang tinggi dan variatif merupakan tantangan besar, baik bagi pasien maupun penyedia layanan kesehatan. Banyak faktor, seperti jenis terapi, stadium kanker, dan kondisi kesehatan pasien, mempengaruhi besaran biaya tersebut. Ketidakmampuan memprediksi biaya dengan akurat sering kali mengakibatkan ketidakstabilan keuangan bagi pasien dan keluarga serta kesulitan pengelolaan anggaran di rumah sakit. Di sisi penyedia layanan, estimasi yang kurang tepat dapat mengganggu alokasi sumber daya yang optimal, menyebabkan masalah ketersediaan layanan di masa mendatang.

Oleh karena itu, diperlukan model prediksi biaya yang mampu memberikan estimasi yang akurat untuk membantu manajemen rumah sakit dalam merencanakan kebutuhan anggaran dan membantu pasien dalam merencanakan biaya perawatan.

### Goals

Tujuan utama dari proyek ini adalah:

1. Membangun model prediksi berbasis *machine learning* yang dapat mengestimasi biaya terapi kanker dengan akurasi tinggi, dengan mempertimbangkan data spesifik pasien, termasuk jenis kanker, stadium, pilihan terapi, dan kondisi lainnya.
2. Memberikan analisis faktor-faktor yang mempengaruhi besarnya biaya perawatan kanker, yang akan berguna bagi rumah sakit dalam menyusun kebijakan biaya dan alokasi sumber daya.
3. Mengurangi ketidakpastian biaya bagi pasien dan keluarganya dengan menyediakan informasi estimasi biaya yang lebih transpara

### Solution statements

* Menerapkan beberapa algoritma *machine learning* seperti  *linear regression* ,  *random forest* , dan *gradient boosting* untuk mengembangkan model prediksi. Setiap algoritma memiliki karakteristik yang berbeda, dan dengan mencoba beberapa algoritma ini, diharapkan dapat ditemukan model dengan kinerja terbaik dalam memprediksi biaya layanan kanker. Setiap model akan dievaluasi menggunakan metrik *Mean Absolute Error* (MAE) dan *Root Mean Squared Error* (RMSE) untuk mengukur akurasinya. MAE memberikan gambaran seberapa besar rata-rata kesalahan prediksi, sementara RMSE lebih sensitif terhadap kesalahan besar, sehingga memungkinkan penilaian yang lebih detail terhadap performa model.
* Menggunakan teknik *hyperparameter tuning* untuk meningkatkan kinerja model. Misalnya, pada model  *random forest* , parameter seperti jumlah *trees* dan kedalaman *tree* dapat disesuaikan untuk mencapai akurasi yang lebih tinggi. Teknik *Grid Search* atau *Random Search* dapat digunakan untuk menemukan kombinasi parameter yang optimal. Hasil dari tuning ini akan dibandingkan dengan baseline model untuk memastikan bahwa tuning parameter memberikan peningkatan yang signifikan dalam performa model. Metrik evaluasi yang digunakan akan tetap sama, yaitu MAE dan RMSE, untuk memastikan konsistensi perbandingan performa antara model yang dituning dan baseline.
* Selain model prediksi, mengembangkan dashboard interaktif yang menampilkan estimasi biaya serta faktor-faktor yang paling mempengaruhi biaya terapi. Dashboard ini akan membantu tim manajemen rumah sakit dalam menganalisis pola biaya dan mengidentifikasi faktor utama yang meningkatkan biaya perawatan. Alat visualisasi ini juga bisa berguna bagi pasien dan keluarga mereka untuk memahami faktor yang mempengaruhi estimasi biaya, yang akan meningkatkan transparansi dan membantu dalam perencanaan finansial.

## Data Understanding

Paragraf awal bagian ini menjelaskan informasi mengenai data yang Anda gunakan dalam proyek. Sertakan juga sumber atau tautan untuk mengunduh dataset. Contoh: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/datasets/Restaurant+%26+consumer+data).

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
