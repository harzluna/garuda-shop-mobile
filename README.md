// TUGAS 7 //

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
