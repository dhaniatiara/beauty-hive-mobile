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
