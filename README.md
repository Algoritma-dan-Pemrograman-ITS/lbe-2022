# Modul LBE Alpro 2022

- [Mengenal Lab Alpro](#mengenal-lab-alpro)

- [Version Control System (VCS) Dengan Git](#version-control-system-vcs-dengan-git)

  - [VCS Secara Singkat](#vcs-secara-singkat)
  - [Three States](#three-states)
  - [Instalasi](#instalasi)
  - [Konfigurasi](#konfigurasi)
  - [Perintah Dasar](#perintah-dasar)
  - [Meletakkan Repositori Lokal Pada Repositori Online](#meletakkan-repositori-lokal-pada-repositori-online)

- [Object-Oriented Programming Dengan Java](#object-oriented-programming-dengan-java)

----

## **Mengenal Lab Alpro**

## **Version Control System (VCS) Dengan Git**

> **Disclaimer**: belajar version control system lebih enak sambil dicobain. Jadi teori di sini secukupnya aja, tapi lebih banyak habiskan waktu untuk coba-coba ya 🚀

### VCS Secara Singkat

Dalam mengerjakan sebuah proyek, seringkali kita perlu berkolaborasi. Dibutuhkan sistem pengerjaan yang terstruktur agar kolaborasi memiliki akuntabilitas dan tidak mengakibatkan kesalahan atau _bug_ yang mengganggu jalannya proyek. Kita bisa menggunakan _version control system_ (VCS) untuk manajemen aset-aset proyek seperti _source code_.

Berikut ini fungsi-fungsi VCS secara lebih lengkap:

- **Kolaborasi**

VCS memungkinkan banyak orang/_device_ mengerjakan satu proyek secara bersamaan. Tiap orang/_device_ punya _copy_ aset-aset proyek sendiri. Saat integrasi dengan _master copy_ diperlukan, barulah dia melakukan **_staging_** dan **_commit_** pada file-file yang dikerjakan agar _master copy_ juga memiliki versi file yang sama dengannya.

- **Integrasi**

Pengerjaan yang dilakukan masing-masin orang/_device_ tidak saling memengaruhi sampai integrasi/**_merging_** dilakukan. Jika ditemukan kesalahan saat integrasi, penentuan versi yang benar dikembalikan kepada orang yang melakukan integrasi.

- **Akuntabilitas**

VCS menyimpan riwayat pengubahan pada proyek, sehingga jika terdapat kesalahan fatal, orang yang memiliki akses ke proyek bisa memilih untuk kembali atau **_revert_** ke versi sebelumnya yang belum terdapat kesalahan. Hal ini mudah karena setiap versi pengubahan yang dilakukan dapat diidentifikasi kapan, siapa yang mengubah, dan bagian apa yang diubah.

Secara umum, terdapat dua jenis _version control_ yang dibedakan dari cara _versioning_-nya, yaitu:

- **Centralized Version Control**

We commit - They update

- **Distributed Version Control**

We commit - We push - They pull - They update

Terdapat beberapa contoh Distributed VCS, seperti Git, Mercurial, dan Subversion. Kita akan lebih banyak membahas **Distributed Version Control** kali ini, persisnya **Git**.

### Three States

![Three States](http://git-scm.com/figures/18333fig0106-tn.png)

Git memiliki 4 _state_ untuk aset/file proyek:

- **Untracked** berarti file tersebut baru ditambahkan atau baru dihapus (di _working directory_)
- **Modified** berarti ada perubahan pada filemu namun kamu belum melakukan _commit_ pada database (di _working directory_)
- **Staged** berarti kamu sudah menandai file yang diubah pada versimu untuk kemudian dilakukan _commit_ (di _staging area_)
- **Committed** berarti data perubahan file telah tersimpan aman pada database lokal (di _git directory_/_repository_)

### Git Interfaces

Kita bisa menggunakan Git dengan berbagai jenis antarmuka:

- CLI (Command Line Interface): UNIX shell, Git Bash, Powershell

  ![CLI](https://gitforwindows.org/img/gw1.png)

- GUI (Graphical User Interface): GitHub Desktop, Sourcetree, VS Code built-in

  ![GUI](https://desktop.github.com/images/github-desktop-screenshot-windows.png)

### Instalasi

Pada LBE ini, kita akan coba belajar Git Bash dan GitHub Desktop.

#### Git, Git Bash, dan Git Bash Terminal di VS Code

1. Download Git dan Git Bash di `http://git-scm.com/download`
2. Konfigurasi dan install (stepnya cukup banyak, bisa mengikuti tutorial `https://www.niagahoster.co.id/blog/git-tutorial-dasar/`)
3. Buka VS Code, tekan ``Ctrl + ` ``
4. Di dropdown jenis terminal (kanan atas), pilih Git Bash

#### GitHub Desktop

1. Download GitHub Desktop di `https://desktop.github.com`
2. Lakukan instalasi
3. Autentikasi akun GitHub-mu dengan memilih File > Options > Accounts > Sign in > Sign in using your browser

#### Git Pada Linux/Ubuntu/macOS

1. Buka terminal
2. Jalankan command berikut

        sudo apt install git

    Untuk mengecek apakah sudah terinstall Git, dapat membuka terminal (apa saja) atau command prompt dan jalankan command berikut

        git --version

### Konfigurasi

Sebelum menggunakan Git, perlu (tidak jika menggunakan Github Desktop) dilakukan konfigurasi terlebih dahulu dengan memasukkan username dan email yang digunakan pada Github.

1. Masukkan username dengan perintah berikut

        git config --global user.name "your_username"

2. Masukkan email dengan perintah berikut

        git config --global user.email "your_email_address@example.com"

3. Cek hasil konfigurasi dengan perintah berikut

        git config --global --list

### Perintah Dasar

#### **ls dan cd**

`ls` adalah sebuah perintah pada sistem operasi Linux (termasuk bash) yang digunakan untuk menampilkan folder/direktori dan file yang terdapat didalam suatu folder/direktori. Berikut adalah contoh penggunaan perintah `ls`:

![image](https://user-images.githubusercontent.com/86661387/194233893-49d299f2-b8e7-4442-996c-6a93ee358107.png)

Adapun `cd` (diketahui juga sebagai `chdir` atau change directory) adalah perintah yang digunakan untuk mengganti direktori yang sedang dikunjungi. Berikut adalah contoh penggunaan perintah `cd`:

![image](https://user-images.githubusercontent.com/86661387/194235633-2339674a-2534-4e3d-b961-dbc478d6db9b.png)

#### **git init**

Perintah `git init` adalah perintah yang digunakan untuk meng-inisialisasi **direktori yang sedang dikunjungi** menjadi sebuah Git Repository.

![image](https://user-images.githubusercontent.com/86661387/194236474-1be6346c-1504-4202-97f0-73f2f2144010.png)

#### **git remote**

`git remote` adalah perintah yang berkaitan dengan "remote" atau tautan dari repository tersebut. Jalankan command berikut untuk menambahkan "remote" pada suatu Git Repository lokal:

    git remote add origin <https repositori>

adapun untuk `<https repositori>` didapat dari

  ![image](https://user-images.githubusercontent.com/86661387/194238445-dd46d2a5-07e6-4808-8ce8-0561ea734c61.png)

Untuk melakukan pengecekan dari remote suatu repositori dapat menjalankan perintah berikut:

    git remote -v

#### **git clone**

`git clone` adalah suatu perintah untuk mengunduh suatu repository yang terdapat pada Github. Berikut adalah langkah-langkah untuk mengunduh suatu repositori:

1. Buka repositori yang akan diunduh pada browser (bebas browser apa).
2. Copy link berikut

    ![image](https://user-images.githubusercontent.com/86661387/194238445-dd46d2a5-07e6-4808-8ce8-0561ea734c61.png)

3. Jalankan perintah berikut:

        git clone <https repositori>

      ![image](https://user-images.githubusercontent.com/86661387/194246694-4efcef76-5219-414a-9b85-afc54619b1b2.png)

4. Direktori dari repository tersebut akan terbentuk di dalam direktori yang sedang dikunjungi, dalam kasus ini, akan terbentuk direktori dengan nama `microservice-app` di dalam direktori `repo`.

#### **branch**

Branch adalah sebuah fitur pada git untuk membuat beberapa copy dari repositori yang sama. Masing-masing branch dapat dilakukan perubahan tersendiri tanpa berefek terhadap branch lainnya, sehingga fitur ini cocok apabila terdapat perubahan yang akan diujicobakan terlebih dahulu atau repositori memiliki lebih dari satu kolaborator.

Buat branch baru dengan menjalankan perintah berikut:

    git checkout -b <nama branch>

Setiap branch yang telah dilakukan perubahan juga dapat digabungkan dengan branch lain untuk menyatukan perubahan dari masing-masing branch

    git checkout <default-branch>
    git merge <feature-branch>

Berikut adalah contoh dari penggabungan dua branch:

    git checkout main
    git merge Alpro-ITS

#### **git checkout/git switch**

`git checkout` atau `git switch` adalah perintah untuk berpindah dari satu branch menuju branch lainnya. Berikut adalah contoh dari penggunaan perintah tersebut:

    git checkout <nama branch>

atau

    git switch <nama branch>

Untuk mengecek branch yang sedang kita kunjungi, dapat menggunakan perintah berikut:

    git branch -v

#### **git add**

`git add` adalah perintah untuk menambahkan perubahan yang dilakukan untuk selanjutnya dilakukan proses "commit" ke dalam repositori. Secara umum perintah `git add` dapat dijalankan dengan format:

    git add <nama direktori/file yang diubah> 

Perintah dibawah akan secara otomatis menambah semua perubahan (termasuk sub-direktori yang ada di dalamnya)

    git add .

#### **git commit**

`git commit` adalah perintah untuk selanjutnya menyimpan hasil perubahan pada repositori lokal. Secara umum perintah `git commit` memiliki format seperti berikut:

    git commit -m "komentar"

Untuk komentar dapat diisi dengan "initial commit" (jika ini adalah commit pertama pada repositori) atau perubahan yang ditambahkan.

#### **git push**

`git push` adalah perintah untuk "mendorong" hasil penyimpanan repositori pada repositori online seperti Github. Berikut adalah format dan contoh perintahnya:

    git push <remote> <branch>

    git push origin main

#### **git pull**

`git pull` adalah perintah untuk "menarik" atau mengunduh perubahan baru pada repositori online. Yang membedakan dengan `git clone` adalah jika `git clone` digunakan untuk mengunduh seluruh repositori, `git pull` biasa digunakan untuk menyamakan atau menyinkronkan repositori lokal dengan repositori online. Berikut adalah format dan contoh perintahnya:

    git pull <remote> <branch>

    git pull origin main

### Meletakkan repositori lokal pada repositori online

1. Buat repositori online pada github
2. Pastikan bahwa repository lokal sudah di-inisialisasi dan telah ditambahkan remotenya
3. Jika pada repositori online terdapat file tambahan seperti `.gitignore` atau `README.md`, jalankan perintah berikut:

    git pull --allow-unrelated-histories origin main

4. Tambahkan branch `main` pada repositori lokal
5. Jalankan perintah berikut secara berurutan:

    git add .
    git commit -m "initial commit"
    git push origin main

## **Object-Oriented Programming Dengan Java**
