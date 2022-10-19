# Modul LBE Alpro 2022

- [Git Lanjutan](#git-lanjutan)
  - [Pull Request](#pull-request)
  - [Merge Conflict](#merge-conflict)
  - [Remote](#remote)

- [Object Oriented Programming](#object-oriented-programming)
  - [Apa itu OOP?](#apa-itu-oop)
  - [4 Prinsip Dasar OOP](#4-prinsip-dasar-oop)
  - [SOLID Principles](#solid-principles)
  - [DRY Principles](#dry-principles)

----

## **Git Lanjutan**

Setelah kalian belajar git pada modul sebelumnya, mari kita kenal lebih dalam lagi tentang git.

### Pull Request

Apa itu pull request di Git? Pull request adalah event di Git di mana kontributor meminta maintainer dari repository Git untuk mereview kode yang ingin mereka gabungkan ke dalam sebuah proyek. Selain itu, maintainer juga dapat meng-accept pull request sehingga perubahan yang ada pada branch yang di-pull request akan di-merge dengan main branch.

Salah satu flow yang dapat dilakukan untuk pull request:
<ol>
  <li>Clone repository</li>
  <li>Membuat perubahan pada isi repository</li>
  <li>Push ke branch baru</li>
  <li>Contributor >> Open pull request</li>
</ol>

![image](https://user-images.githubusercontent.com/87473932/195518366-de446527-fd77-449e-b64d-1f48f87d3a0c.png)
![image](https://user-images.githubusercontent.com/87473932/195520344-a0d1f4bf-4518-41ef-9447-dfed583ba289.png)
![image](https://user-images.githubusercontent.com/87473932/195520601-1bf4429b-b9a7-42ee-8372-b8dae7ef21f2.png)

### Apa yang dapat dilakukan ketika mendapat pull request?
<ul>
  <li> Mereview perubahan </li>
  <li> Memberi komentar pada perubahan </li>
  <li> Menolak merge request </li>
  <li> Dan lain sebagainya </li>
</ul>

### Merge conflict

Setiap orang yang menggunakan Version Control System pasti akan bertemu saat di mana secara tidak sengaja melakukan push di saat main branch-nya berubah. Sehingga, ketika branch tersebut di-pull request, branch tersebut tidak dapat langsung karena terdapat file yang conflicted dengan main branch. Hal ini dikarenakan Git meminta untuk menentukan file mana yang harus dipertahankan.

![image](https://user-images.githubusercontent.com/87473932/196573574-9e96d6fe-a08d-4d3c-b7d9-a212bbc56771.png)
![image](https://user-images.githubusercontent.com/87473932/196573697-b74ce647-b6b8-4b7c-aaec-3d37354ac436.png)

Lalu bagaimana cara kita mengatasi merge conflict?

Sebenarnya, banyak cara yang dapat kita lakukan untuk mengatasi merge conflict. Cara yang paling umum adalah dengan me-resolve conflict di GitHub Web Editor atau website GitHub. Untuk *step-by-step*nya dapat kalian baca dengan mengakses link: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github.

Namun, cara di atas tidak adapat digunakan apabila *resolve button* tidak dapat digunakan. Cara lain yang dapat digunakan apabila kalian menggunakan Visual Studio Code adalah sebagai berikut:
1. Install GitLens
![image](https://user-images.githubusercontent.com/87473932/196575317-e9a0f9d5-7377-4112-ab2c-b1c1de2fa2a5.png)
2. Pull main, maka akan terlihat pada bagian mana saja yang terdapat conflict. Klik **Resolve in merge editor**.
![image](https://user-images.githubusercontent.com/87473932/196576867-3045e677-8435-49c8-bb7c-bea38de3edfc.png)
3. Pilih file mana yang akan dipertahankan
![image](https://user-images.githubusercontent.com/87473932/196577181-cc753d5f-44d0-4952-bc37-18fae5504760.png)
![image](https://user-images.githubusercontent.com/87473932/196577240-8d37310e-6389-4ebb-88fb-1dd943845d70.png)
4. Lakukan hingga tidak terdapat conflict.
5. Lakukan push kembali ke branch dan merge pull request

### Remote
Pada modul sebelumnya, kita telah menggunakan ```remote``` untuk menambahkan ```origin``` dari repository yang kita buat. Namun, ```remote``` memiliki command lainnya:
<ul>
  <li>git remote -v</li>
  <li>git remote add</li>
  <li>git remote rename</li>
  <li>git remote remove</li>
  <li>git remote show</li>
  <li>git remote get-url</li>
  <li>git remote set-url</li>
</ul>

contoh:

![image](https://user-images.githubusercontent.com/87473932/195530137-a8195f33-5dd9-461b-9725-84e1eb35f40b.png)
![image](https://user-images.githubusercontent.com/87473932/195530508-517e3652-6d04-454d-a66f-a588416dca75.png)

untuk selengkapnya, kalian dapat mengakses link ini: https://git-scm.com/docs/git-remote

## **Object Oriented Programming**

### Apa itu OOP?
Object-oriented programming atau OOP diartikan sebagai pemrograman yang berorientasi pada objek yang merupakan model pemrograman komputer dengan pengaturan desain perangkat lunak di sekitar data atau objek. Berbeda dengan pemrograman lain yang berfokus pada fungsi dan logika, OOP lebih menaruh fokus pada objek atau bidang data yang memiliki atribut atau perilaku teknis unik. Fokus OOP pada objek ini memungkinkan adanya manipulasi yang dilakukan pengembang dan cocok untuk pemrograman besar dan kompleks. Pendekatan OOP ini lebih mudah untuk perihal pembaruan dan pemeliharaan.

OOP dapat digunakan dalam berbagai bahasa pemrograman seperti JavaScript, C++, Java, dan Python. Penggunaan kelas dalam pemrograman OOP ini dapat menentukan atribut apa yang akan dimiliki oleh instance objek seperti warna dan sebagainya. Secara umum, OOP menjadi lebih ringkas karena pengembang bisa lebih fokus melakukan manipulasi terhadap objek daripada pada logic atau fungsi. Adapun yang akan kita bahas di sini adalah OOP dalam Java.

### 4 Prinsip Dasar OOP

![image](https://user-images.githubusercontent.com/87473932/196592111-577adcc1-e087-46e5-8a86-40480913ace9.png)
#### 1. Encapsulation
Prinsip enkapsulasi dalam OOP dilakukan ketika setiap objek dalam pemrograman dapat mempertahankan keadaan ***private*** di dalam sebuah kelas-kelas. Dengan begitu, objek lain tidak dapat mengakses status objek tersebut secara langsung. Meski begitu, objek lain tetap dapat memanggil daftar fungsi publik karena objek mengelola statusnya sendiri melalui fungsi-fungsi publik ini.

Dalam Java, enkapsulasi ini dapat dilakukan dengan cara membuat *private* variable dalam sebuah class dan membuat public method untuk mengaksesnya.

#### 2. Abstraction
Prinsip selanjutnya yaitu abstraksi. Prinsip ini sendiri berarti memungkinkan seorang developer memerintahkan suatu fungsi, tanpa harus mengetahui bagaimana fungsi tersebut bekerja. Lebih lanjut, abstraction berarti menyembunyikan detail latar belakang dan hanya mewakili informasi yang diperlukan untuk dunia luar.

Dalam Java, abstraksi ini dapat dilakukan dengan membuat *abstract class* dan *interface*.

#### 3. Inheritance
Inheritance merupakan kemampuan suatu objek untuk memperoleh beberapa atau bahkan semua properti dari objek lain dalam pemrograman OOP. Hal ini bisa dimisalkan dari seorang anak mewarisi sifat-sifat orang tuanya. 

Inheritance ini menggunakan konsep *reusability*, dengan kata lain, apabila kita ingin membuat sebuah class baru dan sudah terdapat class yang mengandung potongan kode yang kita inginkan, maka kita dapat mengambilnya untuk class baru kita hanya dengan meng-*extend*-nya.

#### 4. Polymorphism
Kata **polimorfisme** berarti memiliki banyak bentuk. Dengan kata lain, kita dapat mendefinisikan polimorfisme sebagai kemampuan sebuah objek untuk ditampilkan dalam lebih dari satu bentuk.

Contoh sederhananya adalah kita memiliki class Rectangle dan Square yang merupakan *subclass* dari Rectangle. Kemudian kita memiliki variable r2 yang bertipe data Rectangle tetapi memiliki data yang berisi sebuah Square. Maka, r2 dapat direpresentasikan sebagai Square maupun Rectangle.

Untuk keempat prinsip ini akan dibahas lebih lanjut pada modul berikutnya.

### Prinsip Lain yang Perlu Diperhatikan pada OOP

### SOLID Principles
![image](https://user-images.githubusercontent.com/87473932/196591577-dfd05e30-4a81-4bd5-98e3-ec198aac51d0.png)

**SOLID** adalah sebuah akronim dari lima prinsip. Prinsip ini biasa diterapkan dalam pemrograman berorientasi objek.

Kelima prinsip ini adalah praktek dalam mengembangkan sebuah program dengan mempertimbangkan pemeliharaan serta pengembangan lebih lanjut agar kode mudah dirawat, mudah dimengerti serta fleksibel.

Mengadopsi prinsip ini dapat membantu kalian dalam menghindari bad code, membantu dalam refactoring code serta pengembangan aplikasi secara Agile atau Adaptive.

Singkatan dari SOLID sendiri adalah :
<ul>
  <li> S - Solid-Responsibility Principle: Setiap class hanya memiliki satu tugas, sehingga alasan untuk merubah class tersebut hanya satu, yaitu merubah tugas yang diberikan kepadanya.
  
  [Dapat dicapai dengan menggunakan konsep Class dan Constructor]
  </li>
  
  <li> O - Open-Closed Principle: Objek atau entitas itu terbuka untuk ekstensi tetapi tertutup untuk modifikasi.
  
  [Dapat dicapai dengan konsep Inheritance]
  </li>
  
  <li> L - Liskov Substitution Principle: Fungsi yang mereferensi ke parent class harus dapat menggunakan objek dari kelas turunan tanpa menyimpang dari parent class-nya. Singkatnya, setiap kelas turunan harus bisa menjadi pengganti untuk base class atau kelas parent nya.
  
  [Dapat dicapai dengan konsep Polymorphism]
  </li>
  
  <li> I - Interface Segregation Principle: Objek client tidak boleh dipaksa untuk mengimplementasikan sebuah interface yang tidak ia gunakan.
  
  [Dapat dicapai dengan konsep Abstract Class dan Interface]
  </li>

  <li> D - Dependency Inversion Principle: Sebuah entitas bergantung pada abstraksi. Sehingga sebuah modul tingkat tinggi tidak boleh bergantung pada modul tingkat rendah, tetapi bergantung kepada abstraksi.
  </li>
</ul>

#### DRY Principles
DRY adalah sebuah singkatan dari Don't Repeat Yourself. Prinsip DRY ketika menulis kode diterapkan untuk mengurangi repetisi di penulisan kode dengan prinsip abstraksi. Efek dari ini akan membuat kode lebih mudah dibaca dan dapat mengurangi potensi untuk software bug. Secara garis besar, DRY adalah prinsip anti-perulangan yang tidak perlu. Beberapa contoh penerapan DRY adalah dengan menggunakan Function, Loop, Inheritance, dan lain sebagainya.

## Tugas Modul 1 & Modul 2:

Buatlah sebuah git repository untuk setiap kelompok
Masukkan setiap anggota kelompok menjadi contributor

Hal yang harus dilakukan:
1. Buatlah sebuah README.md tanpa isi
2. Setiap anggota membuat sebuah markdown dengan format nama:
NRP_NamaLengkap, berisikan kesan-pesan selama LBE dan harapan
perkuliahan untuk ke depannya
3. Tuliskan nama dan NRP dalam README.md sebelum melakukan push
4. Buatlah branch untuk setiap anggota dengan format namaPanggilan
5. Push hasil kerjaan setiap anggota ke masing-masing branch
6. Merge setiap branch ke dalam main / master branch, JANGAN
HAPUS BRANCH YANG TELAH DIBUAT

contoh alur pengerjaan:
<br>1 Kelompok berisikan Nopal dan Bgsd
<br>Nopal membuat repository dan menambahkan Bgsd sebagai contributor
<br>Nopal membuat markdown tugas
<br>Nopal mengisikan nama dan NRP nya pada README
<br>Nopal membuat branch "Nopal"
<br>Nopal push hasil kerjaan ke branch "Nopal"
<br>Nopal melakukan merge ke main branch tanpa menghapus branch "Nopal"