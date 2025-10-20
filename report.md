# Mid Term Examination — Drawing Canvas Application

Program ini dibuat menggunakan **Qt Framework (C++)**, tujuannya untuk membuat sebuah aplikasi sederhana yang bisa digunakan untuk menggambar titik di kanvas, menghubungkan titik-titik tersebut dengan garis, dan mendeteksi segmen dari gambar yang sudah dibuat. Dari tugas ini, saya belajar bagaimana cara menangani event di Qt, menggambar menggunakan `QPainter`, dan juga sedikit konsep dasar image processing.

Program ini punya beberapa file utama. Di dalam `drawingcanvas.h`, terdapat deklarasi kelas `DrawingCanvas` yang mengatur seluruh logika kanvas. Lalu di `drawingcanvas.cpp`, semua fungsi utama seperti menggambar titik, membuat garis, dan mendeteksi segmen diimplementasikan. File `mainwindow.cpp` digunakan untuk mengatur tombol-tombol seperti **Draw Lines**, **Detect Segment**, dan **Clear Canvas**, sementara file `main.cpp` menjadi bagian yang menjalankan aplikasi secara keseluruhan.

Pada bagian fungsinya, setiap kali pengguna mengklik area kanvas, posisi klik tersebut disimpan lewat fungsi `mousePressEvent`. Garis antara titik-titik akan digambar menggunakan fungsi `paintLines`, dengan warna merah agar mudah terlihat. Fungsi `segmentDetection` digunakan untuk mengambil gambar dari kanvas, lalu membaca setiap pikselnya. Piksel yang bukan warna putih dianggap sebagai bagian dari objek atau segmen, kemudian hasil perhitungannya ditampilkan di *console output*. Terakhir, fungsi `clearPoints` dipakai untuk menghapus semua titik dan memperbarui tampilan kanvas.

Dari hasil pengujian, semua fitur berjalan sesuai harapan. Titik berwarna biru muncul di tempat yang diklik, dan garis merah berhasil menghubungkan setiap dua titik yang dibuat. Setelah menekan **Detect Segment**, muncul output di console seperti ini:

```
paint lines block is called  
image width 600  
image height 403  
Detected 960 regions
```

Dari hasil itu bisa disimpulkan kalau proses deteksi segmen sudah berjalan dengan benar, karena program bisa mengenali area yang bukan berwarna putih di kanvas sebagai bagian dari gambar yang dideteksi.

Secara keseluruhan, program ini sudah memenuhi semua perintah dari soal. Semua fungsi bisa dijalankan tanpa error, baik untuk menggambar titik, membuat garis, maupun mendeteksi segmen. Aplikasinya juga bisa dijalankan dengan lancar di **Qt Creator** tanpa ada crash. Tugas ini cukup membantu saya memahami alur dasar pembuatan aplikasi GUI di Qt dan bagaimana cara memproses gambar secara sederhana.

# Referensi
Dalam proses pengerjaan, saya sempat berdiskusi dan mencari referensi tambahan mengenai implementasi `QPainter` dan cara kerja `segment detection` di Qt.  
Beberapa penjelasan tambahan saya baca melalui Gemini di link berikut:
[https://gemini.google.com/share/b3dce98e79ae]
