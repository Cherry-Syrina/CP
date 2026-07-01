# Simple Sieve (Sieve of Eratosthenes)

## Definition

Simple Sieve ek efficient algorithm hai jo **1 se N tak saare Prime Numbers** find karta hai.

> **Time Complexity:** O(N log log N)

---

# Prime Number

Prime Number = Jiske sirf **2 factors** hote hain.

Example

```
2 3 5 7 11 13 17 19...
```

Non Prime

```
4 6 8 9 10...
```

---

# Idea

Har number ke liye alag se prime check nahi karte.

Instead,

- Sab numbers ko initially **Prime (true)** maan lo.
- Jo numbers kisi prime ke multiples hain unhe **false** mark kar do.
- End me jo **true** bach jaye wahi Prime Numbers hain.

---

# Algorithm

### Step 1

Boolean array banao.

```java
boolean[] prime = new boolean[n + 1];
```

---

### Step 2

Sabko true mark karo.

```java
Arrays.fill(prime, true);
```

---

### Step 3

0 aur 1 prime nahi hote.

```java
prime[0] = false;
prime[1] = false;
```

---

### Step 4

2 se √N tak loop chalao.

```java
for(int i = 2; i * i <= n; i++)
```

---

### Step 5

Agar current number prime hai

```java
if(prime[i])
```

to uske multiples ko false kar do.

```java
for(int j = i * i; j <= n; j += i)

    prime[j] = false;
```

---

### Step 6

Jo true bach gaye wahi Prime Numbers hain.

```java
for(int i = 2; i <= n; i++){

    if(prime[i])

        System.out.print(i + " ");
}
```

---

# Dry Run (N = 10)

Initially

```
2 3 4 5 6 7 8 9 10

T T T T T T T T T
```

i = 2

```
4 6 8 10

↓

False
```

i = 3

```
9

↓

False
```

Remaining

```
2 3 5 7
```

---

# Why start from i*i ?

Example

For i = 5

```
5 × 2 = 10

5 × 3 = 15

5 × 4 = 20
```

Ye sab pehle hi mark ho chuke hote hain.

Isliye directly

```
5 × 5 = 25
```

se start karte hain.

```java
j = i * i;
```

---

# Why loop till √N ?

Har Composite Number ka ek factor **√N se chhota ya equal** hota hai.

Isliye

```java
i * i <= n
```

tak loop chalana enough hai.

---

# Code

```java
public static void sieve(int n) {

    boolean[] prime = new boolean[n + 1];

    Arrays.fill(prime, true);

    prime[0] = false;
    prime[1] = false;

    for (int i = 2; i * i <= n; i++) {

        if (prime[i]) {

            for (int j = i * i; j <= n; j += i) {
                prime[j] = false;
            }
        }
    }

    for (int i = 2; i <= n; i++) {

        if (prime[i]) {
            System.out.print(i + " ");
        }
    }
}
```

---

# Dry Run of Code

```java
i = 2
```

```
Mark

4
6
8
10
12...
```

↓

```java
i = 3
```

```
Mark

9
12
15
18...
```

↓

```java
i = 4
```

Already false

Skip

↓

```java
i = 5
```

```
Mark

25
30
35...
```

---

# Complexity

| Complexity | Value |
|------------|-------|
| Time | O(N log log N) |
| Space | O(N) |

---

# Important Observations

- No separate `isPrime()` function is used.
- `prime[i] == true` means **i is Prime**.
- `prime[i] == false` means **i is Composite**.
- Every composite number is marked only once for each relevant prime.

---

# Interview Questions

### Q1. Why use Boolean Array?

Prime status store karne ke liye.

---

### Q2. Why start from i*i?

Smaller multiples already mark ho chuke hote hain.

---

### Q3. Why loop till √N?

Uske baad koi naya composite number nahi bachta.

---

### Q4. Time Complexity?

```
O(N log log N)
```

---

### Q5. Space Complexity?

```
O(N)
```

---

# Remember ⭐

```
Step 1 → Sabko Prime maan lo.

↓

Step 2 → Har Prime ke Multiples hata do.

↓

Step 3 → Jo True bach gaye wahi Prime Numbers hain.
```

---

# Quick Revision 🚀

✅ Boolean Array

✅ Initially All = true

✅ 0 & 1 = false

✅ Loop till √N

✅ Start marking from i*i

✅ Multiples = false

✅ Remaining true = Prime Numbers

✅ Time = O(N log log N)

✅ Space = O(N)

Problem Link:https://www.geeksforgeeks.org/problems/sieve-of-eratosthenes5242/1
