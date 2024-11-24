# Laporan Proyek Akhir - Machine Learning - Nazrul Effendy

## Project Overview

Tahun 2021 telah terjadi pandemi Covid-19. Pada masa pandemi ini, banyak kuliah maupun pelatihan yang tidak dapat dilaksankan secara offline, sehingga lebih banyak dilaksanakan secara online untuk pencegahan penyebaran Covid-19 tersebut. Hal ini mendorong munculnya cukup banyak fasilitas MOOC (Massive Open Online Courses). Dengan tersedianya banyak sumber daya belara secara online tersebut baik yang berbayar maupun gratis, para pembelajar memiliki cukup banyak pilihan course yang perlu dipelajari. Karena itu diperlukan suatu sistem yang dapat memberikan rekomendasi course yang sesuai dengan siswa tersebut. Proyek ini dilaksanakan untuk memberikan rekomendasi course  kepada siswa berdasarkan Keterampilan dan Tingkat Kesulitan yang dipilih oleh siswa. Sistem rekomendasi course yang dibuat menggunakan pendekatan content-based filtering. 

**Rubrik/Kriteria Tambahan (Opsional)**:
- Proyek ini perlu dilaksanakan untuk memberikan rekomendasi course yang sesuai dengan kata kunci yang diberikan oleh pengguna (siswa) sehingga diharapkan dapat membantu siswa dalam memilih course di antara pilihan yang cukup banyak tersebut.
- Hasil-hasil riset yang terkait dengan projek ini antara lain adalah yang dilakukan oleh [Zhen and Wang 2024](https://doi.org/10.1016/j.heliyon.2024.e38907), [Zhao et al. 2024](https://doi.org/10.1016/j.procs.2024.08.255), [Ma et al. 2024](https://doi.org/10.1016/j.ipm.2024.103750).
  
**Referensi:**
1. Ma, Wenjun, Wen Chen, Liuxing Lu, and Xiaomao Fan. 2024. “Integrating Learners’ Knowledge Background to Improve Course Recommendation Fairness: A Multi-Graph Recommendation Method Based on Contrastive Learning.” Information Processing & Management 61 (4): 103750. https://doi.org/10.1016/j.ipm.2024.103750.
2. Zhao, Yuxuan, Chuantao Yin, Xi Wang, Yanmei Chai, Hui Chen, and Yuanxin Ouyang. 2024. “Research of Online Courses Recommendation Based on Deep Learning.” Procedia Computer Science, 11th International Conference on Information Technology and Quantitative Management (ITQM 2024), 242 (January):219–27. https://doi.org/10.1016/j.procs.2024.08.255.
3. Zhen, Aiyuan, and Xin Wang. 2024. “The Deep Learning-Based Physical Education Course Recommendation System under the Internet of Things.” Heliyon 10 (19): e38907. https://doi.org/10.1016/j.heliyon.2024.e38907.


## Business Understanding

Proyek ini dilakukan untuk memberikan rekomendasi courses yang sesuai dengan siswa yang diberi rekomendasi. 

### Problem Statements

Problem statement pada proyek ini:
- Course apa yang direkomendasikan sesuai dengan kata kunci yang diberikan oleh pengguna ?

### Goals

Tujuan proyek ini:
- memberikan rekomendasi course yang dapat diambil sesuai dengan kata kunci yang diberikan oleh pengguna berbasis content.

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Dataset yang digunakan berasal dari kaggle di link [Coursera Courses Dataset 2021](https://www.kaggle.com/datasets/khusheekapoor/coursera-courses-dataset-2021/data). Kumpulan data ini diambil dari informasi yang tersedia untuk umum di situs web Coursera pada bulan September 2021 dan dimasukkan secara manual jika terjadi kekeliruan scrapping tersebut. 

Berikut penjelasan mengenai variabel-variabel pada kolom dataset:
| Variabel | Deskripsi |
| --- | --- |
| Course Name |  Nama course  |
| University | Universitas penyelenggara   |
| Difficulty Level | tingkat kesulitan |
| Course Rating | Rating course  |
| Course URL | Link URL |
| Course Description | Deskripsi course   |
| Skills | skill yang akan dipelajari |

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
