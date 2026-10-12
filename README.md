#  Klasifikasi Genre Musik Spotify Menggunakan KNN

##  Deskripsi Project

Project ini merupakan tugas kuliah Machine Learning yang bertujuan untuk mengklasifikasikan genre musik Spotify menggunakan algoritma **K-Nearest Neighbors (KNN)** dengan bahasa pemrograman Python.

Program menggunakan dataset Spotify dalam format CSV. Klasifikasi dilakukan berdasarkan karakteristik audio dari setiap lagu, seperti danceability, energy, loudness, speechiness, acousticness, instrumentalness, liveness, valence, dan tempo.

Melalui project ini, model Machine Learning dilatih untuk memprediksi genre lagu berdasarkan kemiripan karakteristik audio dengan data lagu lainnya.

##  Tujuan Project

1. Memahami penerapan algoritma KNN dalam klasifikasi musik.
2. Mempelajari cara membaca dan mengolah dataset CSV menggunakan Pandas.
3. Melakukan data cleaning untuk mengurangi data duplikat dan data kosong.
4. Memahami proses data splitting menjadi data training dan testing.
5. Menerapkan standardisasi fitur menggunakan StandardScaler.
6. Mengevaluasi performa model menggunakan metrik klasifikasi.

## 🛠️ Teknologi dan Library

Project ini menggunakan Python dan beberapa library berikut:

- **Pandas**: Membaca, membersihkan, dan mengolah dataset Spotify.
- **NumPy**: Mendukung operasi numerik, termasuk pembuatan label untuk confusion matrix.
- **Scikit-learn**: Digunakan untuk data splitting, encoding label, standardisasi fitur, algoritma KNN, dan evaluasi model.

## 📊 Dataset

Dataset yang digunakan adalah dataset Spotify dalam format CSV dengan nama file `spotify.csv`.

Dataset memuat informasi karakteristik audio lagu dan genre musik yang menjadi target klasifikasi.

### Fitur yang Digunakan

| Fitur | Keterangan |
|---|---|
| `danceability` | Tingkat kecocokan lagu untuk menari |
| `energy` | Tingkat intensitas dan energi lagu |
| `loudness` | Tingkat keras suara lagu |
| `speechiness` | Tingkat keberadaan unsur ucapan dalam lagu |
| `acousticness` | Tingkat karakteristik akustik lagu |
| `instrumentalness` | Tingkat kemungkinan lagu tanpa vokal |
| `liveness` | Indikasi karakteristik penampilan langsung |
| `valence` | Gambaran nuansa musik, dari negatif hingga positif |
| `tempo` | Kecepatan lagu dalam satuan BPM |

**Target klasifikasi:** `track_genre`, yaitu genre musik yang akan diprediksi oleh model.

##  Algoritma yang Digunakan

### K-Nearest Neighbors (KNN)

KNN merupakan algoritma Machine Learning yang melakukan prediksi berdasarkan kedekatan suatu data dengan sejumlah tetangga terdekatnya.

Dalam project ini, KNN digunakan untuk mengklasifikasikan genre lagu berdasarkan kemiripan fitur audionya. Nilai K ditentukan menggunakan jumlah terkecil antara 5 dan jumlah data training yang tersedia.

### StandardScaler

StandardScaler digunakan untuk menyamakan skala fitur numerik agar perbedaan rentang nilai tidak terlalu memengaruhi perhitungan jarak pada algoritma KNN.

### LabelEncoder

LabelEncoder digunakan untuk mengubah nama genre musik menjadi angka agar dapat diproses oleh model klasifikasi.

### Train-Test Split

Dataset dibagi menjadi:
- 80% data training untuk melatih model.
- 20% data testing untuk menguji performa model.

Pembagian dilakukan menggunakan `random_state=42` dan `stratify=y` agar proporsi kelas genre tetap terjaga dalam pembagian data.

##  Tahapan Program

1. **Import library** — memanggil library yang dibutuhkan.
2. **Data loading** — membaca dataset `spotify.csv`.
3. **Data cleaning** — merapikan nama kolom, mengubah fitur audio menjadi numerik, memeriksa data kosong, menghapus duplikat, dan membersihkan nama genre.
4. **Menentukan fitur dan target** — menggunakan sembilan fitur audio untuk memprediksi `track_genre`.
5. **Label encoding** — mengubah genre menjadi label numerik.
6. **Data splitting** — membagi dataset menjadi data training dan testing dengan rasio 80:20.
7. **Standardisasi** — menerapkan StandardScaler pada data training dan testing.
8. **Modeling** — melatih model KNN dengan nilai K maksimal 5.
9. **Evaluasi** — mengukur akurasi, menampilkan confusion matrix, serta melihat precision, recall, dan F1-score.

##  Evaluasi Model

Performa model dievaluasi menggunakan beberapa metrik:

- **Accuracy**: Mengukur persentase prediksi genre yang benar.
- **Confusion Matrix**: Menampilkan perbandingan antara genre aktual dan genre hasil prediksi.
- **Precision**: Mengukur ketepatan prediksi pada setiap genre.
- **Recall**: Mengukur kemampuan model mengenali lagu dari setiap genre.
- **F1-score**: Menggabungkan precision dan recall untuk memberikan gambaran performa klasifikasi.

Nilai evaluasi yang sebenarnya diperoleh setelah notebook dijalankan menggunakan dataset.

##  Struktur Project

```text
SPOTIFY-KNN/
├── SPOTIFYDATANEW.ipynb
├── spotify.csv
├── README.md
└── requirements.txt
```

Keterangan:
- `SPOTIFYDATANEW.ipynb`: Notebook yang berisi kode klasifikasi genre musik Spotify.
- `spotify.csv`: Dataset yang digunakan dalam proses klasifikasi.
- `README.md`: Dokumentasi project.
- `requirements.txt`: Daftar library yang diperlukan untuk menjalankan project.

##  Cara Menjalankan Project

### 1. Install Python dan Jupyter Notebook

Pastikan Python dan Jupyter Notebook sudah tersedia di perangkat.

### 2. Install Library

Jalankan perintah berikut di terminal:

```bash
pip install pandas numpy scikit-learn jupyter
```

### 3. Siapkan Dataset

Letakkan file `spotify.csv` di folder yang sama dengan notebook `SPOTIFYDATANEW.ipynb`.

### 4. Buka Notebook

Jalankan perintah:

```bash
jupyter notebook
```

Kemudian buka file `SPOTIFYDATANEW.ipynb`.

Notebook juga dapat dijalankan melalui Visual Studio Code dengan ekstensi Jupyter.

### 5. Jalankan Kode

Jalankan setiap cell secara berurutan dari atas ke bawah untuk melakukan data cleaning, data splitting, pelatihan model KNN, dan evaluasi.

##  Author

**Nama:** Zidan Alfiros  
**Program Studi:** Teknik Informatika  
**Keperluan:** Tugas Laporam Lab Machine Learning

---

Project ini dibuat sebagai sarana pembelajaran untuk memahami penerapan algoritma K-Nearest Neighbors dalam klasifikasi genre musik berdasarkan karakteristik audio menggunakan dataset Spotify.
