# Strobogrammatic Number

## Pattern
- Two Pointers
- HashMap (Character Mapping)

---

# Problem

Ek number **strobogrammatic** tab hota hai jab usse **180° rotate** karne ke baad bhi wahi number dikhe.

Example:

```
69  -> 69 ✅
88  -> 88 ✅
818 -> 818 ✅
962 -> ❌
```

---

# Valid Rotations

| Original | Rotated |
|----------|----------|
| 0 | 0 |
| 1 | 1 |
| 6 | 9 |
| 8 | 8 |
| 9 | 6 |

Invalid Digits:

```
2
3
4
5
7
```

Ye rotate hone ke baad valid digit nahi bante.

---

# Idea 💡

Rotation ke baad:

- Digit bhi change ho sakta hai.
- Position bhi reverse ho jati hai.

Isliye:

```
Left Digit
      │
Rotate
      │
      ▼
Should become
Right Digit
```

Hum har pair ko check karenge.

---

# Algorithm

1. Rotation mapping bana lo.
2. Two pointers use karo.
   - left = 0
   - right = n-1
3. Jab tak `left <= right`
   - Agar left digit map me nahi hai → False
   - Agar rotated value != right digit → False
   - left++
   - right--
4. Sab pairs match ho gaye → True

---

# Dry Run

## Example 1

```
num = "619"

6 1 9
↑   ↑
```

Check

```
6 -> 9 ✅
```

Move

```
6 1 9
  ↑
```

Check

```
1 -> 1 ✅
```

Answer

```
true
```

---

## Example 2

```
num = "962"

9 6 2
↑   ↑
```

Check

```
9 -> 6

Expected = 6
Actual   = 2
```

Mismatch

```
false
```

---

# Java Code

```java
import java.util.HashMap;

class Solution {

    public boolean isStrobogrammatic(String num) {

        HashMap<Character, Character> map = new HashMap<>();

        map.put('0', '0');
        map.put('1', '1');
        map.put('6', '9');
        map.put('8', '8');
        map.put('9', '6');

        int left = 0;
        int right = num.length() - 1;

        while (left <= right) {

            char leftDigit = num.charAt(left);
            char rightDigit = num.charAt(right);

            if (!map.containsKey(leftDigit))
                return false;

            if (map.get(leftDigit) != rightDigit)
                return false;

            left++;
            right--;
        }

        return true;
    }
}
```

---

# Complexity

- **Time:** `O(n)`
- **Space:** `O(1)` *(HashMap me sirf 5 entries hain, isliye constant space.)*

---

# Common Mistakes ❌

### Mistake 1

```
leftDigit == rightDigit
```

Galat.

Compare karna hai:

```
map.get(leftDigit) == rightDigit
```

---

### Mistake 2

Sirf digits rotate karna.

```
619

6→9
1→1
9→6

916 ❌
```

Rotation ke baad **order bhi reverse hota hai**.

---

### Mistake 3

Invalid digits ko ignore kar dena.

```
2
3
4
5
7
```

Ye kabhi valid nahi ho sakte.

---

# Interview Tip ⭐

Is problem ka core concept hai:

```
Rotate + Reverse
```

Isliye **Two Pointers** best approach hai.

---

# Similar Questions

1. Valid Palindrome
2. Valid Palindrome II
3. Reverse String
4. Rotate String
5. Palindrome Number
6. Confusing Number
7. Strobogrammatic Number II
8. Strobogrammatic Number III
