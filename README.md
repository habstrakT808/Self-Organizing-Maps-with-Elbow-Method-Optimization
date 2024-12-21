# Self-Organizing Maps (SOM)

## Deskripsi Proyek
Self-Organizing Maps (SOM) adalah salah satu jenis jaringan syaraf tiruan yang menggunakan pembelajaran tak terawasi (*unsupervised learning*) untuk melakukan clustering data. Proyek ini menerapkan SOM untuk menentukan jumlah cluster optimal menggunakan metode **Elbow** dan mengevaluasi hasil clustering menggunakan **Silhouette Score**.

Pada eksperimen ini, berbagai parameter seperti *learning rate*, *decay rate*, jumlah epoch, dan jumlah cluster diuji untuk mendapatkan hasil clustering yang optimal.

---

## Fitur Utama
1. Implementasi algoritma SOM.
2. Penentuan jumlah cluster optimal dengan metode **Elbow**.
3. Evaluasi kualitas clustering dengan **Silhouette Score**.
4. Visualisasi data dan centroid hasil clustering.

---

## Struktur Proyek

### File Utama
- **`som.py`**: File utama yang berisi implementasi algoritma SOM dan analisis.
- **`Data SOM.csv`**: Dataset yang digunakan untuk eksperimen clustering.

### Fungsi Utama
- **`som(X, lrate, b, max_epoch, n_cluster)`**: Fungsi untuk melatih model SOM.
- **`elbow_method(X, max_cluster)`**: Fungsi untuk menentukan jumlah cluster optimal.
- **`draw(X, target, centroids)`**: Fungsi untuk memvisualisasikan hasil clustering.

---

## Prasyarat
Sebelum menjalankan proyek ini, pastikan Anda telah menginstal pustaka Python berikut:

- `numpy`
- `matplotlib`
- `pandas`
- `scikit-learn`

Instalasi pustaka dapat dilakukan dengan perintah berikut:

```bash
pip install numpy matplotlib pandas scikit-learn
```

---

## Panduan Penggunaan

### 1. Persiapan Data
Dataset **`Data SOM.csv`** harus tersedia di direktori yang sama dengan file skrip. Dataset ini memiliki kolom:
- Fitur A1 hingga A14
- Kolom `CustomerID` dan `Class` yang akan dihapus selama preprocessing.

### 2. Menjalankan Program
Jalankan file Python untuk melatih SOM, menentukan jumlah cluster optimal, dan mengevaluasi hasil clustering:

```bash
python som.py
```

### 3. Output
- Grafik Elbow Method untuk menentukan jumlah cluster optimal.
- Visualisasi clustering dengan centroid yang dihasilkan.
- **Silhouette Score** untuk mengevaluasi kualitas clustering.

---

## Analisis

### 1. Konsep Elbow Method di SOM
Elbow Method digunakan untuk menentukan jumlah cluster optimal dengan menganalisis distorsi (total error) yang terus menurun saat jumlah cluster meningkat. Titik *elbow* menandakan jumlah cluster optimal di mana penambahan cluster tidak memberikan peningkatan signifikan pada hasil clustering.

### 2. Hasil
- **Jumlah cluster optimal:** 2 (berdasarkan Elbow Method).
- **Silhouette Score:** 0.96 (mengindikasikan cluster yang homogen dan terpisah dengan baik).

### 3. Pengaruh Parameter
| Parameter       | Pengaruh                                                                 |
|-----------------|-------------------------------------------------------------------------|
| `lrate`         | Mengontrol kecepatan pembaruan centroid. Nilai besar mempercepat pembaruan. |
| `b`             | Mengurangi *learning rate* seiring waktu untuk konvergensi yang halus.    |
| `max_epoch`     | Menentukan jumlah iterasi pelatihan. Nilai besar meningkatkan presisi.    |
| `n_cluster`     | Menentukan jumlah centroid. Nilai optimal ditemukan dengan Elbow Method. |

---

## Hasil Visualisasi
1. Grafik Elbow Method:
   - Menunjukkan penurunan distorsi dengan peningkatan jumlah cluster.
2. Visualisasi Clustering:
   - Menampilkan titik data dengan warna berdasarkan label cluster dan posisi centroid.

---

## Kesimpulan
Proyek ini menunjukkan bahwa jumlah cluster optimal untuk dataset adalah **2**, yang menghasilkan **Silhouette Score** tinggi, mengindikasikan clustering yang baik. Dengan tuning parameter yang tepat, SOM dapat digunakan untuk analisis clustering yang efektif.

---
