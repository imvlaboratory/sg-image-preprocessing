# Color Modification
Karena gambar memiliki nilai matrix RGB untuk menyimpan informasi warna, nilai tsb dapat diubah.

Bahasa mudahnya adalah mengedit warna gambar tsb. Pasti pernah kan lihat ada filter yang bisa mengubah gambar biasa jadi gambar hitam putih?? nah secara garis besar seperti itu. Pada python kita dapat memanipulasi warna gambar sesuai kebutuhan.

# CV2 Color Space
Sintaks yang digunakan merupakan cv2.cvtColor, terdapat banyak variasi untuk konversi warna ini.

- cv2.COLOR_BGR2GRAY: Konversi dari ruang warna BGR (Blue-Green-Red) ke citra grayscale. Setiap piksel pada citra grayscale hanya memiliki satu saluran yang mewakili kecerahan atau intensitas, tanpa informasi warna.

- cv2.COLOR_GRAY2BGR: Konversi dari citra grayscale ke ruang warna BGR. Mengubah citra grayscale kembali ke format BGR dengan menyalin saluran intensitas ke semua saluran (Blue-Green-Red).

- cv2.COLOR_BGR2RGB: Konversi dari ruang warna BGR ke ruang warna RGB. Kebanyakan perangkat lunak dan tampilan monitor menggunakan ruang warna RGB, sehingga konversi ini berguna ketika ingin menampilkan hasil dari OpenCV ke perangkat atau aplikasi yang menggunakan RGB.

- cv2.COLOR_RGB2BGR: Konversi dari ruang warna RGB ke ruang warna BGR. Ini adalah kebalikan dari cv2.COLOR_BGR2RGB.

- cv2.COLOR_BGR2HSV: Konversi dari ruang warna BGR ke ruang warna HSV (Hue-Saturation-Value). Ruang warna HSV lebih intuitif dalam memanipulasi warna karena memisahkan informasi warna (hue), saturasi, dan nilai kecerahan.

- cv2.COLOR_HSV2BGR: Konversi dari ruang warna HSV ke ruang warna BGR. Ini adalah kebalikan dari cv2.COLOR_BGR2HSV.

- cv2.COLOR_BGR2LAB: Konversi dari ruang warna BGR ke ruang warna CIELAB (Lab*). Ruang warna LAB sering digunakan dalam pengolahan citra untuk memanipulasi warna dengan lebih mudah.

- cv2.COLOR_LAB2BGR: Konversi dari ruang warna CIELAB ke ruang warna BGR. Ini adalah kebalikan dari cv2.COLOR_BGR2LAB.

```python
img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
image = cv2.cvtColor(src, cv2.COLOR_BGR2GRAY) 
```
    
