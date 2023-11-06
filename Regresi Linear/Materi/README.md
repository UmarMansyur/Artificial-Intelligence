# Regresi Linear
Secara bahasa regresi linear merupakan gabungan dari kata regresi dan linear. Regresi merupakan metode statistik yang digunakan untuk mengetahui hubungan antara dua variabel atau lebih. Sedangkan linear merupakan suatu garis lurus. Jadi regresi linear merupakan suatu metode statistik yang digunakan untuk mengetahui hubungan antara dua variabel atau lebih yang berbentuk garis lurus. Dalam regresi linear terdapat dua variabel yaitu variabel bebas (X) dan variabel terikat (Y). Variabel bebas merupakan variabel yang digunakan untuk memprediksi variabel terikat. Sedangkan variabel terikat merupakan variabel yang diprediksi. Dirumuskan dalam bentuk persamaan sebagai berikut:

$$
Y = a + bX
$$
Keterangan:
- Y = variabel terikat
- X = variabel bebas
- a = konstanta
- b = koefisien regresi

## Regresi Linear Sederhana

Regresi linear sederhana merupakan regresi linear yang hanya menggunakan satu variabel bebas dan satu variabel terikat. Persamaan regresi linear sederhana dapat dituliskan sebagai berikut:

$$
Y = a + bX
$$
$$
a = \frac{\sum Y \sum X^2 - \sum X \sum XY}{n \sum X^2 - (\sum X)^2}
$$
$$
b = \frac{n \sum XY - \sum X \sum Y}{n \sum X^2 - (\sum X)^2}
$$

Keterangan:

- Y = variabel terikat
- X = variabel bebas
- a = konstanta
- b = koefisien regresi

## Regresi Linear Berganda
Regresi linear berganda merupakan regresi linear yang menggunakan dua variabel bebas atau lebih dan satu variabel terikat. Persamaan regresi linear berganda dapat dituliskan sebagai berikut:

$$
Y = a + b1X1 + b2X2 + b3X3 + ... + bnXn
$$

## Contoh studi kasus
Seorang penjual sepatu ingin mengetahui hubungan antara harga sepatu dengan jumlah sepatu yang terjual. Berikut adalah data yang diperoleh dari penjual sepatu tersebut.

| Harga (X) | Jumlah (Y) |
|-----------|------------|
| 100000    | 20         |
| 150000    | 25         |
| 200000    | 30         |
| 250000    | 35         |
| 300000    | 40         |
| 350000    | 45         |
| 400000    | 50         |
| 450000    | 55         |
| 500000    | 60         |
| 550000    | 65         |
| 600000    | 70         |
| 650000    | 75         |
| 700000    | 80         |
| 750000    | 85         |
| 800000    | 90         |
| 850000    | 95         |
| 900000    | 100        |
| 950000    | 105        |
| 1000000   | 110        |

Dari data tersebut, kita dapat menghitung nilai koefisien korelasi (r) dan koefisien determinasi (r2) untuk mengetahui seberapa kuat hubungan antara harga sepatu dengan jumlah sepatu yang terjual. Berikut adalah langkah-langkah untuk menghitung nilai koefisien korelasi (r) dan koefisien determinasi (r2).

### Langkah 1: Menghitung nilai r
Langkah pertama yang harus dilakukan adalah menghitung nilai r. Berikut adalah rumus untuk menghitung nilai r.

$$
r = \frac{n \sum XY - \sum X \sum Y}{\sqrt{n \sum X^2 - (\sum X)^2} \sqrt{n \sum Y^2 - (\sum Y)^2}}
$$

$$ 
n = 19
$$

$$
\sum X = 9500000
$$

$$
\sum Y = 1710
$$

$$
\sum X^2 = 9025000000000
$$

$$
\sum Y^2 = 2924100
$$

$$
\sum XY = 1627500000
$$

$$
r = \frac{19(1627500000) - (9500000)(1710)}{\sqrt{19(9025000000000) - (9500000)^2} \sqrt{19(2924100) - (1710)^2}}
$$

$$
r = 0.999999999999999
$$

### Langkah 2: Menghitung nilai r2
Langkah kedua yang harus dilakukan adalah menghitung nilai r2. Berikut adalah rumus untuk menghitung nilai r2.

$$
r^2 = 0.999999999999999^2
$$

$$
r^2 = 0.999999999999998
$$

### Langkah 3: Menentukan nilai korelasi
Langkah ketiga yang harus dilakukan adalah menentukan nilai korelasi. Berikut adalah tabel untuk menentukan nilai korelasi.

| Nilai r | Korelasi |
|---------|----------|
| 0.00 - 0.19 | Sangat lemah |
| 0.20 - 0.39 | Lemah |
| 0.40 - 0.59 | Sedang |
| 0.60 - 0.79 | Kuat |
| 0.80 - 1.00 | Sangat kuat |


