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

# 📘 Correct Comparison Order (Fast → Slow)

```text
O(1)       → constant
O(log n)   → logarithmic
O(√n)      → square root
O(n)       → linear
O(n log n) → linearithmic
O(n²)      → quadratic
```

---

### ✅ কেন এই order?

👉 Speed অনুযায়ী সাজানো:

* **O(1)** → fastest (input এর উপর depend করে না)
* **O(log n)** → খুব দ্রুত grow করে
* **O(√n)** → মাঝামাঝি
* **O(n)** → linear growth
* **O(n log n)** → একটু heavy (sorting)
* **O(n²)** → খুব slow ⚠️

---

## 🔹 Easy Trick to Remember 🧠

```text
1 < log n < √n < n < n log n < n²
```

👉 এই pattern মনে রাখলে সব clear 🔥

---

## 🔹 Example (n = 100)

```text
O(1)     → 1 step
O(log n) → ~7 step
O(√n)    → ~10 step
O(n)     → 100 step
O(nlog n)→ ~700 step
O(n²)    → 10,000 step ⚠️
```


```text
O(1) < O(log n) < O(√n) < O(n) < O(n log n) < O(n²)
```
# 📘 How to Calculate Time Complexity from a Problem

---

## 🔹 Step 1: Loop Count করো

👉 Code এ কয়টা loop আছে দেখো

```cpp
for(int i = 0; i < n; i++)
```

👉 Complexity:

```text
O(n)
```

🔍 Bangla:

* loop n বার চলছে → O(n)

---

## 🔹 Step 2: Nested Loop চেক করো

```cpp
for(int i = 0; i < n; i++){
    for(int j = 0; j < n; j++){
        // work
    }
}
```

👉 Complexity:

```text
O(n²)
```

🔍 Bangla:

* n × n = n²

---

## 🔹 Step 3: Division / Multiplication দেখো

```cpp
while(n > 1){
    n = n / 2;
}
```

👉 Complexity:

```text
O(log n)
```

🔍 Bangla:

* প্রতি বার half হচ্ছে → log n

---

## 🔹 Step 4: Condition Based Loop

```cpp
for(int i = 1; i*i <= n; i++)
```

👉 Complexity:

```text
O(√n)
```

🔍 Bangla:

* i² ≤ n → i ≈ √n

---

## 🔹 Step 5: Multiple Part হলে Add করো

```cpp
for(int i = 0; i < n; i++) {}   // O(n)
for(int i = 0; i < n; i++) {}   // O(n)
```

👉 Total:

```text
O(n) + O(n) = O(2n) = O(n)
```

---

## 🔹 Step 6: Loop inside Loop হলে Multiply করো

```cpp
for(int i = 0; i < n; i++) {
    while(x > 1){
        x = x / 2;
    }
}
```

👉 Complexity:

```text
O(n log n)
```

---

# 🔸 Full Example (Real Problem Style)

```cpp
int n;
cin >> n;

for(int i = 0; i < n; i++) {
    cout << i;
}

for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        cout << i << j;
    }
}
```

---

## 🔹 Calculation

```text
First loop  → O(n)
Second loop → O(n²)

Total → O(n + n²)
Final → O(n²)
```

👉 বড় term নেয়া হয়

---

# 🔹 Shortcut Trick 🔥

| Pattern     | Complexity |
| ----------- | ---------- |
| single loop | O(n)       |
| nested loop | O(n²)      |
| divide by 2 | O(log n)   |
| i*i <= n    | O(√n)      |
| sort()      | O(n log n) |

---

# 🔹 Most Important Rule 🧠

```text
Ignore small terms & constants
Take biggest growth only
```

👉 Example:

```text
O(n² + n + 5) → O(n²)
```

---

# 🎯 Final Summary

👉 Problem দেখলে:

1. loop count করো
2. nested হলে multiply
3. separate হলে add
4. divide হলে log
5. শেষে simplify

---

## 🔥 1 Line Formula

```text
Time Complexity = Total number of operations (in terms of n)
```

---
# 📘 How to Calculate Time from Time Complexity

---

👉 Time complexity directly seconds বলে না
👉 এটা বলে **operation count**

👉 Real time বের করতে:

```text
Execution Time ≈ (Number of Operations) / (Operations per Second)
```

---

## 🔹 Standard Assumption ⚡

Competitive programming এ usually ধরা হয়:

```text
1 second ≈ 10^7 to 10^8 operations
```

👉 safe ধরে:

```text
1 second ≈ 10^7 operations
```

---

# 🔸 Step-by-Step Calculation

## 🔹 Example 1: O(n)

👉 ধরো:

```text
n = 10^5
```

👉 Operation:

```text
≈ 10^5
```

👉 Time:

```text
10^5 / 10^7 = 0.01 sec ✅ fast
```

---

## 🔹 Example 2: O(n²)

👉 ধরো:

```text
n = 10^5
```

👉 Operation:

```text
(10^5)^2 = 10^10
```

👉 Time:

```text
10^10 / 10^7 = 1000 sec ❌ very slow
```

---

## 🔹 Example 3: O(log n)

```text
n = 10^5
log₂(10^5) ≈ 17
```

👉 Time:

```text
17 / 10^7 ≈ almost 0 sec 🚀
```

---

## 🔹 Example 4: O(n log n)

```text
n = 10^5
n log n ≈ 10^5 × 17 = 1.7 × 10^6
```

👉 Time:

```text
1.7×10^6 / 10^7 ≈ 0.17 sec ✅
```

---

# 🔸 Quick Table

```text
n = 10^5

O(1)       → ~0 sec
O(log n)   → ~0 sec
O(n)       → 0.01 sec
O(n log n) → 0.1 sec
O(n²)      → 1000 sec ❌
```

---

# 🔹 Easy Shortcut 🧠

👉 Contest rule:

```text
If operation ≤ 10^7 → OK (1 sec)
If operation > 10^8 → TLE ❌
```

---

# 🔹 Real Use Case

## Input Size vs Complexity

| n value | Safe Complexity  |
| ------- | ---------------- |
| 10⁵     | O(n), O(n log n) |
| 10³     | O(n²)            |
| 10⁶     | O(n), O(log n)   |

---

## 🔹 Example (Your Student Code)

👉 Loop:

```cpp
for(int i = 0; i < n; i++)
```

👉 Complexity:

```text
O(n)
```

👉 যদি n = 10^5:

```text
Time ≈ 0.01 sec ✅
```

---

# 🎯 Final Formula

```text
Time ≈ (Complexity value) / 10^7
```

---

# 📘 Vector in C++ (Easy Notes)

---

`vector` হলো C++ STL এর একটি **dynamic array**।

👉 সহজভাবে:
Array এর মতো, কিন্তু size automatically change হয়

---

## 🔹 Why use Vector?

* Dynamic size (resize লাগে না)
* Easy to use
* Built-in functions আছে

---

## 🔸 Syntax

```cpp
vector<data_type> name;
```

---

# 📘 Vector Declaration Types

---

## 🔹 1️⃣ Empty Vector

```cpp
vector<int> v;
```

👉 পরে `push_back()` দিয়ে data add করা হয়

---

## 🔹 2️⃣ Fixed Size Vector

```cpp
vector<int> v(5);
```

👉 size = 5, default value = 0

```
0 0 0 0 0
```

---

## 🔹 3️⃣ Fixed Size + Value

```cpp
vector<int> v(5, 10);
```

👉 সব element = 10

```
10 10 10 10 10
```

---

## 🔹 4️⃣ Initialization List

```cpp
vector<int> v = {1, 2, 3, 4};
```

---

## 🔹 5️⃣ Copy Vector

```cpp
vector<int> v2(v1);
```

---

## 🔹 6️⃣ Assign Vector

```cpp
vector<int> v2 = v1;
```

---

## 🔹 7️⃣ Range Copy

```cpp
vector<int> v(v1.begin(), v1.end());
```

---

## 🔹 8️⃣ Array to Vector

```cpp
int arr[] = {1,2,3};
vector<int> v(arr, arr+3);
```
---

## 🔹 🔟 Vector of String

```cpp
vector<string> v;
v.push_back("Hello");
v.push_back("World");
```

👉 Output:

```
Hello World
```

---

## 🔹 Vector of Object

```cpp
class Student {
public:
    string name;
    int id;
};

vector<Student> v;
```

---

# 🔹 Vector Modifiers

```cpp
v.push_back(x);   // add last
v.pop_back();     // remove last
v.insert();       // add in position
v.erase();        // remove element
v.clear();        // remove all
```

---

# 🔹 Vector Iteration

## 🔸 Normal Loop

```cpp
for(int i = 0; i < v.size(); i++){
    cout << v[i] << " ";
}
```

## 🔸 Range Loop (Best)

```cpp
for(int x : v){
    cout << x << " ";
}
```

## 🔸 Iterator

```cpp
for(auto it = v.begin(); it != v.end(); it++){
    cout << *it << " ";
}
```

---

# 🔹 Vector Capacity Functions

## 🔸 size()

```cpp
v.size();
```

👉 কত element আছে

---

## 🔸 capacity()

```cpp
v.capacity();
```

👉 কত memory allocate আছে

---

## 🔸 resize()

```cpp
v.resize(n);
```

👉 size change করে

```
1 2 3 → 1 2 3 0 0
```

---

## 🔸 reserve()

```cpp
v.reserve(n);
```

👉 আগে থেকেই memory allocate

---

## 🔸 shrink_to_fit()

```cpp
v.shrink_to_fit();
```

👉 extra memory remove

---

# 🔹 Example (Capacity)

```cpp
#include<iostream>
#include<vector>
using namespace std;

int main() {
    vector<int> v;

    for(int i = 1; i <= 5; i++){
        v.push_back(i);
        cout << "Size: " << v.size()
             << " Capacity: " << v.capacity() << endl;
    }
}
```

---

# 🔹 Important Functions

```cpp
v.size();
v.empty();
v.clear();
v.front();
v.back();
```

---

# 🔹 Sorting Vector

```cpp
#include<algorithm>
sort(v.begin(), v.end());
```

---

# 🔹 Time Complexity

| Operation   | Complexity |
| ----------- | ---------- |
| push_back   | O(1) avg   |
| pop_back    | O(1)       |
| access v[i] | O(1)       |
| sort        | O(n log n) |

---




```cpp
vector<int> v(5);
```

🔍 Explanation:

* size = 5
* default value = 0

👉 Result:

```text
0 0 0 0 0
```

---


## 🔹 Explanation 

* `push_back()` → element add করে
* `v[i]` → access করা যায়
* `size()` → total element

---

## 🔸 Example 2: Initialization

```cpp
vector<int> v = {1, 2, 3, 4};
```

---

## 🔸 Example 3: Input & Output

```cpp
int n;
cin >> n;

vector<int> v(n);

for(int i = 0; i < n; i++){
    cin >> v[i];
}

for(int x : v){
    cout << x << " ";
}
```

# 📘 Linked List in C++

---

Linked List হলো এমন একটি data structure যেখানে data গুলো **node আকারে সংরক্ষণ করা হয়**।

👉 প্রতিটি node এর মধ্যে থাকে:

* একটি value (data)
* একটি pointer (next node এর address)

N.B : 👉 Array এর মতো contiguous memory লাগে না

---
---

## 🔹 Why Use Linked List?

### ✅ 1. Dynamic Size

Array এর size fixed থাকে ❌
Linked List এ size easily change করা যায় ✅

### ✅ 2. Easy Insert & Delete

Array তে insert/delete করলে shift করতে হয় ❌
Linked List এ pointer change করলেই হয়ে যায় ✅

### ✅ 3. Memory Use Efficient

যতটুকু দরকার ততটুকুই memory use হয়

---

## 🔹 Node Structure

```cpp

class Node {
public:
    int val;
    Node* next;
};
```

👉 `val` → data store করে
👉 `next` → next node কে point করে

---

## 🔹 Visualization

```
[10 | • ] → [20 | • ] → [30 | NULL] 
```

👉 এখানে:

* 10 → head (first node)
* 30 → last node (next = NULL)



## 🔹 Basic Operations

| Operation | Explanation       |
| --------- | ----------------- |
| Insert    | নতুন node add করা |
| Delete    | node remove করা   |
| Traverse  | সব node print করা |
| Search    | value খোঁজা       |

---

## 🔹 Linked List vs Array

| Feature       | Array      | Linked List    |
| ------------- | ---------- | -------------- |
| Size          | Fixed      | Dynamic        |
| Memory        | Continuous | Non-continuous |
| Insert/Delete | Slow       | Fast           |
| Access        | Fast       | Slow           |

---

## 🔹 Node Structure (simple)

```cpp
#include<iostream>
using namespace std;


class Node {
public:
    int val;
    Node* next;
};


int main(){
Node a, b, c;

a.val = 10;
b.val = 20;
c.val = 30;

a.next = &b;
b.next = &c;
c.next = NULL;

cout << a.val;              // 10
cout << a.next->val;        // 20
cout << a.next->next->val;  // 30

return 0;

}
```
# Node Structure (With Constructor)

```cpp
#include<iostream>
using namespace std;

class Node {
public:
    int val;
    Node* next;

    // constructor
    Node(int val) {
        this->val = val;
        this->next = NULL;
    }
};

int main() {
    
    Node a(10), b(20), c(30);
  
    a.next = &b;
    b.next = &c;
   
    cout << a.val << endl;              // 10
    cout << a.next->val << endl;        // 20
    cout << a.next->next->val << endl;  // 30
   
    return 0;
}


```
# Dynamic Linked List
```cpp
#include<iostream>
using namespace std;

class Node {
public:
    int val;
    Node* next;

    Node(int val) {
        this->val = val;
        this->next = NULL;
    }
};

int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);

    head->next = a;
    a->next = b;

  // cout<<head->val<<end;
  // cout<<head->next->val<<endl;
 // cout<<head->next->next->val<<endl;

Node* temp =head;

 while(temp != NULL){
  cout<<temp->val<<endl;
   temp =temp->next;
}

    return 0;
}



```
















































