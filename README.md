# Laporan Proyek Akhir - Machine Learning - Nazrul Effendy

## Project Overview

Tahun 2021 telah terjadi lonjakan MOOC karena adanya pandemi Covid-19. Dengan tersedianya banyak sumber daya baik yang berbayar maupun gratis di internet, para pembelajar memiliki cukup banyak pilihan course yang perlu dipelajari. Proyek ini dilaksanakan untuk membuat Sistem Rekomendasi dan merekomendasikan kursus kepada siswa berdasarkan Keterampilan dan Tingkat Kesulitan yang dipilih oleh siswa. Tautan Kursus juga disediakan, yang dapat ditawarkan oleh Sistem Rekomendasi dengan akses yang mudah. [Zhen and Wang 2024](https://doi.org/10.1016/j.heliyon.2024.e38907), [Zhao et al. 2024](https://doi.org/10.1016/j.procs.2024.08.255), [Ma et al. 2024](https://doi.org/10.1016/j.ipm.2024.103750)

**Rubrik/Kriteria Tambahan (Opsional)**:
- Jelaskan mengapa proyek ini penting untuk diselesaikan.
- Menyertakan hasil riset terkait atau referensi. Referensi yang diberikan harus berasal dari sumber yang kredibel dan author yang jelas.
  
**Referensi:**
1. Ma, Wenjun, Wen Chen, Liuxing Lu, and Xiaomao Fan. 2024. “Integrating Learners’ Knowledge Background to Improve Course Recommendation Fairness: A Multi-Graph Recommendation Method Based on Contrastive Learning.” Information Processing & Management 61 (4): 103750. https://doi.org/10.1016/j.ipm.2024.103750.
2. Zhao, Yuxuan, Chuantao Yin, Xi Wang, Yanmei Chai, Hui Chen, and Yuanxin Ouyang. 2024. “Research of Online Courses Recommendation Based on Deep Learning.” Procedia Computer Science, 11th International Conference on Information Technology and Quantitative Management (ITQM 2024), 242 (January):219–27. https://doi.org/10.1016/j.procs.2024.08.255.
3. Zhen, Aiyuan, and Xin Wang. 2024. “The Deep Learning-Based Physical Education Course Recommendation System under the Internet of Things.” Heliyon 10 (19): e38907. https://doi.org/10.1016/j.heliyon.2024.e38907.


## Business Understanding

Kumpulan data ini diambil dari informasi yang tersedia untuk umum di situs web Coursera pada bulan September 2021 dan dimasukkan secara manual jika data diambil secara tidak benar. Kumpulan data ini dapat digunakan dalam Sistem Rekomendasi untuk mempromosikan kursus Coursera berdasarkan Tingkat Kesulitan dan Keterampilan yang dibutuhkan.

### Problem Statements

Menjelaskan pernyataan masalah:
- Pernyataan Masalah 1
- Pernyataan Masalah 2
- Pernyataan Masalah n

### Goals

Menjelaskan tujuan proyek yang menjawab pernyataan masalah:
- Jawaban pernyataan masalah 1
- Jawaban pernyataan masalah 2
- Jawaban pernyataan masalah n

Semua poin di atas harus diuraikan dengan jelas. Anda bebas menuliskan berapa pernyataan masalah dan juga goals yang diinginkan.

**Rubrik/Kriteria Tambahan (Opsional)**:
- Menambahkan bagian “Solution Approach” yang menguraikan cara untuk meraih goals. Bagian ini dibuat dengan ketentuan sebagai berikut: 

    ### Solution statements
    - Mengajukan 2 atau lebih solution approach (algoritma atau pendekatan sistem rekomendasi).

## Data Understanding
Dataset yang digunakan berasal dari kaggle di link [Coursera Courses Dataset 2021](https://www.kaggle.com/datasets/khusheekapoor/coursera-courses-dataset-2021/data).

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
