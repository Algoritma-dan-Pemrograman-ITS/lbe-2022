

# Inheritance
- Inheritance atau pewarisan adalah kemampuan untuk menurunkan sebuah class ke class lain
- dalam artian, kita bisa membuat class Parent dan class Child
- class Child hanya bisa punya 1 parent, tetapi class Parent bisa punya banyak class Child
- saat sebuah class diturunkan, maka semua field dan method yang ada di class Parent secara otomatis akan dimiliki oleh class Child
- Untuk melakukan pewarisan, di class Child kita harus menggunakan keyword "extends" lalu diikuti dengan class parent-nya

// contoh code

## Method Overriding
- Method overriding adalah kemampuan mendeklarasikan ulang method di child class, yang sudah ada di parent class
- saat kita melakukan proses overriding tersebut, secara otomatis ketika kita membuat object dari class child, method yang di class parent tidak bisa diakses lagi

# Encapsulation

Pada dasarnya, enkapsulasi adalah **membuat batasan akses** untuk suatu **objek**, seperti class, variable, dan method.

Analoginya, kita pun sebagai manusia seringkali membuat batasan akses terhadap informasi. Ada hal yang kita sampaikan secara terbuka terhadap publik. Ada yang kita jaga dan sampaikan ke keluarga terdekat saja. Ada juga hal-hal privasi yang kita simpan untuk diri sendiri. 

Enkapsulasi biasanya diimplementasikan dengan menggunakan access modifiers.

## Access Modifiers

Sesuai namanya, access modifiers **memodifikasi jangkauan akses** dari suatu objek. Ada **4 tipe** access modifiers yang tersedia dalam Java:

### **Default**

- Tidak memerlukan keyword.
- Objek dengan access modifier default hanya dapat **diakses** dari **package** yang **sama**.

### Public

- Menggunakan keyword public.
- Jangkauan akses paling luas, bisa **diakses** oleh **siapa saja** dan dimana saja dalam program.
- Kita bisa melakukan **read** dan **write** terhadap variabel public **dari luar**. Read berarti kita membaca nilai variabel, sedangkan write berarti kita menulis suatu nilai ke dalam variabel tersebut.

### Private

- Menggunakan keyword private.
- **Hanya** bisa **diakses** di dalam **class tempat deklarasi** objek.
- Tidak bisa diakses dari kelas lain atau package lain.

### Protected

- Menggunakan keyword protected.
- Dapat **diakses** dari **package** yang **sama**.
- Bisa **diakses** dari **package lain** menggunakan **subclass** atau **child class**. (Inheritance)

## Method Getter dan Setter

Bagaimana jika kita perlu mengakses private variable dari luar? Kita bisa menggunakan method getter dan setter. Method **gette**r digunakan untuk **mengakses nilai** suatu variable, sedangkan method **setter** digunakan untuk **memasukkan nilai** ke dalam suatu variable. 

Untuk syntax penamaan, biasanya dimulai dengan kata get atau set lalu diikuti nama variable dengan huruf pertama kapital. Misalnya getMoney dan setMoney.

Dengan method getter dan setter kita bisa membuat attribute class jadi **read-only** atau **write-only**. Dia akan read-only jika kita hanya membuat getter method, dan dia akan write-only jika kita hanya membuat setter method. 

# Abstraction

## Abstract class
- kita dapat menjadikan sebuah class sebagai abstract class
- abstract class ialah class yang tidak bisa dibuat sebagai object secara langsung, hanya bisa diturunkan
- untuk membuat sebuah class menjadi abstract, kita dapat menggunakan keyword 'abstract' sebelum keyword 'class'


# Polymorphism
- Polymorphism berasal dari bahasa Yunani yang berarti "banyak bentuk"
- dalam OOP, Polymorphism ialah kemampuan sebuah object berubah bentuk menjadi bentuk lain
- konsep ini berkaitan erat dengan Inheritance
- misal kita mempunyai object x yang extend ke object y (berarti object x ialah child dan object y ialah parent). lalu kita mendeklarasikan instance object dari object y (yg parent), maka kita bisa nge create instance object x. (poin ini mgkn bisa direvisi lagi)


# Referensi: 
- [Video Youtube "Tutorial JAVA OOP BAHASA INDONESIA" Channel Programmer Zaman Now](https://youtu.be/f3ZhNnvtV-w)
- [Access Modifiers in Java - GeeksforGeeks](https://www.geeksforgeeks.org/access-modifiers-java/)
- [Access modifiers in java - Javatpoint](https://www.javatpoint.com/access-modifiers)
- [The Access Modifiers in Java | What are access modifiers?-Great Learning (mygreatlearning.com)](https://www.mygreatlearning.com/blog/the-access-modifiers-in-java/#:~:text=Access%20modifiers%20are%20keywords%20that,protected%2C%20default%2C%20and%20private.)
- [Java Access Modifiers (With Examples) (programiz.com)](https://www.programiz.com/java-programming/access-modifiers)
- [Java Encapsulation and Getters and Setters (w3schools.com)](https://www.w3schools.com/java/java_encapsulation.asp)
- [(53) Belajar Java [OOP] - 10 - Getter dan Setter (Encapsulasi) - YouTube](https://www.youtube.com/watch?v=zwDMHJzTUzs&list=PLZS-MHyEIRo6V4_vk1s1NcM2HoW5KFG7i&index=12)
