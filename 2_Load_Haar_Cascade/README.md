# Haar Cascade [<img src="https://github.githubassets.com/assets/GitHub-Logo-ee398b662d42.png" height="20em" align="center" alt="Haar Github" title="Haar Github"/>](https://github.com/opencv/opencv/tree/master/data/haarcascades)

Silahkan buka GitHub menuju repository Haar Cascade Clasifier dengan menekan logo GitHub yang ada di judul materi ini. GitHub ini yang telah disediakan oleh tim OpenCV dan dapat digunakan langsung bersama package OpenCV.

## Load Haar Cascade

Download Haar Cascade dari repository [GitHub OpenCV](https://github.com/opencv/opencv/tree/master/data/haarcascades) yang asli, download file `haarcascade_frontalface_default.xml` untuk file detektor wajah tampak depan, terdapat juga beberapa file lain untuk tipe deteksi lainnya.

Jalankan kode di bawah ini di dalam projek untuk memuat file Haar Cascade.

```python
file_path = 'path/to/file/haarcascade_frontalface_default.xml'
classifier = cv2.CascadeClassifier(file_path)
```

## Detection

Untuk melakukan deteksi wajah, dapat menggunakan metode `detectMultiscale()`, berikut kodenya:

```python
detect = cv2.classifier.detectMultiScale(
    src,            # Parameter sumber gambar
    scaleFactor,    # Parameter seberapa besar gambar dikecilkan saat deteksi
    minNeighbors,   # Berapa banyak tetangga disekitar kotak detektor untuk menyatakan hasil deteksi
    minSize,        # Ukuran terkecil objek, lebih kecil tidak dianggap
    maxSize         # Ukuran maksimum objek, lebih besar tidak dianggap
)
```

Untuk lebih lanjut, silakan temui dokumentasi OpenCV mengenai metode `detectMultiScale` [di sini](https://docs.opencv.org/3.4/d1/de5/classcv_1_1CascadeClassifier.html).

Tidak semua parameter perlu diberikan, hanya parameter `src` yang wajib. Apabila program dijalankan dan tidak mengeluarkan error, kemungkinan besar deteksi berhasil dijalankan. Untuk melihat apakah terdeteksi wajah di gambar yang diberikan, gunakan fungsi `print` pada variable yang dipakai untuk `detectMultiScale`, pada materi ini digunakan variabel `detect`.

## Output Detector

```python
print(detect)
```

Output:

```python
[[137 128 115 115]]
# Koordinat kotak berupa NumPy 2D-Array
```

Output di atas hanyalah contoh dari hasil yang dapat dikeluarkan, berbeda gambar yang diberikan akan mengeluarkan koordinat yang berbeda. Apabila detektor mendeteksi lebih dari satu wajah, akan mengembalikan lebih dari satu koordinat.

Output:

```python
[[ 492  262  681  681]   # Koordinat wajah #1
 [1142  306  620  620]   # Koordinat wajah #2
 [  40  371  602  602]   # Koordinat wajah #3
 [ 214 1081   78   78]]  # Koordinat wajah #4
```

Setelah mendapatkan titik-titik koordinat tersebut, langkah selanjutnya adalah menggambar kotak untuk memvisualisasikan hasil output tersebut yang dibahas pada submateri selanjutnya.

### Good Luck! 🍀
