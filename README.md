# Writing-Week-5

**Senin, 24 Oktober 2022**

### Web Server & RESTful API


#### WEB SERVER
Web server adalah sebuah software (perangkat lunak) yang memberikan layanan berupa data.
Web server terdiri dari 2 komponen penting :
Hardware
Software

#### Hardware
Di sisi perangkat keras, server web adalah komputer yang menyimpan perangkat lunak server web dan file komponen situs web. (misalnya, dokumen HTML, gambar, CSS stylesheet, dan file JavaScript) Server web terhubung ke Internet dan mendukung pertukaran data fisik dengan perangkat lain yang terhubung ke web.


#### Software
Di sisi perangkat lunak, server web mencakup beberapa bagian yang mengontrol bagaimana pengguna web mengakses file yang dihosting. Minimal, ini adalah server HTTP. Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web). Server HTTP dapat diakses melalui nama domain situs web yang disimpannya, dan mengirimkan konten situs web yang dihosting ini ke perangkat pengguna akhir.


#### Static Web Server
Server web statis, atau tumpukan, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kami menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser Anda.


#### Dynamic Web Server
Sebuah server web dinamis terdiri dari server web statis ditambah perangkat lunak tambahan, paling sering server aplikasi dan database. Kami menyebutnya "dinamis" karena server aplikasi memperbarui file yang dihosting sebelum mengirim konten ke browser Anda melalui server HTTP





#### Server Side Programming
Server web menunggu pesan permintaan klien, memprosesnya saat tiba, dan membalas browser web dengan pesan respons HTTP. Respons berisi baris status yang menunjukkan apakah permintaan berhasil atau tidak (mis. "HTTP/1.1 200 OK" untuk berhasil).


#### Static Sites 
Diagram pada slide berikutnya menunjukkan arsitektur server web dasar untuk situs statis (situs statis adalah situs yang mengembalikan konten hard-coded yang sama dari server setiap kali sumber daya tertentu diminta). Saat pengguna ingin menavigasi ke halaman, browser mengirimkan permintaan "GET" HTTP yang menentukan URL-nya.


#### Dynamic Site
Situs web dinamis adalah situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan. Di situs web dinamis, halaman HTML biasanya dibuat dengan memasukkan data dari database ke dalam placeholder di template HTML (ini adalah cara yang jauh lebih efisien untuk menyimpan konten dalam jumlah besar daripada menggunakan situs web statis).

Situs dinamis dapat mengembalikan data yang berbeda untuk URL berdasarkan informasi yang diberikan oleh pengguna atau preferensi yang disimpan dan dapat melakukan operasi lain sebagai bagian dari pengembalian respons (misalnya, mengirim pemberitahuan).

#### Illustration Details
Permintaan untuk sumber daya statis ditangani dengan cara yang sama seperti untuk situs statis (sumber daya statis adalah file apa pun yang tidak berubah —biasanya: CSS, JavaScript, Gambar, file PDF yang dibuat sebelumnya, dll.).
Diagram sederhana dari server web yang menggunakan pemrograman sisi server untuk mendapatkan informasi dari database dan membuat HTML dari template. Ini adalah diagram yang sama seperti pada gambaran umum Client-Server. Permintaan untuk sumber daya dinamis malah diteruskan ke kode sisi server (ditunjukkan dalam diagram sebagai Aplikasi Web).
Untuk "permintaan dinamis" server menafsirkan permintaan, membaca informasi yang diperlukan dari database.
Menggabungkan data yang diambil dengan template HTML 
dan mengirimkan kembali respons yang berisi HTML yang dihasilkan (5,6)


#### Perbedaan Static dan Dynamic Site
Mereka memiliki tujuan dan perhatian yang berbeda.
Mereka umumnya tidak menggunakan bahasa pemrograman yang sama (pengecualiannya adalah JavaScript, yang dapat digunakan di sisi server dan klien).
Mereka berjalan di dalam lingkungan sistem operasi yang berbeda.


### REST
#### REST, atau Representational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain.
Sistem yang sesuai dengan REST, sering disebut sistem RESTful, dicirikan oleh bagaimana mereka tidak memiliki kewarganegaraan dan memisahkan masalah klien dan server


### Komunikasi antara Klien dan Server

Membuat Permintaan
REST mengharuskan klien membuat permintaan ke server untuk mengambil atau mengubah data di server. Permintaan umumnya terdiri dari:
kata kerja HTTP, yang mendefinisikan jenis operasi apa yang harus dilakukan
header, yang memungkinkan klien untuk menyampaikan informasi tentang permintaan
jalan menuju sumber daya
badan pesan opsional yang berisi data

HTTP VERBS
Ada 4 kata kerja HTTP dasar yang kami gunakan dalam permintaan untuk berinteraksi dengan sumber daya dalam sistem REST:
GET — mengambil sumber daya tertentu (berdasarkan id) atau kumpulan sumber daya
POST — buat sumber daya baru
PUT — perbarui sumber daya tertentu (berdasarkan id)
DELETE — menghapus sumber daya tertentu dengan id





#### Paths
Permintaan harus berisi jalur ke sumber daya tempat operasi harus dilakukan. Dalam RESTful API, jalur harus dirancang untuk membantu klien mengetahui apa yang sedang terjadi.
Jalur seperti skilvulstore.com/customers/223/orders/12 jelas dalam apa yang ditunjuknya, bahkan jika Anda belum pernah melihat jalur khusus ini sebelumnya, karena jalur ini bersifat hierarkis dan deskriptif.
Kita dapat melihat bahwa kita mengakses pesanan dengan id 12 untuk pelanggan dengan id 223.


### Sending Responses
#### Content Types
Misalnya, ketika klien mengakses sumber daya dengan id 23 di sumber artikel dengan  GET Request ini:

GET /artikel/23 HTTP/1.1
Accept: text/html, aplikasi/xhtml

Server mungkin mengirim kembali konten dengan header respons:

HTTP/1.1 200 (OK)
Tipe-Konten: teks/html

#### Response Codes
Tanggapan dari server berisi kode status untuk memperingatkan klien tentang informasi tentang keberhasilan operasi. Sebagai pengembang, Anda tidak perlu mengetahui setiap kode status (ada banyak kode status), tetapi Anda harus mengetahui kode yang paling umum dan cara penggunaannya.











**Selasa, 25 Oktober 2022**
### Intro & Essential Node JS

#### Node.js
Node.js adalah lingkungan runtime JavaScript open-source, lintas platform, back-end yang berjalan pada mesin V8 dan mengeksekusi kode JavaScript di luar browser web. Node.js memungkinkan pengembang menggunakan JavaScript untuk menulis alat baris perintah dan untuk skrip sisi server—menjalankan skrip sisi server untuk menghasilkan konten halaman web dinamis sebelum halaman dikirim ke browser web pengguna.


#### Node JS Architecture

#### Single Thread
Thread dalam ilmu komputer adalah eksekusi menjalankan beberapa tugas atau program secara bersamaan. Setiap unit yang mampu mengeksekusi kode disebut thread.

Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.


#### Even Loop
Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread
Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi.
Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.

#### Server Side Scripting
Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. 
Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”. 



### Javascript For Node JS

Sebelum masuk lebih dalam ke Node JS, terdapat beberapa materi yang perlu direview dan di pahami lagi dari bahasa pemrograman javascript agar mempermudah memahami Node JS  yaitu :
Arrow function expression
Asynchronous
JSON
#### Asynchronous
Asynchronous merupakan konsep yang paling penting dari javascript. Pada dasarnya, javascript mengeksekusi code secara single thread dan berurutan baris per baris yang disebut dengan synchronous. Sedangkan asynchronous memungkinkan mengeksekusi code tanpa berurutan dengan cara “skip” code dan melanjutkan eksekusi code selanjutnya. Konsep ini menungkinkan code kita tidak terjadi blocking dan lebih efisien.



### Membuat Web Server dengan Node JS

#### Node JS Web Server
Node.js memiliki built-in modul yang disebut HTTP, built-in modul ini memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP).
Modul HTTP dapat membuat server HTTP yang mendengarkan port server dan memberikan respons kembali ke klien.

Untuk menggunakan modul HTTP, gunakan require()


Gunakan method createServer() untuk membuat server HTTP


Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port 8080.


#### Menambahkan HTTP Header
Kita bisa menggunakan method res.writeHead() untuk menambahkan header HTTP.

Argumen pertama dari method res.writeHead() adalah status code, 200 berarti semuanya OK

Argumen kedua adalah objek yang berisi header respons.

Contoh : 
Jika respons dari server HTTP seharusnya ditampilkan sebagai HTML, maka kita harus menambahkan header HTTP dengan tipe konten yang benar
Respons yang dikembalikan dari HTTP web server bisa dalam berbagai format.

Contohnya, Kita bisa mengembalikan response dalam format JSON dan HTML, namun kita juga dapat mengembalikan format teks lain seperti XML dan CSV.

Selain itu web server dapat mengembalikan data non-teks seperti PDF, file zip, audio, dan video.

Format ini harus ditambahkan kedalam HTTP Header.


#### Membaca Query String
Callback function pada method http.createServer() memiliki argumen req yang mewakili request dari klien, sebagai objek (objek http.IncomingMessage).

Objek ini memiliki sebuah properti yang disebut "url" yang menyimpan informasi url yang sedang mengakses.
Ketika server di jalankan, kemudian kita akses dari browser ke url : http://localhost:8080/skilvul
maka akan tampil tulisan skilvul.

Ketika server di jalankan, kemudian kita akses dari browser ke url : http://localhost:8080/javascript
maka akan tampil tulisan javascript.



#### Split Query String
Ada build-in module yang bisa kita gunakan untuk split query string menjadi beberapa bagian yang dapat dibaca.

Build-in modulenya adalah URL Module.



































**Rabu, 26 Oktober 2022**
### Express JS

#### Express JS
Express.js, atau hanya Express, adalah kerangka aplikasi web back end untuk Node.js, dirilis sebagai perangkat lunak sumber terbuka dan gratis di bawah Lisensi MIT. Ini dirancang untuk membangun aplikasi web dan API. Ini telah disebut sebagai kerangka kerja server standar de facto untuk Node.js.


#### Back End Web Application
Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API

Kelebihan dari framework ini terletak pada fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.


#### Rest API
RESTful API / REST API merupakan penerapan dari API (Application Programming Interface). 

Sedangkan REST (Representional State Transfer) adalah sebuah arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi. Dengan tujuannya untuk menjadikan sistem memiliki performa yang baik, cepat dan mudah untuk di kembangkan (scale) terutama dalam pertukaran dan komunikasi data


##### RESTFUL API memiliki 4 komponen penting yaitu:

URL Design
HTTP Verbs
HTTP Response Code
Format Response.


#### Routes
Routes adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan
Kita bisa menjalankan aplikasi sederhana kita dengan cara menggunakan “node”. Dan aplikasi kita akan berjalan di alamat ‘http://localhost:3000’
Kemudian kita dapat mengaksesnya di website dan menambah route yang akan kita akses yaitu “/”


#### Method
Kita dapat menggunakan method yang dalam REST API seperti POST, PUT, PATCH dan DELETE

#### Response
Di dalam route kita dapat mengirim response menggunakan parameter dari route express.js yaitu “res.Send()” untuk mengirim plain text ketika kita mengakses route tersebut. Terdapat banyak response yang bisa kita buat selain yang dicontohkan.


#### Query
Query merupakan parameter yang digunakan untuk membantu menentukan tindakan yang lebih spesifik daripada hanya sekedar router biasa. Biasanya query ditaruh di akhir route dengan memberikan informasi diawali dengan “?” kemudian tedapat key dan data yang dapat ditindak lanjuti. Ex : “?q=hello&age=23” 



### Middleware
Middleware function adalah sebuah fungsi yang memiliki akses ke object request (req), object response (res), dan sebuah fungsi next didalam request-response cycle.
Fungsi next biasanya di berikan nama variable next.

#### Bagaimana Middleware Bekerja
Jika pada tahap mana pun middleware function menentukan bahwa suatu HTTP Request adalah request yang buruk dan salah, maka middleware function memiliki kemampuan untuk menghentikan request-response cycle.
Berlaku juga sebaliknya, jika middleware function menentukan suatu HTTP Request baik dan benar, maka middleware function memiliki kemampuan untuk melanjutkan request-response cycle ke proses selanjutnya.
Setelah sebuah HTTP Request melewati semua middleware yang ada di aplikasi, HTTP Request tersebut akan mencapai handler function — yang, dalam kasus contoh ilustrasi ini, adalah Anda yang menjual minuman lemon (atau, lebih khusus lagi, proses membuat minuman lemon).



#### Apa Saja Yang Bisa Dilakukan Oleh Function Middleware?
Pada Dasarnya, sebuah middleware function dapat melakukan tugas-tugas berikut :
Menjalankan kode apapun.
Memodifikasi Object Request dan Object Response.
Menghentikan request-response cycle.
Melanjutkan ke middleware function selanjutnya atau ke handler function dalam suatu request response cycle.

#### Jenis Express Middleware Berdasarkan Cara Penggunaan
Express Middleware dapat dikelompokkan berdasarkan dari dimana middleware function itu digunakan :
Application Level Middleware
Router Level Middleware
Error Handling Middleware

#### Jenis Express Middleware Berdasarkan Source Middleware Function
Express Middleware dapat juga dikelompokkan berdasarkan dari dimana middleware function itu didapatkan :
Express Build-in Middleware
Third Party (custom) Middleware

#### Jenis Express Middleware Berdasarkan Source Middleware Function : Express Build-in Middleware
Express JS sudah menyediakan 3 buah build-in middleware function yang bisa digunakan :
express.static()
express.json()
express.urlEncoded()



#### Jenis Express Middleware Berdasarkan Source Middleware Function :  Express Third Party (custom) Middleware

yang dikelola oleh Express JS Team :
cors
body-parser
errorhandler
morgan
Multer

yang dikelola oleh community:
helmet
passport
express-validator
swager-ui-express















**Kamis, 27 Oktober 2022**
### Design Database With MySQL

#### Menentukan Entity
Berdasarkan requirement yang ada kita bisa mulai untuk mengidentifikasi entity dalam database.
Beberapa kandidat yang paling sering menjadi sebuah entity : peoples, things, events, locations
Mari kita lihat kembali requirement yang ada, dan kita mulai list entity yang ada.
Berikut adalah kandidat yang bisa dijadikan enitity dalam database :
User
Singer
Track
Album
Playlist

#### Menentukan Atribbutes dari Entity
Tahapan ini kita akan menentukan attributes apa saja yang akan datanya kita simpan di dalam sebuah entity.
Attributes yang di perlukan didalam entity kemungkinan sudah ada di dalam requirements document, atau mungkin juga diperlukan penafsiran kita sendiri sebagai database developer.

#### Menentukan Relasi Antar Entity
Didalam requirement mungkin sudah dijelaskan relasi dari beberapa entity.
Namun terkadang didalam requirement juga tidak dijelaskan mengenai relasi, dan kita sebagai database developer menafsirkan relasi antar entity

#### Membuat SQL Table dari Entity
Setelah kita punya ERD, maka kita akan lanjut dengan create table berdasarkan dengan data yang kita punya.
Pada kali ini kita akan menggunakan terminal untuk menjalankan query SQL







**Jumat, 28 Oktober 2022**
### Design Database With MySQL

#### Apa itu Basis Data Relasional?
Menurut Oracle, database relasional adalah "sejenis database yang menyimpan dan menyediakan akses ke titik data yang terkait satu sama lain". 
Kami dapat membuat, membaca, memperbarui, dan menghapus (fungsi dasar dari basis data apa pun) informasi dalam basis data relasional kami menggunakan Sistem Manajemen Basis Data Relasional (RDBMS). Contoh RDBMS termasuk Oracle, Microsoft SQL Server, MySQL, dan PostgreSQL, di antara banyak lainnya. Masing-masing memiliki pro dan kontra (dan seperti semua coding-berdekatan, hyper-partisan online mereka), dan SQL tidak diimplementasikan dengan cara yang persis sama di masing-masingnya. Konsepnya sama, tetapi sintaks dan kata kuncinya mungkin sedikit berbeda, jadi biasanya tidak mungkin menggunakan kode SQL yang ditulis untuk PostgreSQL di Microsoft SQL Server, misalnya, tanpa membuat beberapa modifikasi.


#### Primary Key
Setiap produk di sini memiliki bidang 'id_produk', berwarna merah pada gambar di atas. Inilah yang disebut 'Kunci Utama'. Setiap record di setiap tabel di database Anda harus memiliki atribut (atau kombinasi atribut) yang mengidentifikasinya secara unik — ini dikenal sebagai kunci utama.
Dalam kasus kami, 'product_id' sewenang-wenang telah ditetapkan untuk setiap catatan. Juga dimungkinkan untuk menggunakan 'kunci gabungan' yang terdiri dari, misalnya, atribut 'nama_produk' dan 'jenis_produk' bersama-sama, dengan anggapan bahwa ini mengidentifikasi produk secara unik (yaitu Merek Keren™ dll tidak pernah merilis produk lain dengan nama yang sama). Yang digunakan tergantung pada sifat data Anda — yang penting adalah setiap tabel memiliki kunci utama, harus unik dan tidak boleh NULL.


#### Foreign Key
Kita dapat mengungkapkan hubungan antara entitas ini (dalam hal ini, bahwa merek adalah produsen produk) dengan memasukkan kunci utama dari database merek sebagai 'kunci asing' dalam database produk. Ini berarti bahwa setiap produk dapat dikaitkan dengan merek yang sesuai di database kami.
Atribut relasi ini, berapa banyak entitas lain yang dapat memiliki relasi dengan entitas, dikenal sebagai kardinalitas relasi. Hubungan lainnya termasuk 1-ke-1 dan N-to-M (banyak ke banyak). Kami akan membahas ini nanti.
Karena setiap produk dapat memiliki satu dan hanya satu merek, sangat masuk akal untuk menyimpan pengenal unik merek tersebut (dalam contoh kita, nama merek) sebagai atribut produk tersebut. Artinya ketika kita ingin mencari informasi yang tersimpan pada tabel merek yang berkaitan dengan produk tertentu, kita dapat dengan mudah menggunakan kolom nilai merek (Cool Brand™, Rival Brand™, dll) untuk 'mencari' informasi yang relevan pada meja merek.

Basis data kami dapat menjadi sangat kompleks karena kami mulai memiliki beberapa tabel dengan hubungan yang berbeda satu sama lain, tetapi dasar-dasar yang harus difokuskan di sini adalah:
Setiap tabel memiliki kunci utama yang secara unik mengidentifikasi setiap record dalam tabel, dan yang tidak boleh nol.
Untuk setiap hubungan tabel A ke tabel lain, diperlukan kunci asing sebagai atribut dalam tabel A untuk mendefinisikan hubungan itu.
Ini adalah bagaimana kita mendefinisikan hubungan antara data dalam hubungan 1-ke-N dalam database relasional.


#### Defining the requirements
Hal pertama yang harus dipikirkan saat membuat database adalah untuk apa kita menginginkannya. Ini mungkin tampak jelas, tetapi layak untuk dinyatakan secara eksplisit. Persyaratan yang berbeda akan menghasilkan struktur informasi, hubungan, desain, dan implementasi yang berbeda.
Sebaiknya tuliskan persyaratan Anda, atau jika Anda bekerja untuk klien atau membuat database untuk digunakan oleh departemen lain di perusahaan Anda, dapatkan persyaratan dalam bentuk tertulis dari pengguna akhir database.
Informasi apa yang ingin mereka simpan? Jenis entitas apa yang kita perlukan untuk membuat tabel (pelanggan, pesanan, produk, kursus, klik situs web, unduhan data, dll)? Seperti halnya dengan memanfaatkan data, untuk membuat pekerjaan kita menjadi paling efektif, kita perlu memikirkan apa kasus penggunaan dan apa yang dicari pengguna kita.

#### Membuat rencana berdasarkan kebutuhan
Hal pertama yang harus dilakukan adalah membaca dokumen persyaratan dengan cermat, mencatat hal-hal yang mungkin menjadi entitas dalam database kita, dan kemungkinan hubungan di antara mereka.
Penting pada tahap ini untuk mengajukan pertanyaan untuk memperjelas persyaratan. Itu wajar bagi orang yang bekerja dengan sesuatu setiap hari untuk memikirkan beberapa hal sebagai 'akal sehat' atau jelas, ketika mereka mungkin tidak jelas bagi seseorang yang datang dari luar area kerja itu. Juga, orang terkadang tidak terbiasa memikirkan aspek-aspek pekerjaan mereka dengan ketelitian yang diperlukan untuk membuat database.

#### Mengidentifikasi entitas
Mari kita lihat persyaratannya dan lihat apakah kita dapat mengidentifikasi entitas kita. Ini akan paling sering menjadi orang, benda, peristiwa atau lokasi.
Hanya dengan melihat paragraf pertama dari dokumen persyaratan kami, kami dapat melihat klien, lokasi kantor, guru, dan kursus sebagai entitas yang mungkin untuk database kami. Sisa dokumen memberi kita berbagai informasi tentang hubungan antara entitas ini, dan juga menyebutkan peserta (karyawan klien, tetapi dari sudut pandang sekolah, ini adalah peserta kursus bahasa).
Jadi kami memiliki sebagai entitas kandidat:
klien
lokasi kantor
guru
kursus
peserta

#### Memetakan hubungan
Dalam dokumen persyaratan kami, dinyatakan bahwa setiap kursus mungkin hanya memiliki satu guru pada satu waktu, yang masuk akal dalam situasi ini. Juga dijelaskan bahwa seorang guru dapat mengajar beberapa mata pelajaran (ini juga masuk akal, akan sulit bagi seorang guru untuk membayar tagihan mengajar hanya satu pelajaran per minggu). Jadi apa yang kita miliki di sini adalah hubungan 1-ke-N!








