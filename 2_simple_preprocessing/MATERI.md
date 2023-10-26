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

## Color Corection
- Karena gambar memiliki nilai matrix RGB untuk menyimpan informasi warna, nilai tsb dapat diubah.

Bahasa mudahnya adalah mengedit warna gambar tsb. Pasti pernah kan lihat ada filter yang bisa mengubah gambar biasa jadi gambar hitam putih?? nah secara garis besar seperti itu. Pada python kita dapat memanipulasi warna gambar sesuai kebutuhan.