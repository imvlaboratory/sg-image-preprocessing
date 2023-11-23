# Orienting
Gambar bisa di putar orientasinya. Bisa 90 derajat, 180 derajat, atau sudut lainnya. Pada python pun juga dapat memutar orientasi gambar sesuai keinginan.

# Orienting using Cv2
    
- cv2.rotate()
Penggunaannya menggunakan syntax penjelas seperti berikut:
```python
cv2.ROTATE_90_CLOCKWISE
cv2.ROTATE_90_COUNTERCLOCKWISE
cv2.ROTATE_180

# contoh: 
img_rotate_90_clockwise = cv2.rotate(img, cv2.ROTATE_90_CLOCKWISE)
```       
        

- cv2.flip() 
    Penggunaannya menggunakan flipcode untuk menentukan sumbu flip:
```python
flipcode = 0: flip vertically
flipcode > 0: flip horizontally
flipcode < 0: flip vertically and horizontally

# contoh 
img_flip_ud = cv2.flip(img, 0)

```
        
# Orienting using numpy
    
- np.rot90()

    Secara default diputar 90 derajat CCW
    diperlukan argument tambahan untuk mengubah derajat rotasi

    - kode 2 untuk 180 derajat
    - kode 3 untuk 270 derajat
```python
# use case : 
Image.fromarray(np.rot90(img, 2)).save('data/dst/lena_np_rot90_180.jpg')

```
- np.flip()
    
    Untuk flip sendiri memiliki variasi vertikal dan horizontal yang dapat digunakan sesuai keinginan user
        
- np.flipud() flips vertical (up and down)
- np.fliplr() flips horizontal (left and right).
        
    np.flip() bisa digunakan untuk flip horizontal maupun vertikal, tapi lebih mudah menggunakan np.flipud() dan np.fliplr()
```python
# use case :
Image.fromarray(np.flip(img, (0, 1))).save('data/dst/lena_np_flip_ud_lr.jpg')

```
       