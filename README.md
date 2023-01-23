# Laporan Proyek Machine Learning - Muhammad Fadhel Haidar

## Project Overview

Media sosial merupakan salah satu platform yang sangat populer di era digital saat ini. Namun, di balik kepopulerannya, media sosial juga menyimpan berbagai masalah, salah satunya adalah komentar *toxic*. Komentar *toxic* adalah komentar yang menyebarluaskan ujaran kebencian, menyakiti, atau menyebarkan informasi yang tidak benar. Penelitian menunjukkan bahwa komentar toxic dapat menyebabkan efek negatif pada mental dan emosional pengguna media sosial. Hal ini karena komentar toxic dapat menimbulkan rasa tidak aman, kecemasan, dan depresi pada individu yang menerima komentar tersebut berdasarkan junral [Online Social Networking and Mental Health](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4183915/). Selain itu, komentar *toxic* juga dapat menyebarluaskan propaganda dan menyebarkan informasi yang salah, yang dapat mempengaruhi opini publik dan menyebabkan kerusakan pada lingkungan sosial.

Sistem deteksi komentar *toxic* di media sosial merupakan solusi penting dalam menangani masalah kekerasan verbal yang terjadi di dunia maya. Dengan menggunakan teknologi *Natural Language Processing* (NLP), sistem ini dapat mengidentifikasi komentar yang memiliki konten negatif, seperti penghinaan, kebencian, atau ancaman. Menurut jurnal [Deep Learning applied to NLP](https://arxiv.org/abs/1703.03091), *Natural Language Processing* (NLP) merupakan cara komputer untuk menganalisa, memahami dan memaknai bahasa manusia. Sistem ini juga dapat mengklasifikasikan tingkat keparahan dari komentar tersebut, sehingga dapat memberikan tindakan yang sesuai. Sistem deteksi komentar *toxic* di media sosial dapat menjadi solusi efektif dalam menangani masalah kekerasan verbal di dunia maya. 

Pada sistem yang dibuat kali ini, metode yang digunakan dalam untuk melakukan pendekatan dan penyelesaian masalah adalah 'FastText' dan *Neural Network*. 'FastText' adalah sebuah metode pemrosesan bahasa alami yang menggabungkan teknik-teknik dari kedua metode: *word embedding* dan klasifikasi teks. FastText menggunakan embedding kata yang dibentuk dengan cara mengambil rata-rata dari embedding kata dalam kalimat. Kemudian, embedding kalimat ini digunakan sebagai input untuk jaringan saraf yang digunakan untuk melakukan klasifikasi teks. *Neural network* adalah sebuah metode pemrosesan bahasa alami yang menggunakan jaringan saraf untuk melakukan pemrosesan teks. Neural network dapat digunakan untuk berbagai tipe pemrosesan bahasa alami, seperti klasifikasi teks, penerjemahan, dan pembuatan jawaban. Neural network dapat digunakan untuk mengintegrasikan berbagai jenis data, seperti teks, gambar, dan suara, untuk melakukan pemrosesan yang lebih baik. 

## Business Understanding

Masalah yang telah dibahas sebelumnya adalah komentar toxic yang terjadi di media sosial. Komentar toxic dapat menyebabkan efek negatif pada mental dan emosional pengguna media sosial serta dapat menyebarluaskan propaganda dan informasi yang salah. Solusi yang ditawarkan untuk menangani masalah ini adalah dengan menggunakan sistem deteksi komentar toxic di media sosial yang menggunakan teknologi Natural Language Processing (NLP) dan metode 'FastText' dan Neural Network. 'FastText' digunakan untuk mengambil rata-rata dari embedding kata dalam kalimat dan digunakan sebagai input untuk jaringan saraf untuk melakukan klasifikasi teks. Neural network digunakan untuk melakukan pemrosesan teks dan dapat digunakan untuk mengintegrasikan berbagai jenis data. Bila dilihat dari latar belakang masalah yang sudah dijelaskan sebelumnya, maka didapati pernyataan masalah sebagai berikut:

### Problem Statements

- Bagaimanakah nilai _accuracy_ dari model sistem klasifikasi yang dibuat?
- Bagaimanakan nilai _loss_ dari model sistem klasifikasi yang dibuat?

### Goals

- Mendapatkan nilai _accuracy_ dari model sistem klasifikasi.
- Mendapatkan nilai _loss_ dari model sistem klasifikasi.
 
     ### Solution statements
     Metode yang digunakan untuk membuat sistem klasifikasi adalah 'FastTex' yang merupakan *pre-trained embedding library* untuk proses *embedding* dari kata-kata          yang akan dilatih, 'FastText' merupakan *pre-trained embedding library* yang dikembangkan oleh *Facebook AI Research (FAIR)* untuk melakuka proses vektorisasi dan      klasifikasi dari data *text* menggunakan metode *n-gram characters* sebagai unit terkecilnya. Tujuan dari pemilihan *FastText* adalah untuk meningkatkan performa      dari model.
    
## Data Understanding

Pada *dataset Toxic Comment Classification* terdapat kolom *id,	comment_text,	toxic,	severe_toxic,	obscene,	threat,	insult,	identity_hate,	non_toxic*
- id : merupakan kolom yang berisikan nomor *id* dari masing-masing data *text*.
- comment_text : merupakan kolom untuk data *text* yang nantinya akan diolah dan dilatih.
- toxic : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang bersifat *toxic.
- severe_toxic : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang bersifat sangat *toxic.
- obscene : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang bersifat cabul atau tidak senonoh. 
- threat : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang bersifat ancaman.
- identity_hate : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang bersifat rasis atau menyangkut SARA.


Berdasarkan analisis data yang telah dilakukan, diperoleh jumlah observasi untuk setiap kategori label yang ditunjukan pada tabel beriku.

###### Tabel
| category	 | number of comments |
| :-------------: | :-------------: |
| toxic | 15294 |
| severe_toxic | 1595
| obscene | 8449
| threat	| 478
| insult | 7877
| identity_hate | 1405

Berikut merupakan visualisasi dari distribusi data. 

###### Diagram Distribusi Data
![Data Distribtuion Visualization](https://i.imgur.com/I1QmknU.png)


Setelah mengidentifikasi label-label yang ada pada data, korelasi antar label dianalisis menggunakan library 'seaborn'. Hasil analisis menunjukkan nilai-nilai korelasi antar label yang diperoleh. Berikuit merupakan hasil visualisasi dari korelasi antar data.

###### Visualisasi Korelasi Data
![Heatmap for Data Correlation](https://i.imgur.com/5bLBzpt.png)  


## Data Preparation
Berdasarkan analisis data yang telah dilakukan sebelumnya, didapatkan bahwa dataset yang digunakan masih mengandung nilai-nilai yang tidak relevan untuk digunakan dalam proses pemodelan. Oleh karena itu, dibutuhkan tahap preparasi dataset yang disebut dengan proses data cleaning untuk menghilangkan nilai-nilai yang tidak diperlukan dan membuat dataset menjadi lebih bersih. Tahapan-tahapan yang dilakukan dalam proses data cleaning ini adalah sebagai berikut :

```
# Conerting all strings into lower case
data["comment_text"] = data["comment_text"].str.lower()

# Replacing non-breaking space with a regular space 
data["comment_text"] = data["comment_text"].str.replace("\xa0", " ", regex=False).str.split().str.join(" ")

# Removing extra spaces in text
data["comment_text"] = data["comment_text"].map(lambda x: re.sub(r"\s\s+", " ",x))

# Removing Hyperlinks from text
data["comment_text"] = data["comment_text"].map(lambda x: re.sub(r"https?://\S+|www\.\S+","",x))

# Removing Special characters 
data["comment_text"] = data["comment_text"].map(lambda x: re.sub(r"[^a-zA-Z0-9\s\"\',:;?!.()]", " ",x))

```
Kode program di atas digunakan untuk melakukan proses pre-processing pada kolom "comment_text" dari data. Proses pre-processing ini dilakukan dengan beberapa tahap sebagai berikut:

- Mengubah semua teks menjadi huruf kecil dengan menggunakan fungsi str.lower() pada kolom "comment_text".

- Mengganti non-breaking space dengan spasi reguler dengan menggunakan fungsi str.replace() dan str.split().str.join().

- Menghilangkan spasi yang berlebih pada teks dengan menggunakan fungsi re.sub().

- Menghilangkan hyperlink dari teks dengan menggunakan fungsi re.sub().

- Menghilangkan karakter spesial dari teks dengan menggunakan fungsi re.sub() dan menyimpan karakter yang diizinkan seperti huruf, angka, tanda baca, dan karakter lain yang diperlukan.


## Modeling
Pada bagian ini, data text terlebih dahulu menggunakan *pre-trained embedding* 'FastTex', kemudian didapatkan nilai total *text* yang telah divektorisasi sebagai berikut.

###### FastTex Vectorization
 ```
999995it [00:55, 17924.62it/s]
Loaded 999994 word vectors.
total embedded: 85984 common word
 ```

Kemudian hasil dari vektorisasi digunakan sebagai input untuk model, berikut mmerupakan hasil *summary* untuk model *nerural network* yang digunakan pada sistem ini.

###### Model Summary
```
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
embedding (Embedding)        (None, 200, 300)          57044100  
_________________________________________________________________
bidirectional (Bidirectional (None, 200, 128)          187392    
_________________________________________________________________
dropout (Dropout)            (None, 200, 128)          0         
_________________________________________________________________
global_max_pooling1d (Global (None, 128)               0         
_________________________________________________________________
dropout_1 (Dropout)          (None, 128)               0         
_________________________________________________________________
dense (Dense)                (None, 50)                6450      
_________________________________________________________________
dropout_2 (Dropout)          (None, 50)                0         
_________________________________________________________________
dense_1 (Dense)              (None, 6)                 306       
=================================================================
Total params: 57,238,248
Trainable params: 57,238,248
Non-trainable params: 0
_________________________________________________________________
```

Summary di atas menunjukkan arsitektur dari model yang dibuat dan jumlah parameter yang digunakan oleh setiap lapisan. Setiap lapisan ditunjukkan dengan nama lapisan, tipe lapisan, bentuk output, dan jumlah parameter.

1. Lapisan Embedding memiliki output shape (None, 200, 300) dan memiliki jumlah parameter 57044100. Lapisan ini digunakan untuk mengubah token teks menjadi representasi numerik yang dapat diterima oleh model.

2. Lapisan Bidirectional CuDNNLSTM memiliki output shape (None, 200, 128) dan memiliki jumlah parameter 187392. Lapisan ini digunakan untuk menangkap konteks dari teks.

3. Lapisan Dropout memiliki output shape yang sama dengan lapisan sebelumnya (None, 200, 128) dan tidak memiliki parameter. Lapisan ini digunakan untuk mengurangi overfitting.

4. Lapisan GlobalMaxPool1D memiliki output shape (None, 128) dan tidak memiliki parameter. Lapisan ini digunakan untuk mengambil nilai maksimum dari setiap fitur yang dihasilkan oleh lapisan sebelumnya.

5. Lapisan Dense memiliki output shape (None, 50) dan memiliki jumlah parameter 6450. Lapisan ini digunakan sebagai lapisan fully connected yang digunakan untuk mengubah representasi numerik menjadi prediksi klasifikasi.

6. Lapisan Dense memiliki output shape (None, 6) dan memiliki jumlah parameter 306. Lapisan ini digunakan sebagai lapisan output yang digunakan untuk menghasilkan prediksi klasifikasi.

Total jumlah parameter yang digunakan oleh model adalah 57,238,248 dan semua lapisan dapat di-training.

## Evaluation

Hasil evaluasi di atas menunjukkan hasil dari proses pelatihan model dan evaluasi model pada data validasi. Proses pelatihan dilakukan selama 5 epoch dengan 4488 data latih dan evaluasi dilakukan pada data validasi.

Pada setiap epoch, ditunjukkan nilai loss dan accuracy untuk data latih dan data validasi. Loss digunakan untuk mengukur tingkat kesalahan dari model dalam memprediksi data latih, sedangkan accuracy digunakan untuk mengukur tingkat akurasi model dalam memprediksi data latih.

Pada epoch pertama, nilai loss pada data latih adalah 0.0598 dan nilai accuracy adalah 0.9390, sementara nilai loss pada data validasi adalah 0.0476 dan nilai accuracy adalah 0.9934. Ini menunjukkan bahwa model cukup baik dalam memprediksi data latih dan data validasi.

Pada epoch kedua, nilai loss pada data latih dan data validasi menurun, yaitu 0.0431 dan 0.0459, serta nilai accuracy meningkat pada data latih dan data validasi, yaitu 0.9753 dan 0.9937.

Pada epoch ketiga, nilai loss pada data latih menurun, yaitu 0.0367, tetapi nilai loss pada data validasi meningkat, yaitu 0.0462. Sedangkan nilai accuracy pada data latih menurun, yaitu 0.9665 dan nilai accuracy pada data validasi tetap stabil, yaitu 0.9934.

Pada epoch keempat, nilai loss pada data latih menurun, yaitu 0.0310, tetapi nilai loss pada data validasi meningkat, yaitu 0.0496. Sedangkan nilai accuracy pada data latih menurun drastis, yaitu 0.8930 dan nilai accuracy pada data validasi menurun, yaitu 0.9875.

Pada epoch kelima, nilai loss pada data latih menurun, yaitu 0.0264, tetapi nilai loss pada data validasi meningkat, yaitu 0.0552. Sedangkan nilai accuracy pada data latih menurun drastis, yaitu 0.7515 dan nilai accuracy pada data validasi menurun drastis, yaitu 0.6547.

Dari hasil evaluasi tersebut, dapat disimpulkan bahwa model kurang baik dalam memprediksi data validasi pada epoch keempat dan kelima. Oleh karena itu perlu melakukan perbaikan pada model atau menggunakan data latih yang lebih banyak untuk meningkatkan performa model.

Berikut merupaka hasil visualisasi dari evaluasi model pada data validasi

###### Visualisasi Data Latih
![Visualisasi Evalusai](https://i.imgur.com/CSnDNIX.png0)


###### Hasil Data Uji
```
2000/2000 [==============================] - 16s 8ms/step - loss: 0.0827 - accuracy: 0.6621
Test Loss: 0.08266670256853104
Test Accuracy: 0.6620713472366333
```
Hasil di atas menunjukkan hasil evaluasi dari model yang dilatih pada data uji. Data uji terdiri dari 2000 data yang digunakan untuk mengevaluasi performa model setelah proses pelatihan.

Pada hasil di atas ditunjukkan nilai loss dan accuracy dari data uji. Loss digunakan untuk mengukur tingkat kesalahan dari model dalam memprediksi data uji, sedangkan accuracy digunakan untuk mengukur tingkat akurasi model dalam memprediksi data uji.

Nilai loss pada data uji adalah 0.0827 dan nilai accuracy adalah 0.6621. Ini menunjukkan bahwa model kurang baik dalam memprediksi data uji. Namun, nilai loss dan accuracy yang dihasilkan dari data uji sesuai dengan hasil evaluasi data validasi. Oleh karena itu, perlu melakukan perbaikan pada model atau menggunakan data latih yang lebih banyak untuk meningkatkan performa model.


###### Testing Menggunakan *Text*
```
I was merely apologising for my interference ;)
{'toxic': 0.49575552, 'severe_toxic': 0.00014199194, 'obscene': 0.12559554, 'threat': 0.00037173877, 'insult': 0.019666055, 'identity_hate': 0.001066677, 'non_toxic': 0.5097154}


your blatant pov pushing neither of you guys has made any contribution to this italian history article other than to shove your unhistorical unconstructive modern pov in my face. this is a history article. history. have you heard of that? this is the reason why so many people get pissed off about the pedantry and idiocy and triviality of wikipedia. j sus. get a f cking life.
{'toxic': 0.98362917, 'severe_toxic': 0.06779731, 'obscene': 0.89391726, 'threat': 0.0013799085, 'insult': 0.5765569, 'identity_hate': 0.011462662, 'non_toxic': 0.00090842607}
Actual Values: {'toxic': 1, 'severe_toxic': 0, 'obscene': 1, 'threat': 0, 'insult': 0, 'identity_hate': 0, 'non_toxic': 0}
```
