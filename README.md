# Laporan Proyek Machine Learning - Muhammad Fadhel Haidar

## Project Overview

Media sosial merupakan salah satu platform yang sangat populer di era digital saat ini. Namun, di balik kepopulerannya, media sosial juga menyimpan berbagai masalah, salah satunya adalah komentar *toxic*. Komentar *toxic* adalah komentar yang menyebarluaskan ujaran kebencian, menyakiti, atau menyebarkan informasi yang tidak benar. Penelitian menunjukkan bahwa komentar toxic dapat menyebabkan efek negatif pada mental dan emosional pengguna media sosial. Hal ini karena komentar toxic dapat menimbulkan rasa tidak aman, kecemasan, dan depresi pada individu yang menerima komentar tersebut berdasarkan junral [Online Social Networking and Mental Health](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4183915/). Selain itu, komentar *toxic* juga dapat menyebarluaskan propaganda dan menyebarkan informasi yang salah, yang dapat mempengaruhi opini publik dan menyebabkan kerusakan pada lingkungan sosial.

Sistem deteksi komentar *toxic* di media sosial merupakan solusi penting dalam menangani masalah kekerasan verbal yang terjadi di dunia maya. Dengan menggunakan teknologi *Natural Language Processing* (NLP), sistem ini dapat mengidentifikasi komentar yang memiliki konten negatif, seperti penghinaan, kebencian, atau ancaman. Menurut jurnal [Deep Learning applied to NLP](https://arxiv.org/abs/1703.03091), *Natural Language Processing* (NLP) merupakan cara komputer untuk menganalisa, memahami dan memaknai bahasa manusia. Sistem ini juga dapat mengklasifikasikan tingkat keparahan dari komentar tersebut, sehingga dapat memberikan tindakan yang sesuai. Sistem deteksi komentar *toxic* di media sosial dapat menjadi solusi efektif dalam menangani masalah kekerasan verbal di dunia maya. 

Pada sistem yang dibuat kali ini, metode yang digunakan dalam untuk melakukan pendekatan dan penyelesaian masalah adalah 'FastText' dan *Neural Network*. 'FastText' adalah sebuah metode pemrosesan bahasa alami yang menggabungkan teknik-teknik dari kedua metode: *word embedding* dan klasifikasi teks. FastText menggunakan embedding kata yang dibentuk dengan cara mengambil rata-rata dari embedding kata dalam kalimat. Kemudian, embedding kalimat ini digunakan sebagai input untuk jaringan saraf yang digunakan untuk melakukan klasifikasi teks. *Neural network* adalah sebuah metode pemrosesan bahasa alami yang menggunakan jaringan saraf untuk melakukan pemrosesan teks. Neural network dapat digunakan untuk berbagai tipe pemrosesan bahasa alami, seperti klasifikasi teks, penerjemahan, dan pembuatan jawaban. Neural network dapat digunakan untuk mengintegrasikan berbagai jenis data, seperti teks, gambar, dan suara, untuk melakukan pemrosesan yang lebih baik. 

## Business Understanding

Masalah yang telah dibahas sebelumnya adalah komentar toxic yang terjadi di media sosial. Komentar toxic dapat menyebabkan efek negatif pada mental dan emosional pengguna media sosial serta dapat menyebarluaskan propaganda dan informasi yang salah. Solusi yang ditawarkan untuk menangani masalah ini adalah dengan menggunakan sistem deteksi komentar toxic di media sosial yang menggunakan teknologi Natural Language Processing (NLP) dan metode 'FastText' dan Neural Network. 'FastText' digunakan untuk mengambil rata-rata dari embedding kata dalam kalimat dan digunakan sebagai input untuk jaringan saraf untuk melakukan klasifikasi teks. Neural network digunakan untuk melakukan pemrosesan teks dan dapat digunakan untuk mengintegrasikan berbagai jenis data. Bila dilihat dari latar belakang masalah yang sudah dijelaskan sebelumnya, maka didapati pernyataan masalah sebagai berikut:

### Problem Statements

- Bagaimanakah nilai _accuracy_ dari model sistem klasifikasi yang dibuat?
- Bagaimanakan nilai _precision_ dari model sistem klasifikasi yang dibuat?
- Bagaimanakan nilai _Recall_ dari model sistem klasifikasi yang dibuat?
- Bagaimanakan nilai _F1-Score_ dari model sistem klasifikasi yang dibuat?

### Goals

- Mendapatkan nilai _accuracy_ dari model sistem klasifikasi.
- Mendapatkan nilai _precision_ dari model sistem klasifikasi.
- Mendapatkan nilai _Recall_ dari model sistem klasifikasi.
- Mendapatkan nilai _F1-Score_ dari model sistem klasifikasi.
 
    ### Solution statements
Metode yang digunakan untuk membuat sistem klasifikasi adalah 'FastTex' yang merupakan *pre-trained embedding library* untuk proses *embedding* dari kata-kata yang akan dilatih, 'FastText' merupakan * pre-trained embedding library* yang dikembangkan oleh *Facebook AI Research (FAIR)* untuk melakuka proses vektorisasi dan klasifikasi dari data *text* menggunakan metode *n-gram characters* sebagai unit terkecilnya. Tujuan dari pemilihan *FastText* adalah untuk meningkat performa dari model.
    
## Data Understanding


Selanjutnya, uraikanlah seluruh variabel atau fitur pada data. Sebagai contoh:  

Variabel-variabel pada Restaurant UCI dataset adalah sebagai berikut:
- accepts : merupakan jenis pembayaran yang diterima pada restoran tertentu.
- cuisine : merupakan jenis masakan yang disajikan pada restoran.
- dst

**Rubrik/Kriteria Tambahan (Opsional)**:
- Melakukan beberapa tahapan yang diperlukan untuk memahami data, contohnya teknik visualisasi data beserta insight atau exploratory data analysis.

## Data Preparation
Pada bagian ini Anda menerapkan dan menyebutkan teknik data preparation yang dilakukan. Teknik yang digunakan pada notebook dan laporan harus berurutan.

**Rubrik/Kriteria Tambahan (Opsional)**: 
- Menjelaskan proses data preparation yang dilakukan
- Menjelaskan alasan mengapa diperlukan tahapan data preparation tersebut.

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

**---Ini adalah bagian akhir laporan---**

_Catatan:_
- _Anda dapat menambahkan gambar, kode, atau tabel ke dalam laporan jika diperlukan. Temukan caranya pada contoh dokumen markdown di situs editor [Dillinger](https://dillinger.io/), [Github Guides: Mastering markdown](https://guides.github.com/features/mastering-markdown/), atau sumber lain di internet. Semangat!_
- Jika terdapat penjelasan yang harus menyertakan code snippet, tuliskan dengan sewajarnya. Tidak perlu menuliskan keseluruhan kode project, cukup bagian yang ingin dijelaskan saja.
