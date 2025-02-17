Daftar fungsi dalam library Numpy:

---
### **Array Manipulation**:

1. **array()** = Mengonversi input (seperti list atau tuple) menjadi array NumPy untuk operasi numerik yang efisien.  
   ```python
   arr = np.array([1, 2, 3, 4])
   print(arr)
   # Output: [1 2 3 4]
   ```

2. **concatenate()** = Menggabungkan dua atau lebih array secara berurutan.  
   ```python
   arr1 = np.array([1, 2, 3])
   arr2 = np.array([4, 5, 6])
   result = np.concatenate((arr1, arr2))
   print(result)
   # Output: [1 2 3 4 5 6]
   ```

3. **expand_dims()** = Menambahkan dimensi baru ke array pada posisi yang ditentukan.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.expand_dims(arr, axis=0)
   print(result)
   # Output: [[1 2 3]]
   ```

4. **flip()** = Membalik urutan elemen dalam array sepanjang sumbu tertentu.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.flip(arr)
   print(result)
   # Output: [5 4 3 2 1]
   ```

5. **ravel()** = Mengembalikan tampilan array satu dimensi dari array input tanpa menyalin data.  
   ```python
   arr = np.array([[1, 2], [3, 4], [5, 6]])
   result = np.ravel(arr)
   print(result)
   # Output: [1 2 3 4 5 6]
   ```

6. **reshape()** = Mengubah bentuk (dimensi) sebuah array tanpa mengubah datanya.  
   ```python
   arr = np.array([1, 2, 3, 4, 5, 6])
   result = arr.reshape(2, 3)
   print(result)
   # Output: 
   # [[1 2 3]
   #  [4 5 6]]
   ```

7. **roll()** = Menggulung (menggeser) elemen dalam array sepanjang sumbu yang ditentukan.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.roll(arr, 2)
   print(result)
   # Output: [4 5 1 2 3]
   ```

8. **stack()** = Menggabungkan array di sepanjang sumbu baru; terdapat varian seperti hstack() dan vstack() untuk penggabungan horizontal dan vertikal.  
   ```python
   arr1 = np.array([1, 2, 3])
   arr2 = np.array([4, 5, 6])
   result = np.stack((arr1, arr2), axis=0)  # Vertikal
   print(result)
   # Output: 
   # [[1 2 3]
   #  [4 5 6]]
   ```

9. **squeeze()** = Menghapus dimensi tunggal dari array, sehingga mengurangi jumlah dimensi tanpa mengubah data.  
   ```python
   arr = np.array([[[1], [2], [3]]])
   result = np.squeeze(arr)
   print(result)
   # Output: [1 2 3]
   ```

10. **transpose()** = Mengembalikan transpos (pertukaran baris dan kolom) dari array.  
    ```python
    arr = np.array([[1, 2], [3, 4]])
    result = np.transpose(arr)
    print(result)
    # Output: 
    # [[1 3]
    #  [2 4]]
    ```

---

### **Statistical Functions**

1. **mean()** = Menghitung nilai rata-rata dari elemen-elemen dalam array.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.mean(arr)
   print(result)
   # Output: 3.0
   ```

2. **median()** = Menghitung nilai median dari data dalam array.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.median(arr)
   print(result)
   # Output: 3.0
   ```

3. **std()** = Menghitung standar deviasi, ukuran sebaran data dalam array.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.std(arr)
   print(result)
   # Output: 1.4142135623730951
   ```

4. **var()** = Menghitung varians, ukuran dispersi data di sekitar rata-rata.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.var(arr)
   print(result)
   # Output: 2.0
   ```

5. **sum()** = Menjumlahkan semua elemen dalam array, atau sepanjang sumbu tertentu.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.sum(arr)
   print(result)
   # Output: 15
   ```

6. **prod()** = Mengalikan semua elemen dalam array untuk menghasilkan hasil perkalian total.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.prod(arr)
   print(result)
   # Output: 120
   ```

7. **min()** = Mengembalikan nilai minimum dari array.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.min(arr)
   print(result)
   # Output: 1
   ```

8. **max()** = Mengembalikan nilai maksimum dari array.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.max(arr)
   print(result)
   # Output: 5
   ```

9. **argmin()** = Mengembalikan indeks elemen dengan nilai minimum.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.argmin(arr)
   print(result)
   # Output: 0
   ```

10. **argmax()** = Mengembalikan indeks elemen dengan nilai maksimum.  
    ```python
    arr = np.array([1, 2, 3, 4, 5])
    result = np.argmax(arr)
    print(result)
    # Output: 4
    ```

11. **unique()** = Mengembalikan array berisi elemen-elemen unik (tanpa duplikasi) dari array input.  
    ```python
    arr = np.array([1, 2, 2, 3, 3, 3])
    result = np.unique(arr)
    print(result)
    # Output: [1 2 3]
    ```

12. **sort()** = Mengembalikan array yang telah diurutkan.  
    ```python
    arr = np.array([5, 2, 3, 1, 4])
    result = np.sort(arr)
    print(result)
    # Output: [1 2 3 4 5]
    ```

13. **argsort()** = Mengembalikan indeks yang akan mengurutkan array sehingga elemen muncul dalam urutan naik.  
    ```python
    arr = np.array([5, 2, 3, 1, 4])
    result = np.argsort(arr)
    print(result)
    # Output: [3 1 2 4 0]
    ```

13. **cumsum()** = Menghitung jumlah kumulatif elemen dalam array.  
    ```python
    arr = np.array([1, 2, 3, 4, 5])
    result = np.cumsum(arr)
    print(result)
    # Output: [ 1  3  6 10 15]
    ```

14. **cumprod()** = Menghitung hasil perkalian kumulatif dari elemen-elemen dalam array.  
    ```python
    arr = np.array([1, 2, 3, 4, 5])
    result = np.cumprod(arr)
    print(result)
    # Output: [  1   2   6  24 120]
    ```

15. **histogram()** = Menghitung histogram dari data, yaitu mengelompokkan data ke dalam bin dan menghitung frekuensinya.  
    ```python
    arr = np.array([1, 2, 2, 3, 3, 3, 4])
    result = np.histogram(arr, bins=4)
    print(result)
    # Output: (array([0, 2, 3, 2]), array([1. , 2.25, 3.5 , 4.75, 6. ]))
    ```

---

### **Mathematical Operations**

1. **dot()** = Menghitung produk dot (perkalian matriks) antara dua array.  
   ```python
   arr1 = np.array([1, 2, 3])
   arr2 = np.array([4, 5, 6])
   result = np.dot(arr1, arr2)
   print(result)
   # Output: 32
   ```

2. **matmul()** = Melakukan perkalian matriks menggunakan operator @ atau fungsi matmul().  
   ```python
   arr1 = np.array([[1, 2], [3, 4]])
   arr2 = np.array([[5, 6], [7, 8]])
   result = np.matmul(arr1, arr2)
   print(result)
   # Output: [[19 22]
   #          [43 50]]
   ```

3. **exp()** = Mengembalikan nilai eksponensial (e^x) untuk setiap elemen dalam array.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.exp(arr)
   print(result)
   # Output: [ 2.71828183  7.3890561  20.08553692]
   ```

4. **log()** = Menghitung logaritma natural dari masing-masing elemen dalam array.  
   ```python
   arr = np.array([1, np.e, np.e**2])
   result = np.log(arr)
   print(result)
   # Output: [0. 1. 2.]
   ```

5. **sqrt()** = Mengembalikan akar kuadrat dari setiap elemen dalam array.  
   ```python
   arr = np.array([1, 4, 9])
   result = np.sqrt(arr)
   print(result)
   # Output: [1. 2. 3.]
   ```

6. **power()** = Menaikkan setiap elemen array ke pangkat tertentu.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.power(arr, 2)
   print(result)
   # Output: [1 4 9]
   ```

7. **abs()** = Mengembalikan nilai absolut dari setiap elemen dalam array.  
   ```python
   arr = np.array([-1, -2, 3])
   result = np.abs(arr)
   print(result)
   # Output: [1 2 3]
   ```

---

### **Data Filtering and Selection**

1. **where()** = Mengembalikan indeks elemen yang memenuhi kondisi tertentu, berguna untuk filtering data.  
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   result = np.where(arr > 3)
   print(result)
   # Output: (array([3, 4]),)
   ```

2. **nonzero()** = Mengembalikan indeks elemen-elemen yang bukan nol dari array.  
   ```python
   arr = np.array([0, 1, 0, 3, 0])
   result = np.nonzero(arr)
   print(result)
   # Output: (array([1, 3]),)
   ```

3. **clip()** = Membatasi nilai dalam array sehingga tidak melebihi batas minimum dan maksimum yang ditentukan.  
   ```python
   arr = np.array([1, 5, 10, 15, 20])
   result = np.clip(arr, 5, 15)
   print(result)
   # Output: [ 5  5 10 15 15]
   ```

4. **isnan()** = Mengembalikan array boolean yang menandai elemen mana yang merupakan NaN (Not a Number).  
   ```python
   arr = np.array([1, 2, np.nan, 4])
   result = np.isnan(arr)
   print(result)
   # Output: [False False  True False]
   ```

5. **isfinite()** = Mengembalikan array boolean yang menandakan apakah elemen dalam array merupakan nilai finite.  
   ```python
   arr = np.array([1, np.inf, -np.inf, np.nan])
   result = np.isfinite(arr)
   print(result)
   # Output: [ True False False False]
   ```

---

### **File I/O**

1. **loadtxt()** = Membaca data dari file teks dan mengembalikan array NumPy.  
   ```python
   # Misalkan ada file data.txt dengan konten:
   # 1 2 3
   # 4 5 6
   # 7 8 9
   result = np.loadtxt('data.txt')
   print(result)
   # Output:
   # [[1. 2. 3.]
   #  [4. 5. 6.]
   #  [7. 8. 9.]]
   ```

2. **savetxt()** = Menyimpan array NumPy ke dalam file teks dengan format yang ditentukan.  
   ```python
   arr = np.array([[1, 2, 3], [4, 5, 6]])
   np.savetxt('output.txt', arr)
   # Output di dalam file output.txt:
   # 1.0 2.0 3.0
   # 4.0 5.0 6.0
   ```

3. **genfromtxt()** = Membaca data dari file teks dengan penanganan nilai yang hilang (missing values) dan tipe data campuran.  
   ```python
   # Misalkan ada file data.csv dengan konten:
   # Name, Age, Score
   # Alice, 23, 88
   # Bob, 25, 95
   # Carol, , 85
   result = np.genfromtxt('data.csv', delimiter=',', dtype=None, names=True, encoding='utf-8')
   print(result)
   # Output:
   # [('Alice', 23., 88.) ('Bob', 25., 95.) ('Carol', nan, 85.)]
   ```

---

### **Other Functions**

1. **cumsum()** = Menghitung jumlah kumulatif elemen dalam array.  
   ```python
   arr = np.array([1, 2, 3, 4])
   result = np.cumsum(arr)
   print(result)
   # Output:
   # [ 1  3  6 10]
   ```

2. **cumprod()** = Menghitung hasil perkalian kumulatif dari elemen-elemen dalam array.  
   ```python
   arr = np.array([1, 2, 3, 4])
   result = np.cumprod(arr)
   print(result)
   # Output:
   # [ 1  2  6 24]
   ```

3. **diff()** = Menghitung perbedaan antara elemen berturut-turut dalam array.  
   ```python
   arr = np.array([1, 2, 4, 7])
   result = np.diff(arr)
   print(result)
   # Output:
   # [1 2 3]
   ```

4. **tile()** = Mengulangi (mereplikasi) array untuk membentuk array yang lebih besar sesuai pola yang ditentukan.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.tile(arr, 2)
   print(result)
   # Output:
   # [1 2 3 1 2 3]
   ```

5. **repeat()** = Mengulangi elemen dalam array sesuai dengan jumlah pengulangan yang ditentukan.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.repeat(arr, 2)
   print(result)
   # Output:
   # [1 1 2 2 3 3]
   ```

6. **meshgrid()** = Membuat grid koordinat dari dua vektor satu dimensi, berguna untuk evaluasi fungsi di grid dua dimensi.  
   ```python
   x = np.array([1, 2, 3])
   y = np.array([4, 5])
   X, Y = np.meshgrid(x, y)
   print(X)
   print(Y)
   # Output:
   # [[1 2 3]
   #  [1 2 3]]
   # [[4 4 4]
   #  [5 5 5]]
   ```

7. **ravel()** = Mengembalikan tampilan array satu dimensi dari array input tanpa menyalin data.  
   ```python
   arr = np.array([[1, 2, 3], [4, 5, 6]])
   result = np.ravel(arr)
   print(result)
   # Output:
   # [1 2 3 4 5 6]
   ```

8. **squeeze()** = Menghapus dimensi tunggal dari array, sehingga mengurangi jumlah dimensi tanpa mengubah data.  
   ```python
   arr = np.array([[[1], [2], [3]]])
   result = np.squeeze(arr)
   print(result)
   # Output:
   # [1 2 3]
   ```

9. **expand_dims()** = Menambahkan dimensi baru ke array pada posisi yang ditentukan.  
   ```python
   arr = np.array([1, 2, 3])
   result = np.expand_dims(arr, axis=0)
   print(result)
   # Output:
   # [[1 2 3]]
   ```

10. **flip()** = Membalik urutan elemen dalam array sepanjang sumbu tertentu.  
    ```python
    arr = np.array([1, 2, 3])
    result = np.flip(arr)
    print(result)
    # Output:
    # [3 2 1]
    ```

11. **roll()** = Menggulung (menggeser) elemen dalam array sepanjang sumbu yang ditentukan.  
    ```python
    arr = np.array([1, 2, 3, 4])
    result = np.roll(arr, 1)
    print(result)
    # Output:
    # [4 1 2 3]
    ```

---
