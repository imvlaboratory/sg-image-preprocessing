# Pendahuluan Image Preprocessing
1. Apa itu Image Preprocessing?
    - Seperti arti bahasa Indonesianya, yaitu melakukan penyiapan sebelum sebuah gambar di proses.
    - Merupakan tahap memformat gambar/citra yang meliputi resizing, orienting, color correction, dsb.
2. Mengapa perlu image preprocessing?
    - Alasan utamanya adalah untuk membersihkan data berupa gambar
    - Menseragamkan data gambar, data yang seragam lebih rendah terkena potensi error dalam pengelolaan gambar.

## Load Image
    
Membaca suatu file citra dan memberikan output berupa suatu matriks yang memuat nilai-nilai piksel dari file citra yang dibaca.  
                                
    namavariable = cv2.imread('namafile.format')
    contoh:
    img = cv2.imread('baboon.png')

## Show Image
Menampilkan gambar yang telah dibaca pada windows baru

    cv2.imshow("nama windows yang diinginkan", namavariable)
    contoh: 
    cv2.imshow("Image Baboon",img)
    cv2.waitKey(0) 
    cv2.destroyAllWindows() 

Pada baris pertama perintah diatas, terdapat argumen pertama dari fungsi imshow yang bertuliskan Image Baboon. Argumen pertama ini berfungsi untuk menamai window citra yang akan ditampilkan. Sedangkan argumen kedua merupakan citra yang akan ditampilkan. Kemudian pada baris kedua terdapat fungsi yang bernama waitKey(0) dan memiliki nilai waktu dalam satuan millisecond sebagai argumen yang berfungsi sebagai waktu jeda bagi window agar tertutup secara otomatis. Supaya window terbuka terus sampai ditutup secara manual, maka diisi 0. destroyAllWindows() digunakan untuk mengeluarkan semua windows.
## Save Image
Berfungsi untuk menyimpan sebuah citra.

    cv2.imwrite('baboon_new.jpg', img)
output
    
    true

## Mengakses dan Memodifikasi Informasi Pixel pada Gambar
Nilai suatu pixel pada gambar dapat direpresentasikan dalam bentuk koordinat baris dan kolom. Bentuk dari informasi ini merupakan array yang terdiri dari nilai Blue, Green, Red (warna dasar BGR). Nilai dari BGR bergantung pada kondisi yang ada.

    import numpy as np  
    import cv2  
    img = cv2.imread("baboon.png",1)  
    pixel = img[100,100]  
    <!-- membaca informasi di pixel baris 100 kolom 100 -->
    print(pixel)  

output:

    [145 138  88]
    <!-- Merupakan nilai BGR secara berurutan -->

## Vstack, Hstack, dan Concatenate
Menggabungkan dua citra yang berbeda dalam satu window yang sama. Terdapat dua cara dalam melakukannya, yakni dengan vstack dan hstack, serta dengan menggunakan concatenate. Perbedaan stack dan concatenate terletak pada sumbunya, dimana bila stack menggabungkan gambar disepanjang sumbu baru dan concatenate menggabungkan gambar disepanjang sumbu yang sudah ada.

Terdapat dua cara yang bisa digunakan untuk melakukannya, yakni dengan menggunakan np.vstack dan np.hstack, dan juga dengan menggunakan np.concatenate yang berfungsi untuk menggabungkan (bukan menjumlahkan) suatu nilai matriks berdasarkan nilai axis yang diberikan. Jika axis = 0, maka matriks akan digabungkan secara vertikal (dengan matriks pada argumen kedua fungsi concatenate, dan posisinya akan berada di bawahnya). Kemudian jika axis = 1, maka matriks akan digabungkan secara horizontal.


    # Stack

    import cv2 
    import numpy as np 
    
    img = cv2.imread('baboon.png') 
    img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
    
    np_vertical = np.vstack((img,img_hsv)) 
    np_horizontal =np.hstack((img,img_hsv)) 

    cv2.imshow("Vertical Stack", np_vertical) 
    cv2.imshow("Horizontal Stack", np_horizontal) 

    cv2.waitKey(0)
    cv2.destroyAllWindows()


    #Concatenate

    import cv2
    import numpy as np

    img = cv2.imread('baboon.png') 
    img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
    
    vertical_concat=np.concatenate((img,img_hsv),axis=0) 
    horizontal_concat=np.concatenate((img,img_hsv),axis =1) 

    cv2.imshow("Vertical Concatenate", vertical_concat) 
    cv2.imshow("Horizontal Concatenate", horizontal_concat) 
    
    cv2.waitKey(0) 
    cv2.destroyAllWindows()
 ## Penskalaan Gambar (Resize)


Pernah ga sih sadar kalau gambar itu punya ukuran???
coba deh liat misalnya ada kamera yang memiliki sensor 12 MP mampu menangkap gambar 4000 x 3000 Pixels.
Sementara kamera 8 MP secara teoritis hanya mampu menangkap gambar 3840x2160 Pixels.

notes: pixel itu satuan yang dipakai dalam citra/gambar, digunakan umumnya untuk kamera dan display (monitor, LCD HP, Panel OLED, dsb)

- Gambar itu bisa diubah ukurannya
Misalnya sih gambar yang resolusinya 4K bisa kita turunkan atau resize ke resolusi 1080 pixels.
Bisa juga sebaliknya, gambar yang resolusi nya 1080 pixels bisa di resize ke ukuran yang lebih besar, tapi ya nanti hasilnya jadi pecah.

Sintaksnya:
 ![Alt text](image.png)

    import cv2

    img = cv2.imread('lena.png') 
    
    print('Original Dimensions : ',img.shape) 
    
    scale_percent = 60
    width = int(img.shape[1] * scale_percent / 100) 
    height = int(img.shape[0] * scale_percent / 100) 
    dim = (width, height) 

    # resize image 
    resized = cv2.resize(img, dim, interpolation = cv2.INTER_AREA)

    print('Resized Dimensions : ',resized.shape) 
    
    cv2.imshow("Original image", img) 
    cv2.imshow("Resized image", resized) 
    cv2.waitKey(0)
    cv2.destroyAllWindows()

3 Metode dalam penskalaan, nanti perbedaannya akan kita coba satu persatu.

### a. INTER NEAREST : Interpolasi nearest-neighbor.
Interpolasi jenis ini merupakan interpolasi paling sederhana. Dimana hasilnya diambil dari tetangga yang terdekat.

### b. INTER LINEAR : Interpolasi bilinear (default)
Interpolasi jenis INTER LINEAR ini dihasilkan melalui sumbu x linear dan sumbu y linear.

### c. INTER AREA : Melakukan resampling menggunakan relasi area piksel.
INTER AREA merupakan method yang lebih disarankan untuk digunakan karena ia memberikan hasil citra yang moire-free.


## Orienting
Gambar bisa di putar orientasinya. Bisa 90 derajat, 180 derajat, atau sudut lainnya. Pada python pun juga dapat memutar orientasi gambar sesuai keinginan.

Orienting using Cv2
    
- cv2.rotate()
Penggunaannya menggunakan syntax penjelas seperti berikut:
        
        cv2.ROTATE_90_CLOCKWISE
        cv2.ROTATE_90_COUNTERCLOCKWISE
        cv2.ROTATE_180
        contoh: 
        img_rotate_90_clockwise = cv2.rotate(img, cv2.ROTATE_90_CLOCKWISE)

- cv2.flip() 
    Penggunaannya menggunakan flipcode untuk menentukan sumbu flip:

        flipcode = 0: flip vertically
        flipcode > 0: flip horizontally
        flipcode < 0: flip vertically and horizontally

        use case: 
        img_flip_ud = cv2.flip(img, 0)

- Orienting using numpy
    
    - np.rot90()
    Secara default diputar 90 derajat CCW
    diperlukan argument tambahan untuk mengubah derajat rotasi

    kode 2 untuk 180 derajat
    kode 3 untuk 270 derajat

        use case : 
        Image.fromarray(np.rot90(img, 2)).save('data/dst/lena_np_rot90_180.jpg')

    - np.flip()

    Untuk flip sendiri memiliki variasi vertical dan horizontal yang dapat digunakan sesuai keinginan user
        
    np.flipud() flips vertical (up and down)
        
    np.fliplr() flips horizontal (left and right).
        
    np.flip() bisa digunakan untuk flip horizontal maupun vertikal, tapi lebih mudah menggunakan np.flipud() dan np.fliplr()

        use case :
        Image.fromarray(np.flip(img, (0, 1))).save('data/dst/lena_np_flip_ud_lr.jpg')

## Color Modification
Karena gambar memiliki nilai matrix RGB untuk menyimpan informasi warna, nilai tsb dapat diubah.

Bahasa mudahnya adalah mengedit warna gambar tsb. Pasti pernah kan lihat ada filter yang bisa mengubah gambar biasa jadi gambar hitam putih?? nah secara garis besar seperti itu. Pada python kita dapat memanipulasi warna gambar sesuai kebutuhan.

Sintaks yang digunakan merupakan cv2.cvtColor, terdapat banyak variasi untuk konversi warna ini.

    img_hsv = cv2.cvtColor(img,cv2.COLOR_BGR2HSV) 
    image = cv2.cvtColor(src, cv2.COLOR_BGR2GRAY) 


## Subplot
Menggunakan matplotlib untuk memplot gambar pada output

    import cv2
    from matplotlib import pyplot as plt

    img1 = cv2.imread("baboon.png")
    img2 = cv2.imread("mountain.jpg")
    img3 = cv2.imread("car.jpg")
    img4 = cv2.imread("lena.png")

    img1_conv = cv2.cvtColor(img1,cv2.COLOR_BGR2RGB)
    img2_conv = cv2.cvtColor(img2,cv2.COLOR_BGR2RGB)
    img3_conv = cv2.cvtColor(img3,cv2.COLOR_BGR2RGB)
    img4_conv = cv2.cvtColor(img4,cv2.COLOR_BGR2RGB)

    plt.subplot(2, 2, 1)
    plt.imshow(img1_conv) 
    plt.xticks([]),plt.yticks([]) 
    plt.title('Baboon') 
    
    plt.subplot(2, 2, 2) 
    plt.imshow(img2_conv) 
    plt.xticks([]),plt.yticks([]) 
    plt.title('Mountain') 

    plt.subplot(2, 2, 3) 
    plt.imshow(img3_conv) 
    plt.xticks([]),plt.yticks([]) 
    plt.title('Car') 
    
    plt.subplot(2, 2, 4) 
    plt.imshow(img4_conv) 
    plt.xticks([]),plt.yticks([]) 
    plt.title('Lena') 
#### REFERENSI 
https://www.javatpoint.com/opencv-canny-edge-detection