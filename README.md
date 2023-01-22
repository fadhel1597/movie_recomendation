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
- non_toxic : kolom ini merupakan kolom untuk label atau kelas dari dataset yang berisikan kalimat yang btidak termasuk dari 6 label sebelumnya, label *non_toxic* dibuat berdasarkan dari data yang yang tidak memiliki label dan atau sebagai data negatif.

Berdasarkan data yang sudah didapatkan sebelumnya, didapatkan jumlah data untuk masing-masing label sebagai berikut

| category	 | number of comments |
| :-------------: | :-------------: |
| toxic | 15294 |
| severe_toxic | 1595
| obscene | 8449
| threat	| 478
| insult | 7877
| identity_hate | 1405
| non_toxic	| 143346

kemudian dari masing-masing label terdapat nilai nilai korelasi antar label yang didapatkan menggunakan library 'seaborn', didapatkan nilainya sebagai berikut 

![Heatmap for Data Correlation](https://i.imgur.com/eaYtRfg.png)  


## Data Preparation
Beradasarkan data yang sudah didapatkan sebelumnya masih terdapat karakter atau *white space* yang tidak diperlukan, sehingga diperlukannya proses pembersihan dari data sebelum data di-*token* dan dilatih. 



## Modeling
Tahapan ini membahas mengenai model sisten rekomendasi yang Anda buat untuk menyelesaikan permasalahan. Sajikan top-N recommendation sebagai output.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menyajikan dua solusi rekomendasi dengan algoritma yang berbeda.
- Menjelaskan kelebihan dan kekurangan dari solusi/pendekatan yang dipilih.

## Evaluation
Pada bagian ini Anda perlu menyebutkan metrik evaluasi yang digunakan. Kemudian, jelaskan hasil proyek berdasarkan metrik evaluasi tersebut.

Ingatlah, metrik evaluasi yang digunakan harus sesuai dengan konteks data, problem statement, dan solusi yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan formula metrik dan bagaimana metrik tersebut bekerja.
