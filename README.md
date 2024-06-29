# proyek-submission-bookshelf-api ARJUN NOURMANSYAH RAMDANI
Proyek Submission Bookshelf API | Tugas Akhir Kelas Belajar Membuat Aplikasi Back-End untuk Pemula dengan Google Cloud

Kriteria
--------

Terdapat 7 kriteria utama yang harus Anda penuhi dalam membuat proyek Bookshelf API.  
  

### Kriteria 1 : Aplikasi menggunakan port 9000

Aplikasi yang Anda buat harus menggunakan port 9000. Jika komputer yang Anda gunakan untuk membuat submission tidak bisa memakai port 9000,  buatlah submission dengan port lain, lalu ketika submission hendak dikirimkan silakan ganti portnya ke 9000.

  

### Kriteria 2 : Aplikasi dijalankan dengan perintah npm run start.

Aplikasi yang Anda buat harus memiliki runner script start. Cara membuatnya, Anda tambahkan properti start ke dalam properti scripts pada **package.json** seperti berikut:

Pastikan aplikasi **tidak** dijalankan dengan menggunakan **nodemon**. Jika Anda ingin menggunakan nodemon dalam proses development, masukkan nodemon kedalam runner script lain, contohnya:

### Kriteria 3 : API dapat menyimpan buku

API yang Anda buat harus dapat menyimpan buku melalui _route_:

*   Method : **POST**
*   URL : **/books**
*   Body Request:
    
Objek buku yang disimpan pada _server_ harus memiliki struktur seperti contoh di bawah ini:

Properti yang ditebalkan diolah dan didapatkan di sisi _server_. Berikut penjelasannya:

*   id : nilai id haruslah unik. Untuk membuat nilai unik, Anda bisa memanfaatkan [nanoid](https://www.npmjs.com/package/nanoid).
*   finished : merupakan properti _boolean_ yang menjelaskan apakah buku telah selesai dibaca atau belum. Nilai finished didapatkan dari observasi pageCount === readPage.
*   insertedAt : merupakan properti yang menampung tanggal dimasukkannya buku. Anda bisa gunakan new Date().toISOString() untuk menghasilkan nilainya.
*   updatedAt : merupakan properti yang menampung tanggal diperbarui buku. Ketika buku baru dimasukkan, berikan nilai properti ini sama dengan insertedAt.
    

Server harus merespons **gagal** bila:

*   Client tidak melampirkan properti namepada _request body_. Bila hal ini terjadi, maka _server_ akan merespons dengan:
    *   Status Code : **400**
    *   Response Body:
              
*   Client melampirkan nilai properti readPage yang lebih besar dari nilai properti pageCount. Bila hal ini terjadi, maka _server_ akan merespons dengan:
    *   Status Code : **400**
    *   Response Body:
        
Bila buku **berhasil** dimasukkan, _server_ harus mengembalikan respons dengan:

*   Status Code : **201**
*   Response Body:
    
  
### Kriteria 4 : API dapat menampilkan seluruh buku

API yang Anda buat harus dapat menampilkan seluruh buku yang disimpan melalui _route_:

*   Method : **GET**
*   URL: **/books**
    
 
Jika **belum** terdapat buku yang dimasukkan, _server_ bisa merespons dengan _array_ books kosong.


### Kriteria 5 : API dapat menampilkan detail buku

API yang Anda buat harus dapat menampilkan seluruh buku yang disimpan melalui _route_:

*   Method : **GET**
*   URL: **/books/{bookId}**
    
### Kriteria 6 : API dapat mengubah data buku

API yang Anda buat harus dapat mengubah data buku berdasarkan id melalui _route_:

*   Method : **PUT**
*   URL : **/books/{bookId}**
*   Body Request:
    
    
### Kriteria 7 : API dapat menghapus buku

API yang Anda buat harus dapat menghapus buku berdasarkan id melalui _route_ berikut:

*   Method : **DELETE**
*   URL: /books/{bookId}


    
