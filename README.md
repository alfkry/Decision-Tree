# REPORT
Saya memilih dataset ini karena tertarik ingin mengetahui seperti apa dan bagaimana wine yang berkualitas

## Deskripsi Data
Dataset ini memliki 1600 data dengan 12 variabel sebagai berikut:
* fixed acidity: Ini menunjukkan kadar keasaman tetap dalam wine, terutama dari asam tartarat. Keasaman ini tidak mudah menguap dan tetap ada selama proses fermentasi. Keasaman ini memengaruhi rasa tajam pada wine.
* volatile acidity: Mengukur keasaman yang dapat menguap, biasanya asam asetat (komponen utama dalam cuka). Volatile acidity yang tinggi dapat memberi aroma dan rasa yang tajam atau tidak enak pada wine, sehingga wine dengan keasaman volatil tinggi biasanya dianggap berkualitas lebih rendah.
* citric acid: Asam sitrat, salah satu asam yang terkandung dalam wine, yang dapat memberikan sedikit rasa segar atau manis. Jumlah asam sitrat yang lebih tinggi dapat menambah kompleksitas rasa pada wine.
* residual sugar: Ini adalah gula yang tersisa setelah fermentasi. Residual sugar berperan dalam tingkat kemanisan wine. Wine dengan residual sugar rendah cenderung lebih kering (tidak manis).
* chlorides: Ini menunjukkan jumlah kandungan garam dalam wine. Kadar klorida yang lebih tinggi dapat memberi rasa asin, yang biasanya tidak diinginkan dalam wine.
* free sulfur dioxide: Sulfur dioksida bebas adalah bagian dari total sulfur dioksida dalam wine yang belum bereaksi. Ini digunakan untuk melindungi wine dari oksidasi dan pertumbuhan mikroorganisme yang tidak diinginkan.
* total sulfur dioxide: Jumlah total sulfur dioksida (bebas dan terikat) dalam wine. Sulfur dioksida adalah pengawet umum dalam industri wine, tetapi jumlah yang terlalu tinggi dapat memengaruhi aroma dan rasa.
* density: Kepadatan wine, yang bisa menjadi indikator alkohol dan kadar gula. Biasanya, wine yang lebih manis memiliki kepadatan lebih tinggi, sementara wine dengan alkohol tinggi memiliki kepadatan yang lebih rendah.
* pH: pH mengukur tingkat keasaman wine. Rentang pH untuk wine biasanya antara 3 hingga 4, di mana angka lebih rendah menunjukkan wine yang lebih asam.
* sulphates: Senyawa sulfat dalam wine berfungsi sebagai antioksidan dan dapat membantu menjaga kualitas wine. Jumlah yang tepat dapat meningkatkan rasa dan tekstur wine, tetapi kadar yang terlalu tinggi dapat memberikan rasa pahit.
* alcohol: Persentase kandungan alkohol dalam wine. Alkohol mempengaruhi tekstur, rasa, dan tubuh dari wine. Wine dengan kadar alkohol tinggi sering dianggap lebih penuh dan bertekstur kaya.
* quality: Variabel ini adalah label yang menunjukkan skor kualitas wine (biasanya dari 0 hingga 10). Nilai ini ditentukan berdasarkan penilaian dari pakar wine yang mencicipi wine tersebut dan menilai kualitasnya.

## Rekomendasi
Berdasarkan analisis Decision Tree terhadap dataset wine, berikut adalah rekomendasi dan saran untuk pengembangan lebih lanjut:

### 1. **Fokus pada Fitur yang Paling Mempengaruhi Kualitas**
   - **Rekomendasi**: Fitur-fitur seperti `alcohol`, `volatile acidity`, dan `sulphates` tampaknya berperan penting dalam penentuan kualitas wine. Produsen wine dapat memfokuskan kontrol kualitas pada fitur-fitur ini selama proses produksi.
   - **Saran Pengembangan**: Lakukan eksperimen dengan lebih banyak variasi pada fitur utama ini untuk memvalidasi korelasi langsungnya dengan kualitas wine. Pengukuran tambahan pada level produksi dan pasca-produksi bisa memperkuat hasil analisis.

### 2. **Penggunaan Teknik Validasi untuk Evaluasi Model yang Lebih Baik**
   - **Rekomendasi**: Untuk meningkatkan keakuratan evaluasi model, gunakan teknik **cross-validation** sehingga hasil yang diperoleh lebih stabil dan tidak bergantung pada satu set data pengujian.
   - **Saran Pengembangan**: Menerapkan k-fold cross-validation pada model Decision Tree atau model lanjutan lainnya, seperti Random Forest, untuk mengurangi kemungkinan overfitting dan mendapatkan estimasi performa model yang lebih andal.

### 3. **Pertimbangkan Penggunaan Model Lain yang Lebih Kuat**
   - **Rekomendasi**: Model Decision Tree memberikan hasil dasar yang cukup baik, tetapi bisa mengalami overfitting. Pertimbangkan penggunaan model **Random Forest** atau **Gradient Boosting** untuk memaksimalkan akurasi dan generalisasi prediksi kualitas wine.
   - **Saran Pengembangan**: Kembangkan model dengan Random Forest untuk melihat apakah performanya lebih stabil dan tidak terlalu terpengaruh oleh outlier dibandingkan Decision Tree tunggal. Model berbasis ensemble seperti ini juga bisa memberikan hasil yang lebih akurat untuk data kompleks seperti wine.

### 4. **Eksplorasi Fitur Interaksi untuk Meningkatkan Presisi**
   - **Rekomendasi**: Beberapa fitur seperti `fixed acidity` dan `volatile acidity` mungkin memiliki hubungan yang saling mempengaruhi dalam penentuan kualitas. Cobalah memasukkan **fitur interaksi** untuk melihat dampaknya pada prediksi.
   - **Saran Pengembangan**: Buat variabel baru berdasarkan interaksi antara fitur, seperti `fixed acidity` × `citric acid`, untuk melihat apakah interaksi ini menghasilkan prediksi yang lebih presisi. Ini dapat diuji dengan model pohon atau regresi yang mendukung interaksi fitur.

### 5. **Optimasi Hyperparameter untuk Model yang Lebih Baik**
   - **Rekomendasi**: Lakukan pencarian hyperparameter menggunakan teknik seperti **Grid Search** atau **Randomized Search** untuk menemukan parameter optimal seperti `max_depth`, `min_samples_split`, dan `min_samples_leaf`.
   - **Saran Pengembangan**: Gunakan Grid Search untuk mencari kombinasi terbaik dari parameter Decision Tree. Mengoptimalkan parameter ini dapat membantu model mencapai keseimbangan antara akurasi dan generalisasi.

### 6. **Tingkatkan Visualisasi untuk Analisis yang Lebih Kaya**
   - **Rekomendasi**: Visualisasi tambahan dapat membantu memahami struktur pohon dan pengaruh fitur lebih baik. Pertimbangkan menggunakan grafik SHAP atau partial dependence plot untuk menggali dampak fitur secara individual.
   - **Saran Pengembangan**: Gunakan pustaka seperti **SHAP** untuk membuat grafik yang menunjukkan bagaimana setiap fitur mempengaruhi prediksi secara lokal dan global. Ini akan memberikan pandangan yang lebih mendalam tentang bagaimana setiap fitur berkontribusi terhadap kualitas wine yang diprediksi.

### 7. **Ekspansi Dataset dengan Wine Tipe Lain**
   - **Rekomendasi**: Dataset saat ini hanya mencakup red wine. Untuk hasil yang lebih menyeluruh, tambahkan dataset dengan tipe wine yang berbeda, seperti white wine, untuk memahami perbedaan profil kualitas antara berbagai jenis wine.
   - **Saran Pengembangan**: Kumpulkan data dari white wine atau jenis wine lain untuk melihat apakah model yang sama dapat diterapkan atau apakah dibutuhkan model yang berbeda untuk tiap jenis wine.

## Credit
> Yazid Rajif A (4112322011)
