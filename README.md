**// TUGAS 7 //**

1. Jelaskan apa itu widget tree pada Flutter dan bagaimana hubungan parent-child (induk-anak) bekerja antar widget.
    Dalam Flutter, seluruh tampilan UI dibangun menggunakan widget. Semua widget tersebut tersusun dalam sebuah struktur yang disebut widget tree, yaitu pohon hierarki yang menggambarkan bagaimana elemen-elemen UI saling berhubungan satu sama lain. 
    Dalam pohon ini, setiap widget memiliki hubungan parent (induk) dan child (anak). Widget induk adalah yang membungkus widget lainnya, sedangkan widget anak adalah yang berada di dalamnya. Misalnya, ketika kita menulis kode *Center(child: Text('Hello Flutter'))*, maka Center menjadi parent, sedangkan Text menjadi child. Hubungan ini memungkinkan Flutter mengatur bagaimana tata letak ditampilkan dan bagaimana setiap bagian saling mempengaruhi.
    Ketika ada perubahan pada suatu bagian UI, Flutter tidak menggambar ulang seluruh tampilan. Ia hanya memperbarui bagian tertentu dari pohon widget yang mengalami perubahan. Mekanisme ini membuat Flutter sangat efisien dan cepat dalam menampilkan antarmuka pengguna.

2. Sebutkan semua widget yang kamu gunakan dalam proyek ini dan jelaskan fungsinya.
    - **Scaffold**: yang berperan sebagai kerangka utama halaman aplikasi. Scaffold menyediakan struktur dasar seperti app bar, body, drawer, dan floating action button.
    - **AppBar**: bagian di atas halaman yang biasanya berisi judul aplikasi atau ikon navigasi.
    - **Column dan Row**: sebagai pengatur tata letak vertikal dan horizontal.
    - **Card**: menampilkan konten di dalam kotak dengan efek bayangan halus di bawahnya.
    -**Container**: untuk mengatur ukuran, padding, dan tata letak isi dari Card.
    - **Text**: digunakan untuk menampilkan teks di layar dan dapat diberi gaya seperti tebal, ukuran font, atau warna.
    - **InkWell**: widget yang mendeteksi sentuhan (tap).
    - **Material**: dasar tampilan kartu yang memberikan efek material design seperti warna latar belakang dan sudut melengkung.


3. Apa fungsi dari widget MaterialApp? Jelaskan mengapa widget ini sering digunakan sebagai widget root.
    Widget MaterialApp adalah titik awal bagi aplikasi Flutter yang mengikuti prinsip Material Design dari Google. Ia bertugas mengatur hal-hal mendasar seperti tema warna, font, navigasi antarhalaman, serta manajemen rute aplikasi.
    MaterialApp juga menyediakan akses terhadap widget penting lain seperti Navigator dan Theme, sehingga memudahkan pengembang dalam berpindah halaman atau mengubah tampilan aplikasi secara konsisten.Dengan menjadikan MaterialApp sebagai root, semua widget di bawahnya dapat mewarisi pengaturan tema dan navigasi.

4. Jelaskan perbedaan antara StatelessWidget dan StatefulWidget. Kapan kamu memilih salah satunya?
    StatelessWidget adalah widget yang bersifat statis. Artinya, setelah widget tersebut ditampilkan di layar, isinya tidak akan berubah meskipun ada interaksi pengguna. Sebaliknya, StatefulWidget digunakan ketika tampilan perlu berubah berdasarkan aksi atau data tertentu. StatelessWidget digunakan saat developer ingin tampilan tidak berubah. Namun jika tampilan tergantung interaksi pengguna atau data dinamis, maka StatefulWidget adalah pilihan yang lebih tepat.

5. Apa itu BuildContext dan mengapa penting di Flutter? Bagaimana penggunaannya di metode build?
    BuildContext merupakan salah satu konsep paling penting dalam Flutter. Ia dapat diibaratkan sebagai “alamat” dari suatu widget di dalam pohon widget. Dengan BuildContext, Flutter tahu di mana posisi widget berada dan dapat mengakses widget lain yang berada di atasnya dalam hierarki. Setiap widget memiliki BuildContext sendiri yang diteruskan ke metode *build()*. Di sinilah widget dapat memanfaatkan konteks tersebut untuk menentukan bagaimana tampilannya harus dibangun berdasarkan posisi dan properti di dalam tree. Tanpa BuildContext, widget tidak akan tahu bagaimana berinteraksi dengan lingkungan sekitarnya.

6. Jelaskan konsep "hot reload" di Flutter dan bagaimana bedanya dengan "hot restart".
    Hot reload memungkinkan pengembang melihat perubahan kode hampir secara instan tanpa kehilangan data atau status aplikasi saat ini. Misalnya, ketika ingin mengubah warna tombol atau menambahkan teks baru, hasilnya langsung muncul di layar tanpa perlu memulai ulang aplikasi. Sedangkan hot restart akan menjalankan ulang seluruh aplikasi dari awal. Semua data dan state yang sebelumnya ada akan hilang, dan aplikasi kembali ke kondisi awal seperti saat baru dijalankan.
    Hot reload cocok digunakan saat ingin mengubah tampilan atau logika ringan pada UI, sedangkan hot restart diperlukan ketika ingin mengubah struktur kode yang lebih dalam, seperti variabel global, inisialisasi awal, atau dependensi utama aplikasi.



**// TUGAS 8 //**

1. Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement() pada Flutter. Dalam kasus apa sebaiknya masing-masing digunakan pada aplikasi Football Shop kamu?
    Navigator.push(context, route) menambahkan (push) route baru ke atas stack navigasi sehingga route sebelumnya tetap ada di sack dan dapat diakses kembali dengan tombol back yang akan menge-pop, sedangkan Navigator.pushReplacement(context, route) mengganti (replace) route saat ini dengan route baru, yaitu route yang diganti dihapus dari stack yang menyebabkan tidak memungkinkannya kembali ke route yang diganti dengan otmbol back. Navigator.push digunakan saat developer ingin user dapat kembali ke halaman sebelumnya, seperti dari home ke halaman form tambah rpoduk atau halaman detail produk yang jika user masuk ke halaman form/detail produk, user dapat kembali lagi ke halaman home dengan tombol back. Navigator.pushReplacement cocok digunakan jika developer ingin user tidak kembai ke halaman sebelumnhya jika sudah mausk ke halaman yang baru, misalnya setelah user sukses login halaman diteruskna ke halaman Home supaya user tidak dapat kembali ke halaman login dengan tombol back.

2. Bagaimana kamu memanfaatkan hierarchy widget seperti Scaffold, AppBar, dan Drawer untuk membangun struktur halaman yang konsisten di seluruh aplikasi?
    Scaffold digunakan sebagai kerangka halaman (layout dasar) sehingga semua struktur layout halaman diletakkan di sini, AppBar untuk konsistensi header, dan Drawer untuk navigasi global, biasanya dipasang di root Scaffold agar tersedia di banyak halaman. 

3. Dalam konteks desain antarmuka, apa kelebihan menggunakan layout widget seperti Padding, SingleChildScrollView, dan ListView saat menampilkan elemen-elemen form? Berikan contoh penggunaannya dari aplikasi kamu.
    Kelebiihan menggunakan Padding adalah  cepat, eksplisit, konsisten, dan mudah menyesuaikan spacing untuk tiap field; contoh pengguaannya adalah di setiap TextFormField di ProductFormPage dibungkus Padding untuk jarak 8px. SingleChildScrollView membuat satu kolom konten bisa di-scroll ketika tinggi konten melebihi laya sehingga membuat desain tampilan yang vertikal lebih simpel dan mencegah overflow ketika keyboard muncul; contoh penggunaannya di football shop adalah pada ProductFormPage yang membuat form dapat digulir jika isi tampilan melebihi panjang layar atau keyboard dimunculkan. Lalu, ListView memiliki kelebihan yang mengotomasi scroll, lebih baik untuk form panjang atau banyak item karena performa lebih baik daripada Column + SingleChildScrollView dan mendukung padding dan physics langsung; contoh penggunaan ListView adalah untuk Drawer.

4. Bagaimana kamu menyesuaikan warna tema agar aplikasi Football Shop memiliki identitas visual yang konsisten dengan brand toko?
    Untuk membuat tema warna konsisten adalah dengan cara mengatur warna utama (primary), warna aksen (secondary), dan warna komponen UI melalui ThemeData pada MaterialApp.



**// TUGAS 9 //**

1. Jelaskan mengapa kita perlu membuat model Dart saat mengambil/mengirim data JSON? Apa konsekuensinya jika langsung memetakan Map<String, dynamic> tanpa model (terkait validasi tipe, null-safety, maintainability)?

2. Apa fungsi package http dan CookieRequest dalam tugas ini? Jelaskan perbedaan peran http vs CookieRequest.

3. Jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

4. Jelaskan konfigurasi konektivitas yang diperlukan agar Flutter dapat berkomunikasi dengan Django. Mengapa kita perlu menambahkan 10.0.2.2 pada ALLOWED_HOSTS, mengaktifkan CORS dan pengaturan SameSite/cookie, dan menambahkan izin akses internet di Android? Apa yang akan terjadi jika konfigurasi tersebut tidak dilakukan dengan benar?


5. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.


6. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.


7. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).