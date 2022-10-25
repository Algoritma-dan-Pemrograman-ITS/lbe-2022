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

![image](https://user-images.githubusercontent.com/70790033/197672512-b3ab5cd6-9daa-48e6-91cf-a47d33259d4c.png)
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

![image](https://user-images.githubusercontent.com/70790033/197671281-2714c343-894e-49b8-bf3e-d6c6de3185a7.png)

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

![image](https://user-images.githubusercontent.com/70790033/197673115-729627be-6517-4ff0-be34-aa322bfd6d8c.png)

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

![image](https://user-images.githubusercontent.com/70790033/197674436-31f9656c-4016-4f50-86df-32f274ab3d5f.png)

--------------

### Private

- Menggunakan keyword private.
- **Hanya** bisa **diakses** di dalam **class tempat deklarasi** objek.
- Tidak bisa diakses dari class lain atau package lain.
-----------------
**Contoh:**
Kita menambahkan variable private bernama traumaticMemories dan method private bernama reliveTrauma() ke dalam class Monke.

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

![image](https://user-images.githubusercontent.com/70790033/197681403-18f9bb79-ffa5-47ca-83ec-232b0e1ca1b2.png)

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

![image](https://user-images.githubusercontent.com/70790033/197682312-bbcbc19e-48c1-45d4-a100-1a29c14af1cc.png)

-----------------

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
