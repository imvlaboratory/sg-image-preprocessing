# Outline Stacking Image

Menggabungkan dua citra yang berbeda dalam satu window yang sama. Terdapat dua cara dalam melakukannya, yakni dengan vstack dan hstack, serta dengan menggunakan concatenate. 

Perbedaan stack dan concatenate terletak pada sumbunya, 

- Stack  : menggabungkan gambar disepanjang sumbu baru dan 
- Concatenate : menggabungkan gambar disepanjang sumbu yang sudah ada.



# Vstack

Di dalam pemrograman Python, vstack adalah sebuah fungsi yang ada dalam paket NumPy. Fungsi vstack digunakan untuk menumpuk (stack) array secara vertikal atau mendatar (dalam konteks matriks atau array dua dimensi). Istilah "vstack" merupakan kependekan dari "vertical stack".

Dengan menggunakan vstack, Anda dapat menggabungkan dua atau lebih array NumPy menjadi satu array baru. Ketika menggunakan vstack, array-array yang digabungkan harus memiliki ukuran yang sama pada dimensi yang tidak digabungkan.

Vstack dapat juga digunakan untuk menumpuk citra yang telah dibaca

dengan syntax :
```python
img = cv2.imread('nama_file.png') 
img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
np_vertical = np.vstack((img,img_hsv))
```

# Hstack

Di dalam pemrograman Python, khususnya menggunakan paket NumPy, hstack adalah sebuah fungsi yang digunakan untuk menumpuk (stack) array secara horizontal. Istilah "hstack" adalah singkatan dari "horizontal stack".

Fungsi hstack memungkinkan penggabungan (concatenation) dari dua atau lebih array NumPy menjadi satu array baru. Ketika menggunakan hstack, array-array yang digabungkan harus memiliki ukuran yang sama pada dimensi yang tidak digabungkan.


```python
img = cv2.imread('nama_file.png') 
img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
np_horizontal =np.hstack((img,img_hsv)) 
```

# Concatenate
np.concatenate yang berfungsi untuk menggabungkan (bukan menjumlahkan) suatu nilai matriks berdasarkan nilai axis yang diberikan. Jika axis = 0, maka matriks akan digabungkan secara vertikal (dengan matriks pada argumen kedua fungsi concatenate, dan posisinya akan berada di bawahnya). Kemudian jika axis = 1, maka matriks akan digabungkan secara horizontal.
```python
# vertical
vertical_concat=np.concatenate((img,img_hsv),axis=0)


#horizontal 
horizontal_concat=np.concatenate((img,img_hsv),axis =1)     
```