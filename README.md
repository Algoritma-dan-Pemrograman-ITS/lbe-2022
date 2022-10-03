# Modul LBE Alpro 2022

- [Mengenal Lab Alpro](#mengenal-lab-alpro)

- [Version Control System (VCS) Dengan Git](#version-control-system-vcs-dengan-git)
    
    + [VCS Secara Singkat](#vcs-secara-singkat)

    + [Three States](#three-states)
    
    + [Instalasi](#instalasi)

    + [Perintah Dasar](#perintah-dasar)

    + [Konfigurasi](#konfigurasi)

- [Object-Oriented Programming Dengan Java](#object-oriented-programming-dengan-java)

----

## **Mengenal Lab Alpro**

## **Version Control System (VCS) Dengan Git**

> **Disclaimer**: belajar version control system lebih enak sambil dicobain. Jadi teori di sini secukupnya aja, tapi lebih banyak habiskan waktu untuk coba-coba ya 🚀

### VCS Secara Singkat
Dalam mengerjakan sebuah proyek, seringkali kita perlu berkolaborasi. Dibutuhkan sistem pengerjaan yang terstruktur agar kolaborasi memiliki akuntabilitas dan tidak mengakibatkan kesalahan atau _bug_ yang mengganggu jalannya proyek. Kita bisa menggunakan _version control system_ (VCS) untuk manajemen aset-aset proyek seperti _source code_.

Berikut ini fungsi-fungsi VCS secara lebih lengkap:
* **Kolaborasi**\
VCS memungkinkan banyak orang/_device_ mengerjakan satu proyek secara bersamaan. Tiap orang/_device_ punya _copy_ aset-aset proyek sendiri. Saat integrasi dengan _master copy_ diperlukan, barulah dia melakukan **_staging_** dan **_commit_** pada file-file yang dikerjakan agar _master copy_ juga memiliki versi file yang sama dengannya.
* **Integrasi**\
Pengerjaan yang dilakukan masing-masin orang/_device_ tidak saling memengaruhi sampai integrasi/**_merging_** dilakukan. Jika ditemukan kesalahan saat integrasi, penentuan versi yang benar dikembalikan kepada orang yang melakukan integrasi.
* **Akuntabilitas**\
VCS menyimpan riwayat pengubahan pada proyek, sehingga jika terdapat kesalahan fatal, orang yang memiliki akses ke proyek bisa memilih untuk kembali atau **_revert_** ke versi sebelumnya yang belum terdapat kesalahan. Hal ini mudah karena setiap versi pengubahan yang dilakukan dapat diidentifikasi kapan, siapa yang mengubah, dan bagian apa yang diubah.

Secara umum, terdapat dua jenis _version control_ yang dibedakan dari cara _versioning_-nya, yaitu:
* **Centralized Version Control**\
We commit - They update
* **Distributed Version Control**\
We commit - We push - They pull - They update

Terdapat beberapa contoh Distributed VCS, seperti Git, Mercurial, dan Subversion. Kita akan lebih banyak membahas **Distributed Version Control** kali ini, persisnya **Git**.

### Three States
![Three States](http://git-scm.com/figures/18333fig0106-tn.png)

Git memiliki 4 _state_ untuk aset/file proyek:
* **Untracked** berarti file tersebut baru ditambahkan atau baru dihapus (di _working directory_)
* **Modified** berarti ada perubahan pada filemu namun kamu belum melakukan _commit_ pada database (di _working directory_)
* **Staged** berarti kamu sudah menandai file yang diubah pada versimu untuk kemudian dilakukan _commit_ (di _staging area_)
* **Committed** berarti data perubahan file telah tersimpan aman pada database lokal (di _git directory_/_repository_)

### Git Interfaces
Kita bisa menggunakan Git dengan berbagai jenis antarmuka:
* CLI (Command Line Interface): UNIX shell, Git Bash, Powershell\
<img src="https://gitforwindows.org/img/gw1.png" width="500" />\
* GUI (Graphical User Interface): GitHub Desktop, Sourcetree, VS Code built-in\
<img src="https://desktop.github.com/images/github-desktop-screenshot-windows.png" width="600" />\

### Instalasi

Pada LBE ini, kita akan coba belajar Git Bash dan GitHub Desktop.

#### Git, Git Bash, dan Git Bash Terminal di VS Code
1. Download Git dan Git Bash di http://git-scm.com/download
2. Konfigurasi dan install (stepnya cukup banyak, bisa mengikuti tutorial https://www.niagahoster.co.id/blog/git-tutorial-dasar/)
3. Buka VS Code, tekan ``Ctrl + ` ``
4. Di dropdown jenis terminal (kanan atas), pilih Git Bash

#### GitHub Desktop
1. Download GitHub Desktop di https://desktop.github.com/
2. Lakukan instalasi
3. Autentikasi akun GitHub-mu dengan memilih File > Options > Accounts > Sign in > Sign in using your browser

#### Git Pada Linux/Ubuntu/macOS
1. Buka terminal
2. Jalankan command berikut

        sudo apt install git

Untuk mengecek apakah sudah terinstall Git, dapat membuka terminal (apa saja) atau command prompt dan jalankan command berikut

        git --version

### Konfigurasi

Sebelum menggunakan Git, perlu 

### Perintah Dasar

#### ls dan cd

#### git init

#### git clone

#### git add

#### git commit

#### git push

#### git pull

#### git branch

#### git checkout/git switch

#### git remote

## **Object-Oriented Programming Dengan Java**
