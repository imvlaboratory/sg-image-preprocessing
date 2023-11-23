# Subplot
Pada Python, khususnya dalam pemrograman menggunakan library Matplotlib, fungsi subplot() digunakan untuk membuat tata letak (layout) subplot di dalam suatu gambar (figure). Subplot memungkinkan penempatan beberapa plot dalam satu gambar atau window grafik secara teratur dalam baris dan kolom.

Fungsi subplot() membutuhkan tiga parameter utama:

subplot(nrows, ncols, index): Ini mendefinisikan tata letak subplot dengan jumlah baris (nrows) dan jumlah kolom (ncols). Index adalah nomor plot tertentu yang akan digunakan dalam tata letak subplot. Index dimulai dari 1 hingga nrows * ncols.
Menggunakan matplotlib untuk memplot gambar pada output

```python

plt.subplot(2, 2, 1)
plt.imshow(img1_conv) 
plt.xticks([]),plt.yticks([]) 
plt.title('data1') 
    
plt.subplot(2, 2, 2) 
plt.imshow(img2_conv) 
plt.xticks([]),plt.yticks([]) 
plt.title('data2') 

plt.subplot(2, 2, 3) 
plt.imshow(img3_conv) 
plt.xticks([]),plt.yticks([]) 
plt.title('data3') 
    
plt.subplot(2, 2, 4) 
plt.imshow(img4_conv) 
plt.xticks([]),plt.yticks([]) 
plt.title('data4')

``` 