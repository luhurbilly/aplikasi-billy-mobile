## TUGAS 9

- Apakah bisa kita melakukan pengambilan data JSON tanpa membuat model terlebih dahulu? Jika iya, apakah hal tersebut lebih baik daripada membuat model sebelum melakukan pengambilan data JSON?

ya, kita dapat melakukan pengambilan data JSON tanpa membuat model terlebih dahulu, terutama jika data tersebut sederhana dan memiliki 
struktur yang dapat dipahami dengan mudah. kita bisa menggunakan fungsi bawaan atau library pengolahan data 
untuk membaca dan memproses data. namun, jika data JSON kompleks atau membutuhkan analisis yang lebih mendalam, maka membuat model adalah
solusi lebih baik, karena lebih mudah dalam membantu dalam ekstraksi dan manipulasi data yang lebih rumit sesuai dengan kebutuhan.

- Jelaskan fungsi dari CookieRequest dan jelaskan mengapa instance CookieRequest perlu untuk dibagikan ke semua komponen di aplikasi Flutter.

CookieRequest mengacu pada sebuah kelas atau objek dalam konteks aplikasi Flutter yang bertanggung jawab untuk menangani 
permintaan atau informasi terkait cookie. Dengan membagikan instance CookieRequest ke semua bagian dalam aplikasi Flutter, tujuannya 
adalah memberikan akses yang konsisten dan terkoordinasi terhadap data cookie di seluruh aplikasi. Dengan cara ini, setiap bagian 
dapat berinteraksi dengan cookie secara terpusat, memungkinkan akses dan modifikasi tanpa perlu mengulangi proses pengelolaan cookie 
di setiap bagian aplikasi. Pendekatan ini diharapkan dapat meningkatkan efisiensi pengelolaan cookie, mengurangi duplikasi kode, dan 
memastikan konsistensi data di seluruh aplikasi.

- Jelaskan mekanisme pengambilan data dari JSON hingga dapat ditampilkan pada Flutter.

Untuk menampilkan data dari JSON pada Flutter, yang dilakukan pertama-tama adalah membuat model Dart yang merepresentasikan struktur data JSON. 
Kemudian, gunakan package `dart:convert` untuk mengonversi JSON menjadi objek Dart. Jika data berasal dari API, 
gunakan package `http` untuk mengambilnya. Setelah data diperoleh, gunakan widget Flutter seperti `Text` atau `ListView` untuk 
menampilkan informasi tersebut pada UI pengguna. 

- Jelaskan mekanisme autentikasi dari input data akun pada Flutter ke Django hingga selesainya proses autentikasi oleh Django dan tampilnya menu pada Flutter.

Proses autentikasi dari input data akun pada Flutter ke Django yang pertama adalah Flutter mengirimkan 
permintaan HTTP dengan data login ke API Django menggunakan package seperti `http`. lalu, Django memeriksa kredensial, 
mengautentikasi pengguna, dan mengembalikan respons. Jika autentikasi berhasil, Flutter dapat menyimpan token akses yang diterima 
dari Django untuk permintaan selanjutnya. Dengan token ini, Flutter dapat mengakses menu dan fitur tertentu pada Django dengan 
mengirimkan token pada setiap permintaan HTTP. ini memungkinkan aplikasi Flutter berkomunikasi dengan server Django, 
mengelola autentikasi pengguna, dan menampilkan menu yang sesuai setelah proses autentikasi berhasil.

- Sebutkan seluruh widget yang kamu pakai pada tugas ini dan jelaskan fungsinya masing-masing.

- MaterialApp: widget utama untuk mengonfigurasi aplikasi Flutter.

- Scaffold: Widget yang memberikan struktur dasar untuk antarmuka visual aplikasi, termasuk AppBar dan body.

AppBar: Menampilkan aplikasi di bagian atas layar.

Container: Digunakan untuk memberikan gaya dengan latar belakang gradient.

Column: Mengatur widget anak secara vertikal.

Stack: Menempatkan widget anak di atas satu sama lain.

Text: Menampilkan teks dengan gaya tertentu.

TextField: Input teks untuk memasukkan username dan password.

ElevatedButton: Tombol dengan latar belakang terisi, umumnya digunakan untuk tombol login.

GestureDetector: Mendeteksi gesture, sering digunakan untuk membuat teks "Create New Account" dapat diklik.

Navigator: Digunakan untuk navigasi antar halaman.

Form: Kontainer untuk elemen-elemen formulir, memungkinkan validasi dan pengiriman formulir.

GlobalKey: Kunci global untuk mengakses state Form.

TextFormField: Elemen formulir spesifik untuk menangani input teks.

Icon: Ikon grafis, umumnya digunakan untuk ikon di samping kolom input.

TextButton: Tombol dengan tampilan datar, sering digunakan untuk tombol "Submit".

Navigator: Digunakan untuk navigasi antar halaman.

Drawer: Menu sisi kiri yang dapat diakses dengan menggeser dari kiri.

FutureBuilder: Widget untuk membangun antarmuka berdasarkan hasil masa depan (asynchronous).

ListView.builder: Menampilkan daftar item dengan builder callback.

InkWell: Widget yang mendeteksi ketukan dan memberikan respons visual.

- Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial).
  - Membuat halaman login pada proyek tugas Flutter.
  membuat file login.dart di screens, kemudian isi filenya. lalu ubah home di main.dart menjadi LoginPage()
  
  - Membuat model kustom sesuai dengan proyek aplikasi Django.
  membuat model di web quicktype dengan endpoint JSON yang sesuai dengan models app Django kita
  
  - Membuat halaman detail untuk setiap item yang terdapat pada halaman daftar Item.
  membuat file list_item.dart pada folder screens yang berfungsi untuk mengatur tampilan data item pengguna
 

## TUGAS 8
- Jelaskan perbedaan antara Navigator.push() dan Navigator.pushReplacement(), disertai dengan contoh mengenai penggunaan kedua metode tersebut yang tepat!

Navigator.push() dan Navigator.pushReplacement() adalah kedua penggunaan navigator yang digunakan untuk berpindah halaman sesuai route yang diakses
Widget Navigator menampilkan halaman-halaman yang ada kepada layar seakan sebagai sebuah tumpukan (stack). Navigator.push() menambahkan route yang dipilih ke
bagian paling atas stack, sehingga tampilan layar berubah. Sedangkan Navigator.pushReplacement() mengganti route yang sedang ditampilkan dengan
menghapus recent route dan menggantinya dengan route yang dpiilih. sehingga layar berubah tanpa perubahan kondisi stack.
contoh penggunaan push adalah pada saat menambahkan item yang mana akan berpindah ke page form, lalu contoh penggunaan pushReplacement() adalah
setelah berhasil menghapus atau add item yang kemudian langsung mengarahkan ke home.

- Jelaskan masing-masing layout widget pada Flutter dan konteks penggunaannya masing-masing!

Scaffold: kerangka utama untuk halaman Flutter, menyediakan struktur dasar dengan komponen seperti AppBar, Drawer, dan body content. 

SingleChildScrollView: memungkinkan konten untuk discroll secara vertikal, digunakan ketika konten di dalamnya lebih besar dari layar.

Padding: digunakan untuk menambahkan padding (jarak) di sekitar children widget di dalamnya.

Column: mengatur children secara vertikal.

Text: widget untuk menampilkan teks. 

GridView.count: mengatur children dalam bentuk grid dengan jumlah kolom tertentu. 

ShopCard: custom widget mewakili kartu untuk setiap item pada grid. 

Container: widget yang dapat menambahkan padding, margin, border, dan warna latar belakang.


- Sebutkan apa saja elemen input pada form yang kamu pakai pada tugas kali ini dan jelaskan mengapa kamu menggunakan elemen input tersebut!

Nama Item:  menggunakan widget TextFormField dengan tambahan validator yang memeriksa apakah nilai yang diinput kosong 
atau tidak.

Jumlah: menggunakan widget TextFormField, dengan tambahan validator tambahan yang memeriksa apakah nilai yang dimasukkan adalah angka. 

Deskripsi: menggunakan widget TextFormField dengan tambahan validator yang memeriksa apakah nilai yang dimasukkan kosong 
atau tidak. 

penggunaan TextFormField  mempermudah pengelolaan input pengguna dan menyediakan cara yang efektif untuk memvalidasi data sebelum diproses lebih lanjut. 

- Bagaimana penerapan clean architecture pada aplikasi Flutter?

penerapan clean architecture pada flutter biasanya terbagi menjadi tiga bagian:

feature layers: berisi tampilan layar yang akan direpresentasikan dalam aplikasi. biasanya fokus pada UI dan event handlers dari UI tersebut
pada bagian ini, dibutuhkan widget yang akan ditampilkan dalam aplikasi.

domain layer: merupakan bagian yang memiliki struktur yang tidak memiliki ketergantungan dengan layer lain. pada bagian ini biasanya
ditulis menggunakan dart tanpa adanya element flutter karena bagian ini lebih berfokus pada logic aplikasi bukan kepada implementasi.

data layer: berguna untuk pengambilan dan penyimpanan data. modul data, sebagai bagian dari layer terluar, bertanggung jawab 
untuk menarik data, baik melalui API ke server atau database lokal.

- Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step! (bukan hanya sekadar mengikuti tutorial)

  **Membuat minimal satu halaman baru pada aplikasi, yaitu halaman formulir tambah item baru dengan ketentuan sebagai berikut:**

membuat file baru untuk tambah item dengan nama ```shoplist_form.dart``` di folder screens, yang berisikan widget form untuk penginputan data

  **Memakai minimal tiga elemen input, yaitu name, amount, description. Tambahkan elemen input sesuai dengan model pada aplikasi tugas Django yang telah kamu buat.**

menambahkan padding pada column di bagian Form yang merupakan body dengan elemen TextFormField. hintText dan labelText diisi dengan nama input
yang diinginkan. kemudian dibawah code tersebut tambah validator untuk memastikan input data pengguna sesuai yang diharapkan.

  **Memiliki sebuah tombol Save.**

menambahkan tombol save pada file shoplist_form.dart yang memvalidasi input pengguna. jika lolos
validasi maka akan dimunculkan popup detail item yang ditambahkan

  **Mengarahkan pengguna ke halaman form tambah item baru ketika menekan tombol Tambah Item pada halaman utama.**

menambahkan kode pada onTap() di file shop_card dan drawer pada button tambah item. dengan kode ini 
jika widget ditekan maka akan di push ke route ShopFormPage

```
        if (item.name == "Tambah Item") {
            Navigator.push(
                context,
                MaterialPageRoute(
                  builder: (context) => const ShopFormPage(),
                ));
          }
```
  **Memunculkan data sesuai isi dari formulir yang diisi dalam sebuah pop-up setelah menekan tombol Save pada halaman formulir tambah item baru.**

membuat AlertDialog() jika input form berhasil divalidasi, kemudian pada AlertDialog tsb column pada child
diisi text dengan menarik data yang diinput. seperti ini

```
     children: [
        Text('Nama: $_name'),
        Text('Harga: $_price'),
        Text('Deskripsi: $_description'),
      ],
```

  **Membuat sebuah drawer pada aplikasi dengan ketentuan sebagai berikut:**
  
buat file baru dengan nama ```left_drawer.dart``` dalam folder widgets

  - Drawer minimal memiliki dua buah opsi, yaitu Halaman Utama dan Tambah Item.
  
  membuat dua ListTile dengan title "Halaman Utama" dan "Tambah Item"

  - Ketika memiih opsi Halaman Utama, maka aplikasi akan mengarahkan pengguna ke halaman utama.

  tambahkan on Tap pada ListTile dengan title "Halaman Utama", yang kemudian mengarahkan ke route MyHomePage() dengan pushReplacement()

  - Ketika memiih opsi (Tambah Item), maka aplikasi akan mengarahkan pengguna ke halaman form tambah item baru.

  tambahkan on Tap pada ListTile dengan title "Tambah Item", yang kemudian mengarahkan ke route ShopFormPage() dengan pushReplacement()

## Tugas 7

- Apa perbedaan utama antara stateless dan stateful widget dalam konteks pengembangan aplikasi Flutter?

Dalam pengembangan aplikasi Flutter, perbedaan utama antara stateless dan stateful 
widget terletak pada kemampuan untuk mengelola dan merespons perubahan data. Stateless 
widget adalah komponen yang tidak memiliki keadaan internal, sehingga berarti mereka tidak dapat berubah 
selama eksisnya widget tersebut. Mereka digunakan untuk tampilan statis yang tidak memerlukan pembaruan 
berdasarkan perubahan data. Di sisi lain, stateful widget adalah komponen yang dapat memiliki keadaan internal 
dan dapat diperbarui sesuai dengan perubahan data atau tindakan pengguna. Mereka digunakan untuk tampilan yang 
perlu berinteraksi dengan data dinamis atau merespons perubahan status dalam aplikasi. 

- Sebutkan seluruh widget yang kamu gunakan untuk menyelesaikan tugas ini dan jelaskan fungsinya masing-masing.

1. `MyHomePage`: amdblas kelas yang mewakili halaman beranda dari aplikasi. 

2. `Scaffold`: widget yang digunakan untuk membuat kerangka tampilan aplikasi dengan app bar, body, dan lainnya.

3. `AppBar`: app bar yang menampilkan judul aplikasi "Aplikasi Billy" di bagian atas.

4. `SingleChildScrollView`: digunakan untuk mengatur tampilan agar dapat di-scroll jika kontennya lebih panjang daripada layar.

5. `Padding`:= widget yang memberikan padding ke kontennya.

6. `Column`: digunakan untuk menempatkan konten secara vertikal, seperti judul dan grid layout.

7. `GridView.count`: widget yang digunakan untuk membuat tampilan grid dengan beberapa item.

8. `ShopItem`: kelas yang merepresentasikan item toko dengan nama dan ikon.

9. `ShopCard`: digunakan untuk menampilkan setiap item toko dalam bentuk kartu. Ini berisi ikon dan teks.

10. `Material`: widget yang memberikan latar belakang warna indigo dan efek interaksi ketika ditekan.

11. `InkWell`: widget yang membuat area item responsif terhadap sentuhan pengguna.

12. `SnackBar`: widget yang muncul sebagai pemberitahuan kecil saat item toko diklik.

14. `MaterialApp`: widget yang mengonfigurasi aplikasi Flutter dan mengatur tema dan halaman beranda.

15. `theme`: tema aplikasi dengan warna primer indigo.

16. `useMaterial3`: mengaktifkan Material You, yang memungkinkan perubahan dinamis pada tema aplikasi.

- Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas secara step-by-step (bukan hanya sekadar mengikuti tutorial)

1. Membuat sebuah program Flutter baru dengan tema inventory seperti tugas-tugas sebelumnya.

jalankan di terminal ```create flutter aplikasi_billy_mobile```

2. Membuat tiga tombol sederhana dengan ikon dan teks

di file main.dart hapus ```MyHomePage(title: 'Flutter Demo Home Page')``` menjadi ```MyHomePage()```
di file menu.dart tambahkan teks dan card dengan menambahkan barang-barang yang dijual.

```
class ShopItem {
    final String name;
    final IconData icon;
                    
    ShopItem(this.name, this.icon);
}
```

ubah sifat widget page dari stateful menjadi stateless. Lakukan perubahan pada bagian ```({super.key, required this.title})``` menjadi ```({Key? key}) : super(key: key);```. 
Selain itu, tambahkan barang-barang yang dijual (nama, harga, dan icon barang tersebut) dengan code berikut:

```
final List<ShopItem> items = [
    ShopItem("Lihat Item", Icons.checklist),
    ShopItem("Tambah Item", Icons.add_shopping_cart),
    ShopItem("Logout", Icons.logout),
    ];
```
    
kemudian ubah method @override Widget build(BuildContext context) dan Tampilkan card dengan membuat widget stateless baru:

3. Memunculkan Snackbar dengan tulisan

di file menu.dart pada class ShopCard extends StatelessWidget tambahkan pada method override jadi seperti ini

```
@override
Widget build(BuildContext context){
    return Material(
        ....
        child: InkWell(
            onTap: () {
            // Memunculkan SnackBar ketika diklik
            ScaffoldMessenger.of(context)
                ..hideCurrentSnackBar()
                ..showSnackBar(SnackBar(
                    content: Text("Kamu telah menekan tombol ${item.name}!")));
            },
            ....
        )
    )
}
```

method diatas berguna untuk mengatur respon widget pada saat ikon dipesan dan 
akan memunculkan pesan sesuai dengan ikon yang ditekan
           

