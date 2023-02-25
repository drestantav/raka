# Kelompok 5 Final Project

## 1. Data Cleansing

Handle missing values, Handle duplicated data, Handle outliers : Tidak ada missing value, duplicated data, dan Outlier tidak di-handle karena data sudah bagus. 

Feature transformation: pada stage kali ini kelompok 5 melakukan feature transformation menggunakan pipeline dan juga tanpa pipeline menghasilkan distribusi yang sama. Distribusi datanya uniform dan multimodal, maka data tidak akan ditransformasi, karena tidak akan terjadi perubahan (mendekati normal).

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p1.png)

Untuk memastikan konsistensi data, pipeline harus menyertakan setiap langkah yang diperlukan untuk melatih dan menilai set data pelatihan dan pengujian.

Setelah feature engineering pipeline dibuat untuk data numerik dan kategorikal, kita akan menggunakan kelas ColumnTransformer untuk menggabungkannya menjadi satu preprosesor. Kita akan menggunakan fitur numerik dan kategorik yang kita buat sebelumnya untuk menentukan kolom mana yang harus diteruskan ke pipa mana.

Feature Encoding : feature encoding yang digunakan adalah binary encoding pada feature state dan profession karena pada feature ini memiliki banyak nilai kategori yang berbeda-beda. Jika menggunakan one-hot encoding untuk kedua feature ini, maka akan menghasilkan banyak fitur yang dapat menyebabkan masalah overfitting. Binary encoding mengonversi setiap nilai kategori menjadi representasi biner (0 dan 1) dan memungkinkan setiap fitur kategori direpresentasikan dalam jumlah kolom yang lebih sedikit. Dengan jumlah kolom yang lebih sedikit, dapat mengurangi dimensi data dan menghindari masalah overfitting

Selanjutnya dilakukan scalling pada data numerik untuk untuk mengubah rentang nilai dari masing-masing fitur sehingga memiliki skala yang sama. Proses scalling ini dilakukan setelah proses split data train dan data test, karena melakukan scaling sebelum proses split dapat mengakibatkan kebocoran informasi dari data test ke data train, sehingga model yang dihasilkan dapat mengalami overfitting pada data test.

Handle Class Imbalance : Pada dataset loan prediction, kelas minoritas dapat dianggap sebagai kelas yang mewakili pelanggan yang memiliki risiko kredit yang lebih tinggi (Risk_Flag = 1), sementara kelas mayoritas mewakili pelanggan yang memiliki risiko kredit yang lebih rendah (Risk_Flag = 0). Class imbalance dapat menyebabkan model menjadi bias terhadap kelas mayoritas dan memiliki performa yang buruk dalam mengenali kelas minoritas. Oleh karena itu, strategi yang digunakan untuk menangani masalah class imbalance adalah dengan menggunakan class weighting. Class weighting adalah teknik yang digunakan untuk memberikan bobot yang berbeda pada setiap kelas. Dalam kasus dataset loan prediction, kita dapat memberikan bobot yang lebih tinggi pada kelas minoritas (Risk_Flag = 1) dan bobot yang lebih rendah pada kelas mayoritas (Risk_Flag = 0). Dengan memberikan bobot yang berbeda, model akan lebih sensitif terhadap kelas minoritas dan akan lebih cenderung untuk memprediksi dengan benar kelas yang kurang diwakili dalam dataset. Dalam kasus ini, penggunaan class weighting pada dataset loan prediction dapat membantu meningkatkan performa model dalam mengenali pelanggan yang memiliki risiko kredit yang lebih tinggi, yang merupakan kelas minoritas.


## 2. Feature Engineering

Feature Selection : Ada dua kolom yang dibuang yaitu, kolom Id dan CITY. Kolom CITY dibuang karena memilik unique value yang terlalu banyak dan diputuskan untuk menggunakan kolom STATE saja.

Feature Extraction : Tidak ada fitur baru yang dibuat, tetapi ada pecahan dari beberapa fitur kategorikal setelah dilakukan encoding

Feature Tambahan : Fitur yang mungkin perlu ditambahkan : Total amount of loan, Uda berapa kali loan di tempat ini (payment/loan history), Pengeluaran Bulanan, Banyaknya pengajuan pinjaman setiap bulannya., customer creadit score, the lenght of time of the customer has been employed.
