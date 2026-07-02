# 🚀 Segmented Sieve Algorithm (Java)

## 📌 Definition

**Segmented Sieve** is an optimized version of the **Sieve of Eratosthenes**.

Jab **N bahut bada** ho (e.g. `10^8`, `10^9`), tab normal sieve me `O(N)` memory lagti hai, jo practical nahi hoti.

Segmented Sieve sirf **`O(√N)` extra memory** use karta hai.

---

# 💡 Idea

Instead of processing **2 → N** ek hi baar me, range ko **small segments (blocks)** me divide karte hain.

```
Example: N = 100

√100 = 10

Base Primes
2 3 5 7

Segments
11 - 21
22 - 32
33 - 43
44 - 54
...
```

Har segment ke andar base primes ki help se composite numbers remove karte hain.

---

# 📝 Algorithm

## Step 1: Find Base Primes

Simple Sieve chalao till **√N**.

```java
int limit = (int) Math.sqrt(n);
ArrayList<Integer> basePrimes = simpleSieve(limit);
```

Example

```
N = 100

limit = 10

Base Primes
2
3
5
7
```

---

## Step 2: Create First Segment

```java
int low = limit + 1;
int high = low + limit;
```

Example

```
Segment

11 - 21
```

---

## Step 3: Assume Every Number is Prime

```java
boolean[] mark = new boolean[high - low + 1];
Arrays.fill(mark, true);
```

Initially

```
T T T T T T T T T T T
```

---

## Step 4: Process Every Base Prime

```java
for (int p : basePrimes)
```

Har base prime ke multiples current segment me remove karte hain.

---

## Step 5: Find First Multiple

```java
int firstMultiple = (low / p) * p;

if (firstMultiple < low)
    firstMultiple += p;
```

### Example

```
low = 11
p = 3

11 / 3 = 3

3 × 3 = 9

9 < 11

Next multiple = 12
```

---

## Step 6: Start from p²

```java
firstMultiple = Math.max(firstMultiple, p * p);
```

### Why?

Smaller multiples already kisi chhote prime dwara remove ho chuke hote hain.

Example

```
p = 5

20 bhi multiple hai

lekin

20 ko 2 already remove kar chuka hai.

Isliye start = 25
```

---

## Step 7: Mark Multiples

```java
for (int j = firstMultiple; j <= high; j += p)
    mark[j - low] = false;
```

Example

```
Segment = 11 - 21

p = 2

Remove

12
14
16
18
20
```

---

## Step 8: Index Mapping ⭐

Current segment starts from **low**, but array starts from **0**.

```
Numbers

11 12 13 14 15

Indexes

0  1  2  3  4
```

Formula

```java
index = number - low;
```

Therefore

```java
mark[j - low] = false;
```

---

## Step 9: Remaining True Values are Prime

```java
for (int i = low; i <= high; i++) {

    if (mark[i - low])
        ans.add(i);

}
```

---

## Step 10: Move to Next Segment

```java
low = high + 1;
high = low + limit;
```

Repeat until `low > n`.

---

# 🔍 Dry Run

## Input

```
N = 30
```

### Base Primes

```
2
3
5
```

---

### Segment 1

```
6 - 11
```

After removing multiples

```
6  ✖
7  ✔
8  ✖
9  ✖
10 ✖
11 ✔
```

---

### Segment 2

```
12 - 17
```

```
12 ✖
13 ✔
14 ✖
15 ✖
16 ✖
17 ✔
```

---

### Segment 3

```
18 - 23
```

```
18 ✖
19 ✔
20 ✖
21 ✖
22 ✖
23 ✔
```

---

### Final Output

```
2 3 5 7 11 13 17 19 23 29
```

---

# 💻 Java Code

```java
static ArrayList<Integer> segmentedSieve(int n) {

    int limit = (int) Math.sqrt(n);

    // Base primes till √N
    ArrayList<Integer> basePrimes = simpleSieve(limit);

    ArrayList<Integer> ans = new ArrayList<>(basePrimes);

    int low = limit + 1;
    int high = low + limit;

    while (low <= n) {

        if (high > n)
            high = n;

        boolean[] mark = new boolean[high - low + 1];
        Arrays.fill(mark, true);

        for (int p : basePrimes) {

            int firstMultiple = (low / p) * p;

            if (firstMultiple < low)
                firstMultiple += p;

            firstMultiple = Math.max(firstMultiple, p * p);

            for (int j = firstMultiple; j <= high; j += p) {
                mark[j - low] = false;
            }
        }

        for (int i = low; i <= high; i++) {

            if (mark[i - low])
                ans.add(i);

        }

        low = high + 1;
        high = low + limit;
    }

    return ans;
}
```

---

# ⏱️ Complexity

| Complexity | Value |
|------------|-------|
| **Time** | `O(N log log N)` |
| **Space** | `O(√N)` |

---

# 🎯 Interview Points

- ✅ Optimized version of Sieve of Eratosthenes.
- ✅ Uses **Simple Sieve till √N** only.
- ✅ Processes numbers **segment by segment**.
- ✅ Uses only **`O(√N)` extra memory**.
- ✅ `mark[j - low]` converts actual number into array index.
- ✅ Multiples start from `max(firstMultiple, p²)`.
- ✅ Best when **N is very large**.

---

# 🧠 Revision Trick

> **Segmented Sieve = Simple Sieve till √N + Divide into Segments + Mark Multiples + Remaining Numbers are Prime.**
