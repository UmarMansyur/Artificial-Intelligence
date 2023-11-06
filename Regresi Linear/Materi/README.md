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


Dalam AI, variabel bebas dan variabel terikat akan menjadi parameter penting untuk memprediksi variabel terikat dari variabel bebas tertentu. Algoritma regresi linear memberikan 


|X (Harga per Kilogram) | Y (Total Harga)
---------------------- | ---------------
10000                  | 50000
12000                  | 36000
15000                  | 30000
11000                  | 44000
13000                  | 26000
14000                  | 14000
10500                  | 63000
11500                  | 57500
12500                  | 62500
13500                  | 54000
12500                  | 50000
11800                  | 47200
14500                  | 43500
10800                  | 64800
9500                   | 61750
11000                  | 60500
12000                  | 72000
13000                  | 91000
14000                  | 98000
11500                  | 80500
10500                  | 94500
12250                  | 98000
13500                  | 94500
14250                  | 71250
10250                  | 92250
11750                  | 94150
14500                  | 87000
13250                  | 86000
12000                  | 96000
11500                  | 69000
9500                   | 66500
11000                  | 82500
10500                  | 84000
11800                  | 82600
10800                  | 81000
13500                  | 101250
13000                  | 78000
12750                  | 95500
11250                  | 112500
15000                  | 93000
13500                  | 81000
14500                  | 82500
11000                  | 93500
11750                  | 107250
12800                  | 102400
12500                  | 95000
11500                  | 103500
12000                  | 102000
13000                  | 78000
10500                  | 115500
11250                  | 135000
13000                  | 123500
9500                   | 104500
14000                  | 91000
12500                  | 117500
13250                  | 148750
10800                  | 135000
11750                  | 136250
10250                  | 112750
9500                   | 133000
14500                  | 116500
13500                  | 155250
11800                  | 141100
10500                  | 126000
13000                  | 117000
12000                  | 156000
11250                  | 168750
13250                  | 129250
14000                  | 154000
9500                   | 123500
10800                  | 162000
12250                  | 168750
14500                  | 159750
11000                  | 137500
12750                  | 144375
11500                  | 161500
13500                  | 182250
12500                  | 150000
10500                  | 178500
11250                  | 157500
9500                   | 190000
12000                  | 190000
13000                  | 169000
10800                  | 205200
12250                  | 214125
11750                  | 204750
11250                  | 202500
13500                  | 189750
14500                  | 217250
9500                   | 209750
10500                  | 201900
12500                  | 212500
13000                  | 221000
11000                  | 209000
14000                  | 196000
11800                  | 230600
14500                  | 218750
10800                  | 212400
12750                  | 229500
11250                  | 236250
10250                  | 235250
9500                   | 237500
13500                  | 256500
13000                  | 253000
10500                  | 252000
14000                  | 294000
12250                  | 272750
11750                  | 263750
11800                  | 295400
11250                  | 270000
12000                  | 288000
14500                  | 310250
12500                  | 312500
10800                  | 302400
9500                   | 323000
13500                  | 310500
13000                  | 325000
11000                  | 330000
10500                  | 324500
11250                  | 337500
14500                  | 326750
10250                  | 360750
12500                  | 350000
14000                  | 364000
13500                  | 351000
12000                  | 372000
10800                  | 345600
11750                  | 366250
11250                  | 382500
11000                  | 396000
12250                  | 409375
