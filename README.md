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
           

