# Implementasi Image Filter

**Soal :**

- buat program dari algoritma dibawah ini
- buat variabel H (matriks/array) untuk kernel atau filter
- buat variabel X (matriks/array) untuk  untuk image input/image original
- buat variabel Y (matrik/array) untuk image output
  ```
  For x=0 to picturel .ScaleWidth-1
For to picturel .ScaleHeight-1
for kl to nFilterX-1
for k2=O to nFilterY-1
,k2)*l(x+k1 ,y+k2)
next k2
next kl
next y
Next x
```

# Jawaban

```python
import numpy as np

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
