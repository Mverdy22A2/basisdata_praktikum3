# basisdata_praktikum3
## 1. melakukan penambahan data pada table mahasiswa dengan mengisi kd_ds yang belum ada pada data dosen

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/1bc8b935-0ff2-457e-9167-402cacfe4375)

## 2. menghapus satu record data pada table dosen yang telah dirujuk pada tabel mahasiswa.

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/8f4b622d-fbb3-4b94-82c2-48e1a8a8d455)

## 3. mengubah mode menjadi ON UPDATE CASCADE ON DELETE RESTRICT

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/0ef0b787-ab03-4471-a2b5-2bd511319bc8)

## 4. melakukan perubahan data pada table dosen (kd_ds)

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/2c8f5c46-7471-4f5c-ba5c-94cc9d35740b)

## 5. melakukan penghapusan data pada table dosen

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/6351dd39-2a17-495d-8643-e32b7195a3db)

## 6. mengubah mode menjadi ON UPDATE CASCADE ON DELETE SET NULL

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/91fcccb8-c2e5-47fc-80b6-8f8fe30b19bf)

## 7. melakukan penghapusan data pada table dosen

![image](https://github.com/verz666/basisdata_praktikum3/assets/115523263/566d55db-563c-44be-8069-464aef90c986)

# evaluasi dan pertanyaan 
## Apa bedanya penggunaan RESTRICT dan penggunaan CASCADE

Pada dasarnya, "RESTRICT" dan "CASCADE" adalah dua opsi yang dapat digunakan dalam hubungan referensial antara tabel di MySQL untuk mengatur perilaku saat dilakukan operasi penghapusan atau pembaruan data pada tabel utama. Berikut adalah perbedaan antara penggunaan "RESTRICT" dan "CASCADE":

RESTRICT:

- Dalam penggunaan "RESTRICT", jika ada baris data pada tabel utama yang memiliki referensi ke tabel lain, operasi penghapusan atau pembaruan pada baris tersebut akan ditolak.
- Misalnya, jika kita menggunakan "RESTRICT" pada penghapusan, ketika kita mencoba menghapus baris pada tabel utama yang memiliki referensi ke tabel lain, MySQL akan menolak penghapusan tersebut dan menghasilkan kesalahan.
- Dengan kata lain, "RESTRICT" membatasi tindakan penghapusan atau pembaruan jika ada referensi yang terkait.

CASCADE:

- Dalam penggunaan "CASCADE", jika ada baris data pada tabel utama yang memiliki referensi ke tabel lain, operasi penghapusan atau pembaruan pada baris tersebut akan mempengaruhi tabel lain juga.
- Misalnya, jika kita menggunakan "CASCADE" pada penghapusan, ketika kita menghapus baris pada tabel utama, MySQL akan secara otomatis menghapus baris yang terkait pada tabel lain yang memiliki referensi tersebut.
- Dengan kata lain, "CASCADE" menyebabkan tindakan penghapusan atau pembaruan terpropagasi ke tabel yang terkait.

Dalam kasus spesifik "ON UPDATE CASCADE ON DELETE SET NULL" yang telah disebutkan sebelumnya, penggunaan "CASCADE" akan mengakibatkan penghapusan data pada tabel utama juga menghapus data yang terkait pada tabel "dosen", sedangkan penggunaan "SET NULL" akan mengatur nilai kolom yang terkait pada tabel "dosen" menjadi NULL saat baris data pada tabel utama diperbarui atau dihapus.

Pemilihan antara "RESTRICT" dan "CASCADE" tergantung pada kebutuhan aplikasi dan logika bisnis yang terlibat dalam hubungan antara tabel-tabel tersebut.

## kesimpulan

RESTRICT:

- Menghalangi operasi penghapusan atau pembaruan pada baris data pada tabel utama jika ada referensi ke tabel lain.
- Menyebabkan MySQL menolak tindakan penghapusan atau pembaruan, menghasilkan kesalahan.
- Digunakan untuk mencegah kerusakan integritas referensial dan memastikan keberadaan referensi yang valid.

CASCADE:

- Mengakibatkan operasi penghapusan atau pembaruan pada baris data pada tabel utama mempengaruhi tabel terkait yang memiliki referensi.
- Menghapus baris data terkait pada tabel lain saat penghapusan pada tabel utama dengan menggunakan "CASCADE".
- Mengatur nilai kolom yang terkait menjadi NULL saat pembaruan atau penghapusan pada tabel utama dengan menggunakan "SET NULL".
- Digunakan untuk menjaga konsistensi data di antara tabel-tabel yang terkait dan menghindari duplikasi atau referensi yang tidak valid.

Pemilihan antara "RESTRICT" dan "CASCADE" tergantung pada kebutuhan aplikasi dan logika bisnis yang terlibat. Jika kita ingin membatasi atau mencegah penghapusan atau pembaruan yang dapat merusak referensi, maka "RESTRICT" cocok digunakan. Di sisi lain, jika kita ingin memastikan bahwa perubahan pada tabel utama secara otomatis mempengaruhi tabel terkait, termasuk penghapusan atau pengaturan nilai NULL, maka "CASCADE" dapat digunakan.

Adalah penting untuk memahami konsekuensi dari masing-masing opsi dan mempertimbangkan struktur database dan kebutuhan aplikasi secara menyeluruh sebelum memilih salah satu opsi tersebut.
