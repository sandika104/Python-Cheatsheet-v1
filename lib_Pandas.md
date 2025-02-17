Daftar fungsi dalam library Pandas:

## **Data Creation & Importing**

### **1. read_csv()** = Membaca file CSV dan mengonversinya menjadi DataFrame.  
   p :  
   - `filepath_or_buffer` : (str) Lokasi file atau objek file yang ingin dibaca.  
   - `sep` : (str) Separator untuk memisahkan kolom, defaultnya adalah koma (`,`).  
   - `header` : (int, list) Baris yang digunakan sebagai header.  
   - `index_col` : (int, str) Kolom yang digunakan sebagai indeks.  
   - `usecols` : (list) Kolom-kolom yang ingin dibaca.  
   - `dtype` : (dict) Menentukan tipe data kolom tertentu.  
   - `skiprows` : (int) Jumlah baris yang dilewati saat membaca file.  

   Contoh:
   ```python
   import pandas as pd

   # Contoh data CSV:
   # name,age,city
   # Alice,30,New York
   # Bob,25,Los Angeles
   # Charlie,35,Chicago

   df = pd.read_csv('data.csv')
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **2. read_excel()** = Membaca file Excel dan mengonversinya menjadi DataFrame.  
   p :  
   - `io` : (str) Lokasi file atau objek file yang ingin dibaca.  
   - `sheet_name` : (str, int, list) Nama sheet atau indeks sheet yang ingin dibaca.  
   - `header` : (int, list) Baris yang digunakan sebagai header.  
   - `index_col` : (int, str) Kolom yang digunakan sebagai indeks.  
   - `usecols` : (list) Kolom-kolom yang ingin dibaca.  
   - `dtype` : (dict) Menentukan tipe data kolom tertentu.  
   - `skiprows` : (int) Jumlah baris yang dilewati saat membaca file.  

   Contoh:
   ```python
   df = pd.read_excel('data.xlsx', sheet_name=0)
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **3. read_json()** = Membaca file JSON dan mengonversinya menjadi DataFrame.  
   p :  
   - `path_or_buffer` : (str) Lokasi file atau objek file yang ingin dibaca.  
   - `orient` : (str) Format JSON, seperti 'records', 'index', dll.  
   - `typ` : (str) Tipe DataFrame yang ingin dikembalikan, bisa 'frame' atau 'series'.  

   Contoh:
   ```python
   # Contoh data JSON:
   # [{"name": "Alice", "age": 30, "city": "New York"},
   #  {"name": "Bob", "age": 25, "city": "Los Angeles"},
   #  {"name": "Charlie", "age": 35, "city": "Chicago"}]

   df = pd.read_json('data.json')
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **4. read_sql()** = Membaca data dari database SQL dan mengonversinya menjadi DataFrame.  
   p :  
   - `sql` : (str) Query SQL yang ingin dijalankan.  
   - `con` : (SQLAlchemy connectable, sqlite3 database connection, or string) Koneksi ke database.  
   - `index_col` : (str) Kolom yang digunakan sebagai indeks.  
   - `params` : (tuple, list, or dict) Parameter untuk query SQL.  
   - `parse_dates` : (bool, list, or dict) Kolom yang akan diubah menjadi format datetime.

   Contoh:
   ```python
   import sqlite3

   conn = sqlite3.connect('example.db')
   query = "SELECT * FROM users"
   df = pd.read_sql(query, conn)
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **5. read_html()** = Membaca tabel dari halaman HTML dan mengonversinya menjadi DataFrame.  
   p :  
   - `io` : (str) Lokasi file HTML atau URL halaman yang berisi tabel.  
   - `match` : (str) Menentukan ekspresi reguler untuk mencari tabel berdasarkan nama atau id.  
   - `header` : (int, list) Baris yang digunakan sebagai header.  
   - `index_col` : (int, str) Kolom yang digunakan sebagai indeks.  
   - `attrs` : (dict) Menentukan atribut HTML seperti id atau class untuk memilih tabel.

   Contoh:
   ```python
   url = "https://example.com/data"
   dfs = pd.read_html(url)
   print(dfs[0])  # Menampilkan tabel pertama dari halaman HTML
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **6. read_parquet()** = Membaca file Parquet dan mengonversinya menjadi DataFrame.  
   p :  
   - `path` : (str) Lokasi file Parquet yang ingin dibaca.  
   - `columns` : (list) Kolom-kolom yang ingin dibaca dari file Parquet.  
   - `use_nullable_dtypes` : (bool) Menentukan apakah tipe data nullable digunakan untuk kolom yang kompatibel.

   Contoh:
   ```python
   df = pd.read_parquet('data.parquet')
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **7. to_csv()** = Menyimpan DataFrame ke dalam file CSV.  
   p :  
   - `path_or_buffer` : (str) Lokasi file CSV yang ingin disimpan.  
   - `sep` : (str) Separator untuk memisahkan kolom.  
   - `index` : (bool) Menentukan apakah indeks akan disertakan dalam file CSV.  
   - `header` : (bool) Menentukan apakah header kolom akan disertakan dalam file CSV.  
   - `columns` : (list) Kolom yang ingin disertakan dalam file CSV.

   Contoh:
   ```python
   df.to_csv('output.csv', index=False)
   ```

   Output (file `output.csv`):
   ```
   name,age,city
   Alice,30,New York
   Bob,25,Los Angeles
   Charlie,35,Chicago
   ```

---

### **8. to_excel()** = Menyimpan DataFrame ke dalam file Excel.  
   p :  
   - `excel_writer` : (str) Lokasi file Excel yang ingin disimpan.  
   - `sheet_name` : (str) Nama sheet di file Excel.  
   - `index` : (bool) Menentukan apakah indeks akan disertakan dalam file Excel.  
   - `columns` : (list) Kolom yang ingin disertakan dalam file Excel.

   Contoh:
   ```python
   df.to_excel('output.xlsx', index=False)
   ```

   Output (file `output.xlsx`):
   ```
   | name    | age | city         |
   |---------|-----|--------------|
   | Alice   | 30  | New York     |
   | Bob     | 25  | Los Angeles  |
   | Charlie | 35  | Chicago      |
   ```

---

### **9. to_json()** = Menyimpan DataFrame ke dalam format JSON.  
   p :  
   - `path_or_buffer` : (str) Lokasi file JSON yang ingin disimpan.  
   - `orient` : (str) Format JSON, seperti 'records', 'split', dll.  
   - `lines` : (bool) Menyimpan dalam format baris JSON.

   Contoh:
   ```python
   df.to_json('output.json', orient='records')
   ```

   Output (file `output.json`):
   ```json
   [
     {"name":"Alice","age":30,"city":"New York"},
     {"name":"Bob","age":25,"city":"Los Angeles"},
     {"name":"Charlie","age":35,"city":"Chicago"}
   ]
   ```

---

### **10. to_sql()** = Menyimpan DataFrame ke dalam database SQL.  
   p :  


   - `name` : (str) Nama tabel di database.  
   - `con` : (SQLAlchemy connectable, sqlite3 database connection, or string) Koneksi ke database.  
   - `if_exists` : (str) Menentukan apa yang dilakukan jika tabel sudah ada, seperti 'replace', 'append', atau 'fail'.  
   - `index` : (bool) Menentukan apakah indeks DataFrame akan disertakan sebagai kolom.  
   - `dtype` : (dict) Menentukan tipe data kolom di tabel SQL.

   Contoh:
   ```python
   conn = sqlite3.connect('example.db')
   df.to_sql('users', conn, if_exists='replace', index=False)
   ```

   Output (Tabel `users` dalam database `example.db`):
   ```
   | name    | age | city         |
   |---------|-----|--------------|
   | Alice   | 30  | New York     |
   | Bob     | 25  | Los Angeles  |
   | Charlie | 35  | Chicago      |
   ```

---

### **11. to_parquet()** = Menyimpan DataFrame ke dalam format Parquet.  
   p :  
   - `path` : (str) Lokasi file Parquet yang ingin disimpan.  
   - `engine` : (str) Mesin untuk menulis file Parquet, seperti 'pyarrow' atau 'fastparquet'.  
   - `compression` : (str) Tipe kompresi untuk file Parquet, seperti 'snappy', 'gzip', atau 'brotli'.

   Contoh:
   ```python
   df.to_parquet('output.parquet')
   ```

   Output: File `output.parquet` disimpan dengan konten DataFrame yang terkompresi.

---

### **12. DataFrame()** = Membuat DataFrame baru dari dictionary, list, atau array.  
   p :  
   - `data` : (dict, list, array, or DataFrame) Data yang digunakan untuk membuat DataFrame.  
   - `columns` : (list) Nama kolom yang digunakan.  
   - `index` : (list) Indeks yang digunakan.

   Contoh:
   ```python
   data = {'name': ['Alice', 'Bob', 'Charlie'], 'age': [30, 25, 35], 'city': ['New York', 'Los Angeles', 'Chicago']}
   df = pd.DataFrame(data)
   print(df)
   ```

   Output:
   ```
       name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **13. Series()** = Membuat objek Series (kolom tunggal) dari list, dictionary, atau array.  
   p :  
   - `data` : (list, array, or dict) Data untuk membuat Series.  
   - `index` : (list) Indeks untuk Series.

   Contoh:
   ```python
   s = pd.Series([30, 25, 35], index=['Alice', 'Bob', 'Charlie'])
   print(s)
   ```

   Output:
   ```
   Alice      30
   Bob        25
   Charlie    35
   dtype: int64
   ```

---
---

## **Data Exploration**

### **1. head()** = Menampilkan beberapa baris pertama dari DataFrame.  
   p :  
   - `n` : (int) Jumlah baris yang ingin ditampilkan. Defaultnya adalah 5.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
       'age': [30, 25, 35, 40, 29],
       'city': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
   })
   print(df.head(3))
   ```

   Output:
   ```
        name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   ```

---

### **2. tail()** = Menampilkan beberapa baris terakhir dari DataFrame.  
   p :  
   - `n` : (int) Jumlah baris yang ingin ditampilkan. Defaultnya adalah 5.

   Contoh:
   ```python
   print(df.tail(2))
   ```

   Output:
   ```
       name  age      city
   3    David   40   Houston
   4      Eva   29   Phoenix
   ```

---

### **3. info()** = Menampilkan informasi ringkas tentang DataFrame, termasuk tipe data dan jumlah nilai non-null.  
   p :  
   - `verbose` : (bool) Menampilkan lebih banyak informasi jika diatur ke `True`.  
   - `null_counts` : (bool) Menampilkan jumlah nilai null jika diatur ke `True`.  

   Contoh:
   ```python
   df.info()
   ```

   Output:
   ```
   <class 'pandas.core.frame.DataFrame'>
   RangeIndex: 5 entries, 0 to 4
   Data columns (total 3 columns):
    #   Column  Non-Null Count  Dtype 
   ---  ------  --------------  ----- 
    0   name    5 non-null      object
    1   age     5 non-null      int64 
    2   city    5 non-null      object
   dtypes: int64(1), object(2)
   memory usage: 163.0+ bytes
   ```

---

### **4. describe()** = Menampilkan ringkasan statistik dari DataFrame untuk kolom numerik.  
   p :  
   - `percentiles` : (list) Persentil yang ingin ditampilkan, seperti [0.25, 0.5, 0.75].  
   - `include` : (str or list) Menentukan tipe data yang akan disertakan, misalnya 'all' untuk semua kolom, 'number' untuk kolom numerik.

   Contoh:
   ```python
   print(df.describe())
   ```

   Output:
   ```
            age
   count   5.000000
   mean   31.800000
   std     5.315071
   min    25.000000
   25%    29.000000
   50%    30.000000
   75%    35.000000
   max    40.000000
   ```

---

### **5. value_counts()** = Menghitung jumlah kemunculan nilai dalam kolom.  
   p :  
   - `normalize` : (bool) Menentukan apakah hasilnya akan dihitung sebagai proporsi relatif (True) atau jumlah absolut (False).  
   - `sort` : (bool) Menentukan apakah hasilnya akan diurutkan (True).  
   - `ascending` : (bool) Mengurutkan hasil secara menaik jika diatur ke `True`.

   Contoh:
   ```python
   print(df['city'].value_counts())
   ```

   Output:
   ```
   New York      1
   Los Angeles   1
   Chicago       1
   Houston       1
   Phoenix       1
   Name: city, dtype: int64
   ```

---

### **6. isnull()** = Menentukan apakah nilai dalam DataFrame adalah null atau NaN.  
   p :  
   - Tidak ada parameter.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', None, 'David', 'Eva'],
       'age': [30, 25, 35, None, 29],
       'city': ['New York', 'Los Angeles', 'Chicago', 'Houston', None]
   })
   print(df.isnull())
   ```

   Output:
   ```
          name   age   city
   0    False  False  False
   1    False  False  False
   2     True  False  False
   3    False   True  False
   4    False  False   True
   ```

---

### **7. notnull()** = Menentukan apakah nilai dalam DataFrame bukan null atau NaN.  
   p :  
   - Tidak ada parameter.

   Contoh:
   ```python
   print(df.notnull())
   ```

   Output:
   ```
          name    age   city
   0     True   True   True
   1     True   True   True
   2    False   True   True
   3     True  False   True
   4     True   True  False
   ```

---

### **8. nunique()** = Menghitung jumlah nilai unik dalam setiap kolom.  
   p :  
   - Tidak ada parameter.

   Contoh:
   ```python
   print(df.nunique())
   ```

   Output:
   ```
   name    5
   age     4
   city    5
   dtype: int64
   ```

---

### **9. corr()** = Menghitung koefisien korelasi antara kolom numerik dalam DataFrame.  
   p :  
   - `method` : (str) Metode yang digunakan untuk menghitung korelasi, bisa 'pearson', 'kendall', atau 'spearman'.  
   - `min_periods` : (int) Jumlah minimum observasi yang diperlukan untuk menghitung korelasi.

   Contoh:
   ```python
   df = pd.DataFrame({
       'age': [30, 25, 35, 40, 29],
       'income': [50000, 40000, 60000, 70000, 45000]
   })
   print(df.corr())
   ```

   Output:
   ```
             age    income
   age     1.000000  0.825764
   income  0.825764  1.000000
   ```

---

### **10. cov()** = Menghitung kovarians antar kolom numerik dalam DataFrame.  
   p :  
   - `min_periods` : (int) Jumlah minimum observasi yang diperlukan untuk menghitung kovarians.

   Contoh:
   ```python
   print(df.cov())
   ```

   Output:
   ```
             age   income
   age     28.750000  6250000
   income  6250000.0  100000000
   ```

---

### **11. sample()** = Mengambil sampel acak dari DataFrame.  
   p :  
   - `n` : (int) Jumlah sampel yang ingin diambil.  
   - `frac` : (float) Fraksi sampel yang ingin diambil.  
   - `replace` : (bool) Apakah sampel diambil dengan penggantian atau tidak.

   Contoh:
   ```python
   print(df.sample(2))
   ```

   Output:
   ```
       age  income
   2  35  60000
   0  30  50000
   ```

---

### **12. shape()** = Menampilkan dimensi (baris dan kolom) dari DataFrame.  
   p :  
   - Tidak ada parameter.

   Contoh:
   ```python
   print(df.shape)
   ```

   Output:
   ```
   (5, 2)
   ```

---
---

## **Data Selection & Filtering**

### **1. loc[]** = Seleksi data berdasarkan label atau nama indeks (baris dan kolom).  
   p :  
   - `row_labels` : (label atau list) Baris yang akan dipilih berdasarkan labelnya.  
   - `col_labels` : (label atau list, opsional) Kolom yang akan dipilih berdasarkan labelnya.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
       'age': [30, 25, 35, 40, 29],
       'city': ['New York', 'Los Angeles', 'Chicago', 'Houston', 'Phoenix']
   })
   print(df.loc[0:2, ['name', 'age']])
   ```

   Output:
   ```
        name  age
   0    Alice   30
   1      Bob   25
   2  Charlie   35
   ```

---

### **2. iloc[]** = Seleksi data berdasarkan posisi integer (baris dan kolom).  
   p :  
   - `row_index` : (int atau list) Indeks baris berdasarkan posisi integer.  
   - `col_index` : (int atau list, opsional) Indeks kolom berdasarkan posisi integer.

   Contoh:
   ```python
   print(df.iloc[0:3, [0, 1]])
   ```

   Output:
   ```
        name  age
   0    Alice   30
   1      Bob   25
   2  Charlie   35
   ```

---

### **3. at[]** = Seleksi satu elemen berdasarkan label baris dan kolom.  
   p :  
   - `row_label` : (label) Label baris yang ingin dipilih.  
   - `col_label` : (label) Label kolom yang ingin dipilih.

   Contoh:
   ```python
   print(df.at[1, 'name'])
   ```

   Output:
   ```
   Bob
   ```

---

### **4. iat[]** = Seleksi satu elemen berdasarkan posisi integer baris dan kolom.  
   p :  
   - `row_position` : (int) Posisi baris berdasarkan integer.  
   - `col_position` : (int) Posisi kolom berdasarkan integer.

   Contoh:
   ```python
   print(df.iat[1, 0])
   ```

   Output:
   ```
   Bob
   ```

---

### **5. filter()** = Menyaring kolom atau baris berdasarkan nama kolom atau pola tertentu.  
   p :  
   - `items` : (list) Daftar nama kolom atau baris yang ingin dipilih.  
   - `like` : (str) Pola yang harus ada dalam nama kolom atau baris.  
   - `regex` : (str) Ekspresi regular untuk pencocokan nama kolom atau baris.

   Contoh:
   ```python
   print(df.filter(items=['name', 'age']))
   ```

   Output:
   ```
        name  age
   0    Alice   30
   1      Bob   25
   2  Charlie   35
   3    David   40
   4      Eva   29
   ```

---

### **6. query()** = Menyaring DataFrame menggunakan ekspresi query.  
   p :  
   - `expr` : (str) Ekspresi filter menggunakan nama kolom.  
   - `inplace` : (bool) Jika `True`, memodifikasi DataFrame secara langsung tanpa membuat salinan.

   Contoh:
   ```python
   print(df.query('age > 30'))
   ```

   Output:
   ```
        name  age      city
   2  Charlie   35   Chicago
   3    David   40   Houston
   ```

---

### **7. isin()** = Memeriksa apakah nilai-nilai dalam kolom atau DataFrame ada dalam daftar nilai tertentu.  
   p :  
   - `values` : (list atau array) Daftar nilai yang ingin diperiksa.

   Contoh:
   ```python
   print(df[df['name'].isin(['Alice', 'Eva'])])
   ```

   Output:
   ```
        name  age         city
   0    Alice   30     New York
   4      Eva   29     Phoenix
   ```

---

### **8. between()** = Menyaring nilai dalam rentang tertentu.  
   p :  
   - `left` : (scalar) Batas bawah rentang.  
   - `right` : (scalar) Batas atas rentang.  
   - `inclusive` : (str) Menentukan apakah batas rentang inklusif atau eksklusif (opsional, defaultnya 'both').

   Contoh:
   ```python
   print(df[df['age'].between(30, 40)])
   ```

   Output:
   ```
        name  age      city
   0    Alice   30   New York
   2  Charlie   35   Chicago
   3    David   40   Houston
   ```

---

### **9. drop()** = Menghapus baris atau kolom berdasarkan label.  
   p :  
   - `labels` : (str atau list) Label baris atau kolom yang ingin dihapus.  
   - `axis` : (int) Menentukan apakah yang dihapus adalah baris (`axis=0`) atau kolom (`axis=1`).

   Contoh:
   ```python
   print(df.drop(columns=['city']))
   ```

   Output:
   ```
        name  age
   0    Alice   30
   1      Bob   25
   2  Charlie   35
   3    David   40
   4      Eva   29
   ```

---

### **10. select_dtypes()** = Memilih kolom berdasarkan tipe data.  
   p :  
   - `include` : (str atau list) Tipe data yang ingin dipilih.  
   - `exclude` : (str atau list) Tipe data yang ingin dikecualikan.

   Contoh:
   ```python
   print(df.select_dtypes(include=['int64']))
   ```

   Output:
   ```
        age
   0    30
   1    25
   2    35
   3    40
   4    29
   ```

---

### **11. set_index()** = Mengatur kolom sebagai indeks dari DataFrame.  
   p :  
   - `keys` : (str atau list) Kolom yang akan digunakan sebagai indeks.  
   - `drop` : (bool) Jika `True`, kolom yang dipilih sebagai indeks akan dihapus dari DataFrame.

   Contoh:
   ```python
   df = df.set_index('name')
   print(df)
   ```

   Output:
   ```
           age         city
   name                     
   Alice    30     New York
   Bob      25  Los Angeles
   Charlie  35      Chicago
   David    40      Houston
   Eva      29      Phoenix
   ```

---

### **12. reset_index()** = Mengatur ulang indeks DataFrame.  
   p :  
   - `drop` : (bool) Jika `True`, indeks yang lama akan dihapus dan tidak dimasukkan sebagai kolom.

   Contoh:
   ```python
   df = df.reset_index()
   print(df)
   ```

   Output:
   ```
        name  age         city
   0    Alice   30     New York
   1      Bob   25  Los Angeles
   2  Charlie   35      Chicago
   3    David   40      Houston
   4      Eva   29     Phoenix
   ```

---
---

## **Data Cleaning & Handling Missing Values**

### **1. isna()** = Memeriksa apakah elemen dalam DataFrame atau Series adalah NaN (Not a Number).  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', None, 'David', 'Eva'],
       'age': [30, None, 35, 40, 29]
   })
   print(df.isna())
   ```

   Output:
   ```
        name    age
   0  False  False
   1  False   True
   2   True  False
   3  False  False
   4  False  False
   ```

---

### **2. isnull()** = Fungsi ini adalah alias dari `isna()`, memeriksa elemen yang merupakan NaN (Not a Number).  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   print(df.isnull())
   ```

   Output:
   ```
        name    age
   0  False  False
   1  False   True
   2   True  False
   3  False  False
   4  False  False
   ```

---

### **3. notna()** = Memeriksa apakah elemen dalam DataFrame atau Series bukan NaN (Not a Number).  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   print(df.notna())
   ```

   Output:
   ```
        name    age
   0   True   True
   1   True  False
   2  False   True
   3   True   True
   4   True   True
   ```

---

### **4. notnull()** = Fungsi ini adalah alias dari `notna()`, memeriksa elemen yang bukan NaN.  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   print(df.notnull())
   ```

   Output:
   ```
        name    age
   0   True   True
   1   True  False
   2  False   True
   3   True   True
   4   True   True
   ```

---

### **5. dropna()** = Menghapus baris atau kolom yang mengandung nilai NaN.  
   p :  
   - `axis` : (int) Menentukan apakah menghapus baris (`axis=0`) atau kolom (`axis=1`).  
   - `how` : (str) Menentukan apakah baris atau kolom dihapus jika *semua* atau *beberapa* nilai adalah NaN.  
   - `thresh` : (int) Menentukan jumlah nilai non-NaN minimum yang harus ada di baris atau kolom agar tidak dihapus.  
   - `subset` : (list) Kolom-kolom tertentu yang dipertimbangkan untuk penghapusan NaN.  
   - `inplace` : (bool) Jika `True`, melakukan perubahan langsung pada DataFrame tanpa mengembalikan salinan.

   Contoh:
   ```python
   print(df.dropna())
   ```

   Output:
   ```
        name   age
   0    Alice  30.0
   4      Eva  29.0
   ```

---

### **6. fillna()** = Mengisi nilai NaN dengan nilai tertentu atau nilai statistik.  
   p :  
   - `value` : (scalar, dict, atau Series) Nilai yang digunakan untuk menggantikan NaN.  
   - `method` : (str) Metode pengisian ('ffill' untuk forward fill, 'bfill' untuk backward fill).  
   - `axis` : (int) Menentukan apakah pengisian dilakukan per baris (`axis=0`) atau per kolom (`axis=1`).  
   - `inplace` : (bool) Jika `True`, melakukan perubahan langsung pada DataFrame tanpa mengembalikan salinan.

   Contoh:
   ```python
   print(df.fillna({'age': 30, 'name': 'Unknown'}))
   ```

   Output:
   ```
        name   age
   0    Alice  30.0
   1      Bob  30.0
   2  Unknown  35.0
   3    David  40.0
   4      Eva  29.0
   ```

---

### **7. replace()** = Mengganti nilai tertentu dalam DataFrame atau Series dengan nilai baru.  
   p :  
   - `to_replace` : (scalar, list, dict, atau regex) Nilai yang akan diganti.  
   - `value` : (scalar, list, atau dict) Nilai pengganti.  
   - `inplace` : (bool) Jika `True`, melakukan perubahan langsung pada DataFrame tanpa mengembalikan salinan.  
   - `regex` : (bool atau str) Jika `True`, pencocokan nilai menggunakan regular expression.

   Contoh:
   ```python
   print(df.replace({None: 'Unknown', 35: 36}))
   ```

   Output:
   ```
        name   age
   0    Alice  30.0
   1      Bob  30.0
   2  Unknown  36.0
   3    David  40.0
   4      Eva  29.0
   ```

---

### **8. interpolate()** = Menginterpolasi nilai NaN dalam DataFrame atau Series.  
   p :  
   - `method` : (str) Metode interpolasi ('linear', 'polynomial', dll.).  
   - `axis` : (int) Menentukan arah interpolasi, baris (`axis=0`) atau kolom (`axis=1`).  
   - `limit` : (int) Membatasi jumlah nilai NaN yang dapat diinterpolasi.  
   - `inplace` : (bool) Jika `True`, melakukan perubahan langsung pada DataFrame tanpa mengembalikan salinan.

   Contoh:
   ```python
   print(df.interpolate(method='linear'))
   ```

   Output:
   ```
        name   age
   0    Alice  30.0
   1      Bob  32.5
   2  Unknown  35.0
   3    David  40.0
   4      Eva  29.0
   ```

---

### **9. drop_duplicates()** = Menghapus baris duplikat berdasarkan kolom tertentu atau semua kolom.  
   p :  
   - `subset` : (str atau list) Kolom yang digunakan untuk mendeteksi duplikat.  
   - `keep` : (str) Menentukan apakah mempertahankan baris pertama ('first'), baris terakhir ('last'), atau menghapus semua duplikat ('False').  
   - `inplace` : (bool) Jika `True`, melakukan perubahan langsung pada DataFrame tanpa mengembalikan salinan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Bob', 'David', 'Eva'],
       'age': [30, 25, 25, 40, 29]
   })
   print(df.drop_duplicates(subset=['name'], keep='first'))
   ```

   Output:
   ```
        name  age
   0    Alice   30
   1      Bob   25
   3    David   40
   4      Eva   29
   ```

---

### **10. duplicated()** = Memeriksa apakah baris dalam DataFrame adalah duplikat dari baris sebelumnya.  
   p :  
   - `subset` : (str atau list) Kolom yang digunakan untuk mendeteksi duplikat.  
   - `keep` : (str) Menentukan apakah baris pertama ('first'), baris terakhir ('last'), atau semua duplikat ('False') yang dianggap duplikat.

   Contoh:
   ```python
   print(df.duplicated(subset=['name']))
   ```

   Output:
   ```
   0    False
   1     True
   2     True
   3    False
   4    False
   dtype: bool
   ```

---
---

## **Data Transformation**

### **1. astype()** = Mengonversi tipe data kolom dalam DataFrame atau Series.  
   p :  
   - `dtype` : (str, type, atau dict) Tipe data yang ingin diubah.  
   - `copy` : (bool) Jika `True`, membuat salinan data.  
   - `errors` : (str) Menangani kesalahan, bisa 'raise' untuk menampilkan kesalahan atau 'ignore' untuk mengabaikan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'age': [30, 25, 35, 40],
       'salary': [50000, 60000, 70000, 80000]
   })
   df['age'] = df['age'].astype(float)
   print(df)
   ```

   Output:
   ```
      age  salary
   0  30.0   50000
   1  25.0   60000
   2  35.0   70000
   3  40.0   80000
   ```

---

### **2. apply()** = Menerapkan fungsi ke setiap elemen atau kolom/row dalam DataFrame.  
   p :  
   - `func` : (fungsi) Fungsi yang ingin diterapkan.  
   - `axis` : (int) Arah penerapan fungsi ('0' untuk kolom, '1' untuk baris).  
   - `raw` : (bool) Jika `True`, fungsi diterapkan ke array Numpy mentah.

   Contoh:
   ```python
   df['age'] = df['age'].apply(lambda x: x + 1)
   print(df)
   ```

   Output:
   ```
      age  salary
   0  31.0   50000
   1  26.0   60000
   2  36.0   70000
   3  41.0   80000
   ```

---

### **3. applymap()** = Menerapkan fungsi ke setiap elemen dalam seluruh DataFrame (hanya berlaku untuk DataFrame, bukan Series).  
   p :  
   - `func` : (fungsi) Fungsi yang ingin diterapkan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'age': [30, 25, 35, 40],
       'salary': [50000, 60000, 70000, 80000]
   })
   df = df.applymap(lambda x: x * 1.1)
   print(df)
   ```

   Output:
   ```
      age   salary
   0  33.0  55000.0
   1  27.5  66000.0
   2  38.5  77000.0
   3  44.0  88000.0
   ```

---

### **4. map()** = Menerapkan fungsi atau pemetaan nilai ke setiap elemen dalam Series.  
   p :  
   - `arg` : (fungsi, dict, atau Series) Fungsi atau dictionary yang digunakan untuk pemetaan nilai.  

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [30, 25, 35, 40]
   })
   df['age'] = df['age'].map(lambda x: x * 1.1)
   print(df)
   ```

   Output:
   ```
        name   age
   0    Alice  33.0
   1      Bob  27.5
   2  Charlie  38.5
   3    David  44.0
   ```

---

### **5. merge()** = Menggabungkan dua DataFrame berdasarkan kolom atau index tertentu.  
   p :  
   - `right` : (DataFrame) DataFrame yang akan digabungkan.  
   - `how` : (str) Jenis penggabungan, bisa 'inner', 'outer', 'left', atau 'right'.  
   - `on` : (str atau list) Nama kolom yang digunakan sebagai key penggabungan.  
   - `left_on`, `right_on` : (str atau list) Kolom yang digunakan untuk penggabungan pada DataFrame kiri atau kanan.  
   - `left_index`, `right_index` : (bool) Menentukan apakah index digunakan sebagai key penggabungan.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'id': [1, 2, 3, 4],
       'name': ['Alice', 'Bob', 'Charlie', 'David']
   })
   df2 = pd.DataFrame({
       'id': [1, 2, 3, 4],
       'age': [30, 25, 35, 40]
   })
   merged_df = pd.merge(df1, df2, on='id', how='inner')
   print(merged_df)
   ```

   Output:
   ```
      id     name  age
   0   1    Alice   30
   1   2      Bob   25
   2   3  Charlie   35
   3   4    David   40
   ```

---

### **6. pivot()** = Mengubah DataFrame panjang menjadi lebar dengan mengatur kolom sebagai indeks dan data lainnya sebagai kolom.  
   p :  
   - `index` : (str) Kolom yang akan digunakan sebagai indeks.  
   - `columns` : (str) Kolom yang akan digunakan sebagai kolom dalam tabel pivot.  
   - `values` : (str) Kolom yang akan digunakan untuk mengisi nilai-nilai dalam tabel pivot.

   Contoh:
   ```python
   df = pd.DataFrame({
       'date': ['2021-01-01', '2021-01-01', '2021-01-02', '2021-01-02'],
       'city': ['A', 'B', 'A', 'B'],
       'temperature': [30, 25, 35, 40]
   })
   pivot_df = df.pivot(index='date', columns='city', values='temperature')
   print(pivot_df)
   ```

   Output:
   ```
   city            A   B
   date                  
   2021-01-01    30  25
   2021-01-02    35  40
   ```

---

### **7. pivot_table()** = Membuat tabel pivot dengan agregasi fungsi untuk menggabungkan nilai-nilai dalam tabel.  
   p :  
   - `values` : (str) Kolom yang akan digunakan untuk agregasi.  
   - `index` : (str atau list) Kolom yang akan digunakan sebagai indeks.  
   - `columns` : (str atau list) Kolom yang akan digunakan sebagai kolom dalam tabel pivot.  
   - `aggfunc` : (fungsi atau list) Fungsi agregasi, seperti `np.mean`, `np.sum`, dll.

   Contoh:
   ```python
   df = pd.DataFrame({
       'date': ['2021-01-01', '2021-01-01', '2021-01-02', '2021-01-02'],
       'city': ['A', 'B', 'A', 'B'],
       'temperature': [30, 25, 35, 40],
       'humidity': [60, 65, 70, 75]
   })
   pivot_table_df = df.pivot_table(values='temperature', index='date', columns='city', aggfunc='mean')
   print(pivot_table_df)
   ```

   Output:
   ```
   city            A   B
   date                  
   2021-01-01    30  25
   2021-01-02    35  40
   ```

---

### **8. set_index()** = Mengatur kolom sebagai indeks DataFrame.  
   p :  
   - `keys` : (str, list) Nama kolom atau kolom-kolom yang akan dijadikan indeks.  
   - `drop` : (bool) Jika `True`, kolom yang digunakan sebagai indeks akan dihapus dari DataFrame.  
   - `inplace` : (bool) Jika `True`, perubahan dilakukan langsung pada DataFrame tanpa mengembalikan salinan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'id': [1, 2, 3, 4],
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [30, 25, 35, 40]
   })
   df.set_index('id', inplace=True)
   print(df)
   ```

   Output:
   ```
        name  age
   id             
   1    Alice   30
   2      Bob   25
   3  Charlie   35
   4    David   40
   ```

---
---

## **Grouping & Aggregation**

### **1. groupby()** = Mengelompokkan data berdasarkan satu atau lebih kolom untuk analisis lebih lanjut.  
   p :  
   - `by` : (str, list, atau dict) Kolom atau fungsi untuk mengelompokkan data.  
   - `axis` : (int) Arah pengelompokan, bisa 0 untuk baris atau 1 untuk kolom.  
   - `as_index` : (bool) Jika `True`, kolom yang digunakan untuk pengelompokan menjadi indeks hasil.  
   - `sort` : (bool) Jika `True`, hasilnya akan diurutkan berdasarkan kelompok.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department')
   print(grouped.mean())
   ```

   Output:
   ```
               salary
   department         
   HR            52500
   IT            67500
   ```

---

### **2. agg()** = Menerapkan fungsi agregasi ke kelompok yang dihasilkan dari `groupby()`.  
   p :  
   - `func` : (fungsi, list, dict) Fungsi agregasi yang akan diterapkan.  
   - `axis` : (int) Arah penerapan fungsi.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000],
       'age': [30, 25, 40, 35, 28]
   })
   grouped = df.groupby('department').agg({
       'salary': 'mean',
       'age': 'max'
   })
   print(grouped)
   ```

   Output:
   ```
               salary  age
   department             
   HR            52500   40
   IT            67500   35
   ```

---

### **3. transform()** = Menerapkan fungsi pada setiap grup, tetapi mengembalikan DataFrame atau Series dengan ukuran yang sama seperti input aslinya.  
   p :  
   - `func` : (fungsi) Fungsi yang akan diterapkan ke setiap grup.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   df['salary_adjusted'] = df.groupby('department')['salary'].transform(lambda x: x - x.mean())
   print(df)
   ```

   Output:
   ```
   department employee  salary  salary_adjusted
   0         HR     John   50000          -2500.0
   1         IT     Mike   60000          -7500.0
   2         HR     Sara   55000           1500.0
   3         IT    David   70000          2500.0
   4         IT     Nina   75000          7000.0
   ```

---

### **4. size()** = Menghitung jumlah elemen dalam setiap grup.  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department').size()
   print(grouped)
   ```

   Output:
   ```
   department
   HR    2
   IT    3
   dtype: int64
   ```

---

### **5. sum()** = Menghitung jumlah dari elemen-elemen dalam grup.  
   p :  
   - `axis` : (int) Arah penerapan fungsi (default 0, untuk baris).  
   - `skipna` : (bool) Jika `True`, akan mengabaikan nilai NaN.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department').sum()
   print(grouped)
   ```

   Output:
   ```
               salary
   department         
   HR            105000
   IT            205000
   ```

---

### **6. first()** = Mengambil elemen pertama dalam setiap grup.  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department').first()
   print(grouped)
   ```

   Output:
   ```
               employee  salary
   department                  
   HR               John   50000
   IT               Mike   60000
   ```

---

### **7. last()** = Mengambil elemen terakhir dalam setiap grup.  
   p :  
   - Tidak ada parameter khusus.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department').last()
   print(grouped)
   ```

   Output:
   ```
               employee  salary
   department                  
   HR               Sara   55000
   IT               Nina   75000
   ```

---

### **8. nth()** = Mengambil elemen pada posisi tertentu dalam setiap grup.  
   p :  
   - `n` : (int) Posisi elemen yang ingin diambil dalam grup (dimulai dari 0).  
   - `dropna` : (bool) Jika `True`, mengabaikan grup yang memiliki nilai NaN.

   Contoh:
   ```python
   df = pd.DataFrame({
       'department': ['HR', 'IT', 'HR', 'IT', 'IT'],
       'employee': ['John', 'Mike', 'Sara', 'David', 'Nina'],
       'salary': [50000, 60000, 55000, 70000, 75000]
   })
   grouped = df.groupby('department').nth(1)
   print(grouped)
   ```

   Output:
   ```
               employee  salary
   department                  
   HR               Sara   55000
   IT               David   70000
   ```

---
---

## **Merging & Joining Data**

### **1. merge()** = Menggabungkan dua DataFrame berdasarkan kolom atau indeks yang cocok.  
   p :  
   - `right` : (DataFrame) DataFrame yang akan digabungkan dengan DataFrame kiri.  
   - `how` : (str) Metode penggabungan, seperti 'inner', 'outer', 'left', atau 'right'.  
   - `on` : (str atau list) Kolom yang digunakan untuk penggabungan.  
   - `left_on` dan `right_on` : (str atau list) Kolom dari DataFrame kiri dan kanan untuk penggabungan.  
   - `left_index` dan `right_index` : (bool) Jika `True`, akan menggunakan indeks untuk penggabungan.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'id': [1, 2, 3],
       'name': ['Alice', 'Bob', 'Charlie']
   })
   df2 = pd.DataFrame({
       'id': [1, 2, 4],
       'age': [25, 30, 35]
   })
   result = pd.merge(df1, df2, on='id', how='inner')
   print(result)
   ```

   Output:
   ```
      id     name  age
   0   1    Alice   25
   1   2      Bob   30
   ```

---

### **2. join()** = Menggabungkan DataFrame dengan menggunakan indeks.  
   p :  
   - `other` : (DataFrame) DataFrame yang akan digabungkan.  
   - `on` : (str) Kolom yang digunakan untuk penggabungan (opsional, jika menggunakan kolom).  
   - `how` : (str) Metode penggabungan, seperti 'left', 'right', 'outer', atau 'inner'.  
   - `lsuffix` dan `rsuffix` : (str) Sufiks yang ditambahkan ke kolom yang memiliki nama yang sama.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie'],
       'age': [25, 30, 35]
   }, index=[1, 2, 3])
   df2 = pd.DataFrame({
       'salary': [50000, 60000, 70000]
   }, index=[1, 2, 3])
   result = df1.join(df2)
   print(result)
   ```

   Output:
   ```
        name  age  salary
   1    Alice   25   50000
   2      Bob   30   60000
   3  Charlie   35   70000
   ```

---

### **3. concat()** = Menggabungkan dua atau lebih DataFrame atau Series secara vertikal atau horizontal.  
   p :  
   - `objs` : (list) Daftar DataFrame atau Series yang akan digabungkan.  
   - `axis` : (int) Arah penggabungan, 0 untuk vertikal, 1 untuk horizontal.  
   - `join` : (str) Metode penggabungan indeks atau kolom ('inner' atau 'outer').  
   - `ignore_index` : (bool) Jika `True`, mengabaikan indeks asli dan membuat indeks baru.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'name': ['Alice', 'Bob'],
       'age': [25, 30]
   })
   df2 = pd.DataFrame({
       'name': ['Charlie', 'David'],
       'age': [35, 40]
   })
   result = pd.concat([df1, df2], ignore_index=True)
   print(result)
   ```

   Output:
   ```
       name  age
   0    Alice   25
   1      Bob   30
   2  Charlie   35
   3    David   40
   ```

---

### **4. append()** = Menambahkan baris baru ke DataFrame yang sudah ada.  
   p :  
   - `other` : (DataFrame) DataFrame yang akan ditambahkan.  
   - `ignore_index` : (bool) Jika `True`, mengabaikan indeks asli dan membuat indeks baru.  
   - `sort` : (bool) Jika `True`, mengurutkan kolom secara otomatis.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'name': ['Alice', 'Bob'],
       'age': [25, 30]
   })
   df2 = pd.DataFrame({
       'name': ['Charlie', 'David'],
       'age': [35, 40]
   })
   result = df1.append(df2, ignore_index=True)
   print(result)
   ```

   Output:
   ```
       name  age
   0    Alice   25
   1      Bob   30
   2  Charlie   35
   3    David   40
   ```

---

### **5. merge_asof()** = Menggabungkan dua DataFrame berdasarkan kunci yang lebih besar dari atau lebih kecil dari kunci yang sesuai, berguna untuk data time series.  
   p :  
   - `right` : (DataFrame) DataFrame yang akan digabungkan dengan DataFrame kiri.  
   - `on` : (str) Kolom yang digunakan untuk penggabungan.  
   - `by` : (str atau list) Kolom untuk mengelompokkan sebelum penggabungan.  
   - `direction` : (str) Arah pencocokan, bisa 'forward', 'backward', atau 'nearest'.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'time': [1, 2, 3, 4],
       'data': ['A', 'B', 'C', 'D']
   })
   df2 = pd.DataFrame({
       'time': [2, 3, 4, 5],
       'value': [100, 200, 300, 400]
   })
   result = pd.merge_asof(df1, df2, on='time')
   print(result)
   ```

   Output:
   ```
      time data  value
   0     1    A   100.0
   1     2    B   100.0
   2     3    C   200.0
   3     4    D   300.0
   ```

---

### **6. merge_ordered()** = Menggabungkan dua DataFrame berdasarkan urutan yang sudah ditentukan, digunakan pada data yang terurut.  
   p :  
   - `right` : (DataFrame) DataFrame yang akan digabungkan dengan DataFrame kiri.  
   - `on` : (str) Kolom yang digunakan untuk penggabungan.  
   - `left_by` dan `right_by` : (str atau list) Kolom untuk pengurutan data.

   Contoh:
   ```python
   df1 = pd.DataFrame({
       'time': [1, 2, 3],
       'data': ['A', 'B', 'C']
   })
   df2 = pd.DataFrame({
       'time': [1, 2, 3],
       'value': [10, 20, 30]
   })
   result = pd.merge_ordered(df1, df2, on='time')
   print(result)
   ```

   Output:
   ```
      time data  value
   0     1    A     10
   1     2    B     20
   2     3    C     30
   ```

---
---

## **Sorting & Reordering Data**

### **1. sort_values()** = Mengurutkan DataFrame atau Series berdasarkan nilai dalam satu atau lebih kolom.  
   p :  
   - `by` : (str atau list) Kolom atau kolom-kolom yang digunakan untuk pengurutan.  
   - `axis` : (int) Arah pengurutan, 0 untuk baris, 1 untuk kolom.  
   - `ascending` : (bool atau list) Urutan pengurutan, jika `True` diurutkan naik, jika `False` diurutkan turun.  
   - `inplace` : (bool) Jika `True`, mengubah DataFrame secara langsung tanpa membuat salinan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df.sort_values(by='age', ascending=False)
   print(result)
   ```

   Output:
   ```
       name  age
   2  Charlie   35
   1      Bob   30
   0    Alice   25
   3    David   20
   ```

---

### **2. sort_index()** = Mengurutkan DataFrame atau Series berdasarkan indeksnya.  
   p :  
   - `axis` : (int) Arah pengurutan, 0 untuk baris, 1 untuk kolom.  
   - `ascending` : (bool) Urutan pengurutan, jika `True` diurutkan naik, jika `False` diurutkan turun.  
   - `inplace` : (bool) Jika `True`, mengubah DataFrame secara langsung tanpa membuat salinan.  
   - `kind` : (str) Jenis pengurutan, misalnya 'quicksort', 'mergesort', atau 'heapsort'.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   }, index=[3, 2, 1, 0])
   result = df.sort_index(ascending=True)
   print(result)
   ```

   Output:
   ```
       name  age
   0    David   20
   1  Charlie   35
   2      Bob   30
   3    Alice   25
   ```

---

### **3. rank()** = Memberikan peringkat pada elemen DataFrame atau Series berdasarkan nilai kolom atau indeks.  
   p :  
   - `axis` : (int) Arah perankingan, 0 untuk baris, 1 untuk kolom.  
   - `method` : (str) Metode perankingan, bisa 'average', 'min', 'max', 'first', atau 'dense'.  
   - `ascending` : (bool) Jika `True`, peringkat naik, jika `False`, peringkat turun.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df['age'].rank(ascending=False)
   print(result)
   ```

   Output:
   ```
   0    3.0
   1    2.0
   2    1.0
   3    4.0
   Name: age, dtype: float64
   ```

---

### **4. reindex()** = Mengubah indeks DataFrame atau Series dengan indeks yang baru, memungkinkan penataan ulang data.  
   p :  
   - `labels` : (array-like) Indeks baru yang akan diterapkan.  
   - `axis` : (int) Arah perubahan indeks, 0 untuk baris, 1 untuk kolom.  
   - `method` : (str) Metode pengisian nilai yang hilang, seperti 'ffill' (forward fill), 'bfill' (backward fill).  
   - `inplace` : (bool) Jika `True`, mengubah DataFrame secara langsung tanpa membuat salinan.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df.reindex([3, 2, 1, 0])
   print(result)
   ```

   Output:
   ```
       name  age
   3    David   20
   2  Charlie   35
   1      Bob   30
   0    Alice   25
   ```

---

### **5. argsort()** = Mengembalikan urutan indeks yang akan mengurutkan data dalam urutan menaik atau menurun.  
   p :  
   - `axis` : (int) Arah pengurutan, 0 untuk baris, 1 untuk kolom.  
   - `ascending` : (bool) Urutan pengurutan, jika `True` diurutkan naik, jika `False` diurutkan turun.  
   - `kind` : (str) Jenis pengurutan, misalnya 'quicksort', 'mergesort', atau 'heapsort'.

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df['age'].argsort()
   print(result)
   ```

   Output:
   ```
   [3 0 1 2]
   ```

---

### **6. nlargest()** = Mengambil N elemen terbesar dari DataFrame atau Series.  
   p :  
   - `n` : (int) Jumlah elemen terbesar yang diambil.  
   - `columns` : (str) Kolom yang digunakan untuk pengurutan.  
   - `keep` : (str) Menentukan apakah duplikat diperbolehkan ('first', 'last', atau 'all').

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df.nlargest(2, 'age')
   print(result)
   ```

   Output:
   ```
       name  age
   2  Charlie   35
   1      Bob   30
   ```

---

### **7. nsmallest()** = Mengambil N elemen terkecil dari DataFrame atau Series.  
   p :  
   - `n` : (int) Jumlah elemen terkecil yang diambil.  
   - `columns` : (str) Kolom yang digunakan untuk pengurutan.  
   - `keep` : (str) Menentukan apakah duplikat diperbolehkan ('first', 'last', atau 'all').

   Contoh:
   ```python
   df = pd.DataFrame({
       'name': ['Alice', 'Bob', 'Charlie', 'David'],
       'age': [25, 30, 35, 20]
   })
   result = df.nsmallest(2, 'age')
   print(result)
   ```

   Output:
   ```
       name  age
   3    David   20
   0    Alice   25
   ```

---
---

## **Time Series & Date Functions**

### **1. to_datetime()** = Mengonversi objek yang dapat dipahami sebagai tanggal (seperti string atau integer) menjadi objek `datetime` Pandas.  
   p :  
   - `arg` : (str, int, atau datetime-like) Data yang akan dikonversi.  
   - `format` : (str, optional) Format string untuk parsing data tanggal.  
   - `errors` : (str) Penanganan kesalahan, bisa 'raise', 'coerce', atau 'ignore'.  
   - `dayfirst` : (bool) Jika `True`, menganggap format tanggal adalah DD/MM/YYYY.

   Contoh:
   ```python
   dates = ['2025-01-01', '2025-02-01', '2025-03-01']
   result = pd.to_datetime(dates)
   print(result)
   ```

   Output:
   ```
   DatetimeIndex(['2025-01-01', '2025-02-01', '2025-03-01'], dtype='datetime64[ns]', freq=None)
   ```

---

### **2. to_timedelta()** = Mengonversi objek yang dapat dipahami sebagai selisih waktu (seperti string atau integer) menjadi objek `timedelta` Pandas.  
   p :  
   - `arg` : (str, int, atau timedelta-like) Data yang akan dikonversi.  
   - `unit` : (str) Satuan waktu, bisa 'D', 'H', 'T', 'S', dll.  
   - `errors` : (str) Penanganan kesalahan, bisa 'raise', 'coerce', atau 'ignore'.

   Contoh:
   ```python
   time_diff = ['1 days', '2 days', '3 days']
   result = pd.to_timedelta(time_diff)
   print(result)
   ```

   Output:
   ```
   TimedeltaIndex(['1 days', '2 days', '3 days'], dtype='timedelta64[ns]', freq=None)
   ```

---

### **3. date_range()** = Membuat urutan tanggal dengan interval yang teratur.  
   p :  
   - `start` : (str atau datetime-like) Tanggal awal untuk rentang.  
   - `end` : (str atau datetime-like, optional) Tanggal akhir untuk rentang.  
   - `periods` : (int, optional) Jumlah total tanggal dalam rentang (salah satu dari `end` atau `periods` harus diberikan).  
   - `freq` : (str, optional) Frekuensi antara tanggal-tanggal dalam rentang. Misalnya, 'D' untuk harian, 'M' untuk bulanan.

   Contoh:
   ```python
   result = pd.date_range(start='2025-01-01', periods=5, freq='D')
   print(result)
   ```

   Output:
   ```
   DatetimeIndex(['2025-01-01', '2025-01-02', '2025-01-03', '2025-01-04', '2025-01-05'], dtype='datetime64[ns]', freq='D')
   ```

---

### **4. bdate_range()** = Membuat urutan tanggal kerja (business day) dengan interval yang teratur.  
   p :  
   - `start` : (str atau datetime-like) Tanggal awal untuk rentang.  
   - `end` : (str atau datetime-like, optional) Tanggal akhir untuk rentang.  
   - `periods` : (int, optional) Jumlah total tanggal dalam rentang (salah satu dari `end` atau `periods` harus diberikan).  
   - `freq` : (str, optional) Frekuensi antara tanggal-tanggal dalam rentang. Frekuensi default adalah 'B' (business day).

   Contoh:
   ```python
   result = pd.bdate_range(start='2025-01-01', periods=5)
   print(result)
   ```

   Output:
   ```
   DatetimeIndex(['2025-01-01', '2025-01-02', '2025-01-05', '2025-01-06', '2025-01-07'], dtype='datetime64[ns]', freq='B')
   ```

---

### **5. Timedelta()** = Mewakili perbedaan waktu, dapat digunakan untuk penambahan atau pengurangan waktu pada objek `datetime`.  
   p :  
   - `days` : (int, optional) Jumlah hari dalam selisih waktu.  
   - `hours` : (int, optional) Jumlah jam dalam selisih waktu.  
   - `minutes` : (int, optional) Jumlah menit dalam selisih waktu.  
   - `seconds` : (int, optional) Jumlah detik dalam selisih waktu.  
   - `microseconds` : (int, optional) Jumlah mikrodetik dalam selisih waktu.

   Contoh:
   ```python
   result = pd.Timedelta(days=2, hours=5)
   print(result)
   ```

   Output:
   ```
   2 days 05:00:00
   ```

---

### **6. strftime()** = Mengonversi objek `datetime` ke dalam string dengan format yang ditentukan.  
   p :  
   - `format` : (str) Format string untuk konversi, seperti '%Y-%m-%d' atau '%H:%M:%S'.  

   Contoh:
   ```python
   date = pd.to_datetime('2025-01-01')
   result = date.strftime('%Y-%m-%d')
   print(result)
   ```

   Output:
   ```
   2025-01-01
   ```

---

### **7. strptime()** = Mengonversi string menjadi objek `datetime` dengan format yang ditentukan.  
   p :  
   - `arg` : (str) String yang akan diubah menjadi `datetime`.  
   - `format` : (str) Format string untuk parsing data tanggal.

   Contoh:
   ```python
   result = pd.to_datetime('01-01-2025', format='%d-%m-%Y')
   print(result)
   ```

   Output:
   ```
   2025-01-01 00:00:00
   ```

---

### **8. isna()** = Mengecek apakah nilai dalam DataFrame atau Series adalah `NaT` (Not a Time), yang setara dengan `NaN` dalam data waktu.  
   p : Tidak ada parameter.

   Contoh:
   ```python
   dates = pd.to_datetime(['2025-01-01', None, '2025-03-01'])
   result = dates.isna()
   print(result)
   ```

   Output:
   ```
   [False  True False]
   ```

---

### **9. is_leap_year()** = Mengecek apakah tahun dalam objek `datetime` adalah tahun kabisat.  
   p : Tidak ada parameter.

   Contoh:
   ```python
   date = pd.to_datetime('2025-01-01')
   result = date.is_leap_year
   print(result)
   ```

   Output:
   ```
   False
   ```

---
---

## **Plotting & Visualization**

### **1. plot()** = Membuat plot (grafik) berdasarkan data dalam DataFrame atau Series. Fungsi ini menyediakan antarmuka sederhana untuk membuat grafik menggunakan Matplotlib.  
   p :  
   - `kind` : (str) Tipe plot, seperti 'line', 'bar', 'hist', 'scatter', dll.  
   - `ax` : (matplotlib.axes.Axes, optional) Objek axes tempat plot akan digambar.  
   - `subplots` : (bool, optional) Jika `True`, akan membuat subplot untuk setiap kolom DataFrame.  
   - `title` : (str, optional) Judul untuk grafik.  
   - `xlabel` / `ylabel` : (str, optional) Label untuk sumbu x dan y.  
   - `grid` : (bool, optional) Menambahkan grid ke grafik.

   Contoh:
   ```python
   data = pd.Series([1, 3, 2, 4])
   result = data.plot(kind='line', title='Line Plot', grid=True)
   ```

   Output: Sebuah plot garis dengan data yang diberikan.

---

### **2. hist()** = Membuat histogram untuk DataFrame atau Series. Digunakan untuk memvisualisasikan distribusi data.  
   p :  
   - `bins` : (int, optional) Jumlah bins (kelompok) dalam histogram.  
   - `by` : (str, optional) Nama kolom dalam DataFrame yang akan digunakan untuk grup.  
   - `xlabel` / `ylabel` : (str, optional) Label untuk sumbu x dan y.  
   - `alpha` : (float, optional) Transparansi histogram, antara 0 dan 1.

   Contoh:
   ```python
   data = pd.Series([1, 3, 2, 4, 5, 2, 3, 6])
   result = data.hist(bins=5, alpha=0.7)
   ```

   Output: Sebuah histogram dengan 5 bins.

---

### **3. boxplot()** = Membuat boxplot untuk DataFrame atau Series, berguna untuk visualisasi distribusi dan pencilan.  
   p :  
   - `column` : (str, optional) Nama kolom yang akan digambar boxplot-nya.  
   - `by` : (str, optional) Nama kolom untuk grup.  
   - `patch_artist` : (bool, optional) Jika `True`, menggambar kotak dengan warna yang diisi.

   Contoh:
   ```python
   data = pd.DataFrame({
       'A': [1, 2, 3, 4, 5],
       'B': [5, 4, 3, 2, 1]
   })
   result = data.boxplot(column=['A', 'B'])
   ```

   Output: Sebuah boxplot untuk kolom A dan B.

---

### **4. scatter()** = Membuat scatter plot (grafik sebar) dari data dalam DataFrame atau Series.  
   p :  
   - `x` : (str) Kolom data untuk sumbu x.  
   - `y` : (str) Kolom data untuk sumbu y.  
   - `c` : (str, optional) Warna titik berdasarkan kolom tertentu.  
   - `s` : (int, optional) Ukuran titik.

   Contoh:
   ```python
   data = pd.DataFrame({
       'x': [1, 2, 3, 4],
       'y': [5, 6, 7, 8]
   })
   result = data.plot.scatter(x='x', y='y')
   ```

   Output: Scatter plot dari kolom `x` dan `y`.

---

### **5. bar()** = Membuat grafik batang dari data dalam DataFrame atau Series.  
   p :  
   - `x` : (str, optional) Kolom untuk sumbu x (index digunakan secara default).  
   - `height` : (str atau array) Kolom untuk nilai batang.

   Contoh:
   ```python
   data = pd.Series([3, 2, 5, 7])
   result = data.plot.bar(title='Bar Plot')
   ```

   Output: Sebuah grafik batang dari data yang diberikan.

---

### **6. area()** = Membuat plot area dari data dalam DataFrame atau Series.  
   p :  
   - `stacked` : (bool, optional) Jika `True`, plot akan menampilkan area bertumpuk.

   Contoh:
   ```python
   data = pd.DataFrame({
       'A': [1, 2, 3],
       'B': [4, 5, 6]
   })
   result = data.plot.area(stacked=True)
   ```

   Output: Plot area bertumpuk untuk kolom `A` dan `B`.

---

### **7. pie()** = Membuat pie chart (grafik lingkaran) dari data dalam DataFrame atau Series.  
   p :  
   - `labels` : (array, optional) Label untuk setiap sektor pie.  
   - `autopct` : (str, optional) Format label presentase.  
   - `startangle` : (float, optional) Sudut awal untuk memulai pie chart.

   Contoh:
   ```python
   data = pd.Series([1, 2, 3, 4])
   result = data.plot.pie(autopct='%1.1f%%', startangle=90)
   ```

   Output: Pie chart untuk data yang diberikan.

---

### **8. hexbin()** = Membuat hexbin plot (grafik hexagonal) untuk dua variabel numerik, berguna untuk visualisasi data besar.  
   p :  
   - `x` : (str) Kolom untuk sumbu x.  
   - `y` : (str) Kolom untuk sumbu y.  
   - `gridsize` : (int, optional) Ukuran grid hexagonal.  
   - `cmap` : (str, optional) Skema warna.

   Contoh:
   ```python
   data = pd.DataFrame({
       'x': [1, 2, 3, 4, 5],
       'y': [5, 6, 7, 8, 9]
   })
   result = data.plot.hexbin(x='x', y='y', gridsize=10)
   ```

   Output: Hexbin plot untuk kolom `x` dan `y`.

---

### **9. hist2d()** = Membuat histogram 2D untuk dua variabel numerik dalam DataFrame atau Series.  
   p :  
   - `x` : (str) Kolom untuk sumbu x.  
   - `y` : (str) Kolom untuk sumbu y.  
   - `bins` : (int, optional) Jumlah bins untuk histogram.

   Contoh:
   ```python
   data = pd.DataFrame({
       'x': [1, 2, 3, 4],
       'y': [4, 3, 2, 1]
   })
   result = data.plot.hist2d(x='x', y='y', bins=4)
   ```

   Output: Histogram 2D untuk kolom `x` dan `y`.

---

### **10. density()** = Membuat plot kepadatan (density plot) untuk distribusi data.  
   p :  
   - `bw_method` : (float, optional) Parameter untuk bandwidth kernel estimator.  
   - `ind` : (array, optional) Titik evaluasi untuk distribusi.

   Contoh:
   ```python
   data = pd.Series([1, 2, 3, 4, 5])
   result = data.plot.density()
   ```

   Output: Plot kepadatan untuk data yang diberikan.

---
