# OpenCV [<img src="https://opencv1.b-cdn.net/wp-content/uploads/2022/05/logo.png" height="30em" align="center" alt="OpenCV" title="OpenCV Site"/>](https://opencv.org/)

Seperti yang sudah dipelajari pada materi sebelumnya, pada kali ini package OpenCV akan digunakan untuk keperluan deteksi wajah. Pastikan OpenCV telah diinstall, apabila belum gunakan perintah ini:

```bash
pip install opencv_python
```

Gunakan perintah ini untuk memasukkan OpenCV ke dalam projek:

```python
import cv2
```

## Load and Prepare an Image

OpenCV dapat membaca dan membuka file gambar yang diberikan, namun apa sebenarnya yang dibaca oleh kode?

<img src="lena.png" height="200em" align="center" alt="Lena" title="Lena"/>

Manusia dapat melihat gambar dan warna karena pantulan cahaya yang mengenai retina, di dalam sebuah retina terdapat sel sensitif (cone & rod) yang mengubah frekuensi cahaya yang diterima menjadi suatu sinyal yang dialirkan ke dalam otak. Otak lalu menafsirkan sinyal tersebut sebagai bentuk dan warna yang kita lihat.

Hal yang sama tidak dapat dikatakan untuk sebuah program dalam menafsirkan warna.

```python
lena_path = 'lena.png'
lena_read = cv2.imread(lena_path)
print(type(lena_read))
```

Output:

```bash
<class 'numpy.ndarray'>
```

Kode di atas membaca file 'lena.png' dan menentukan tipe dari variabel **lena_read** yang menjalankan fungsi `imread` dari OpenCV. Perhatikan output, `type` mengembalikan <class 'numpy.ndarray'> sebagai bentuk dari gambar yang telah dibaca.

### What is a numpy.ndarray?

NumPy adalah salah satu package yang menjadi kebutuhan dalam memproses gambar menggunakan OpenCV. Di dalamnya, NumPy sering digunakan untuk secara mudah membentuk array multidimensi yang memiliki ukuran besar.

Secara kode, sebuah gambar adalah array multidimensi yang dipenuhi oleh kode penentu warna, biasanya kode RGB. Jalankan perintah ini:

```python
print(lena_read)
```

Perhatikan output yang diberikan oleh perintah di atas, bandingkan dengan output dari perintah di bawah ini yang sudah mengubah gambar Lena menjadi hitam putih:

```python
lena_GRAY = cv2.cvtColor(lena_read, cv2.COLOR_RGB2GRAY)
print(lena_GRAY)
```

[<img src="https://i0.wp.com/indianaiproduction.com/wp-content/uploads/2019/06/NumPy-array.png?resize=640%2C307&ssl=1" height="200em" align="center" alt="Multidimensional Array" title="Multidimensional Array"/>](https://indianaiproduction.com/python-numpy-array/)

Gambar Lena yang masih berwarna merupakan NumPy 3D Array, sedangkan Lena yang sudah diwarnai hitam putih merupakan NumPy 2D Array.

### Good Luck! 🍀
