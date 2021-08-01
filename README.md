## Daftar Isi

* [Pengenalan Bahasa C++](https://github.com/Abdunnafi25/Modul-HGTS-01#pengelan-bahasa-c)
* [Struktur Program](https://github.com/Abdunnafi25/Modul-HGTS-01#struktur-program)
* [Tipe Data dan Variabel Scope](https://github.com/Abdunnafi25/Modul-HGTS-01#tipe-data-dan-variabel-scope)
* [Input dan Output](https://github.com/Abdunnafi25/Modul-HGTS-01#input-dan-output)
* [Operator](https://github.com/Abdunnafi25/Modul-HGTS-01#operator)
* [Contoh Soal](https://github.com/Abdunnafi25/Modul-HGTS-01#contoh-soal)

## Pengelan Bahasa C++
Bahasa Pemrograman C++ adalah bahasa pemrograman komputer yang bisa dipakai untuk membuat berbagai aplikasi (_general-purpose programming language_), dan merupakan pengembangan dari bahasa pemrograman C. Karena termasuk _general-purpose programming language_, bahasa pemrograman C++ bisa dipakai untuk membuat aplikasi desktop seperti antivirus, software pengolah gambar (image processing), aplikasi pengolah kata (word processing), hingga untuk membuat compiler bahasa pemrograman lain.


## Struktur Program
Setiap program C++ menggunakan _library_, yang memberikan kemampuan untuk menjalankan fungsi yang diperlukan. Misalnya, fungsi paling dasar yang disebut 'cout', yang mencetak ke layar, terdapat dalam file header `iostream`. Jadi agar program dapat mencetak sesuatu ke layar komputer, program c++ harus menyertakan (_include_) header `iostream`. Baris berikutnya adalah `std` yang merupakan ruang lingkup dari _identifier_.
```cpp
#include <iostream>
using namespace std;
```
Setiap program dari c++ akan dimulai dari fungsi utama, yaitu _main_. Jadi meskipun ada baris fungsi lain di atas maupun bawah, maka fungsi _main_ inilah yang akan pertama dijalankan.
```cpp
int main(){
  // baris kode
}
```
Setiap fungsi pada c++ pasti memiliki nilai pengembalian (_return value_), pada fungsi _main_ ini sendiri nilai yang dimaksud adalah sebuah bilangan bulat, yaitu _int_. Jika fungsi berjalan dengan baik, maka nilai yang dikembalikan adalah 0, sedangkan selain itu artinya program tidak berjalan dengan baik (gagal). Oleh karena itu terkadang pada akhir fungsi main akan ditulis:
```c++
return 0;
```
meskipun ada beberapa yang tidak menggunakannya.

Setiap baris perintah pada c++ harus diakhiri dengan `;` yang menyatakan baris perintah selesai karena jika tidak, program akan mengalami eror.

## Tipe Data dan Variabel Scope
C++ menyediakan serangkaian tipe data bawaan dan buatan pengguna. Tabel berikut mencantumkan tujuh tipe data dasar C++:
- Boolean - `bool` - bernilai benar atau salah saja.
- Characters - alfabet dan simbol, untuk deklarasi menggunakan `char`.
- Integers - semua bilangan baik positif maupun negatif yang terdiri dari beberapa bit bilangan.
- Floating point numbers - bilangan pecahan dan dideklarasikan dengan `float` ataupun `double`.
- Valueless atau tidak ada nilainya yang dideklarasikan dengan `void`.
- Wide character dengan keyword `wchar_t`.
Tipe-tipe tersebut dapat juga menggunakan tanda (`signed`), tanpa tanda (`unsigned`) ataupun dengan jangkauan lebih luas menggunakan `long`. Maksud dari menggunakan tanda adalah tanda positif maupun negatif, sedangkan jika tidak menggunakan tanda hanya ada tipe data yang bernilai positif.

Sedangkan tipe data buatan pengguna:
- Struct
- Class
yang akan dipelajari pertemuan mendatang.

### Cara deklarasi dan menggunakan variabel
Pertama, pastikan terlebih dahulu tipe data dari variabel tersebut dan gunakan nama dengan beberapa aturan:
- Terdiri dari 1 - 255 karakter (huruf, angka dan simbol)
- Semua variabel harus dimulai dengan huruf atau _underscore_ (\_)
- Setelah itu variabel dapat dinamai dengan huruf atau angka.
- Nama variabel _case sensitive_, artinya `nama` dengan `Nama` adalah 2 variabel berbeda.
- Penamaan pada variabel tidak boleh ada spasi.
- Tidak boleh menggunakan c++ _keyword_ sebagai nama variabel.

Misalkan
```c++
int umur;
string nama = 'Himpunan Mahasiswa Teknik Computer - Informatika ITS';

umur = 32;
```

Semua variabel tergantung pada scope-nya, dimana ia bisa digunakan dan dimana ia tidak dapat digunakan. Misal:
```c++
#include <iostream>
using namespace std;

int global_scope;

int main(){
  int local_scope;
  while(true){
    int while_only;
    // ....
  }
}
```

Pada contoh tersebut, `global_scope` dapat digunakan di seluruh bagian program c++ tanpa memperdulikan fungsi, maupun potongan yang ada di dalamnya. Kemudian `local_scope` dapat digunakan hanya pada fungsi `main` dan tidak untuk fungsi di luar `main`. Terakhir variabel `while_only` hanya dapat digunakan pada perulangan `while` saja, setelah keluar program variabel tersebut akan hilang meskipun akan ada `while` kedua di luar yang pertama.
```c++
while(true)
{
  int while_only;
  while(true)
  {
    // dapat menggunakan while_only karena di dalam program
    while_only = 0;
  }
}

while(true){
  // tidak dapat karena berbeda dengan while sebelumnya
  while_only = 10;  //eror karena variabel tidak diketahui
}
```
Pada contoh tersebut, `while` pertama dimulai dari baris kedua sampai baris ke-8. Jadi selama variabel sudah dideklarasikan dan ada pada jangkauan tersebut, variabel dapat digunakan.

## Input dan Output
Sebenarnya setiap program komputer hanya terdiri dari 3 bagian saja, yaitu:
- Input : merupakan data yang diberikan oleh pengguna program. Input dapat berasal dari keyboard, mikrofon, kamera ataupun media yang dapat menerima input.
- Proses : bagian program yang meengolah data yang didapat dari input atau dideklarasikan dari awal ketika program dijalankan.
- Output : Informasi yang diperoleh program ketika proses sudah selesai dijalankan dan ditampilkan ke layar.

### Input
Untuk menerima suatu input, fungsi yang dapat digunakan adalah `cin` atau fungsi dari bahasa C, yaitu `scanf`. Cara menggunakan:
```c++
string nama;
int umur;

cin>>nama>>umur;              // cara 1

scanf("%s %d", nama, &umur);  // cara 2
```
Perbedaan antara keduanya adalah bahwa penggunaan `cin` tidak memerlukan format dari variabel, sedangkan pada `scanf` harus. `cin` dipisahkan dengan `>>` untuk menginput variabel yang berbeda.

Macam-macam format dalam bahasa C yang umum digunakan (dasar):
- %s : untuk string/teks/kumpulan karakter
- %d, %i : untuk bilangan bulat/integer;
- %c : untuk sebuah karakter

### Output
Ada beberapa cara untuk mencetak keluaran (_Output_), yaitu:
- `cout` : sama seperti `cin` yang tidak memerlukan format, `cout` juga dipisahkan dengan `<<` setiap variabel berbeda/tidak berkaitan.
- `printf` : seperti scanf yang menggunakan format, `printf` juga lebih mudah jika ingin mencetak keluaran yang terdiri dari beberapa string dan variabel.
- `puts` : sama seperti `cout` yang tidak memerlukan format untuk mencetak keluaran.

Contoh:
```c++
string nama;
int umur;

cin>>nama>>umur;
cout<<"Halo, nama saya "<<nama<<" dan saya berumur "<<umur<<" tahun"<<endl;
```
atau
```c++
string nama;
int umur;

scanf("%s%d", nama, &umur);
printf("Halo, nama saya %s dan saya berumur %d tahun\n", nama, umur);
```
Kelemahan dari menggunakan `cin` dan `%s` adalah hanya mengambil 1 kata saja.
Untuk mengatasi hal tersebut, gunakan:
```c++
scanf("%[^\n]s", nama);
// atau
getline(cin, nama);
```

## Operator
Seperti halnya matematika, kita juga bisa membuat proses pada program dengan menggunakan operator penjumlahan, pengurangan, perkalian maupun pembagian (dan bahkan lebih). Operator juga memiliki jenis-jenis seperti aritmatika, _assignment_, pembanding, logika, _bitwise_.
### Operator aritmatika:
- (+) : untuk menjumlahkan data (baik angka maupun variabel)
- (-) : untuk mengurangi data
- (*) : perkalian
- (/) : pembagian dengan pembulatan ke bawah jika menggunakan tipe data _integer_
- (%) : operasi modulo (sisa bagi)

### Pembanding:
Seperti namanya, jenis operator ini digunakan untuk membandingkan dua nilai, baik itu antar variabel, variabel dengan angka, maupun angka dengan angka.
- (>) : lebih dari, akan bernilai `true` jika ruas kiri lebih besar
- (<) : kurang dari, akan bernilai `true` jika ruas kiri lebih kecil nilainya
- (==) : sama dengan, akan bernilai `true` jika keduanya bernilai sama
- (!=) : bernilai `true` jika kedua ruas tidak bernilai sama
- (>=) : lebih dari atau sama dengan yang bernilai `true` jika nilai ruas kiri lebih besar atau sama
- (<=) : kurang dari atau sama dengan yang bernilai `true` jika nilai ruas kiri lebih kecil atau sama

### Logika:
Untuk operator yang menunjukkan logika AND, OR dan NOT.
- (&&) : AND, bernilai `true` jika kedua ruas bernilai `true`
- (||) : OR, bernilai `true` jika minimal 1 ruas bernilai `true`
- (!) : NOT, akan bernilai kebalikan dari nilai sekarang

### _Bitwise_:
Operator _bitwise_ adalah operator yang mengubah tiap bit bilangan.
- (&) : AND
- (|) : OR
- (~) : NOT
- (^) : XOR
- (<<) : Left Shift
- (>>) : Right Shift
Contoh:
Biner dari 100 adalah 1100100
Biner dari 40 adalah 101000.
Jika dilakukan operasi AND (_bitwise_):
100 & 40 = 1100100 & 101000
```
1100100
0101000
------- &
0100000
```
Jadi hasil dari `100 & 40` adalah 100000, yaitu 32.

### _Assignment_:
Sebenarnya _assignment_ hanya memberi nilai pada sebuah variabel saja, misal:
```c++
int umur = 18;
```
Artinya `umur` akan bernilai 18. Ada lagi operator pada pemrograman c++ yang digunakan dengan menggabungkan _assignment_ dengan aritmatika. Misal:
```c++
int umur = 18;  // umur bernilai 18

umur *= 2;    // umur dikalikan dua menjadi 18
// Atau sama dengan umur = umur * 2;
```
Macam-macam:
- (+=) : menjumlahkan variabel dengan bilangan di ruas kanan
- (-=) : mengurangi nilai variabel
- (*=) : mengalikan variabel
- (/=) : membagi variabel
- (%=) : mengubah variabel menjadi bilangan sisa baginya terhadap bilangan di kanannya.
- (<<=) : _assignment_ dan _shift left_
- (>>=) : _assignment_ dan _shift right_
- (&=) : _assignment_ dan _bitwise_ AND
- (|=) : _assignment_ dan _bitwise_ OR
- (^=) : _assignment_ dan _bitwise_ XOR

## Contoh Soal


## Referensi
https://www.duniailkom.com/tutorial-belajar-c-plus-plus-pengertian-bahasa-pemrograman-c-plus-plus/
https://www.learn-cpp.org/en/Variables_and_Types
https://www.petanikode.com/cpp-input-output/
