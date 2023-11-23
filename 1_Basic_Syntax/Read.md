# Outline Basic Syntax
Pada file ini terdapat materi tentang cara membaca gambar, menampilkan gambar, dan menyimpan gambar dengan menggunakan library cv2 pada python.

# Load Image
    
Membaca suatu file citra dan memberikan output berupa suatu matriks yang memuat nilai-nilai piksel dari file citra yang dibaca.  

```python                           
namavariable = cv2.imread('namafile.format')
    # contoh:
img = cv2.imread('baboon.png')
``` 
Membaca beberapa image file secara bersamaan menggunakan library glob

```python
import glob
path = glob.glob("alamat/ke/file/*.jpg")

for file in path
    img = cv2.imread(file)
```
perlu diperhatikan bahwa perintah glob di atas hanya dapat membaca jenis file .jpg saja

# Show Image

Menampilkan gambar yang telah dibaca pada windows baru
``` python
cv2.imshow("nama windows yang diinginkan", namavariable)
# contoh: 
cv2.imshow("Image Baboon",img)
cv2.waitKey(0) 
cv2.destroyAllWindows() 
```
Pada baris pertama perintah diatas, terdapat argumen pertama dari fungsi imshow yang bertuliskan Image Baboon. 

Argumen pertama ini berfungsi untuk menamai window citra yang akan ditampilkan. Sedangkan argumen kedua merupakan citra yang akan ditampilkan. 

Kemudian pada baris kedua terdapat fungsi yang bernama waitKey(0) dan memiliki nilai waktu dalam satuan millisecond sebagai argumen yang berfungsi sebagai waktu jeda bagi window agar tertutup secara otomatis. 

Supaya window terbuka terus sampai ditutup secara manual, maka diisi 0. destroyAllWindows() digunakan untuk mengeluarkan semua windows.

## Save Image
Berfungsi untuk menyimpan sebuah citra. Penulisan menggunakan syntax yang tersedia pada library cv2

```python
cv2.imwrite('nama_file_yang_diinginkan.jpg', nama_variable)
```
output yang diharapkan

    true 

output jika error

    false 


# Mengakses dan Memodifikasi Informasi Pixel pada Gambar
Nilai suatu pixel pada gambar dapat direpresentasikan dalam bentuk koordinat baris dan kolom. Bentuk dari informasi ini merupakan array yang terdiri dari nilai Blue, Green, Red (warna dasar BGR). Nilai dari BGR bergantung pada kondisi yang ada.

```python
import numpy as np  
import cv2  
img = cv2.imread("baboon.png",1)  
pixel = img[100,100]  # membaca informasi di pixel baris 100 kolom 100
print(pixel)  
```
output:

    [145 138  88]
    <!-- Merupakan nilai BGR secara berurutan -->