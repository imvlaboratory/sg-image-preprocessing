# IMPORTANT!!!!!!

Sebelum belajar modul ini kalian harus melakukan hal ini yakk!!

Install Depedencies yang diperlukan dengan cara membuka TERMINAL dan mengetik command berikut:
    
1. Install OpenCV

        pip install opencv-python
   
2. Install numpy

        pip install numpy

3. Install Matplotlib

       pip install matplotlib
   
 # Pendahuluan Image Preprocessing
1. Apa itu Image Preprocessing?
    - Seperti arti bahasa Indonesianya, yaitu melakukan penyiapan sebelum sebuah gambar di proses.
    - Merupakan tahap memformat gambar/citra yang meliputi resizing, orienting, color correction, dsb.
2. Kompleksitas Data Gambar
    - Resolusi Berbeda: Gambar bisa memiliki resolusi yang berbeda-beda. Dalam sebuah dataset, perbedaan resolusi dapat mengganggu proses analisis atau mempengaruhi performa model.
    - Kualitas Beragam: Gambar dapat memiliki kualitas yang bervariasi, termasuk noise, kecerahan, atau kontras yang berbeda. Hal ini dapat mempengaruhi interpretasi dan analisis data.

3. Kebutuhan Preprocessing
    - Standardisasi Data: Preprocessing memungkinkan untuk standarisasi format data gambar, seperti ukuran yang sama atau skala warna yang seragam, untuk mempermudah analisis dan pemrosesan data lebih lanjut.
    - Pembersihan Data: Penghapusan noise, penghalusan, atau peningkatan kualitas gambar membantu meningkatkan kualitas data sebelum diolah oleh model atau algoritma.
    
4. Persiapan Data untuk Model
    - Kesiapan untuk Machine Learning: Preprocessing membantu dalam persiapan data gambar agar cocok untuk digunakan dalam model machine learning, seperti normalisasi, ekstraksi fitur, atau augmentasi data.
    - Efisiensi Model: Data yang sudah diproses dengan baik dapat meningkatkan efisiensi dan akurasi model, serta mengurangi waktu pelatihan.
5. Reduksi Overhead Komputasi
    - Pengurangan Kompleksitas: Beberapa teknik preprocessing, seperti pengurangan dimensi atau penyesuaian warna, dapat mengurangi kompleksitas data, sehingga mempercepat proses analisis dan komputasi.
6. Penerapan pada Berbagai Kasus Penggunaan
    - Vision Computing: Image preprocessing menjadi kunci dalam vision computing, seperti deteksi objek, klasifikasi gambar, segmentasi, atau pengenalan pola.
    - Bidang Medis: Dalam bidang medis, preprocessing membantu meningkatkan interpretasi gambar medis seperti MRI, CT scans, atau citra mikroskopis.
    - Pengolahan Citra: Dalam pengolahan citra lebih umum, seperti dalam industri fotografi, rekayasa, atau analisis visual.

Image preprocessing menjadi tahap penting dalam workflow pengolahan data gambar di Python, memungkinkan untuk mempersiapkan data dengan baik sebelum dilakukan tugas analisis atau pengolahan lebih lanjut. Dengan memahami latar belakang dan tujuan dari setiap teknik preprocessing, dapat dihasilkan data yang lebih baik dan hasil analisis yang lebih akurat.

## Topik Image Preprocessing

- [Basic Syntax](1_Basic_Syntax/Read.md)   
    - [Load Image](1_Basic_Syntax/Read.md#Load-Image)
    - [Show Image](1_Basic_Syntax/Read.md#Show-Image)
    - [Save Image](1_Basic_Syntax/Read.md#Save-Image)

- [Stacking Image](2_Stacking_Image/Read.md)
    - [Vstack](2_Stacking_Image/Read.md#vstack)
    - [HStack](2_Stacking_Image/Read.md#hstack)
    - [Concatenate](2_Stacking_Image/Read.md#concatenate)
- [Image Scale](3_Scale/Read.md)
    - [Penskalaan Gambar](3_Scale/Read.md#penskalaan-gambar-resize)
    - [Inter Nearest](3_Scale/Read.md#a-inter-nearest--interpolasi-nearest-neighbor)
    - [Inter Linear](3_Scale/Read.md#b-inter-linear--interpolasi-bilinear-default)
    - [Inter Area](3_Scale/Read.md#c-inter-area--melakukan-resampling-menggunakan-relasi-area-piksel)
- [Orienting](4_Orienting/Read.md)
    - [Orienting](4_Orienting/Read.md#orienting)
    - [Orienting CV2](4_Orienting/Read.md#orienting-using-cv2)
    - [Orienting Numpy](4_Orienting/Read.md#orienting-using-numpy)
- [Color Modification](5_Color_Modification/Read.md)
    - [Color Modification](5_Color_Modification/Read.md#cv2-color-space)
- [Subplot](6_Subplot/Read.md)

## REFERENSI 
https://www.javatpoint.com/opencv-canny-edge-detection
