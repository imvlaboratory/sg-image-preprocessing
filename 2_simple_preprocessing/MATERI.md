## Pendahuluan Image Preprocessing
1. Apa itu Image Preprocessing?
    - Seperti arti bahasa Indonesianya, yaitu melakukan penyiapan sebelum sebuah gambar di proses.
    - Merupakan tahap memformat gambar/citra yang meliputi resizing, orienting, color correction, dsb.
2. Mengapa perlu image preprocessing?
    - Alasan utamanya adalah untuk membersihkan data berupa gambar
    - Menseragamkan data gambar, data yang seragam lebih rendah terkena potensi error dalam pengelolaan gambar.

## Resize
- Pernah ga sih sadar kalau gambar itu punya ukuran???
coba deh liat misalnya ada kamera yang memiliki sensor 12 MP mampu menangkap gambar 4000 x 3000 Pixels.
Sementara kamera 8 MP secara teoritis hanya mampu menangkap gambar 3840x2160 Pixels.

notes: pixel itu satuan yang dipakai dalam citra/gambar, digunakan umumnya untuk kamera dan display (monitor, LCD HP, Panel OLED, dsb)

- Gambar itu bisa diubah ukurannya
Misalnya sih gambar yang resolusinya 4K bisa kita turunkan atau resize ke resolusi 1080 pixels.
Bisa juga sebaliknya, gambar yang resolusi nya 1080 pixels bisa di resize ke ukuran yang lebih besar, tapi ya nanti hasilnya jadi pecah.

## Orienting
- Simple aja sih, gambar bisa di putar orientasinya. Bisa 90 derajat, 180 derajat, atau sudut lainnya. Pada python pun juga dapat memutar orientasi gambar sesuai keinginan.

- Orienting using Cv2
basic syntax yang digunakan  adalah 
    - cv2.rotate() untuk rotasi 
    Penggunaannya menggunakan syntax penjelas seperti berikut:
    cv2.ROTATE_90_CLOCKWISE
    cv2.ROTATE_90_COUNTERCLOCKWISE
    cv2.ROTATE_180

    use case: 
    img_rotate_90_clockwise = cv2.rotate(img, cv2.ROTATE_90_CLOCKWISE)

    - cv2.flip() untuk flip gambar
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

## Color Corection
- Karena gambar memiliki nilai matrix RGB untuk menyimpan informasi warna, nilai tsb dapat diubah.

Bahasa mudahnya adalah mengedit warna gambar tsb. Pasti pernah kan lihat ada filter yang bisa mengubah gambar biasa jadi gambar hitam putih?? nah secara garis besar seperti itu. Pada python kita dapat memanipulasi warna gambar sesuai kebutuhan.