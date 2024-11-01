#Implementasi Image FilteringPenugasan

**Soal :**

1.buat program dari algoritma dibawah ini
2. buat variabel H (matriks/array) untuk kernel atau filter
3. buat variabel X (matriks/array) untuk  untuk image input/image original
4. buat variabel Y (matrik/array) untuk image output

**Hasil :**

```import numpy as np

# Inisialisasi kernel/filter H (Contoh kernel 3x3 untuk deteksi tepi)
H = np.array([[1, 1, 1],
              [1, 4, 1],
              [1, 1, 1]])

# Inisialisasi gambar input X (Contoh gambar 5x5)
X = np.array([[0, 0, 0, 0, 0, 0],
              [0, 1, 0, 0, 0, 0],
              [0, 1, 1, 1, 0, 0],
              [0, 1, 1, 1, 0, 0],
              [0, 1, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0]])

# Mendapatkan ukuran gambar dan kernel
tinggi_gambar, lebar_gambar = X.shape
tinggi_kernel, lebar_kernel = H.shape

# Inisialisasi gambar output Y dengan nilai nol
Y = np.zeros((tinggi_gambar - tinggi_kernel + 1, lebar_gambar - lebar_kernel + 1))

# Melakukan operasi konvolusi
for x in range(Y.shape[0]):
    for y in range(Y.shape[1]):
        # Perkalian elemen-wise dan penjumlahan
        Y[x, y] = np.sum(X[x:x+tinggi_kernel, y:y+lebar_kernel] * H)

# Menampilkan hasil
print("Gambar output Y:")
print(Y)
```

Gambar output Y:
```
[[ 6.  4.  2.  1.]
 [ 8. 10.  7.  2.]
 [ 8. 10.  7.  2.]
 [ 6.  4.  2.  1.]]
```
