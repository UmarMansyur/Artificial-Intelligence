# K-Nearest Neighbors
Algoritma KNN merupakan algoritma yang tergolong pada _Lazy Learning_. Jika pada materi sebelumnya anda mengerti tentang splitting data antara data train dan data test maka tentu anda akan mengerti bahwa algoritma KNN tidak membutuhkan data train. Algoritma KNN hanya membutuhkan data test untuk melakukan prediksi. Algoritma KNN juga merupakan algoritma yang paling mudah dipahami karena algoritma ini hanya membandingkan data test dengan data train yang terdekat. Jika anda pernah belajar tentang _Euclidean Distance_ maka anda akan mengerti bahwa algoritma KNN hanya membandingkan jarak antara data test dengan data train. Jika anda belum mengerti tentang _Euclidean Distance_ maka anda bisa membaca materi tentang _Euclidean Distance_ pada link berikut: [Euclidean Distance](https://en.wikipedia.org/wiki/Euclidean_distance).

![Euclidean Distance](https://upload.wikimedia.org/wikipedia/commons/thumb/5/55/Euclidean_distance_2d.svg/1200px-Euclidean_distance_2d.svg.png)

Dari gambar diatas dapat dilihat bahwa _Euclidean Distance_ merupakan jarak antara dua titik. Jika anda pernah belajar tentang _Pythagoras_ maka anda akan mengerti bahwa _Euclidean Distance_ merupakan jarak antara dua titik yang dapat dihitung dengan rumus _Pythagoras_. Rumus _Pythagoras_ dapat dilihat pada gambar berikut:

$$
C = \sqrt{A^2 + B^2}
$$
Dan rumus _Euclidean Distance_ dapat dilihat pada rumus berikut:
$$
d(p,q) = \sqrt{(q_1 - p_1)^2 + (q_2 - p_2)^2 + ... + (q_n - p_n)^2}
$$

Dalam kemiringan rumus _Euclidean Distance_ terdapat variabel $p$ dan $q$. Variabel $p$ merupakan data test dan variabel $q$ merupakan data train. Variabel $n$ merupakan jumlah **_fitur_** yang ada pada data.

## Algoritma KNN
1. Tentukan nilai $k$ yang akan digunakan. Nilai $k$ ini dapat anda tentukan sendiri. Cara menentukan nilai $k$ yang paling ideal adalah dengan mencoba nilai $k$ yang berbeda-beda dan melihat akurasi dari nilai $k$ tersebut. Nilai $k$ yang paling ideal adalah nilai $k$ yang memiliki akurasi paling tinggi.
2. Hitung jarak antara data test dengan data train menggunakan rumus _Euclidean Distance_.
3. Ambil $k$ data train yang memiliki jarak terdekat dengan data test.
4. Tentukan golongan dari data test berdasarkan golongan dari $k$ data train yang memiliki jarak terdekat dengan data test.

## Dataset
Dataset yang akan kita gunakan adalah data tentang penentuan golongan darah. Dataset ini terdiri dari 4 fitur yaitu:
1. Golongan darah
2. Tinggi badan
3. Berat badan
4. Umur

Dataset ini terdiri dari 20 data dengan 4 fitur. Dataset ini dapat anda lihat pada tabel berikut:

| Golongan Darah | Tinggi Badan | Berat Badan | Umur |
| :------------: | :----------: | :---------: | :--: |
|       A        |      180     |     70      |  20  |
|       A        |      170     |     65      |  18  |
|       B        |      165     |     60      |  35  |
|       B        |      170     |     65      |  22  |
|       B        |      175     |     70      |  25  |
|       O        |      180     |     75      |  20  |
|       AB       |      155     |     50      |  20  |
|       AB       |      175     |     70      |  25  |
|      ?        |      180     |     70      |  20  |

Dari data diatas dapat dilihat bahwa data terakhir memiliki golongan darah yang tidak diketahui. Data ini akan kita gunakan untuk melakukan prediksi menggunakan algoritma KNN.
## Implementasi KNN menggunakan Python
Pertama-tama kita akan mengimport library yang akan kita gunakan. Library yang akan kita gunakan adalah _pandas_ dan _numpy_. _Pandas_ digunakan untuk membaca dataset yang berupa file csv dan _numpy_ digunakan untuk melakukan perhitungan matematika.

```python
import pandas as pd
import numpy as np
```

Setelah itu kita akan membaca dataset yang berupa file csv menggunakan _pandas_.

```python
data = pd.read_csv('data.csv')
```
Setelah itu kita akan menentukan nilai $k$ yang akan kita gunakan. Pada contoh ini kita akan menggunakan nilai $k$ sebesar 3.

```python
k = 3
```

Setelah itu kita akan menghitung jarak antara data test dengan data train menggunakan rumus _Euclidean Distance_. Untuk menghitung jarak antara data test dengan data train kita akan menggunakan fungsi _euclideanDistance_ yang akan mengembalikan nilai jarak antara data test dengan data train.

```python
def euclideanDistance(dataTest, dataTrain):
    distance = 0
    for i in range(len(dataTest)):
        distance += np.square(dataTest[i] - dataTrain[i])
    return np.sqrt(distance)
```

Setelah itu kita akan mengambil $k$ data train yang memiliki jarak terdekat dengan data test. Untuk mengambil $k$ data train yang memiliki jarak terdekat dengan data test kita akan menggunakan fungsi _getNeighbors_ yang akan mengembalikan $k$ data train yang memiliki jarak terdekat dengan data test.

```python
def getNeighbors(dataTest, dataTrain, k):
    distances = []
    for i in range(len(dataTrain)):
        distance = euclideanDistance(dataTest, dataTrain[i])
        distances.append((distance, i))
    distances.sort()
    neighbors = []
    for i in range(k):
        neighbors.append(distances[i][1])
    return neighbors
```

Setelah itu kita akan menentukan golongan dari data test berdasarkan golongan dari $k$ data train yang memiliki jarak terdekat dengan data test. Untuk menentukan golongan dari data test berdasarkan golongan dari $k$ data train yang memiliki jarak terdekat dengan data test kita akan menggunakan fungsi _getPrediction_ yang akan mengembalikan golongan dari data test berdasarkan golongan dari $k$ data train yang memiliki jarak terdekat dengan data test.

```python
def getPrediction(dataTest, dataTrain, k):
    neighbors = getNeighbors(dataTest, dataTrain, k)
    countA = 0
    countB = 0
    countO = 0
    countAB = 0
    for i in range(len(neighbors)):
        if dataTrain[neighbors[i]][0] == 'A':
            countA += 1
        elif dataTrain[neighbors[i]][0] == 'B':
            countB += 1
        elif dataTrain[neighbors[i]][0] == 'O':
            countO += 1
        elif dataTrain[neighbors[i]][0] == 'AB':
            countAB += 1
    if countA > countB and countA > countO and countA > countAB:
        return 'A'
    elif countB > countA and countB > countO and countB > countAB:
        return 'B'
    elif countO > countA and countO > countB and countO > countAB:
        return 'O'
    elif countAB > countA and countAB > countB and countAB > countO:
        return 'AB'
```

Setelah itu kita akan melakukan prediksi terhadap data test. Untuk melakukan prediksi terhadap data test kita akan menggunakan fungsi _predict_ yang akan mengembalikan prediksi terhadap data test.

```python
def predict(dataTest, dataTrain, k):
    predictions = []
    for i in range(len(dataTest)):
        predictions.append(getPrediction(dataTest[i], dataTrain, k))
    return predictions
```

Setelah itu kita akan memanggil fungsi _predict_ untuk melakukan prediksi terhadap data test.

```python
predictions = predict(dataTest, dataTrain, k)
```

Setelah itu kita akan menampilkan hasil prediksi.

```python
print(predictions)
```

Kita juga dapat menampilkan akurasi dari prediksi yang kita lakukan. Untuk menampilkan akurasi dari prediksi yang kita lakukan kita akan menggunakan fungsi _accuracy_ yang akan mengembalikan akurasi dari prediksi yang kita lakukan.

```python
def accuracy(predictions, dataTest):
    correct = 0
    for i in range(len(predictions)):
        if predictions[i] == dataTest[i][0]:
            correct += 1
    return (correct / float(len(predictions))) * 100.0
```

## Implementasi KNN menggunakan Scikit Learn

Pertama-tama kita akan mengimport library yang akan kita gunakan. Library yang akan kita gunakan adalah _pandas_ dan _sklearn_. _Pandas_ digunakan untuk membaca dataset yang berupa file csv dan _sklearn_ digunakan untuk melakukan prediksi menggunakan algoritma KNN.

```python
import pandas as pd
from sklearn.neighbors import KNeighborsClassifier
```

Setelah itu kita akan membaca dataset yang berupa file csv menggunakan _pandas_.

```python
data = pd.read_csv('data.csv')
```

Setelah itu kita akan menentukan nilai $k$ yang akan kita gunakan. Pada contoh ini kita akan menggunakan nilai $k$ sebesar 3.

```python
k = 3
```

Setelah itu kita akan memisahkan data train dan data test. Untuk memisahkan data train dan data test kita akan menggunakan fungsi _train_test_split_ yang akan memisahkan data train dan data test.

```python
from sklearn.model_selection import train_test_split
dataTrain, dataTest = train_test_split(data, test_size=0.2)
```

**_"Mengapa kita masih perlu memisahkan data train dan data test? Karena kita perlu memisahkan data train dan data test untuk mengetahui akurasi dari prediksi yang kita lakukan."_**

Setelah itu kita akan melakukan prediksi terhadap data test. Untuk melakukan prediksi terhadap data test kita akan menggunakan fungsi _KNeighborsClassifier_ yang akan melakukan prediksi terhadap data test.

```python
knn = KNeighborsClassifier(n_neighbors=k)
knn.fit(dataTrain[['Tinggi Badan', 'Berat Badan', 'Umur']], dataTrain['Golongan Darah'])
predictions = knn.predict(dataTest[['Tinggi Badan', 'Berat Badan', 'Umur']])
```

Setelah itu kita akan menampilkan hasil prediksi.

```python
print(predictions)
```

Kita juga dapat menampilkan akurasi dari prediksi yang kita lakukan. Untuk menampilkan akurasi dari prediksi yang kita lakukan kita akan menggunakan fungsi _accuracy_score_ yang akan mengembalikan akurasi dari prediksi yang kita lakukan.

```python
from sklearn.metrics import accuracy_score
print(accuracy_score(dataTest['Golongan Darah'], predictions))
```

## Kesimpulan
Dari materi ini dapat disimpulkan bahwa algoritma KNN merupakan algoritma yang tergolong pada _Lazy Learning_. Algoritma KNN merupakan algoritma yang paling mudah dipahami karena algoritma ini hanya membandingkan data test dengan data train yang terdekat. Algoritma KNN juga merupakan algoritma yang paling mudah diimplementasikan karena algoritma ini tidak membutuhkan data train. Algoritma KNN hanya membutuhkan data test untuk melakukan prediksi. Algoritma KNN juga merupakan algoritma yang paling mudah diimplementasikan karena algoritma ini hanya membandingkan jarak antara data test dengan data train. Algoritma KNN juga merupakan algoritma yang paling mudah diimplementasikan karena algoritma ini hanya membandingkan jarak antara data test dengan data train menggunakan rumus _Euclidean Distance_.



