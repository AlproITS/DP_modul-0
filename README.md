# Pengenalan Bahasa C

## Statement

Dalam program, sebuah **statement** adalah intruksi/perintah yang mempunyai makna tertentu sehingga menyebabkan program tersebut dapat melakukan suatu aksi.

Analoginya, untuk berbicara kepada seseorang, kita menggunakan bahasa tertentu yang dapat dimengerti, sehingga kita dapat menyampaikan apa yang ingin disampaikan. Nah, seperti itulah statement. Apa yang kita sampaikan kepada orang lain layaknya statement pada program yang kita sampaikan kepada komputer.

## Program "Hello, world."

Mari kita mulai dengan membuat program sederhana, yakni program untuk menampilkan kalimat **“Hello, world!”** pada layar (konsol). Berikut adalah kode program tersebut.

```c
#include <stdio.h>  

int main()
{  
      
    printf("Hello, world!\n");  
    return 0;  
}  
```

Salinlah kode di atas pada IDE, kemudian compile dan jalankan. Akan menghasilkan output berikut.

```
Hello, world!\n"
```

## Struktur Program

Untuk menjelaskan bagaimana program di atas bekerja, mari kita pisahkan satu persatu bagian-bagian dari kode tersebut.

### Header File

Baris 1 pada kode di atas disebut dengan preprocessor directive. Preprocessor yang digunakan dalam hal ini adalah `#include`.

Preprocessor `#include` menjelaskan bahwa program tersebut menyertakan file header `<stdio.h>`. File header  tersebut merupakan library bawaan C yang berisi fungsi-fungsi penting yang dibutuhkan oleh program, misalnya pada kasus ini, program membutuhkan fungsi `printf()` untuk mencetak kalimat **“Hello, world!”**. Tanpa adanya library, program tersebut tidak akan bisa di-compile.

### Fungsi main()

Fungsi `main()` pada kode tersebut ditunjukan pada baris ke 3 hingga baris ke 7.

```c
int main()
{  
      
    printf("Hello, world!\n");  
    return 0;  
}
```

Dalam bahasa C, fungsi `main()` adalah fungsi utama yang harus ada. Hal ini dikarenakan eksekusi kode akan dimulai dari awal fungsi `main()`. 

+ Baris 3 menunjukkan nama dari fungsi dan tipe return dari fungsi tersebut. int merupakan tipe return dari fungsi yang bernama `main()`. Kemudian terdapat tanda  `{` yang menandakan awal pembuka dari fungsi `main()`.
+ Baris 4 s.d 6 merupakan tubuh dari fungsi `main()`.
+ Baris 8 terdapat tanda `}` yang menandakan akhir dari fungsi `main()`. Pada dasarnya, tubuh dari sebuah fungsi berada di antara tanda `{ }`.

### Whitespace

Dapat diperhatikan pada kode bahwa baris 2 dan 4 kosong (tidak terdapat karakter apapun). Ini disebut dengan **whitespace**. Whitespace adalah area kosong pada kode, dan biasanya dtujukan agar kode mudah dibaca.

Terdapat tiga jenis whitespace, yakni **space**, **tab**, dan **new line**. Baris 2 dan 4 adalah contoh dari new line.

### Statement

Di dalam fungsi `main()`, terdapat dua statement yang ditunjukkan pada baris 5 dan 6. Sebagian besar statement diakhiri oleh tanda titik-koma (`;`).

```c
printf("Hello, world!\n");  
return 0;  
```

Statement pada baris 5 menginstruksikan program untuk memanggil fungsi `printf()`. Fungsi `printf()` adalah fungsi yang tersedia dalam library header `<stdio.h>` dan digunakan untuk mencetak output pada konsol (layar). Dalam hal ini, fungsi `printf()` menerima argumen string bertuliskan **“Hello, world!\n”**. Tanda `‘\n’` dalam string tersebut merupakan karakter spesial yang berfungsi untuk mencetak new line.

Sedangkan statement pada baris 6 disebut dengan return statement. Perintah `return 0` pada fungsi `main()` digunakan untuk mengakhiri program dan menandakan program tersebut sukses dieksekusi.

## Komentar

Komentar (_comment_) adalah bagian dari program yang tidak akan dieksekusi. Komentar sangat berguna untuk mendeskripsikan program yang dibuat, misalnya saja untuk menjelaskan bagian dari kode agar mudah dipahami oleh programmer lainnya. Terdapat dua jenis komentar dalam bahasa C.

### Komentar Single-Line

Seperti namanya, komentar single-line hanya bekerja pada satu baris. Komentar single-line diawali dengan simbol `//` . Semua karakter (pada satu baris) dibelakang simbol `//` akan diabaikan.

```c
// Ini adalah komentar single-line  
  
// Fungsi untuk mencetak ke layar  
printf("HALO\n");  

```

### Komentar Multi-Line

Sedangkan komentar multi-line dapat bekerja pada lebih dari satu baris. Pasangan simbol `/*` dan `*/` digunakan untuk membuat komentar multi-line. Semua karakter yang berada di antara dua simbol tersebut akan diabaikan.

```c
/* 
Ini adalah komentar multi-line 
Semua yang berada di sini akan 
diabaikan 
*/  
```

# Keyword dan Identifier

## Keyword

Keyword merupakan kata khusus yang telah dipesan (reserved) pada bahasa pemograman. Kata-kata khusus tersebut mempunyai makna tersendiri bagi compiler, dan kata-kata tersebut merupakan bagian dari sintaks dan tidak dapat digunakan sebagai identifier.
Berikut adalah daftar keyword pada bahasa C.

|               |           |           |           |
|---------------|:----------|:----------|:----------|
| auto          | double    | int       | struct    |
| break         | else      | long      | switch    |
| case          | enum      | register  | typedef   |
| char          | extern    | return    | union     |
| continue      | for       | signed    | void      |
| do            | if        | static    | while     |
| default       | goto      | sizeof    | volatile  |
| const         | float     | short     | unsigned  |

## Identifier

Identifier merujuk kepada penamaan sebuah entitas, seperti pada variabel, fungsi, structures dan lain-lain. Karena identifier menamai sebuah entitas, maka nama dari identifier harus unik (dua entitas tidak boleh mempunyai nama identifier yang sama).

Aturan penamaan identifier :

+ Identifier bukan merupakan keyword.
+ Identifier hanya boleh terdiri dari huruf lowercase, huruf uppercase, digit, dan simbol underscore ( _ ).
+ Identifier tidak boleh mengandung whitespace.
+ Identifier harus dimulai dengan huruf atau simbol underscore. Tidak boleh dimulai dengan digit/angka.
+ Bersifat case-sensitive, artinya identifier `variable` berbeda dengan `vAriaBle`.

# Variabel

## Pengenalan Variabel

**Variabel** adalah suatu tempat yang digunakan untuk menampung data atau nilai pada memori yang mempunyai nilai yang dapat berubah–ubah selama proses program. Pada bahasa C, variabel menyimpan data/nilai dengan tipe data tertentu. Seperti halnya variabel yang menyimpan bilangan bulat (integer).

Variabel dapat dianalogikan sebagai sebuah gelas. Gelas dalam hal ini disebut sebagai **variabel**. Pada umumnya, gelas digunakan untuk menampung cairan. Dalam hal ini cairan adalah **tipe datanya**. Kemudian, contoh dari cairan adalah air, yakni dalam hal ini **data** yang akan disimpan oleh gelas.

Pada dasarnya program bekerja dengan mengolah data-data. Data-data inilah yang kemudian disimpan pada variabel.

## Deklarasi dan Definisi Variabel

Pada bahasa C, variabel harus dideklarasikan terlebih dahulu sebelum bisa digunakan. Seperti halnya gelas tadi, gelas tersebut harus ada terlebih dahulu sebelum bisa digunakan.

Untuk mendeklarasikan sebuah variabel, sintaksnya adalah sebagai berikut.

```
<tipe_data> <identifier>
```

Misalkan, potongan kode berikut mendeklarasikan variabel `x` yang bertipe `int`.

```c
int x
```

Jika ingin mendeklarasikan lebih dari satu variabel dengan tipe yang sama, bisa menggunakan operator koma (`,`).

```
<tipe_data> <variabel1>, <variabel2>, ... dst;
```

```c
int x, y;
```

## Pengisian Nilai Pada Variabel

Setelah dideklarasikan, variabel dapat diisi oleh sebuah nilai. Untuk melakukannya,  yakni dengan menggunakan operator assignment (simbol `=`).

```
identifier_variabel = <nilai yang bersesuaian>
```

Contoh :

```c
int x, y;  
x = 10;  
y = -2; 
```

Dalam hal ini, variabel `x` dan `y` akan mempunyai nilai masing-masing `10` dan `-2`.

## Inisialisasi Variabel

Deklarasi dan pengisian nilai pada variabel dapat dilakukan dalam satu instruksi sekaligus. Hal ini disebut dengan **inisialisasi**. Dengan melakukan inisialisasi variabel, berarti kita memberikan nilai awal pada variabel tersebut.

```
tipe_data identifier_variabel = <nilai yang bersesuaian>;
```

Contoh :

```c
int x = 10;
```

# Konstanta dan Literal

## Konstanta dan Literal

Istilah konstanta merujuk pada suatu nilai tetap, tidak dapat berubah/diubah bahkan oleh program itu sendiri. Literal adalah konstanta yang nilainya kita tulis secara eksplisit pada kode. Contohnya :

```c
5       // Literal bilangan bulat  
1.23    // Literal bilangan real  
'S'     // Literal karakter  
"Hai"   // Literal string  
```

Berikut adalah jenis-jenis literal dalam bahasa C.

| Literal                   | Contoh                        | Tipe Default  |
|---------------------------|:------------------------------|:--------------|
| Bilangan bulat            | `10, 0, -1 dll.`              | int           |
| Bilangan real (floating)  | `202.15, 33.24, -12.45 dll.`  | double        |
| Karakter                  | `‘A’, ‘1’, ‘#’`               | char          |
| String                    | `“Hai”`                       | const char[4] |

### Bilangan Bulat

Terdapat tiga cara untuk menuliskan literal bilangan bulat. Yakni menggunakan basis 10 (desimal), basis 8 (oktal) dan basis 16 (heksadesimal).
| Desimal - ditulis seperti bilangan pada umumnya. Contohnya 100, -22.
| Oktal - diawali dengan angka “0”, kemudian diikuti bilangan oktal. Contohnya 077, 033.
| Heksadesimal - diawali dengan “0x”, kemudian diikuti bilangan heksadesimal. Contohnya 0x7f, 0x521.

### Bilangan Real (floating)

Bilangan real (floating) dituliskan dengan menggunakan pemisah tanda titik (.) antara bilangan bulat dan bilangan pecahannya. Contohnya 2.321, -11.22, 0.00012.

### Karakter

Literal karakter dituliskan dengan mengapitnya menggunakan tanda petik. Misalnya karakter A ditulis ‘A’. Selain karakter normal, terdapat karakter khusus dalam bahasa C yang mempunyai fungsi-fungsi khusus atau karakter yang tidak bisa begitu saja dituliskan dengan bentuk aslinya. Misalnya, “new line” direpresentasikan dengan ‘\n’, simbol backslash direpresentasikan dengan ‘\\’. Karakter-karakter tersebut disebut dengan escape sequence. Berikut adalah escape sequence yang terdapat dalam bahasa C.

| Escape Sequence | Karakter            |
|-----------------|:--------------------|
| `\b`            | Backspace           |
| `\f`            | Form feed           |
| `\n`            | Newline             |
| `\r`            | Return              |
| `\t`            | Tab horisontal      |
| `\v`            | Tab vertikal        |
| `\\`            | Backslash           |
| `\’`            | Tanda petik         |
| `\”`            | Tanda petik dua     |
| `\?`            | Tanda tanya         |
| `\0`            | Karakter null       |
| `\b`            | Backspace           |


### String

String adalah kumpulan dari satu karakter atau lebih. Literal string diapit oleh tanda kutip. Misalnya, `“Hello, world.”`. Representasi string dalam bahasa C menggunakan array bertipe `char`. Kita akan mempelajarinya di bagian selanjutnya.

## Mendefinisikan Konstanta

Untuk mendefinisikan konstanta, dapat dilakukan dengan cara-cara seperti berikut.

### Mendefinisikan Variabel Konstan

Variabel juga dapat dibuat konstan nilainya agar tidak dapat berubah/diubah selama program berjalan. Variabel konstan dibuat dengan menambahkan keyword `const` saat pendefinisian variabel.
 
```c
const tipe_data nama_var = <nilai yang bersesuaian>
```

Perlu diperhatikan bahwa definisi variabel konstan harus disertai inisialisasinya.
Contoh :

```c
const int    konstInt = 23;  
const double konstDouble = 23.12;
```

Segala bentuk perubahan yang dilakukan terhadap variabel konstan akan menghasilkan error.

```c
const int konstInt = 23;  
konsInt = 11; // Error
```

### Menggunakan #define

Cara lainnya adalah menggunakan prepocessor directive `#define`. Sintaksnya adalah sebagai berikut.
 
```
#define nama <nilai yang bersesuaian>
```

Contoh
```c
#define konstInt    23  
#define konstDouble 23.11  
  
int main()  
{  
    int    a = konstInt;  
    double b = konstDouble;  
}  
```

# Tipe Data Dasar

Secara sederhana **tipe data** adalah jenis data dan ukuran data yang akan ditampung dan oleh **variabel** (atau objek secara umum). Tipe data menentukan tipe dan jenis data seperti apa yang akan dimiliki oleh suatu variabel.

Dalam bahasa C terdapat beberapa jenis tipe data. Diantaranya adalah tipe data dasar, tipe data turunan dan void. Untuk kali ini kita akan berfokus pada tipe data dasar.

## Tipe Bilangan Bulat (integer)

Bilangan bulat adalah bilangan yang tidak mempunyai nilai pecahan (real). Tipe data bilangan bulat pada bahasa C diantaranya sebagai berikut.

**TABEL**

Seperti namanya, tipe-tipe data di atas adalah tipe data yang digunakan untuk merepresentasikan bilangan bulat (positif dan negatif) dan bilangan 0. Misalnya, 0, -5, 12, -1, 200 dsb. **Perlu ditekankan** bahwa tipe-tipe data di atas tidak dapat digunakan untuk merepresentasikan bilangan floating-point (bilangan real).

Jika diperhatikan, terdapat dua jenis tipe data antara lain signed dan unsigned. Lalu apa perbedaan dari kedua jenis tersebut? Perbedaannya adalah terletak pada kemampuan untuk menampung bilangan negatif. **signed** dapat menampung bilangan negatif, sedangkan **unsigned** tidak.

## Tipe Bilangan Real (floating)

Bilangan real atau floating-point adalah bilangan yang mempunyai nilai pecahan (real). Tipe data bilangan real pada bahasa C diantaranya adalah sebagai berikut.

**TABEL**

Tipe data di atas digunakan untuk menyimpan data berupa bilanga real (floating-point)/bilangan berkoma. Misalnya, `2.35, -12.246, 0.005` dsb.

## Tipe Karakter

Karakter dalam bahasa C sebenarnya adalah bilangan bulat. Setiap karakter mempunyai kode tersendiri yang disebut dengan ASCII, dan kode tersebut diwakili oleh sebuah bilangan bulat.

**TABEL**

Penggunaan paling umum dari tipe data di atas adalah untuk merepresentasikan satu karakter. Misalnya, `‘A’`, `‘-‘`, dan sebagainya.

# Input dan Output Dasar

> Pembahasan input dan output pada chapter ini hanya terbatas pada input dari keyboard (STDIN) dan output pada layar (STDOUT).

Program yang kita buat dapat dibuat menjadi program yang interaktif. Kita dapat menginstruksikannya untuk menerima input (dari keyboard) lalu menampilkan hasil output (pada konsol layar). Fungsi-fungsi yang berkaitan dengan input/output ada di dalam library `<stdio.h>` (standard input output).

## Output Dasar

### Fungsi `printf()`

Untuk mencetak output pada konsol, fungsi yang digunakan adalah fungsi `printf()`. Seperti yang sudah kita ketahui sebelumnya, fungsi `printf()` dapat menerima string sebagai argumen.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("Ini adalah sebuah string\n");  
    return 0;  
} 
```

Output

```
Ini adalah sebuah string
```


Kita juga dapat menambahkan escape sequence pada string. Misalkan, kita ubah statement `printf()` di atas menjadi :

```c
printf("Ini adalah sebuah string\nAku adalah new-line\n\tAku adalah karakter \\tab");
```  
 
```
Ini adalah sebuah string
Aku adalah new-line
    Aku adalah karakter \tab
```

Memisahkan dua statement `printf()` pada baris berbeda bukan berarti mencetak pada baris berbeda juga.

```c
#include <stdio.h>  
  
int main()   
{  
    printf("Pikirmu aku akan");  
    printf("Berpindah baris?");  
    return 0;  
}  
```

Output

```
Pikirmu aku akanBerpindah baris?
```

Contoh-contoh di atas adalah contoh untuk mencetak string tetap. Lalu bagaimana jika kita ingin mencetak string bersama dengan nilai dari suatu variabel?


### Output Dengan Format Specifier

Untuk mencetak nilai dari suatu variabel, kita perlu menambahkan argumen pada fungsi `printf()`. Argumen pertama pada fungsi `printf()` selalu berupa string. Kita dapat memasukkan variabel/nilai pada argumen ke-2, 3, 4 dan seterusnya sesuai kebutuhan.
Ingat, pada chapter Tipe Data Dasar, setiap tipe data mempunyai format specifier masing-masing. Nah, format specifier inilah yang akan kita gunakan untuk mencetak nilai dari suatu variabel.
 
```
printf(“<format string>”, var1, var2, var3, ... dst);
```

Misalnya saja, kita mempunyai dua variabel bertipe int dan char yakni `a = 2` dan `b = ‘X’`. Kita hendak mencetak nilai dari a dan b dipisahkan oleh spasi, maka programnya seperti :   

```c
#include <stdio.h>  
  
int main()   
{  
    int  a = 2;  
    char b = 'X';  
    printf("%d %c", a, b);  
    return 0;  
}
```

Output

```
2 X
```
 
Perhatikan Ilustrasi di bawah.
 
![Oi ini nanti gambar]()

Dengan menyertakan format specifier dari tipe data yang bersesuaian, kita dapat mencetak nilai dari variabel tersebut. 
+ Fungsi `printf()` di atas mencetak string dengan nilai dua variabel (dua format specifier yang dipisahkan spasi).
+ Format specifier pertama adalah format specifier tipe data int dan akan merujuk pada variabel pertama yang dimasukkan, yakni a.
+ Format specifier kedua adalah format specifier tipe data char dan akan merujuk pada variabel kedua, yakni b.
+ Dan begitu seterusnya, satu format specifier untuk satu variabel berurutan.
Dengan begitu, kita dapat menyertakan format specifier bersamaan dengan string.

```c
printf("Nilai dari a = %d, dan b = '%c'", a, b);    
```

```
Nilai dari a = 2, dan b = ‘X’
```

## Input Dasar

### Fungsi `scanf()`

Umumnya kita melakukan input untuk menerima data/nilai dari user. Kemudian, data/nilai tersebut akan dimasukkan pada variabel yang akan diproses kemudian.
Untuk melakukan input dari keyboard fungsi yang digunakan adalah fungsi `scanf()`. Parameter dari fungsi `scanf()` sama persis dengan fungsi `printf()`. Kita menggunakan format specifier untuk menentukan jenis tipe data yang kita input, kemudian nilai input tersebut akan di-assign pada variabel.

Contoh :

Program di bawah menerima input berupa bilangan bulat yang disimpan pada variabel n, kemudian mencetak nilai variabel n dengan format _“n mempunyai nilai = n”_.

```c
#include <stdio.h>  
  
int main()   
{  
    int n;  
    scanf("%d", &n);  
    printf("n mempunyai nilai = %d", n);  
    return 0;  
} 
```

Input
 
```
3
```

Output

```
n mempunyai nilai = 3
```
 
> Perlu diperhatikan bahwa fungsi `scanf()` akan berhenti membaca input ketika menjumpai whitespace (apabila mengetikkan spasi, new line, dan tab). Jadi apabila pada program sebelumnya kita meng-inputkan :
> 124 432
> maka nilai yang terbaca hanyalah 124 karena setelah itu dipisahkan oleh spasi yang menyebabkan fungsi `scanf()` berhenti membaca input.

# Operator

Operator dapat dipahami sebagai sesuatu yang dapat melakukan operasi pada operan (variabel/nilai). Contohnya, operator + digunakan untuk operasi penjumlahan.

Dilihat dari jumlah operan-nya, operator dibagi menjadi tiga jenis, yaitu.

+ **Unary** – yakni operator yang bekerja pada satu operan, misalnya -5.
+ **Binary** – yakni operator yang bekerja pada dua operan, misalnya 2 + 3.
+ **Ternary** – yakni operator yang bekerja pada tiga operan. (Akan dibahas pada bagian selanjutnya).

Dilihat dari kegunaannya, berikut adalah jenis-jenis operator pada bahasa C.

## Operator Assignment

Operator assignment digunakan untuk mengisikan (assign) sebuah nilai ke variabel. Simbol yang biasa digunakan adalah tanda sama dengan  `=`. Contohnya :

```c
int x, y;  
x = 4;  
y = 3;  
x = x + y; // x = 7  
y = x + x; // y = 14 
```

## Operator Aritmatika

Seperti namanya, operator aritmatika melakukan operasi layaknya pada matematika seperti penjumlahan, pengurangan, pembagian dsb. Beberapa operator menggunakan simbol yang sama pada matematika (penjumlahan dengan simbol `‘+’`, pengurangan dengan `‘-‘`, dst.). Operator-operator aritmatika pada bahasa C adalah sebagai berikut.

**TABEL**

## Operator Gabungan

Operator Gabungan adalah operator yang terdiri dari gabungan dua operator. Tujuan dari operator gabungan adalah untuk mempersingkat penulisan kode. Berikut adalah operator gabungan dalam bahasa C.

**TABEL**

## Operator Increment dan Decrement

Operator `++` disebut dengan operator increment, sedangkan operator -- merupakan operator decrement. Kedua operator ini digunakan untuk menambah (increment)/mengurangi (decrement) nilai dari suatu variabel sebanyak `satu`.

Terdapat dua cara untuk menggunakan operator ini.

+ **Prefix** - yakni dengan meletakkan operator increment/decrement didepan nama variabel. 

    ```c
    int a, b;  
    a = 5;  
    ++a; // Nilai a sekarang adalah 6  
    --a; // Nilai a sekarang adalah 5 
    ```

    Cara kerja dari operator increment/decrement prefix adalah dengan menambahkan/mengurangi nilai variabel sebanyak satu terlebih dahulu, sebelum operan tersebut digunakan pada operasi lainnya pada sekuens intstruksi yang sama. Untuk lebih jelasnya, perhatikan potongan kode berikut

    ```c
    int a, b;  
    a = 5;  
    b = ++a; // Nilai b sekarang adalah 6  
    a = --b; // Nilai a sekarang adalah 5 
    ```

    Disini, saat instruksi `b = ++a;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` ditambahkan satu terlebih dahulu, kemudian baru di-assign nilainya ke variabel `b`.

+ **Postfix** - yakni dengan meletakkan operator increment/decrement di belakang nama variabel. Cara kerja dari operator increment/decrement postfix berbeda dari prefix. Pada postfix, nilai variabel akan ditambah satu setelah operan digunakan pada operasi lainnya pada sekuens instruksi yang sama. Perhatikan potongan kode berikut.

    ```c
    int a, b;  
    a = 5;  
    b = a++; // Nilai b sekarang adalah 6  
    a = b--; // Nilai a sekarang adalah 5 
    ```

    Disini, saat instruksi `b = a++;` dieksekusi, yang terjadi pertama kali adalah nilai dari `a` akan di-assign terlebih dahulu ke variabel `b`, kemudian baru ditambahkan satu. Karena itulah variabel `b` mendapat nilai dari `a` sebelum terjadi penambahan.

## Operator Relasional

Operator relasional digunakan untuk memeriksa relasi dan membandingkan nilai dari dua operan. Jika benar akan menghasilkan nilai TRUE (direpresentasikan angka 1), jika salah maka akan menghasilkan nilai FALSE (direpresentasikan angka 0).

Berikut adalah operator relasional dalam bahasa C.

**TABEL**

## Operator Logika

Operator logika digunakan untuk melakukan tes pada kondisi/ekspresi, apakah kondisi tersebut benar atau salah. Operator logika hanya akan menghasilkan nilai **TRUE** (jika benar) atau **FALSE** (jika salah). TRUE direpresentasikan oleh angka 1, sedangkan FALSE oleh angka 0.

Operator-operator logika dalam bahasa C adalah sebagai berikut.

**TABEL**

Operator logika pada umumnya digunakan bersamaan dengan operator relasional untuk melakukan tes pada ekspresi yang berhubungan dengan kebenaran suatu kondisi. Penggunaan paling umum adalah untuk melakukan percabangan (akan dipelajari di bagian selanjutnya).

Contoh:

```c
int a, b, c, d;  
a = 11;  
b = 24;  
c = 11;  
d = ((a == c) && (b > a));               // 1 (TRUE)  
d = ((a >= b) || (a < c));               // 0 (FALSE)  
d = ((b != b) || (b > c)) && (c == a);   // 1 (TRUE) 
```

## Operator Bitwise

Operator bitwise, seperti namanya digunakan untuk melakukan operasi pada dua operan dalam skala biner (bilangan basis 2). Sebelum mempelajari lebih lanjut cara kerja operasi bitwise, sebaiknya kamu harus paham terlebih dahulu mengenai bilangan dalam basis biner.

Terdapat 6 jenis operator bitwise, yakni **AND**, **OR**, **XOR**, **COMPELEMENT**, **SHIFT LEFT**, dan **SHIFT RIGHT**. Untuk lebih memahami perbedaan cara kerja operator bitwise, perhatikan tabel berikut.

**TABEL**

**Contoh penggunaan operator bitwise :**

Misal 12 dan 5. Representasi 12 dan 5 dalam basis biner adalah 12 = 11002 dan 5 = 01012. Maka, operasi bitwise adalah sebagai berikut.

+ **Bitwise AND**

    ```
    12 = 1100
     5 = 0101
    ---------- &
     4 = 0100
    ```

+ **Bitwise OR**

    ```
    12 = 1100
     5 = 0101
    ---------- | 
    13 = 1101
    ```

+ **Bitwise XOR**

    ```
    12 = 1100
     5 = 0101
    ---------- ^
     9 = 1001
    ```

+ **Bitwise COMPLEMENT**

    ```
     12 = 1100
    ~12 = 0011
    ```

+ **Bitwise SHIFT LEFT**

    Misal kita hendak menggeser bit bilangan 13 ke kiri sebanyak 2, maka 13 << 2.

    ```
         13 = 001101
    13 << 2 = 110100 
    ```

    Bisa diperhatikan, bit paling kanan setelah digeser akan diisi oleh 0. Maka hasil dari 13 << 2 = 52.

+ **Bitwise SHIFT LEFT**

    Misal kita hendak menggeser bit bilangan 13 ke kanan sebanyak 2, maka 13 >> 2.

    ```
         13 = 001101
    13 >> 2 = 000011
    ```

    Bisa diperhatikan, bit paling kiri setelah digeser akan diisi oleh 0. Maka hasil dari 13 >> 2 = 3.
