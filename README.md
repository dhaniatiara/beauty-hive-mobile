# Beauty Hive Mobile

**Dhania Tiaraputri Herdiani**

**2306165881**

A new Flutter project.

<details>
  <summary>Getting Started (Default Flutter Info)</summary>

This project is a starting point for a Flutter application.

A few resources to get you started if this is your first Flutter project:

- [Lab: Write your first Flutter app](https://docs.flutter.dev/get-started/codelab)
- [Cookbook: Useful Flutter samples](https://docs.flutter.dev/cookbook)

For help getting started with Flutter development, view the
[online documentation](https://docs.flutter.dev/), which offers tutorials,
samples, guidance on mobile development, and a full API reference.
</details>

## Tugas 7

### 1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget, dan jelaskan perbedaan dari keduanya.

a. Penjelasan stateless widget: Stateless widget dalam Flutter adalah komponen yang menggambarkan bagian dari antarmuka pengguna yang hanya dapat ditentukan oleh konfigurasi di dalam konstruktor. Stateless widget tidak menyimpan status yang bisa diubah. Contoh dari widget Stateless adalah Icon, IconButton, dan Text. Berikut adalah contoh potongan kodenya:
```
class MyStatelessWidget extends StatelessWidget {
      // This widget is the root of your application.
      @override
      Widget build(BuildContext context) {
        return Container(
          child: Text('This is a Stateless Widget'),
        );
      }
    }
```
Stateless widget dalam Flutter memiliki siklus hidup sederhana yang terdiri dari hanya satu tahap: Creation. Stateless widget mudah untuk diinstansiasi. Kita dapat membuat sebuah instance darinya, dan Flutter akan mengurus sisanya. Flutter akan merender widget tersebut lalu menghancurkannya. Setelah dirender, stateless widget menunggu perintah build berikutnya. Setiap kali widget induk memutuskan untuk mengubah konfigurasi widget ini, widget tersebut akan dibuang dan digantikan dengan widget baru. 

b. Penjelasan stateful widget: Sedangkan, stateful widget dalam Flutter adalah widget yang dapat mengubah statusnya seiring waktu. Perubahan ini bisa berasal dari interaksi pengguna atau pembaruan data secara real-time. Contoh widget Stateful meliputi checkbox, radio button, slider, input formulir, dan lain-lain.

Berbeda dengan Stateless Widget, Stateful Widget memiliki siklus hidup yang lebih rumit. Siklus ini mencakup tahap Inisialisasi, Pembuatan State, Rendering, dan Pembuangan. Siklus hidup dari Stateful Widget di Flutter dimulai dengan pemanggilan konstruktor. Framework Flutter memanggil metode createState(), yang membuat konfigurasi default untuk Stateful Widget baru. Metode createState() dioverride dan mengembalikan instance baru dari kelas state, yaitu _MyStatefulWidgetState.

c. Perbedaan: Meskipun Stateless Widget cukup praktis dan mudah dipahami, kelemahannya adalah widget ini memerlukan pembangunan ulang pada pohon widget setiap kali ada perubahan, sehingga mengonsumsi memori dan waktu pemrosesan. Di sisi lain, Stateful Widget memungkinkan perubahan pada state tanpa perlu membangun ulang seluruh pohon widget, sehingga memberikan solusi yang lebih efisien untuk konten dinamis.

### 2. Sebutkan widget apa saja yang kamu gunakan pada proyek ini dan jelaskan fungsinya

1. MaterialApp: Sebagai root aplikasi Flutter dengan gaya desain material. MaterialApp mengelola tema, navigasi, dan pengaturan aplikasi secara keseluruhan.
2. Scaffold: Memberikan struktur dasar untuk halaman aplikasi, seperti AppBar, body, dan floatingActionButton. Scaffold menyediakan layout dasar untuk membangun UI di dalam aplikasi.
3. AppBar: Menampilkan bar di bagian atas layar yang sering berisi judul aplikasi atau tombol aksi, seperti tombol kembali atau menu.
4. Text: Menampilkan teks pada layar. Text digunakan untuk menampilkan judul, deskripsi, atau label pada elemen-elemen tertentu di antarmuka pengguna.
5. Column: Menyusun widget secara vertikal (dari atas ke bawah). Column sangat berguna untuk mengatur tata letak beberapa widget dalam satu kolom.
6. ElevatedButton: Menampilkan tombol yang dapat ditekan oleh pengguna. ElevatedButton memiliki efek elevasi (ketinggian) dan dapat menggabungkan ikon serta teks. Digunakan untuk tombol-tombol seperti "Lihat Daftar Produk", "Tambah Produk", dan "Logout".
7. ElevatedButton.icon: Variasi dari ElevatedButton yang menampilkan ikon dan teks secara bersamaan. Ini memberikan pengalaman visual yang lebih informatif pada tombol-tombol utama di aplikasi.
8. Icon: Menampilkan ikon yang memberikan visualisasi sederhana, seperti ikon daftar, tambah, dan logout pada tombol-tombol. Ikon membantu pengguna mengenali fungsi tombol dengan cepat.
9. FloatingActionButton: Menampilkan tombol tindakan utama melayang di pojok layar, biasanya untuk aksi utama pada halaman tersebut. Pada proyek ini, digunakan sebagai tombol untuk meningkatkan counter saat ditekan.
10. SnackBar: Menampilkan pesan sementara di bagian bawah layar saat pengguna melakukan suatu aksi. SnackBar digunakan untuk memberi umpan balik segera setelah tombol "Lihat Daftar Produk", "Tambah Produk", atau "Logout" ditekan.
11. ScaffoldMessenger: Mengelola SnackBar di dalam Scaffold. ScaffoldMessenger membantu menampilkan SnackBar di halaman yang menggunakan Scaffold sebagai struktur dasarnya.
12. SizedBox: Memberikan spasi atau jarak antara widget, atau digunakan untuk mengatur ukuran widget tertentu. Dalam proyek ini, SizedBox digunakan untuk menambahkan jarak antar tombol.
13. ThemeData: Mengelola tema aplikasi, termasuk warna utama, skema warna, dan gaya elemen UI lainnya. ThemeData membantu menjaga konsistensi tampilan aplikasi.

### 3. Apa fungsi dari setState()? Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut

SetState adalah fungsi penting dalam Flutter yang terutama digunakan untuk memicu pembangunan ulang pada widget stateful. Ketika data berubah dan kita perlu menampilkan perubahan tersebut di UI, kita memanggil SetState. 

Variable yang dapat terdampak pada fungsi tersebut adalah: 
- Variabel Counter Saat setState() memodifikasi _counter, UI akan menampilkan nilai terbaru.
- Variabel yang menyimpan data input pengguna, seperti teks pada TextField. Ketika input pengguna berubah, kita bisa memanggil setState() untuk memperbarui UI dengan teks baru.
- Variabel boolean yang mengontrol visibilitas, gaya, atau status lainnya pada widget, seperti isLoading untuk menampilkan loading spinner atau tombol submit. Dengan setState(), kita bisa mengubah variabel ini untuk menampilkan atau menyembunyikan elemen tertentu di UI.
- Data yang diambil dari sumber eksternal, seperti API atau database, juga bisa disimpan dalam variabel yang di-update melalui setState(). Misalnya, daftar produk yang didapat dari API bisa disimpan dalam List dan diperbarui ketika data baru diterima.

### 4. Jelaskan perbedaan antara const dengan final

Final digunakan untuk membuat objek yang bersifat tidak dapat diubah (immutable). Gunakan “final” untuk menunjukkan variabel yang tidak boleh diubah setelah diberikan nilai, untuk mendorong sifat immutabilitas dan mengurangi bug yang terkait dengan perubahan yang tidak disengaja.

Perbedaan utama antara kata kunci final dan const terletak pada penggunaannya. Sedangkan const adalah konstanta pada waktu kompilasi, sedangkan kata kunci final adalah konstanta pada waktu eksekusi. Gunakan “const” ketika memiliki nilai yang diketahui dan dapat dihitung pada waktu kompilasi, seperti literal atau ekspresi yang hanya melibatkan konstanta lain.

### 5. Cara mengimplementasikan checklist-checklist di atas

1. Pertama, saya membuat program flutter baru dengan judul beauty_hive (apikasi dan tema e-commerce yang saya pada tugas tugas sebelumnya). 
2. Setelah itu, saya membuat file baru bernama `menu.dart` pada direktori lib dan melakukan modifikasi seperti pada tutorial agar kode saya lebih rapih.
3. Setelah itu, saya mulai membuat tiga tombol sederhana dengan ikon dan teks dengan judul `Lihat Daftar Produk`, `Tambah Produk`, `Logout`. Saya terlebih dahulu mendefinisikan Kelas ItemHomepage untuk Setiap Tombol. Saya buat kelas ItemHomepage yang akan menyimpan nama tombol, ikon, dan warna yang diinginkan untuk setiap tombol seperti berikut
```
class ItemHomepage {
  final String name;
  final IconData icon;
  final Color color;

  ItemHomepage(this.name, this.icon, this.color);
}
```

4. Kemudian. saya buat daftar items di dalam MyHomePage yang akan berisi tiga instance ItemHomepage dan menentukan ikon dan warna masing-masing tombol sesuai kebutuhan seperti berikut
```
final List<ItemHomepage> items = [
  ItemHomepage("Lihat Daftar Produk", Icons.list, const Color(0xFFF4F478)), // Kuning
  ItemHomepage("Tambah Produk", Icons.add, const Color(0xFFED6E4B)),       // Merah
  ItemHomepage("Logout", Icons.logout, const Color(0xFFDBC1FE)),           // Ungu Muda
];
```
5. Lalu, saya buat widget stateless ItemCard yang menerima satu ItemHomepage dan menampilkannya sebagai tombol. 
6. Untuk menampilkan pesan snackbar saat tombol ditekan, saya menggunakan `ScaffoldMessenger.of(context):`. ScaffoldMessenger adalah widget yang mengontrol tampilan Snackbar. Setelah mendapatkan instance ScaffoldMessenger, saya menggunakan metode showSnackBar untuk menampilkan Snackbar di layar. Untuk membuat Snackbar, saya buat objek SnackBar dengan konten berupa teks atau widget lainnya. Lalu. saya tambahkan Pesan Snackbar pada onTap untuk menampilkan pesan Snackbar setiap kali tombol ditekan.
Contoh implementasinya pada kode say aseperti berikut
```
onTap: () {
  // Menampilkan Snackbar dengan pesan khusus
  ScaffoldMessenger.of(context)
    ..hideCurrentSnackBar() // Menyembunyikan Snackbar sebelumnya
    ..showSnackBar(
      SnackBar(
        content: Text("Kamu telah menekan tombol ${item.name}!"), // Pesan Snackbar
        duration: const Duration(seconds: 2), // Durasi tampil 2 detik
      ),
    );
},
```
7. Terakhir, saya tampilkan Tombol dalam `GridView` di MyHomePage untuk menampilkan daftar ItemCard. Sehingga tombol muncul dalam format grid.


## Tugas 8

### 1. Apa kegunaan const di Flutter? Jelaskan apa keuntungan ketika menggunakan const pada kode Flutter. Kapan sebaiknya kita menggunakan const, dan kapan sebaiknya tidak digunakan?

Kata kunci const digunakan untuk mendeklarasikan variabel yang merupakan compile time constants.

Keuntungan menggunakan const pada kode Flutter: 

- Optimasi Performa: Variabel “const” dievaluasi dan diselesaikan pada waktu kompilasi, menghasilkan peningkatan performa saat runtime.

- Efisiensi Memori: Karena variabel “const” diselesaikan pada waktu kompilasi, variabel-variabel tersebut disimpan di satu lokasi memori, sehingga mengurangi penggunaan memori.

- Optimasi Kode: Penggunaan “const” membantu mengidentifikasi dan menghilangkan perhitungan atau objek yang redundan, meningkatkan efisiensi kode.

const sebaiknya digunakan saat memiliki nilai yang sudah diketahui dan dapat dihitung pada waktu kompilasi, seperti literal atau ekspresi yang hanya melibatkan konstanta lainnya

### 2. Jelaskan dan bandingkan penggunaan Column dan Row pada Flutter. Berikan contoh implementasi dari masing-masing layout widget ini!

Pada Row, main axis berjalan secara horizontal dan cross axis berjalan secara vertikal. Untuk Column, main axis berjalan secara vertikal dan cross axis berjalan secara horizontal.

Contoh implementasi row:
```
Row(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('images/pic1.jpg'),
    Image.asset('images/pic2.jpg'),
    Image.asset('images/pic3.jpg'),
  ],
);
```

Contoh implementasi column:
```
Column(
  mainAxisAlignment: MainAxisAlignment.spaceEvenly,
  children: [
    Image.asset('images/pic1.jpg'),
    Image.asset('images/pic2.jpg'),
    Image.asset('images/pic3.jpg'),
  ],
);
```

### 3. Sebutkan apa saja elemen input yang kamu gunakan pada halaman form yang kamu buat pada tugas kali ini. Apakah terdapat elemen input Flutter lain yang tidak kamu gunakan pada tugas ini? Jelaskan!

Elemen input yang digunakan:

1. TextFormField: Digunakan untuk menerima input teks, seperti Name, Description, Shade, dan Size dan digunakan untuk input numerik dengan validasi tambahan, seperti Price dan Amount.

2. ElevatedButton: Digunakan untuk tombol Save yang akan menyimpan data setelah form tervalidasi.

Elemen Input Lain di Flutter yang Tidak Digunakan dalam Tugas Ini:

1. Checkbox: Checkbox membuat user bisa memilih atau membatalkan pilihan dari sebuah opsi yang berbentuk kotak centang. Biasanya digunakan untuk menampilkan pilihan boolean.
2. Radio Button: Radio Button membuat user bisa memilih salah satu opsi dari beberapa pilihan. Biasanya digunakan untuk memilih satu dari beberapa opsi eksklusif.


### 4. Bagaimana cara kamu mengatur tema (theme) dalam aplikasi Flutter agar aplikasi yang dibuat konsisten? Apakah kamu mengimplementasikan tema pada aplikasi yang kamu buat?

Untuk menjaga konsistensi tema dalam aplikasi Flutter, saya menggunakan ThemeData yang diterapkan di `main.dart`. Dengan menggunakan ThemeData, kita dapat menentukan scheme warna, gaya teks, dan elemen visual lain secara global, sehingga semua halaman dan widget dalam aplikasi mengikuti tampilan yang seragam.

Di `main.dart` saya menambahkan
```
theme: ThemeData(
  colorScheme: ColorScheme.fromSeed(seedColor: Colors.white),
  useMaterial3: true,
),
```

Dan untuk mengaksesnya saya bisa menulis kode ini di setiap halaman atau widget
```
backgroundColor: Theme.of(context).colorScheme.primary,
```

### 5. Bagaimana cara kamu menangani navigasi dalam aplikasi dengan banyak halaman pada Flutter?

Saya menangani navigasi dengan menggunakan Navigator dan Route. Yang saya gunakan adalah Navigator.push() dan Navigator.pop()

Navigator.push: Menambahkan halaman baru ke tumpukan (stack) navigasi. Halaman baru akan berada di atas halaman sebelumnya, sehingga pengguna dapat kembali dengan menekan tombol "Back".


Navigator.pop: Menghapus halaman teratas dari tumpukan dan kembali ke halaman sebelumnya.

## Tugas 9

### 1. Jelaskan mengapa kita perlu membuat model untuk melakukan pengambilan ataupun pengiriman data JSON? Apakah akan terjadi error jika kita tidak membuat model terlebih dahulu?

Membuat model untuk mengelola data JSON membantu dalam strukturisasi data sehingga mempermudah proses parsing (mengubah JSON menjadi objek Dart) dan serialisasi (mengubah objek Dart menjadi JSON). Model memastikan bahwa data JSON yang diterima memiliki struktur yang sesuai dengan aplikasi. Mempermudah validasi data, terutama jika ada perubahan pada struktur JSON. Dengan model, kita dapat menggunakan properti (misalnya product.fields.name) daripada harus memanipulasi data JSON mentah.

Jika tidak menggunakan model, Anda harus mem-parsing JSON secara manual, yang lebih rentan terhadap error seperti null atau ketidaksesuaian tipe data.Error parsing bisa terjadi jika data yang diterima tidak sesuai ekspektasi.

### 2. Jelaskan fungsi dari library http yang sudah kamu implementasikan pada tugas ini

Dalam tugas ini, library http berguna untuk:
- Fungsi get digunakan untuk mengirim permintaan HTTP GET ke server dan menerima respons JSON.
- Fungsi post digunakan untuk mengirim data dari aplikasi Flutter ke server melalui body request.
- http menyediakan mekanisme untuk menangani status kode respons (200, 404, dll.) dan parsing data dari respons server.

### 3. Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

CookieRequest menyimpan cookie yang diterima dari server setelah login, yang digunakan untuk autentikasi di permintaan selanjutnya. Cookie membantu menjaga sesi pengguna tetap aktif tanpa harus login ulang. CookieRequest memungkinkan pengiriman permintaan HTTP GET dan POST dengan menyertakan cookie secara otomatis. Dengan cookie, server dapat mengenali pengguna yang sedang terautentikasi.


### 4. Jelaskan mekanisme pengiriman data mulai dari input hingga dapat ditampilkan pada Flutter.

1. Input Data oleh Pengguna: Data diinput melalui form Flutter menggunakan widget seperti TextFormField. Data yang diinput disimpan ke variabel atau model Dart.
2. Mengirim Data ke Server: Data dikirim melalui HTTP POST menggunakan CookieRequest.postJson atau http.post. Data dikirim dalam format JSON ke endpoint API Django.
3. Pemrosesan di Django: Django menerima data dari Flutter dan memvalidasinya. Data kemudian disimpan ke database jika valid. 
4. Mengambil Data dari Server: Flutter menggunakan HTTP GET untuk meminta data dari endpoint API. Django mengirimkan data dalam format JSON ke Flutter.
5. Menampilkan Data: Flutter mem-parsing JSON menjadi objek model Dart. Data yang sudah diproses ditampilkan pada UI menggunakan widget seperti ListView atau GridView.


### 5. Jelaskan mekanisme autentikasi dari login, register, hingga logout. Mulai dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

1. Login:

- Input: Pengguna memasukkan email/username dan password di Flutter.
- Proses di Django: Data dikirim melalui HTTP POST ke endpoint login Django. Django memvalidasi username dan password. Jika valid: Django membuat session dan mengirimkan cookie session ke Flutter.
- Flutter: Cookie disimpan oleh CookieRequest untuk digunakan pada permintaan berikutnya

2. Register:

- Input: Pengguna memasukkan data seperti nama, email, dan password di Flutter.
- Proses di Django: Data dikirim melalui HTTP POST ke endpoint register Django. Django memvalidasi dan menyimpan data ke database.
- Flutter: Jika registrasi sukses, pengguna diarahkan ke halaman login.

3. Logout:

- Flutter: Flutter mengirim HTTP GET atau POST ke endpoint logout Django menggunakan cookie session.
- Django: Django menghapus sesi pengguna. Cookie menjadi tidak valid.
- Flutter: Cookie dihapus dari CookieRequest, dan pengguna diarahkan kembali ke halaman login. Tampilkan Menu Setelah Login:

Setelah login, cookie session dikirim bersama setiap permintaan ke server untuk mengakses data dan halaman yang memerlukan autentikasi. Jika cookie valid, server mengembalikan data yang diminta, dan Flutter menampilkan menu atau halaman yang sesuai.

### 6. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)

- Saya pertama mengimplementasikan fitur registrasi akun pada Flutter dengan cara membuat authentication django app di proyek django saya yaitu beautyhive. Setelah aku saya mengatur segala peraturan yang diperlukan saat membaut django app baru seperti modifikasi di settings.py, melakukan pip install, dan menambahkan requirements.txt.
- Saya kemudian membuat metode view di views.py dalam authentication yang berfungsi untuk menjalankan login. Kemudian tidak lupa mengatur urls nya. 
- Untuk integrasi sistem autentikasi pada flutter, saya instal package yang seperti ada pada tutorial, kemudian saya mengubah main.dart saya menjadi seperti berikut:

```
import 'package:beauty_hive/screens/login.dart';
import 'package:flutter/material.dart';
import 'package:pbp_django_auth/pbp_django_auth.dart';
import 'package:provider/provider.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return Provider(
      create: (_) {
        CookieRequest request = CookieRequest();
        return request;
      },
      child: MaterialApp(
        title: 'BeautyHive',
        theme: ThemeData(
          useMaterial3: true,
          colorScheme: ColorScheme.fromSeed(seedColor: Colors.white),
          
        ),
        home: const LoginPage()
      ),
    );
  }
}
```

- Setelah itu saya membuat file login.dart di dalam screens untuk menampilkan tampilan halaman login
- Lalu saya menambahkn fungsi register di views.py django authentication saya agar dapat melakukan registrasi bagi pengguna baru. Kemudian lanjut membuat screen baru bernama register.dart
- Untuk membuat model kustom, saya login local django saya dan mengakses json nya, kemudian membuka situs quicktype untuk mendapatkan data json yang diolah di quicktype. Hasil dari kode tersebut saya masukkan ke file dinamakan product_entry.dart di dalam folder baru di dalam lib yaitu models. 
- Untuk fetch data dari django, saya melakukan `flutter pub add http` pada proyek flutter dan melakukan modifkasi pada file yang ada di folder android seperti pada tutorial. 
- Saya kemudian membuat screen baru yang dinamakan list_productentry.dart dan mengisi nya seperti pada tutorial dan menyesuaikan flutter dan django saya. Lalu saya menambahkan halaman page tersebut di widget left drawer dan juga melakukan penyesuaian lainnya pada file lain agar halaman ini bisa dikunjungi oleh pengguna di menu dan leftdrawer. 
- Untuk list_productentry saya hanya dapat menampilkan name, price, description pada produk.
- Saya kemudian membuat halaman detail untuk setiap item yang ada pada list_productentry dengan cara membuat screen baru yang dinamakan product_detail. Product_detail akan berfungsi menampilkan detail model saya lainnya yaitu menampilkan size dan shade dari produk dan juga tombol back untuk kembali ke page list_productentry. Untuk menampilakn detail kurang lebih membuat kode berikut
```
const SizedBox(height: 8),
Text("Price: Rp${product.fields.price}"),
const SizedBox(height: 8),
Text("Description: ${product.fields.description}"),
const SizedBox(height: 8),
Text("Shade: ${product.fields.shade}"),
const SizedBox(height: 8),
Text("Size: ${product.fields.size}"),
const SizedBox(height: 20),
```
- Kemudian saya juga melakukan pengaturan terhadap halaman list_productentry.dart agar tiap box detail halaman bisa dipencet dan mengarah pada detail produk. Untuk menampilkan detail produk tertentu saya menggunakan 
```
  Future<Product> fetchProductDetail(CookieRequest request) async {
    final response = await request.get('http://127.0.0.1:8000/json/${widget.productID}/');

    // Decode the response into JSON and convert it into a Product object
    return Product.fromJson(response[0]);
  }
```
- Hal ini agar flutter dapat menampilkan detail dari produk tertentu. 
- Untuk integrasi form flutter dengan django, saya memodifikasi file views pada django main app dengan menambahkan fungsi create_product_flutter dan memanggilnya di dalam productentry_form.dart pada proyek flutter saya dan lanjut melakukan penyesuaian fungsionalitas lainnya di file tersebut. 
- Saya juga menambahkan fitur logout yang proses nya kurang lebih sama seperti login.
