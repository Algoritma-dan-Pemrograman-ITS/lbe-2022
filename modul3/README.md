

## Inheritance
- Inheritance atau pewarisan adalah kemampuan untuk menurunkan sebuah class ke class lain
- dalam artian, kita bisa membuat class Parent dan class Child
- class Child hanya bisa punya 1 parent, tetapi class Parent bisa punya banyak class Child
- saat sebuah class diturunkan, maka semua field dan method yang ada di class Parent secara otomatis akan dimiliki oleh class Child
- Untuk melakukan pewarisan, di class Child kita harus menggunakan keyword "extends" lalu diikuti dengan class parent-nya

// contoh code

### Method Overriding
- Method overriding adalah kemampuan mendeklarasikan ulang method di child class, yang sudah ada di parent class
- saat kita melakukan proses overriding tersebut, secara otomatis ketika kita membuat object dari class child, method yang di class parent tidak bisa diakses lagi

## Encaptulation



## Abstraction

### Abstract class
- kita dapat menjadikan sebuah class sebagai abstract class
- abstract class ialah class yang tidak bisa dibuat sebagai object secara langsung, hanya bisa diturunkan
- untuk membuat sebuah class menjadi abstract, kita dapat menggunakan keyword 'abstract' sebelum keyword 'class'


## Polymorphism
- Polymorphism berasal dari bahasa Yunani yang berarti "banyak bentuk"
- dalam OOP, Polymorphism ialah kemampuan sebuah object berubah bentuk menjadi bentuk lain
- konsep ini berkaitan erat dengan Inheritance
- misal kita mempunyai object x yang extend ke object y (berarti object x ialah child dan object y ialah parent). lalu kita mendeklarasikan instance object dari object y (yg parent), maka kita bisa nge create instance object x. (poin ini mgkn bisa direvisi lagi)


Referensi: Vidoe youtube "TUTORIAL JAVA OOP BAHASA INDONESIA" Channel Programmer Zaman Now https://youtu.be/f3ZhNnvtV-w