# Prediksi Harga Saham menggunakan Algoritma Double Exponential Smoothing

sebuah project machine learning yang saya buat untuk menganalisa seberapa akurat kinerja algoritma tersebut untuk memprediksi harga saham

Alur Penelitian :

1. pre-processing dataset untuk membersihkan data dari missing value, data yang tidak perlu, dll
2. membuat model training dan testing
3. implementasi algoritma

# Problem statement
Memprediksi adjusted closing price (adj close) harga saham BBTN menggunakan Riwayat harga saham BBTN selama 8 tahun dengan total 2171 data yang telah dilakukan pre processing.
 ![image](https://user-images.githubusercontent.com/84274028/214829455-6cc52ee8-19f7-4d48-bbfb-e12cb12ad6e9.png)

Sebagai catatan, hari sabtu, minggu, dan tanggal merah tidak dimasukkan ke dataset karena bursa saham libur.

Berikut merupakan plot diagram dari atribut ‘adj close’ (adjusted closing price) dari seluruh dataset
![image](https://user-images.githubusercontent.com/84274028/214829592-fee25dbf-7198-4586-95fd-0c6d9a5ae83a.png)

Untuk mengevaluasi kinerja double exponential secara efektif, digunakan metrics Root Mean Square Error (RMSE), Mean Absolute Percentage Error (MAPE), dan metrics Mean Absolute Error (MAE). Untuk semua metrics, semakin rendah nilai metrics-nya, semakin bagus hasil prediksinya.

# Training dan Validasi
Untuk melakukan prediksi, dibutuhkan data training dan validasi. Di penelitian ini akan menggunakan data 3 tahun sebagai kumpulan data, yang setara dengan 756 hari karena ada sekitar 252 hari perdagangan dalam setahun. Selanjutnya digunakan data 1 tahun berikutnya untuk melakukan validasi sebanyak 252 hari. Dengan kata lain, dibutuhkan 756 + 252 = 1008 hari data untuk training dan validasi model. Model akan di latih menggunakan train set serta hyperparameter ⍺ (alpha) dan β (beta).

![image](https://user-images.githubusercontent.com/84274028/214829855-9a85d7c7-9a2e-49d0-a4d6-5d0686fb8fb2.png)

# Penerapan Algoritma
Pada penerapan metode double exponential smoothing pada dataset ini, saya memvariasikan nilai ⍺ dan β dari 0,01 hingga 0,99 dengan dan memilih nilai optimal untuk nilai ⍺ dan β yang memberikan RMSE terendah pada set validasi.

Dibawah ini Hasil Akhir dari nilai RMSE, MAPE, dan MAE, serta nilai ⍺ dan β yang telah disesuaikan menggunakan validasi set masing-masing.
![image](https://user-images.githubusercontent.com/84274028/214830266-a055554e-052e-47dd-9a7c-29976c1242b4.png)

Didapat MAPE MAE terkecil pada pengujian ke 10 yaitu, MAPE sebesar 1.55% dan MAE sebesar 24.19
