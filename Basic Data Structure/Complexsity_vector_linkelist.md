# 📘 Asymptotic Notation in C++

---

**Asymptotic notation** ব্যবহার করা হয় algorithm এর **performance (time/space)** measure করার জন্য, যখন input size অনেক বড় হয়।

👉 সহজভাবে:
**n বড় হলে algorithm কেমন behave করে → সেটাই asymptotic notation**

---

## 🔹 Why Important?

* Algorithm compare করতে
* Efficient solution select করতে
* Competitive programming & interview এ খুব important

---

# 🔸 Types of Asymptotic Notation

## 1️⃣ Big-O Notation (O) → Worst Case

👉 সবচেয়ে বেশি সময় লাগলে কত লাগবে

---

### 🔸 Example

```cpp id="o1"
for(int i = 0; i < n; i++) {
    cout << i;
}
```

👉 Time Complexity:

```text id="o2"
O(n)
```

🔍 Explanation
সবচেয়ে খারাপ অবস্থায় loop n বার চলবে

---

## 2️⃣ Omega Notation (Ω) → Best Case

👉 সবচেয়ে কম সময় লাগলে কত লাগবে

---

### 🔸 Example

```cpp id="o3"
if(x == 5) {
    return true;
}
```

👉 Time Complexity:

```text id="o4"
Ω(1)
```

🔍 Explanation:
একবারেই condition true হলে constant time

---

## 3️⃣ Theta Notation (Θ) → Average Case

👉 average case performance

---

### 🔸 Example

```cpp id="o5"
for(int i = 0; i < n; i++) {
    cout << i;
}
```

👉 Time Complexity:

```text id="o6"
Θ(n)
```

🔍 Explanation:
average case এও n বার run করবে

---

# 🔸 Comparison Table

| Notation | Meaning     | Case    |
| -------- | ----------- | ------- |
| O(n)     | Upper bound | Worst   |
| Ω(n)     | Lower bound | Best    |
| Θ(n)     | Tight bound | Average |

---

# 🔸 Real Example (Search)

```cpp id="o7"
for(int i = 0; i < n; i++) {
    if(arr[i] == x) return i;
}
```

👉 Complexity:

```text id="o8"
Best → Ω(1)
Worst → O(n)
Average → Θ(n)
```

---

## 🔹 Explanation 

* প্রথমেই পেলে → O(1)
* শেষে পেলে → O(n)
* মাঝামাঝি → Θ(n)

---

# 📘 Important Time Complexities in C++

---

# 🔹 1️⃣ Linear Complexity — O(n)

👉 Loop n বার চলে

```cpp
for(int i = 0; i < n; i++) {
    cout << i;
}
```

🔍 Explanation (Bangla):

* n যত বাড়বে, time তত proportional বাড়বে
* n = 100 → 100 operation

---

# 🔹 2️⃣ Logarithmic Complexity — O(log n)

👉 প্রতি step এ input কমে যায় (divide / multiply)

---

## 🔸 (a) Division Based

```cpp
while(n > 1) {
    n = n / 2;
}
```

🔍 Explanation:

* প্রতি step এ n half হচ্ছে
* তাই total step ≈ log₂n

---

## 🔸 (b) Multiplication Based

```cpp
for(int i = 1; i < n; i = i * 2) {
    cout << i;
}
```

🔍 Explanation (Bangla):

* i প্রতি বার double হচ্ছে
* তাই loop ≈ log n বার চলে

---

# 🔹 3️⃣ Square Root Complexity — O(√n)

👉 Loop √n পর্যন্ত চলে

```cpp
for(int i = 1; i * i <= n; i++) {
    cout << i;
}
```

🔍 Explanation (Bangla):

* i² ≤ n → i ≈ √n
* তাই loop √n বার চলে

---

# 🔹 4️⃣ Quadratic Complexity — O(n²)

👉 Nested loop

```cpp
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        cout << i << j;
    }
}
```

🔍 Explanation (Bangla):

* n × n = n² operations
* n বাড়লে খুব দ্রুত slow হয়ে যায় ⚠️

---

# 🔹 5️⃣ Linearithmic Complexity — O(n log n)

👉 Linear × Logarithmic

---

## 🔸 Example 1: Sorting

```cpp
sort(a, a + n);
```

👉 Complexity:

```text
O(n log n)
```

---

## 🔸 Example 2: Loop + Log

```cpp
for(int i = 0; i < n; i++) {
    int x = n;
    while(x > 1) {
        x = x / 2;
    }
}
```

🔍 Explanation (Bangla):

* outer loop → n
* inner loop → log n
  👉 total = n × log n

---

# 🔹 Visualization

```text
n = 100

O(1)     → 1 step
O(log n) → ~7 step
O(√n)    → ~10 step
O(n)     → 100 step
O(n²)    → 10,000 step ⚠️
```

---

# 🔹 Comparison Order (Fast → Slow)

```text
O(1) < O(log n) < O(√n) < O(n) < O(n log n) < O(n²)
```








































