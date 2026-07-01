# Java Introduction ☕

## Java Kya Hai?

Java ek **High-Level, Object-Oriented (OOP)** aur **Platform Independent** programming language hai.

Developed by **Sun Microsystems** (ab Oracle).

> **WORA = Write Once, Run Anywhere**

Matlab ek baar code likho aur JVM ki help se kisi bhi Operating System (Windows/Linux/Mac) par chala sakte ho.

---

# Java Compilation Process

```text
Java Code (.java)
      │
      ▼
Compiler (javac)
      │
      ▼
Bytecode (.class)
      │
      ▼
JVM
      │
      ▼
Machine Code
      │
      ▼
Output
```

> **Exam Point:** Java Compiler **Machine Code** nahi banata, **Bytecode** banata hai.

---

# Java Features

- ✅ Platform Independent
- ✅ Object-Oriented
- ✅ Secure
- ✅ Robust (Error Handling + Garbage Collection)
- ✅ Portable
- ✅ Multithreading Support
- ✅ High Performance (JIT Compiler)
- ✅ Distributed
- ✅ Dynamic

---

# Java Program Structure

```java
public class Demo {

    public static void main(String[] args) {

        System.out.println("Hello World");

    }

}
```

### Main Method

```java
public static void main(String[] args)
```

| Keyword | Meaning |
|----------|---------|
| public | Sab jagah se access ho sakta hai |
| static | Object banane ki need nahi |
| void | Kuch return nahi karega |
| main | Program ka Entry Point |
| String[] args | Command Line Arguments |

---

# JDK vs JRE vs JVM

```text
JDK
│
├── JRE
│      │
│      └── JVM
```

## JDK (Java Development Kit)

- Java Program Develop karne ke liye
- Contains Compiler + JRE

## JRE (Java Runtime Environment)

- Java Program Run karne ke liye
- Contains JVM + Required Libraries

## JVM (Java Virtual Machine)

- Bytecode Execute karta hai
- Memory Manage karta hai
- Garbage Collection karta hai

### Easy Trick 🧠

| Component | Yaad Rakho |
|------------|------------|
| JDK | Develop |
| JRE | Run |
| JVM | Execute |

---

# Data Types

## Primitive Data Types (8)

| Data Type | Size |
|-----------|------|
| byte | 1 Byte |
| short | 2 Bytes |
| int | 4 Bytes |
| long | 8 Bytes |
| float | 4 Bytes |
| double | 8 Bytes |
| char | 2 Bytes |
| boolean | true/false |

Example

```java
int age = 20;
double cgpa = 8.5;
char grade = 'A';
boolean pass = true;
```

---

## Non-Primitive Data Types

- String
- Array
- Class
- Interface
- Object

Example

```java
String name = "Sushma";
```

---

# Variable

Variable ek **named memory location** hoti hai jisme data store hota hai.

```java
int marks = 95;
```

---

# Identifiers

### ✅ Valid

```text
age
studentName
_marks
abc123
```

### ❌ Invalid

```text
123abc
class
int
```

---

# Java Keywords

Examples

```text
class
public
static
void
int
double
if
else
while
return
```

> Keywords ko variable name nahi bana sakte.

---

# Comments

### Single Line

```java
// This is a comment
```

### Multi Line

```java
/*
This is
Multi Line Comment
*/
```

---

# Escape Sequences

| Escape | Meaning |
|---------|---------|
| \n | New Line |
| \t | Tab Space |
| \" | Double Quote |
| \\ | Backslash |

---

# Sample Program

```java
public class Student {

    public static void main(String[] args) {

        String name = "Sushma";
        int age = 21;

        System.out.println(name);
        System.out.println(age);
    }

}
```

---

# Interview Questions

### Q1. Java Platform Independent kyu hai?

➡️ Kyunki Java Compiler **Bytecode** banata hai aur JVM us Bytecode ko kisi bhi Operating System par execute kar deta hai.

---

### Q2. JVM ka kaam kya hai?

- Bytecode Execute karna
- Memory Management
- Garbage Collection

---

### Q3. Bytecode kya hota hai?

Java Compiler (`javac`) dwara generate kiya gaya intermediate code jo JVM execute karta hai.

---

# Exam Important ⭐

- Java Features
- Java Architecture
- JDK vs JRE vs JVM
- Primitive vs Non-Primitive Data Types
- Java Program Structure
- main() Method
- Bytecode
- Platform Independence

---

# Quick Revision 🚀

✅ Java = High-Level + OOP + Platform Independent

✅ WORA = Write Once, Run Anywhere

✅ Java Code → Compiler → Bytecode → JVM → Output

✅ JDK = Develop

✅ JRE = Run

✅ JVM = Execute

✅ Primitive Data Types = 8

✅ `main()` = Entry Point of Program
