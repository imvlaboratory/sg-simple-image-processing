# Menggambar Bentuk

Package OpenCV dapat membantu kita dalam menggambar bentuk-bentuk geometri seperti garis, lingkaran, kotak, dan poligon. Lihat dokumentasi lengkapnya [di sini](https://docs.opencv.org/3.4/dc/da5/tutorial_py_drawing_functions.html).

## Membuat Kotak Hasil Deteksi

Untuk keperluan materi ini kita hanya akan menggunakan fungsi `rectangle` yang akan membuat suatu kotak apabila diberikan koordinat.

```python
cv2.rectangle(
    src,        # Sumber gambar
    pt1,        # Titik koordinat
    pt2,        # Titik koordinat oposisi dari pt1
    color,      # Kode warna garis
    thickness,  # Ketebalan garis
)
```

Dengan menggunakan output koordinat berupa array NumPy 2D yang sebelumnya telah diberikan sebagai nilai balik `detectMultiScale`, kita dapat dengan mudah memberikan nilai `pt1` dan `pt2`, berikut contoh dari hasil output pada materi sebelumnya:

```python
for x, y, w, h in detect:
    cv2.rectangle(
        lena_read,
        (x,y),
        (x+w, y+h),     
        (0, 255, 0),   
        3,              
    )
```

Fungsi di atas akan menggambar sebuak kotak dari koordinat yang telah diberikan, mewarnai garis dengan warna hijau, dan menentukan tebal garis.

## Menampilkan Gambar Dengan Kotak Deteksi

Untuk menampilkan kembali gambar yang telah digambar dengan `cv2.rectangle()`, kita hanya perlu untuk menjalankan fungsi `cv2.imshow()` seperti contoh kode di bawah ini:

```python
cv2.imshow('Label Window', src)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

Fungsi `cv2.imshow()` menunjukkan gambar `src` melalui sebuah window baru yang terbuka dan memiliki label `'Label Window'`, isian string dapat diubah sesuai kebutuhan namun pastikan `src` adalah gambar yang ingin ditampilkan.

Fungsi `cv2.waitKey()` digunakan untuk membaca input keyboard dari pengguna, angka integer di dalamnya menentukan waktu delay yang dipasang untuk menutup window.

Fungsi `cv2.destroyAllWindows()` digunakan untuk menutup semua windows yang dibuka oleh OpenCV, fungsi ini diperlukan dalam menutup windows yang terbuka karena apabila dilakukan secara manual (menutup window dengan tombol silang yang ada), terkadang window akan stuck dan hang yang memerlukan restart kernel Jupyter untuk kembali dapat dijalankan.

### Good Luck! 🍀
