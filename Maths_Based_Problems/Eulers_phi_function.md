# Euler's Phi (Totient) Function

## 📌 Pattern
**Number Theory → Prime Factorization**

---

# 📖 Definition

**φ(n)** = `1 se n` tak kitne numbers `n` ke saath **coprime** hain.

👉 Coprime matlab

```text
gcd(a, n) = 1
```

### Example

```text
n = 8

Numbers = 1 2 3 4 5 6 7 8

Coprime = 1, 3, 5, 7

φ(8) = 4
```

---

# 🐢 Brute Force

Har number ke liye GCD check karo.

```java
int count = 0;

for(int i = 1; i <= n; i++){
    if(gcd(i, n) == 1)
        count++;
}
```

### Complexity

- **Time:** `O(n log n)`
- **Space:** `O(1)`

❌ Bade constraints ke liye slow hai.

---

# 💡 Optimized Idea

Har number ka GCD check karne ki zarurat nahi.

Bas **Prime Factors** nikal lo.

## Formula

Agar

```text
n = p1^a × p2^b × ...
```

to

```text
φ(n) = n × (1-1/p1) × (1-1/p2) × ...
```

⚠️ **Sirf DISTINCT prime factors use honge.**

---

# 🚀 Algorithm

### Step 1

Initially

```java
result = n;
```

Answer `result` me store hoga.

---

### Step 2

2 se √n tak loop chalao.

```java
for(int i = 2; i * i <= n; i++)
```

Prime factors find karne ke liye.

---

### Step 3

Agar `i` prime factor hai

```java
if(n % i == 0)
```

to uski saari powers remove kar do.

```java
while(n % i == 0)
    n /= i;
```

### Example

```
60

↓

30

↓

15
```

Matlab **2² remove ho gaya.**

👉 Isliye same prime factor dobara process nahi hoga.

---

### Step 4

Prime factor mil gaya,

ab formula apply karo.

```java
result -= result / i;
```

Ye exactly

```text
result = result × (1 - 1/i)
```

ke barabar hai.

---

### Step 5

Loop ke baad agar

```java
n > 1
```

hai,

to matlab ek prime factor abhi bhi bacha hua hai.

Uske liye

```java
result -= result / n;
```

---

### Step 6

Answer return kar do.

```java
return result;
```

---

# ✍️ Dry Run

## φ(60)

### Initial

```text
n = 60
result = 60
```

---

### Prime Factor = 2

```
60 → 30 → 15
```

```text
result = 60 - 60/2

       = 30
```

Current

```text
n = 15
result = 30
```

---

### Prime Factor = 3

```
15 → 5
```

```text
result = 30 - 30/3

       = 20
```

Current

```text
n = 5
result = 20
```

---

### Remaining Prime Factor = 5

```text
result = 20 - 20/5

       = 16
```

✅ Final Answer

```text
φ(60) = 16
```

---

# 💻 Code

```java
class Solution {
    public int etf(int n) {

        int result = n;

        // Prime factors find karo
        for (int i = 2; i * i <= n; i++) {

            // Agar i prime factor hai
            if (n % i == 0) {

                // i ki saari powers remove karo
                while (n % i == 0) {
                    n /= i;
                }

                // Euler Phi Formula apply karo
                result -= result / i;
            }
        }

        // Agar ek prime factor bach gaya ho
        if (n > 1) {
            result -= result / n;
        }

        return result;
    }
}
```

---

# ⚡ Complexity

| Complexity | Value |
|------------|-------|
| Time | **O(√n)** |
| Space | **O(1)** |

---

Revision Trick

```
result = n

↓

Har DISTINCT prime factor nikalo

↓

result -= result / primeFactor

↓

Return result
```

**Bas itna hi algorithm hai! 🎯**

---

# 📚 Similar Questions

- Prime Factorization
- Sieve of Eratosthenes
- Segmented Sieve
- Euler Phi Sieve (1 to N)
- Euler's Theorem
- Modular Exponentiation
