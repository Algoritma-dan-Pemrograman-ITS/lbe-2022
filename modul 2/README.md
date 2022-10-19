# Modul LBE Alpro 2022

- [Git Lanjutan](#git-lanjutan)

- [Object Oriented Programming](#object-oriented-programming)

  - [Tools](#tools)
  - [Pengenalan OOP](#pengenalan-oop)

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

### Mengatasi merge conflict

Setiap orang yang menggunakan Version Control System pasti akan bertemu saat di mana secara tidak sengaja melakukan push di saat main branch-nya berubah. Sehingga, ketika branch tersebut di-pull request, branch tersebut tidak dapat langsung karena terdapat file yang conflicted dengan main branch. Hal ini dikarenakan Git meminta untuk menentukan file mana yang harus dipertahankan.

![image](https://user-images.githubusercontent.com/87473932/196573574-9e96d6fe-a08d-4d3c-b7d9-a212bbc56771.png)
![image](https://user-images.githubusercontent.com/87473932/196573697-b74ce647-b6b8-4b7c-aaec-3d37354ac436.png)

Lalu bagaimana cara kita mengatasi merge conflict?

Sebenarnya, banyak cara yang dapat kita lakukan untuk mengatasi merge conflict. Cara yang paling umum adalah dengan me-resolve conflict di GitHub Web Editor atau website GitHub. Untuk *step-by-step*nya dapat kalian baca dengan mengakses link: https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/resolving-a-merge-conflict-on-github
Namun, cara di atas tidak adapat digunakan apabila *resolve button* tidak dapat digunakan.

Cara lain yang dapat digunakan apabila kalian menggunakan Visual Studio Code adalah sebagai berikut:
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
