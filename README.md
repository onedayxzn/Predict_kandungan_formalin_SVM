# Klasifikasi Kandungan Formalin pada Mie Basah Menggunakan SVM

Proyek ini bertujuan untuk mengklasifikasikan kandungan formalin dalam mie basah menggunakan data dari electronic nose (e-nose) yang diolah dengan algoritma Support Vector Machine (SVM). Model ini mampu mengkategorikan mie sebagai Aman, Tidak Sehat, atau Bahaya berdasarkan respons sensor terhadap aroma sampel.

## Dataset
Data yang digunakan adalah hasil pembacaan enam sensor gas (TGS2600, TGS2602, TGS2611, TGS2610, TGS2620, dan TGS826) dari sampel mie basah yang diberi tiga konsentrasi formalin berbeda: 0 ppm, 15 ppm, dan 35 ppm

***Deskripsi Fitur:***
- Time (s)	Waktu pembacaan data dalam detik.
- Number	Waktu dalam detik untuk setiap kategori proses.
- TGS2600 - TGS826	Nilai tegangan yang dihasilkan oleh sensor gas.
- Proses	Kategori proses pengukuran oleh e-nose.
   - B (Baseline): Pembacaan daya sensor tanpa sampel uji.
   - S (Sensing): Proses pembauan aroma sampel oleh sensor.
   - P (Purging): Proses pembersihan sensor dengan udara bersih.
- ppm	Konsentrasi kandungan formalin dalam parts per million.
- Kategori	Label Target, ditentukan berdasarkan nilai ppm:
  - Aman: Jika ppm = 0.
  - Tidak Sehat: Jika ppm = 15.
  - Bahaya: Jika ppm = 35.

<br>

## Metodelogi Proyek
Proses analisis dan pemodelan dalam notebook ini mencakup langkah-langkah berikut:

1. Pengumpulan Data: Data dari file-file .xls dengan konsentrasi formalin yang berbeda (0, 15, dan 35 ppm) digabungkan menjadi satu DataFrame tunggal.
2. Pra-pemrosesan Data:
    - Membersihkan data pada kolom Proses.
    - Membuat kolom target Kategori berdasarkan nilai ppm.
    - Mengubah data kategorikal (Proses dan Kategori) menjadi numerik untuk pemodelan.
3. Analisis Data Eksploratif (EDA):
    - Menghitung rerata pembacaan sensor selama fase Sensing untuk setiap konsentrasi formalin.
    - Melakukan uji linearitas dengan menghitung koefisien determinasi (R2) untuk melihat hubungan antara respons sensor dan konsentrasi formalin.
    - Melakukan uji presisi dengan menghitung Coefficient of Variation (CV) untuk mengevaluasi keandalan sensor.
4. Pemodelan SVM:
    - Data dibagi menjadi data latih (80%) dan data uji (20%).
    - Fitur yang digunakan adalah semua sensor TGS dan nilai ppm.
    - Target prediksi adalah kolom Kategori.
    - Model SVM dilatih menggunakan data latih.

## Hasil dan Evaluasi 
Model SVM yang dilatih menunjukkan performa yang sangat tinggi pada data uji, dengan keberhasilan klasifikasi yang sempurna.

***Matriks Kebingungan (Confusion Matrix)***
Matriks kebingungan di bawah ini menunjukkan bahwa tidak ada kesalahan klasifikasi sama sekali pada data uji.
```plaintext
[[1932    0    0]
 [   0 2038    0]
 [   0    0 2143]]
```

***Matriks EValuasi (Evaluation Metrics)***  
Akurasi	100%: Persentase total prediksi yang benar.  
Sensitivitas (Recall)	100%:	Kemampuan model untuk mengidentifikasi semua sampel positif.  
Selektivitas	100%: 	Kemampuan model untuk mengidentifikasi semua sampel negatif.

Tentu, ini adalah README yang dibuat berdasarkan file Jupyter Notebook yang Anda berikan.

Klasifikasi Kandungan Formalin pada Mie Basah Menggunakan SVM
Proyek ini bertujuan untuk mengklasifikasikan kandungan formalin dalam mie basah menggunakan data dari electronic nose (e-nose) yang diolah dengan algoritma Support Vector Machine (SVM). Model ini mampu mengkategorikan mie sebagai Aman, Tidak Sehat, atau Bahaya berdasarkan respons sensor terhadap aroma sampel.

## Dataset
Data yang digunakan adalah hasil pembacaan enam sensor gas (TGS2600, TGS2602, TGS2611, TGS2610, TGS2620, dan TGS826) dari sampel mie basah yang diberi tiga konsentrasi formalin berbeda: 0 ppm, 15 ppm, dan 35 ppm.

Deskripsi Fitur
Nama Kolom	Deskripsi
Time (s)	Waktu pembacaan data dalam detik.
Number	Waktu dalam detik untuk setiap kategori proses.
TGS2600 - TGS826	Nilai tegangan yang dihasilkan oleh sensor gas.
Proses	Kategori proses pengukuran oleh e-nose.
B (Baseline): Pembacaan daya sensor tanpa sampel uji.
S (Sensing): Proses pembauan aroma sampel oleh sensor.
P (Purging): Proses pembersihan sensor dengan udara bersih.
ppm	Konsentrasi kandungan formalin dalam parts per million.
Kategori	Label Target, ditentukan berdasarkan nilai ppm:
Aman: Jika ppm = 0.
Tidak Sehat: Jika ppm = 15.
Bahaya: Jika ppm = 35.

Ekspor ke Spreadsheet
<br>

## Metodologi Proyek
Proses analisis dan pemodelan dalam notebook ini mencakup langkah-langkah berikut:

Pengumpulan Data: Data dari file-file .xls dengan konsentrasi formalin yang berbeda (0, 15, dan 35 ppm) digabungkan menjadi satu DataFrame tunggal.

Pra-pemrosesan Data:

Membersihkan data pada kolom Proses.

Membuat kolom target Kategori berdasarkan nilai ppm.

Mengubah data kategorikal (Proses dan Kategori) menjadi numerik untuk pemodelan.

Analisis Data Eksploratif (EDA):

Menghitung rerata pembacaan sensor selama fase Sensing untuk setiap konsentrasi formalin.

Melakukan uji linearitas dengan menghitung koefisien determinasi (R 
2
 ) untuk melihat hubungan antara respons sensor dan konsentrasi formalin.

Melakukan uji presisi dengan menghitung Coefficient of Variation (CV) untuk mengevaluasi keandalan sensor.

Pemodelan SVM:

Data dibagi menjadi data latih (80%) dan data uji (20%).

Fitur yang digunakan adalah semua sensor TGS dan nilai ppm.

Target prediksi adalah kolom Kategori.

Model SVM dilatih menggunakan data latih.

## Hasil dan Evaluasi
Model SVM yang dilatih menunjukkan performa yang sangat tinggi pada data uji, dengan keberhasilan klasifikasi yang sempurna.

Matriks Kebingungan (Confusion Matrix)
Matriks kebingungan di bawah ini menunjukkan bahwa tidak ada kesalahan klasifikasi sama sekali pada data uji.

```plaintext
Confusion Matrix :
[[1932    0    0]
 [   0 2038    0]
 [   0    0 2143]]
```
Metrik Evaluasi
Hasil evaluasi model diringkas dalam tabel berikut:

Metrik	Nilai	Deskripsi
```plaintext
Akurasi	100%	Persentase total prediksi yang benar.
Sensitivitas (Recall)	100%	Kemampuan model untuk mengidentifikasi semua sampel positif.
Selektivitas	100%	Kemampuan model untuk mengidentifikasi semua sampel negatif.
```

Laporan klasifikasi menunjukkan bahwa nilai precision, recall, dan f1-score untuk setiap kategori (aman, tidak sehat, dan berbahaya) adalah 1.0, yang mengindikasikan performa model yang sempurna.


```plaintext
   precision    recall  f1-score   support

        aman      1.000     1.000     1.000      1932
 tidak sehat      1.000     1.000     1.000      2038
   berbahaya      1.000     1.000     1.000      2143

    accuracy                          1.000      6113
   macro avg      1.000     1.000     1.000      6113
weighted avg      1.000     1.000     1.000      6113
```

## Kesimpulan
Berdasarkan hasil evaluasi, model Support Vector Machine (SVM) yang dikombinasikan dengan data e-nose terbukti sangat efektif dan akurat dalam mengklasifikasikan kandungan formalin pada mie basah. Model ini berhasil mencapai akurasi 100% pada set data yang diuji, menunjukkan potensinya sebagai alat deteksi yang andal.
