# Kelompok 5 Final Project

## 1. Descriptive Statistics

Setelah melakukan function info terhadap dataset kita bisa melihat bahwa terdapat 13 variabel berbeda dimana ada 6 variabel dengan tipe data int64 yaitu ['Income', 'Age', 'Experience', 'CURRENT_JOB_YRS', 'CURRENT_HOUSE_YRS']. 

Untuk variable tersebut bisa dikategorikan sebagai tipe data numerical. Selain itu terdapat 6 variabel dengan tipe data object yaitu ['Married/Single', 'Car_Ownership', 'House_Ownership', 'Profession', 'CITY', 'STATE']

Setelah melakukan function describe kita bisa melihat bahwa untuk nilai summary di setiap kolom masih tidak ada masalah. Bisa dilihat bahwa untuk setiap kolom perbedaan antara mean dan median tidak begitu jauh.

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p1.png)

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p2.png)

Di dataset ini tidak terdapat nilai kosong di 13 variabel tersebut.

## 2. Univariate Analysis

Untuk tahap awal univariate analysis kita akan memvisualisasikan tiap distribusi dari data numerik menggunakan boxplot

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p3.png)

Dari distribusi boxplot diatas untuk tipe data yang numerik bisa dilihat bahwa tidak terdapat outlier sama sekali di masing-masing kolom. 

Setelah itu kita bisa melihat distribusinya menggunakan displot atau kdeplot seperti plot dibawah

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p4.png)

Dari distribution plot diatas bisa dilihat bahwa untuk variabel 'Income', 'Age' dan 'Experience' distribusinya mendekati normal. Sedangkan untuk 'CURRENT\_JOB\_YRS' distribusinya skew ke kanan, dimana nilai mean lebih besar daripada nilai median. Terakhir untuk distribusi 'CURRENT\_HOUSE\_YRS' distribusinya merupakan multimodal dimana memiliki beberapa puncak. Di tahap data pre-processing sepertinya perlu di normalisasi agar distribusi yang skew menjadi normal.

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p5.png)

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p6.png)

Untuk data kategorik, dapat dilihat untuk kolom 'Married/Single' didominasi oleh value 'single', kolom 'Car\_Ownership' didominasi oleh value 'no', dan kolom 'House\_Ownership' didominasi oleh value 'rented'. Ketiga kolom tersebut nantinya akan dilakukan encoding untuk mengubah valuenya menjadi numerik.

Untuk kolom 'Profession','CITY', dan 'STATE', memiliki banyak unique value, sehinggauntuk data tersebut akan dilihat apakah kolom tersebut berpengaruh terhadap target atau tidak. Jika tidak akan didrop, jika iya maka akan dilakukan encoding atau dilakukan pengerucutan dulu lalu encoding.

## 3. Multivariate Analysis

Untuk multivariate analysis bisa kita visualisasikan menggunakan heatmap

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p7.png)

## 4. Business Insight

- Total User (Paid Vs Defaulted)

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p8.png)

Presentase user yang default sebesar 12% dengan banyak nya user yang default sebesar 30996 user. 

- Presentase Pinjaman yang berhasil bayar tiap state

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p9.png)

Dari hasil visualisasi diatas dapat kita lihat bahwa Manipur memiliki presentase yang default paling tinggi yaitu sebesar 21% dan yang berhasil bayar yaitu Sikkim.

- Presentase pinjamanyang berhasil bayar tiap profesi

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p10.png)![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p11.png)

Profesi yang paling banyak default yaitu Police\_officer.

- House Ownership

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p12.png)![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p13.png)

Dari hasil visualisasi didaptkan bahwa user yang rented cenderung yang paling banyak melakukan peminjaman dan risk flag yang paling tinggi.

- Presentase pinjaman yang berhasil bayar berdasarkan car ownership

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p14.png)![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p15.png)

User yang paling banyak melakukan pinjaman dan default lebih banyak pada user yang tidak memiliki mobil dibandingkan dengan yang punya mobil. 

- Martial Status

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p16.png)![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p17.png)

- Income dan Risk Flag

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p18.png)

Dari hasil visualisai terlihat bahwa income dan risk flag terdistribusi normal.

- Current Job Years dan Risk Flag

![alt text](https://github.com/drestantav/raka_project_repo/blob/main/gambar/p19.png)

Dari grafik diatas didapat insight sebagai berikut:

- 88% data merupakan user dengan risk flag 0
- Data didominasi oleh user dengan martial status single, no car ownership, rented house ownership, dan user dengan current job years 3-5 tahun
- Presentase user yang berhasil membayar loan relative kecil untuk semua data kategorik (rata-rata kurang dari 20%)
- Distribusi income, age, dan experience uniform
- Distribusi data numerik untuk data dengan risk flag 1 hampir sama
- Perbandingan data kategorik dengan risk flag 0 dan dengan risk flag 1 hampir sama

Dari data yang diperoleh cukup sulit untuk menentukan alasan user gagal melakukan pembayaran, karena sebagian besar distribusi datanya uniform. sehingga kami berhipotesa bahwa alasan user gagal melakukan pembayaran yaitu total loan nya. Untuk mengatasi permasalahan tersebut dan mengurangi default rate dan revenue loss, kami merekomendasikan untuk melakukan segmentasi customer, dimana customer akan dibagi ke dalam beberapa tier berdasarkan data customer, dan jumlah pinjamannya berdasarkan tier customernya.