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



## Operator



## Contoh Soal
