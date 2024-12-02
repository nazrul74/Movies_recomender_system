# Laporan Proyek Akhir - Machine Learning - Nazrul Effendy

## Project Overview

Tahun 2021 telah terjadi pandemi Covid-19. Pada masa pandemi ini, banyak kuliah maupun pelatihan yang tidak dapat dilaksankan secara offline, sehingga lebih banyak dilaksanakan secara online untuk pencegahan penyebaran Covid-19 tersebut. Hal ini mendorong munculnya cukup banyak fasilitas MOOC (Massive Open Online Courses). Dengan tersedianya banyak sumber daya belara secara online tersebut baik yang berbayar maupun gratis, para pembelajar memiliki cukup banyak pilihan course yang perlu dipelajari. Karena itu diperlukan suatu sistem yang dapat memberikan rekomendasi course yang sesuai dengan siswa tersebut. Proyek ini dilaksanakan untuk memberikan rekomendasi course  kepada siswa berdasarkan Keterampilan dan Tingkat Kesulitan yang dipilih oleh siswa. Sistem rekomendasi course yang dibuat menggunakan pendekatan content-based filtering. 

Proyek ini perlu dilaksanakan untuk memberikan rekomendasi course yang sesuai dengan kata kunci yang diberikan oleh pengguna sehingga diharapkan dapat membantu siswa dalam memilih course di antara pilihan yang cukup banyak tersebut. Sistem rekomendasi course dapat dikembangkan berbasis deep learning [Zhen and Wang 2024](https://doi.org/10.1016/j.heliyon.2024.e38907), [Zhao et al. 2024](https://doi.org/10.1016/j.procs.2024.08.255), dan dapat juga diintegrasikan dengan pengetahuan yang telah dimiliki oleh pengguna [Ma et al. 2024](https://doi.org/10.1016/j.ipm.2024.103750).
  
**Referensi:**
1. Ma, Wenjun, Wen Chen, Liuxing Lu, and Xiaomao Fan. 2024. “Integrating Learners’ Knowledge Background to Improve Course Recommendation Fairness: A Multi-Graph Recommendation Method Based on Contrastive Learning.” Information Processing & Management 61 (4): 103750. https://doi.org/10.1016/j.ipm.2024.103750.
2. Zhao, Yuxuan, Chuantao Yin, Xi Wang, Yanmei Chai, Hui Chen, and Yuanxin Ouyang. 2024. “Research of Online Courses Recommendation Based on Deep Learning.” Procedia Computer Science, 11th International Conference on Information Technology and Quantitative Management (ITQM 2024), 242 (January):219–27. https://doi.org/10.1016/j.procs.2024.08.255.
3. Zhen, Aiyuan, and Xin Wang. 2024. “The Deep Learning-Based Physical Education Course Recommendation System under the Internet of Things.” Heliyon 10 (19): e38907. https://doi.org/10.1016/j.heliyon.2024.e38907.


## Business Understanding

Proyek ini dilakukan untuk memberikan rekomendasi course yang sesuai dengan siswa yang diberi rekomendasi. 

### Problem Statements

Problem statement pada proyek ini:
- Course apa yang direkomendasikan sesuai dengan kata kunci yang diberikan oleh pengguna ?

### Goals

Tujuan proyek ini adalah untuk memberikan rekomendasi course yang dapat diambil sesuai dengan kata kunci yang diberikan oleh pengguna berbasis content.

## Solution statements
- Pada proyek ini, diajukan penyelesaian masalah tersebut dengan sistem rekomendasi berbasis konten.

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

Beberapa tahapan yang dilakukan untuk memahami dataset pada proyek ini, antara lain adalah:
1. Mencari ukuran dataset:

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/size.JPG?raw=true"/>
</p>

Dari coding di atas diperoleh dataset tersebut memiliki 3522 baris dan 7 kolom.

2. Mencari jumlah baris yang ada duplikasi dengan baris yang lain:

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/df_duplicate.JPG?raw=true"/>
</p>

Dari coding di atas, terdapat 98 baris yang merupakan duplikasi dari baris yang lain.

3. Menampilkan tipe data setiap kolom pada dataset "df" seperti pada gambar berikut.

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/df_info.JPG?raw=true"/>
</p>

4. Pengecekan jumlah variabel yang bernilai Null

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/df_isnul.JPG?raw=true"/>
</p>

Dari coding di atas, diperoleh bahwa dataset tersebut tidak memiliki variabel yang bernilai Null.

5. Melihat statistik dataset menggunakan coding describe dan hasilnya diperlihatkan pada gambar berikut.

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/df_describe.JPG?raw=true"/>
</p>

## Data Preparation
Teknik data preparation yang dilakukan terdiri dari: 
1. Menghilangkan baris yang terdapat duplikasi dengan baris lain.

```
df.drop_duplicates(inplace=True)
```

2. Membuat suatu fungsi untuk mengganti nama kolom pada suatu dataset

```
def rename_col(col_name):
    col_name = col_name.split(' ')
    col_name = '_'.join(col_name)
    return col_name
```

3. Menampilkan nama kolom sebelum rename, melakukan rename nama kolom dan menampilkan nama kolom setelah rename:

```
print("Columns names before renaming: ", df.columns.to_list())
df.columns = [rename_col(col) for col in df.columns]
print("Columns names after renaming: ", df.columns.to_list())
```

4. Mendefinisikan feature yang dipilih

```
features_selected = ["Course_Name", "Course_Description", "Skills", "Difficulty_Level"]
```

5. membuat dataset baru yang memiliki kolom sesuai feature yang dipilih

```
new_df = df[features_selected]
new_df.head()
```

6. Menggabungkan konten semua fitur untuk membentuk satu fitur, menampilkan 5 baris pertama dataset yang sudah diolah tersebut

```
new_df["description_key_words"] = ['' for i in range(new_df.shape[0])]
for col in features_selected:
    new_df["description_key_words"] += [' ' for i in range(new_df.shape[0])] + new_df[col]
new_df.head()
```

7. Dataset dibuat supaya hanya memiliki kolom Course_Name dan description_key_words

```
new_df = new_df[["Course_Name", "description_key_words"]]
new_df
```

8. Menampilkan isi baris ke 5 dari kolom "description_key_words"

```
new_df["description_key_words"].iloc[5]
```

9. Mendefinisikan my_lematizer dan mendefinisikan fungsi PreprocessText

```
my_lematizer = WordNetLemmatizer()

def PreprocessText(text):

    cleaned_text = re.sub(r'-',' ',text)

    # remove  urls
    cleaned_text = re.sub(r'https?://\S+|www\.\S+|http?://\S+',' ',cleaned_text)
    # remove html tags
    cleaned_text = re.sub(r'<.*?>',' ',cleaned_text)
    # replace all numbers
    cleaned_text = re.sub(r'[0-9]', '', cleaned_text)
    # filtering out miscellaneous text.
    cleaned_text = re.sub(r"\([^()]*\)", "", cleaned_text)
    # remove mentions
    cleaned_text = re.sub('@\S+', '', cleaned_text)
    # removes ponctuations
    cleaned_text = re.sub('[%s]' % re.escape("""!"#$%&'()*+,-./:;<=>?@[\]^_`{|}~"""), '', cleaned_text)

    cleaned_text = re.sub(r'ML',' Machine Learning ',cleaned_text)

    cleaned_text = re.sub(r'DL',' Deep Learning ',cleaned_text)

    cleaned_text = cleaned_text.lower() #
    cleaned_text = cleaned_text.split()

    # apply lematisation
    cleaned_text = ' '.join([my_lematizer.lemmatize(word) for word in cleaned_text])

    return cleaned_text
```

10. Download 'wordnet' dan 'omw-1.4' dari nltk

```
nltk.download('wordnet')
nltk.download('omw-1.4')
```

11. Menerapkan pemrosesan teks pada description_key_words dan menampilkan hasilnya pada iloc 5

```
new_df["description_key_words"] = new_df["description_key_words"].apply(PreprocessText)
new_df["description_key_words"].iloc[5]
```

12. Vectorization

```
vectorizer = CountVectorizer(max_features=10000, stop_words='english')
vectors = vectorizer.fit_transform(new_df["description_key_words"]).toarray()
```

13. Menampilkan bentuk matriks feature dan ukuran kamus

```
print("Shape of feature  matrix: ", vectors.shape)
print("Vocabulary size : ", len(vectorizer.vocabulary_))
```

## Modeling and Results
Sistem rekomendasi untuk menyelesaikan permasalahan ini dibuat berbasis konten. 

1. Membuat fungsi course_id_recommended

```
def course_id_recommended(description, vectorizer, vectors, number_of_recommendation=5):
    # preprocess text
    description = [PreprocessText(description)]

    # Melakukan vectorization
    vect = vectorizer.transform(description)

    # menghitung similarity dengan vektor feature yang lain
    similars_vectors = cosine_similarity(vect, vectors)[0]

    # Mengurutkan nilai similarity dengan urutan ascending (Hasilnya berupa suatu list indices)
    ordered_similars_vectors = list(similars_vectors.argsort())

    # Membalikkan urutan
    reverse_ordered_similars_vectors = [index for index in reversed(ordered_similars_vectors)]

    # Top number_of_recommendation rekomendasi dipilih berdasarkan pada koefiesien similaritay tertinggi
    best_indexs = reverse_ordered_similars_vectors[1:number_of_recommendation]

    return best_indexs
```

Fungsi course_id_recommended terdiri dari beberapa fungsi lain secara berurutan, yaitu 
- preprocess text
- transformasi vectorizer
- menghitung similarity dengan vektor feature yang lain menggunakan cosine_similarity
- Mengurutkan nilai similarity dengan urutan ascending (Hasilnya berupa suatu list indices)
- Membalikkan urutan
- Top number_of_recommendation rekomendasi dipilih berdasarkan pada koefiesien similaritay tertinggi. Dalam hal ini, secara default, number_of_recommendation sama dengan lima rekomendasi. 

Pada fungsi tersebut digunakan fungsi cosine similarity dari scikit-learn. Cosine similarity dihitung menggunakan rumus sebagai berikut [Understanding Cosine Similarity in Python with Scikit-Learn](https://memgraph.com/blog/cosine-similarity-python-scikit-learn):

<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/cosine_similarity.JPG?raw=true"/>
</p>

2. Membuat fungsi recommend_me

```
def recommend_me(description):
    course_index = course_id_recommended(description, vectorizer, vectors, number_of_recommendation=10)
    if course_index != None:
        course_to_recommend = list(new_df.iloc[course_index]["Course_Name"])
        print("Courses yang direkomendasikan ke user: ")
        print("------------------------------------------------------------------")
        for i, course in enumerate(course_to_recommend):
            print(f"\t{i+1}- {course}")
        print("------------------------------------------------------------------")
    else:
        print("Tidak ada course yang direkomendasikan ke anda")
```

3. Menampikan top 9 course yang direkomendasikan ke user dari kata kunci "Python programming

```
recommend_me("Python programming")
```

Dari coding di atas, muncul top 9 courses yang direkomendasikan, yaitu:
<p align="center">
  <img src="https://github.com/nazrul74/courses_recomender_system/blob/main/img/rekomendasi.JPG?raw=true"/>
</p>

## Evaluation
Dari hasil pengujian di atas, diperoleh bahwa 9 course yang direkomendasikan semuanya mengandung kata "Python", sehingga dapat diperoleh tingkat kebenaran rekomendasi tersebut adalah sebesar 9 / 9 atau 100% benar. Evaluasi ini menunjukkan bahwa proyek yang dikerjakan telah dapat menjawab problem statement yang disampaikan sebelumnya. Goals yang diharapkan juga telah berhasil dicapai. Solution statement berupa sistem rekomendasi berbasis konten telah berhasil menyelesaikan masalah yang dibahas sebelumnya.
