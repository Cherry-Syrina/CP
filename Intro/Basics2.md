# Basic I/O & Operators

## Basic I/O

I/O = **Input + Output**

- **Input** → User se data lena
- **Output** → Screen par data dikhana

---

# Output

Java me output print karne ke liye:

```java
System.out.print("Hello");
System.out.println("Hello");
System.out.printf("Hello");
```

## Difference

### print()

Cursor next line me nahi jata.

```java
System.out.print("Hello");
System.out.print("World");
```

Output

```
HelloWorld
```

---

### println()

Print karne ke baad next line me chala jata hai.

```java
System.out.println("Hello");
System.out.println("World");
```

Output

```
Hello
World
```

---

### printf()

Formatted output ke liye.

```java
int age = 20;

System.out.printf("Age = %d", age);
```

Output

```
Age = 20
```

---

# Input

Java me input lene ke liye **Scanner Class** use hoti hai.

## Scanner Import

```java
import java.util.Scanner;
```

## Scanner Object

```java
Scanner sc = new Scanner(System.in);
```

---

# Input Methods

| Method | Input |
|---------|-------|
| nextInt() | Integer |
| nextDouble() | Decimal |
| nextFloat() | Float |
| nextLong() | Long |
| next() | Single Word |
| nextLine() | Complete Line |
| nextBoolean() | true/false |

---

# Example

```java
import java.util.Scanner;

class Demo{

    public static void main(String args[]){

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Name : ");

        String name = sc.nextLine();

        System.out.print("Enter Age : ");

        int age = sc.nextInt();

        System.out.println(name);
        System.out.println(age);

    }

}
```

---

# Operators

Operator = Jo operations perform karta hai.

Example

```java
a + b
```

Yaha '+' ek operator hai.

---

# Types of Operators

- Arithmetic
- Assignment
- Relational
- Logical
- Unary
- Increment/Decrement
- Ternary
- Bitwise
- Shift

---

# 1. Arithmetic Operators

| Operator | Meaning |
|----------|---------|
| + | Addition |
| - | Subtraction |
| * | Multiplication |
| / | Division |
| % | Modulus |

Example

```java
int a = 10;
int b = 3;

System.out.println(a+b);
System.out.println(a-b);
System.out.println(a*b);
System.out.println(a/b);
System.out.println(a%b);
```

Output

```
13
7
30
3
1
```

---

# 2. Assignment Operators

| Operator | Example |
|----------|---------|
| = | a = 10 |
| += | a += 5 |
| -= | a -= 5 |
| *= | a *= 5 |
| /= | a /= 5 |
| %= | a %= 5 |

Example

```java
int a = 10;

a += 5;

System.out.println(a);
```

Output

```
15
```

---

# 3. Relational Operators

Comparison ke liye use hote hain.

Result hamesha **true ya false** hota hai.

| Operator | Meaning |
|----------|---------|
| == | Equal |
| != | Not Equal |
| > | Greater Than |
| < | Less Than |
| >= | Greater Than Equal |
| <= | Less Than Equal |

Example

```java
int a = 10;

System.out.println(a > 5);
```

Output

```
true
```

---

# 4. Logical Operators

Boolean values par kaam karte hain.

| Operator | Meaning |
|----------|---------|
| && | AND |
| \|\| | OR |
| ! | NOT |

Example

```java
true && false
```

Output

```
false
```

Truth Table

| A | B | A&&B | A\|\|B |
|---|---|------|--------|
| T | T | T | T |
| T | F | F | T |
| F | T | F | T |
| F | F | F | F |

---

# 5. Unary Operators

Sirf ek operand par kaam karte hain.

| Operator | Meaning |
|----------|---------|
| + | Positive |
| - | Negative |
| ++ | Increment |
| -- | Decrement |
| ! | Logical NOT |

---

# Increment

## Pre Increment

```java
int a = 5;

System.out.println(++a);
```

Output

```
6
```

---

## Post Increment

```java
int a = 5;

System.out.println(a++);
System.out.println(a);
```

Output

```
5
6
```

---

# Decrement

```java
--a
a--
```

Same logic as Increment.

---

# 6. Ternary Operator

Shortcut of if-else.

Syntax

```java
condition ? true : false;
```

Example

```java
int a = 10;

String ans = (a > 5) ? "Yes" : "No";

System.out.println(ans);
```

Output

```
Yes
```

---

# 7. Bitwise Operators

Binary bits par kaam karte hain.

| Operator | Meaning |
|----------|---------|
| & | Bitwise AND |
| \| | Bitwise OR |
| ^ | XOR |
| ~ | NOT |

Mostly interviews aur advanced coding me use hote hain.

---

# 8. Shift Operators

| Operator | Meaning |
|----------|---------|
| << | Left Shift |
| >> | Right Shift |
| >>> | Unsigned Right Shift |

Example

```java
5 << 1
```

Output

```
10
```

---

# Operator Precedence

Highest → Lowest

```
()
Unary
* / %
+ -
< > <= >=
== !=
&&
||
?:
=
```

---

# Interview Questions

### Difference between print() and println()

- print() → Same line
- println() → Next line

---

### Difference between next() and nextLine()

next()

```
Only One Word
```

nextLine()

```
Complete Sentence
```

---

### Difference between == and =

```
=  → Assignment

== → Comparison
```

---

### Difference between ++a and a++

```
++a → Pehle Increment

a++ → Baad me Increment
```

---

# Exam Important ⭐

- Scanner Class
- Input Methods
- print vs println vs printf
- Arithmetic Operators
- Relational Operators
- Logical Operators
- Unary Operators
- Increment vs Decrement
- Ternary Operator
- Operator Precedence

---

# Quick Revision 🚀

✅ Input → Scanner

✅ Output → print(), println(), printf()

✅ next() = Single Word

✅ nextLine() = Complete Line

✅ == = Comparison

✅ = = Assignment

✅ ++a = Pre Increment

✅ a++ = Post Increment

✅ ?: = Ternary Operator

✅ && = AND

✅ || = OR

✅ ! = NOT
