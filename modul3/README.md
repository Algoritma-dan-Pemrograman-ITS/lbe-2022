# Modul 3 LBE Alpro 2022

- [Inheritance](#inheritance)
	- [Method Overriding](#method-overriding)
- [Encapsulation](#encapsulation)
	- [Access Modifiers](#access-modifiers)
		- [Default](#default)
		- [Public](#public)
		- [Private](#private)
		- [Protected](#protected)
	- [Method Getter dan Setter](#method-getter-dan-setter)
- [Polymorphism](#polymorphism)
- [Abstraction](#abstraction)
	- [Abstract Class dan Abstract Method](#abstract-class-dan-abstract-method)
- [Referensi](#referensi)

	

# Inheritance

Bayangkan, kita ingin membuat 2 object *Monke* (monyet) dan *Apes* (kera). Mereka 2 jenis yang mirip, tetapi monyet itu memiliki ekor, sedangkan kera tidak. Keduanya bisa berjalan, makan pisang, dan memiliki rambut. Kita ingin membuat implementasi kodenya, kita dapat membuat seperti ini: 

```java
// Kode tanpa inheritance
class Monke {
	float weight;

	public void say(){
		System.out.println("hu hu ha ha");
	}

	public static void main() {
		Monke myMonke = new Monke();
		myMonke.say();
	}
}

// **********

class Apes {
	float weight;
	float tail_length;

	public void say() {
		System.out.println("hu hu ha ha");
	}

	public static void main() {
		Apes myApes = new Apes();
		myApes.say();
	}
}
```

Bayangkan, apabila kita juga ingin membuat class Gorilla, Simpanse, dan lainnya? Maka dari itu, mari kita mengenal konsep **inheritance.**

- Inheritance atau pewarisan adalah kemampuan untuk menurunkan sebuah class ke class lain
- Dalam artian, kita bisa membuat class Parent dan class Child
- Class Child hanya bisa punya 1 parent, tetapi class Parent bisa punya banyak class Child
- Saat sebuah class diturunkan, maka semua field dan method yang ada di class Parent secara otomatis akan dimiliki oleh class Child
- Untuk melakukan pewarisan, di class Child kita harus menggunakan keyword **extends** lalu diikuti dengan class parent-nya

Berikut contoh kode menggunakan inheritance

```java
class Primate {
	float weight;
	public void say() {
		System.out.println("hu hu ha ha");
	}
}

// *******

class Monke extends Primate {
	float tail_length;
	public static void main() {
		Monke myMonke = new Monke();
		myMonke.say(); // memanggil method dari Primate (parent)
	}
}

// ********

class Apes extends Primate {
	public static void main() {
		Apes myApes = new Apes();
		myMonke.say();	// memanggil method dari Primate (parent)
	}
}
```

## Method Overriding

- Method overriding adalah kemampuan mendeklarasikan ulang method di child class, yang sudah ada di parent class
- Saat kita melakukan proses overriding tersebut, secara otomatis ketika kita membuat object dari class child, method yang di class parent tidak bisa diakses lagi

Contoh : 

```java
class Apes extends Primate {
	@Overriding
	public void say() {
		System.out.println("hihi haha");
	}

	public static void() {
		Apes myApes = new Apes();
		myApes.say();	// memanggil method dari Primate (parent)
	}
}
```


# Encapsulation

Pada dasarnya, enkapsulasi adalah **membuat batasan akses** untuk suatu **objek**, seperti class, variable, attribute, dan method.

Analoginya, kita pun sebagai manusia seringkali membuat batasan akses terhadap informasi. Ada hal yang kita sampaikan secara terbuka terhadap publik. Ada yang kita jaga dan sampaikan ke keluarga terdekat saja. Ada juga hal-hal privasi yang kita simpan untuk diri sendiri. 

Enkapsulasi biasanya diimplementasikan dengan menggunakan access modifiers.

## Access Modifiers

<img src="https://user-images.githubusercontent.com/70790033/197654334-9753bee6-fee8-449f-9252-fe5c0fe71293.png" width="600">

Sesuai namanya, access modifiers **memodifikasi jangkauan akses** dari suatu objek. Ada **4 tipe** access modifiers yang tersedia dalam Java:

### **Default**

- Tidak memerlukan keyword.
- Objek dengan access modifier default hanya dapat **diakses** dari **package** yang **sama**.
-----------------
**Contoh:**
```java
package mammals;

// Class Monke mempunyai akses modifier default
class Monke {
	void eatBanana()
	{
		System.out.println("Banana Yum Yum!");
	}
	
}
```
Di sini kita mencoba untuk mengakses fungsi eatBanana() milik class Monke melalui class Crocs yang berada di package lain.
```java
package reptiles;
import mammals.*;

// Class Crocs juga mempunyai akses modifier default
class Crocs {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.eatBanana();
    }
}
```

**Output**

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	The method eatBanana() from the type Monke is not visible

	at lbe_encapsulation/reptiles.Crocs.main(Crocs.java:9)
```

Terlihat bahwa tidak bisa.

-----------------
Sekarang kita coba lagi mengakses fungsi eatBanana() melalui class lain yang masih satu package dengan Monke, yakni class Apes.

```java
package mammals;

// Class Apes juga mempunyai akses modifier default
class Apes {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.eatBanana();
    }
}
```

**Output**

```java
Banana Yum Yum!
```

-----------------

### Public

- Menggunakan keyword public.
- Jangkauan akses paling luas, bisa **diakses** oleh **siapa saja** dan dimana saja dalam program.
- Kita bisa melakukan **read** dan **write** terhadap variabel public **dari luar**. Read berarti kita membaca nilai variabel, sedangkan write berarti kita menulis suatu nilai ke dalam variabel tersebut.
-----------------
**Contoh:**

Kali ini kita akan membuat class Monke menjadi public. Lalu, kita menambahkan method public bernama breatheAir(). 

```java
package mammals;

public class Monke {
	void eatBanana()
	{
		System.out.println("Banana Yum Yum!");
	}
	
	public void breatheAir()
	{
		System.out.println("Breathe Air!");
	}
}
```
Mari kita coba akses dari class Crocs.
```java
package reptiles;
import mammals.*;

class Crocs {
    public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.breatheAir();
    }
}
```

**Output**

```java
Breathe Air!
```

Terlihat bahwa method breatheAir() dapat diakses oleh class Croc yang berada di package lain. 

--------------

Package lain saja bisa, apalagi dari package yang sama

```java
package mammals;

class Apes {
    public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.breatheAir();
    }
}
```

**Output**

```java
Breathe Air!
```

--------------

### Private

- Menggunakan keyword private.
- **Hanya** bisa **diakses** di dalam **class tempat deklarasi** objek.
- Tidak bisa diakses dari class lain atau package lain.
-----------------
**Contoh:**
Kita menambahkan attribute private bernama traumaticMemories dan method private bernama reliveTrauma() ke dalam class Monke.

```java
package mammals;

public class Monke {
	
	public String traumaticMemories;
	
	public Monke() {
		traumaticMemories = "Hunted by hoomans...";
	}

	private void reliveTrauma()
  	{
        	System.out.println(this.traumaticMemories);
 	}
	
	void eatBanana()
	{
		System.out.println("Banana Yum Yum!");
	}
	
	public void breatheAir()
	{
		System.out.println("Breathe Air!");
	}
	
}
```

Kemudian, kita mencoba mengakses method reliveTrauma() dari class Apes. 

```java
package mammals;

class Apes {
    public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.reliveTrauma();
    }
}
```

**Output:**

```java
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	The method reliveTrauma() from the type Monke is not visible

	at lbe_encapsulation/mammals.Apes.main(Apes.java:7)
```

Terlihat bahwa Apes tidak bisa mengakses trauma milik Monke. Method dan class private tidak bisa diakses oleh class dalam package yang sama.

-----------------

Package yang sama saja tidak bisa, apalagi yang berbeda. 

```java
package reptiles;
import mammals.*;

class Crocs {
    public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.reliveTrauma();
    }
}
```

**Output:**

```
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	The method reliveTrauma() from the type Monke is not visible

	at lbe_encapsulation/reptiles.Crocs.main(Crocs.java:8)
```

-----------------

### Protected

- Menggunakan keyword protected.
- Dapat **diakses** dari **package** yang **sama**.
- Bisa **diakses** dari **package lain** menggunakan **subclass** atau **child class**. (Inheritance)
-----------------
**Contoh:**
Kita menambahkan attribute dan method protected bernama bananaStash dan checkBananaStash

```java
package mammals;

public class Monke {
	
	public String traumaticMemories;
	protected int bananaStash;
	
	public Monke() {
		traumaticMemories = "Hunted by hoomans...";
		bananaStash = 100;
	}
	
	protected void checkBananaStash()
	{
		System.out.printf("Monke has %d banana", this.bananaStash);
	}

	private void reliveTrauma()
    {
        System.out.println(this.traumaticMemories);
    }
	
	void eatBanana()
	{
		System.out.println("Banana Yum Yum!");
		this.bananaStash--;
	}
	
	public void breatheAir()
	{
		System.out.println("Breathe Air!");
	}
	
}
```
Kemudian, kita mencoba mengakses method checkBananaStash() dari class Apes. 

```java
package mammals;

class Apes {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.checkBananaStash();
    }
}
```

**Output:**
```
Monke has 100 banana
```
Terlihat bahwa kita dapat mengakses method checkBananaStash() dari class di yang package sama. 

-----------------
Ditambahkan class baru bernama Baboon yang terletak di package mammals2. Baboon merupakan subclass dari class Monke. Kita coba lagi mengakses method checkBananaStash() dari class tersebut. 

```java
package mammals2;
import mammals.*;

public class Baboon extends Monke {
	public static void main(String args[])
    {
        Baboon obj = new Baboon();
        obj.checkBananaStash();
    }

}
```

**Output:**
```
Monke has 100 banana
```
Terlihat bahwa kita dapat mengakses method checkBananaStash() dari class yang berada di package lain. Dengan syarat class tersebut merupakan subclass. 

-----------------
Misal kita coba mengakses method checkBananaStash() dari class Crocs.

```java
package reptiles;
import mammals.*;

class Crocs {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.checkBananaStash();
    }
}
```

**Output:**
```java
Exception in thread "main" java.lang.Error: Unresolved compilation problem: 
	The method checkBananaStash() from the type Monke is not visible

	at lbe_encapsulation/reptiles.Crocs.main(Crocs.java:8)
```

Terlihat bahwa method protected tidak dapat diakses oleh class dari package lain yang bukan merupakan subclass.

-----------------

## Method Getter dan Setter

Bagaimana jika kita perlu mengakses private attribute dari luar? Kita bisa menggunakan method getter dan setter. Method **getter** digunakan untuk **mengakses nilai** suatu attribute, sedangkan method **setter** digunakan untuk **memasukkan nilai** ke dalam suatu attribute. 

Untuk syntax penamaan, biasanya dimulai dengan kata get atau set lalu diikuti nama attribute dengan huruf pertama kapital. Misalnya getMoney dan setMoney.

Dengan method getter dan setter kita bisa membuat attribute class jadi **read-only** atau **write-only**. Dia akan read-only jika kita hanya membuat getter method, dan dia akan write-only jika kita hanya membuat setter method. 

-----------------
**Contoh**

Di sini kita sudah menambahkan fungsi getter dan setter untuk attribute traumaticMemories dan bananaStash.

```java
package mammals;

public class Monke {

	public String traumaticMemories;
	protected int bananaStash;
	
	public String getTraumaticMemories() {
		return traumaticMemories;
	}

	public void setTraumaticMemories(String traumaticMemories) {
		this.traumaticMemories = traumaticMemories;
	}

	public int getBananaStash() {
		return bananaStash;
	}

	public void setBananaStash(int bananaStash) {
		this.bananaStash = bananaStash;
	}

	public Monke() {
		traumaticMemories = "Hunted by hoomans...";
		bananaStash = 100;
	}
	
}
```
Kemudian kita coba mengakses method getTraumaticMemories() dari class Crocs. 

```java
package reptiles;
import mammals.*;

class Crocs {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        System.out.printf(obj.getTraumaticMemories());
    }
}
```

**Output:**
```java
Hunted by hoomans...
```
Terlihat bahwa sekarang Crocs dapat mengakses isi attribute traumaticMemories melalui method getTraumaticMemories().

---------------
Bahkan, Crocs bisa juga mengganti isi attribute traumaticMemories melalui method setTraumaticMemories.

```java
package reptiles;
import mammals.*;

class Crocs {
	public static void main(String args[])
    {
        Monke obj = new Monke();
        obj.setTraumaticMemories("Family eaten by crocodiles...");
        System.out.printf(obj.getTraumaticMemories());
    }
}
```

**Output:**
```java
Family eaten by crocodiles...
```

---------------

# Polymorphism
- Polymorphism berasal dari bahasa Yunani yang berarti "banyak bentuk"
- Dalam OOP, Polymorphism ialah kemampuan sebuah object berubah bentuk menjadi bentuk lain
- Konsep ini berkaitan erat dengan Inheritance
- Misal kita mempunyai object x yang extend ke object y (berarti object x ialah child dan object y ialah parent). Lalu kita mendeklarasikan instance object dari object y (yg parent), maka kita bisa nge create instance object x, dan menambahkan method yang berbeda tiap class childnya.

Contoh penerapan Polymorphism:

Kita mempunyai parent class sebagai berikut:
```java
	class Primate {
	void say (){
		System.out.println("Primataaaaa...");
	}
}
```
Didalam parent classnya kita bisa lihat bahwa ada method `say()` dengan mengoutputkan "Primataaaa..."

Lalu kita juga mempunyai child class dengan menggunakan inherit ke parent classnya sebagai berikut:

```java
class Monke extends Primate {
	void say () {
		System.out.println("UU AAA UU AA");
	}
}

class Apes extends Primate{
	void say() {
		System.out.println("HAHA HIHI HAHA HIHI");
	}
}
```
Kita bisa lihat bahwa method yang akan di outputkan dari kedua child class dan mother class itu berbeda. Lalu kita akan mengeksekusi output method dari tiap kelas tersebut di dalam fungsi main sebagai berikut:

```java
public class main {
	public static void main(String args[]){
		Primate blublu;
		blublu = new Primate();
		blublu.say();

		blublu = new Monke();
		blublu.say();

		blublu = new Apes();
		blublu.say();
	}
}
```

Di dalam fungsi main kita sudah memanggil `blublu` sebagai mother class, dan juga sebagai child class. Lalu kita panggil method `say()` dari tiap-tiap class dan hasil outputnya akan menjadi:

```
Primataaaaa... 			//mother class
UU AAA UU AA 			//child class (Monke)
HAHA HIHI HAHA HIHI 	//child class (Apes)
```

# Abstraction

## Abstract Class dan Abstract Method
- Kita dapat menjadikan sebuah class sebagai abstract class
- `Abstract class` adalah class terbatas yang tidak dapat digunakan untuk membuat objek (untuk mengaksesnya, harus inherit dari kelas lain).
- `Method Class` hanya dapat digunakan dalam kelas abstrak, dan tidak memiliki body. body disediakan oleh subclass (inherit).
- Untuk membuat sebuah class menjadi abstract, kita dapat menggunakan keyword 'abstract' sebelum keyword 'class'

Contoh penerapan Abstract class:

Setelah kita sudah mengetahui polymorphism, untuk menjalankan suatu absract class kita perlu menerapkan polymorphism juga untuk lebih mudah memahami aa itu abstract class.

Kita mempunyai parent class sebagai berikut:
```java
abstract class Primate { // abstract class
	abstract void eat(); // abstract method
	void say (){
		System.out.println("Primataaaaa...");
	}
}
```
Berbeda bukan? inilah cara menerapkan `abstract class` kedalam class. Kita bisa lihat ada method eat dengan abstract class seperti contoh di atas. Lalu kita mempunyai child class sebagai berikut:

```java
class Monke extends Primate {
	void say () {
		System.out.println("UU AAA UU AA");
	}
	void eat() {
		System.out.println("Banana is yummy");
	}
}

class Apes extends Primate{
	void say() {
		System.out.println("HAHA HIHI HAHA HIHI");
	}
	void eat() {
		System.out.println("Apple is Yummy");
	}
}
```

Dengan menambahkan method eat yang berasal dari class abstract parent class.

Jika kita menggunakan fungsi main seperti polymorphism (Mendefinisikan parent child) maka akan memunculkan output `error`.

```java
public class main {
	public static void main(String args[]){
		Primate blublu;
		blublu = new Primate() 	//error
		blublu = new Monke();
		blublu.say();
		blublu.eat();

		blublu = new Apes();
		blublu.say();
		blublu.eat();
	}
}
```

```
java: Primate.Primate is abstract; cannot be instantiated
```

Maka kita hanya bisa men-declare seperti berikut:
```java
public class main {
	public static void main(String args[]){
		Primate blublu;

		blublu = new Monke();
		blublu.say();
		blublu.eat();

		blublu = new Apes();
		blublu.say();
		blublu.eat();
	}
}
```
Dengan output:
```
UU AAA UU AA
Banana is yummy
HAHA HIHI HAHA HIHI
Apple is Yummy
```


# Referensi: 
- [Video Youtube "Tutorial JAVA OOP BAHASA INDONESIA" Channel Programmer Zaman Now](https://youtu.be/f3ZhNnvtV-w)
- [Access Modifiers in Java - GeeksforGeeks](https://www.geeksforgeeks.org/access-modifiers-java/)
- [Access modifiers in java - Javatpoint](https://www.javatpoint.com/access-modifiers)
- [The Access Modifiers in Java | What are access modifiers?-Great Learning (mygreatlearning.com)](https://www.mygreatlearning.com/blog/the-access-modifiers-in-java/#:~:text=Access%20modifiers%20are%20keywords%20that,protected%2C%20default%2C%20and%20private.)
- [Java Access Modifiers (With Examples) (programiz.com)](https://www.programiz.com/java-programming/access-modifiers)
- [Java Encapsulation and Getters and Setters (w3schools.com)](https://www.w3schools.com/java/java_encapsulation.asp)
- [(53) Belajar Java [OOP] - 10 - Getter dan Setter (Encapsulasi) - YouTube](https://www.youtube.com/watch?v=zwDMHJzTUzs&list=PLZS-MHyEIRo6V4_vk1s1NcM2HoW5KFG7i&index=12)
