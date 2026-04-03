# C++ Array (অ্যারে)

**Array** হলো একই ধরনের অনেকগুলো data একসাথে একটি variable এর মধ্যে সংরক্ষণ করার উপায়।

উদাহরণ  
৫ জন ছাত্রের মার্কস:

```
80 75 90 85 70
```

এগুলো আলাদা variable এ না রেখে **Array** ব্যবহার করা যায়।

---

# Array Declaration

Array তৈরি করার নিয়ম

```
data_type array_name[size];
```

Example

```cpp
int marks[5];
```

---

# Array Initialization

```cpp
int marks[5] = {80,75,90,85,70};
```

---

# Array Index

Array এর index **0 থেকে শুরু হয়**।

```
marks[0] = 80
marks[1] = 75
marks[2] = 90
marks[3] = 85
marks[4] = 70
```

---

# Array Input (Loop ব্যবহার করে)

```cpp
#include<iostream>
using namespace std;

int main()
{
    int arr[5];

    for(int i=0;i<5;i++)
    {
        cin >> arr[i];
    }

    return 0;
}
```

---

# Array Output (Loop ব্যবহার করে)

```cpp
for(int i=0;i<5;i++)
{
    cout << arr[i] << " ";
}
```
# C++ Array Memory Address

কম্পিউটারের মেমোরিতে প্রতিটি data একটি নির্দিষ্ট **address** এ সংরক্ষণ করা থাকে।  
Array এর প্রতিটি element **continuous memory location** এ থাকে।

অর্থাৎ array এর সব value **একটার পর একটা memory address এ রাখা হয়**।

---

# Example Array

```cpp
int arr[5] = {10,20,30,40,50};
```

Memory এ এটা এমনভাবে থাকে:

| Index | Value | Memory Address (Example) |
|------|------|------|
| arr[0] | 10 | 1000 |
| arr[1] | 20 | 1004 |
| arr[2] | 30 | 1008 |
| arr[3] | 40 | 1012 |
| arr[4] | 50 | 1016 |

Explanation

- `int` সাধারণত **4 byte** জায়গা নেয়
- তাই প্রতিটি element এর address **4 করে বাড়ে**

```
1000
1004
1008
1012
1016
```

---

# Memory Address Print

Array এর memory address দেখতে `&` operator ব্যবহার করা হয়।

```cpp
#include<iostream>
using namespace std;

int main()
{
    int arr[3] = {10,20,30};

    cout << &arr[0] << endl;
    cout << &arr[1] << endl;
    cout << &arr[2] << endl;

    return 0;
}
```

Output (example)

```
0x61ff08
0x61ff0c
0x61ff10
```

---

# Loop ব্যবহার করে Address Print

```cpp
int arr[5] = {10,20,30,40,50};

for(int i=0;i<5;i++)
{
    cout << &arr[i] << endl;
}
```

---

# Important Point

- Array এর **প্রথম element এর address** = Array এর নাম।

Example

```cpp
cout << arr;
```

এটা আসলে

```
arr == &arr[0]
```

---

# সহজভাবে মনে রাখো

| Concept | Meaning |
|------|------|
| `arr[0]` | প্রথম element |
| `&arr[0]` | প্রথম element এর memory address |
| `arr` | পুরো array এর starting address |

---

# Small Story

ধরো একটি **বইয়ের তাক** আছে।

```
Shelf 1 → 10
Shelf 2 → 20
Shelf 3 → 30
Shelf 4 → 40
Shelf 5 → 50
```

প্রতিটি shelf এর একটি **address (location)** আছে।

Array ঠিক এমনভাবেই **memory তে data সাজিয়ে রাখে**।

---

---

# Array Sum Operation

Array এর সব সংখ্যার যোগফল বের করা।

```cpp
int sum = 0;

for(int i=0;i<5;i++)
{
    sum = sum + arr[i];
}

cout << sum;
```

---

# Even Number from Array

```cpp
for(int i=0;i<5;i++)
{
    if(arr[i] % 2 == 0)
    {
        cout << arr[i] << " ";
    }
}
```

---

# Odd Number from Array

```cpp
for(int i=0;i<5;i++)
{
    if(arr[i] % 2 != 0)
    {
        cout << arr[i] << " ";
    }
}
```

---

# Maximum Number from Array

```cpp
int max = arr[0];

for(int i=1;i<5;i++)
{
    if(arr[i] > max)
    {
        max = arr[i];
    }
}

cout << max;
```

---

# Minimum Number from Array

```cpp
int min = arr[0];

for(int i=1;i<5;i++)
{
    if(arr[i] < min)
    {
        min = arr[i];
    }
}

cout << min;
```

---

# Reverse Array

```cpp
for(int i=4;i>=0;i--)
{
    cout << arr[i] << " ";
}
```

---

# Full Example (Input + Output + Sum)

```cpp
#include<iostream>
using namespace std;

int main()
{
    int arr[5];
    int sum = 0;

    for(int i=0;i<5;i++)
    {
        cin >> arr[i];
    }

    for(int i=0;i<5;i++)
    {
        cout << arr[i] << " ";
        sum = sum + arr[i];
    }

    cout << endl;
    cout << "Sum = " << sum;

    return 0;
}
```

---

# Array Operations Summary

| Operation | কাজ |
|------|------|
| Input | array এ data নেওয়া |
| Output | array এর data print করা |
| Sum | সব সংখ্যার যোগ |
| Even | জোড় সংখ্যা বের করা |
| Odd | বিজোড় সংখ্যা বের করা |
| Max | সবচেয়ে বড় সংখ্যা |
| Min | সবচেয়ে ছোট সংখ্যা |
| Reverse | উল্টোভাবে print |

---
# C++ Array Operations

Array এর উপর আমরা বিভিন্ন ধরনের operation করতে পারি যেমন:

- Insert (নতুন value যোগ করা)
- Remove / Delete (value মুছে ফেলা)
- Swap (দুইটা value পরিবর্তন করা)
- Reverse (উল্টো করে দেওয়া)

---

# 1️⃣ Insert Value at Any Position

যে position এ value বসাতে চাই, তার পরে সব element **একটা করে right shift** করতে হয়।

### Code

```cpp
#include<iostream>
using namespace std;

int main()
{
    int n;
    cin >> n;

    int arr[n+1];

    for(int i=0;i<n;i++)
    {
        cin >> arr[i];
    }

    int idx,value;
    cin >> idx >> value;

    for(int i=n;i>idx;i--)
    {
        arr[i] = arr[i-1];
    }

    arr[idx] = value;
    n++;

    for(int i=0;i<n;i++)
    {
        cout << arr[i] << " ";
    }
}
```

Example

```
Input
5
10 20 30 40 50
2 25

Output
10 20 25 30 40 50
```

---

# 2️⃣ Remove / Delete Value from Any Position

Delete করতে হলে element গুলোকে **left shift** করতে হয়।

### Code

```cpp
int idx;
cin >> idx;

for(int i=idx;i<n-1;i++)
{
    arr[i] = arr[i+1];
}

n--;

for(int i=0;i<n;i++)
{
    cout << arr[i] << " ";
}
```

Example

```
Array: 10 20 30 40 50
Delete index 2

Result:
10 20 40 50
```

---

# 3️⃣ Swap Two Values

দুইটা index এর value change করা।

### Code

```cpp
int i,j;
cin >> i >> j;

int temp = arr[i];
arr[i] = arr[j];
arr[j] = temp;
```

Example

```
Array: 10 20 30 40
Swap index 1 and 3

Result:
10 40 30 20
```

---

# 4️⃣ Reverse Array

Array উল্টো করে print করা।

### Code

```cpp
for(int i=n-1;i>=0;i--)
{
    cout << arr[i] << " ";
}
```

Example

```
Array: 10 20 30 40

Output:
40 30 20 10
```

---

# Reverse Array (Swap Method)

```cpp
for(int i=0;i<n/2;i++)
{
    int temp = arr[i];
    arr[i] = arr[n-1-i];
    arr[n-1-i] = temp;
}
```

---

# Array Operations Summary

| Operation | Description |
|----------|-------------|
| Insert | নির্দিষ্ট position এ নতুন value যোগ করা |
| Delete | নির্দিষ্ট position এর value remove করা |
| Swap | দুইটা element এর জায়গা পরিবর্তন |
| Reverse | array উল্টো করে দেওয়া |

---

# Simple Example

Array

```
10 20 30 40 50
```

Operations

```
Insert 25 at index 2 → 10 20 25 30 40 50
Delete index 3       → 10 20 25 40 50
Swap index 1 & 3     → 10 40 25 20 50
Reverse              → 50 20 25 40 10
```

---

# Two Pointer Technique (C++)

Two Pointer Technique হলো এমন একটি পদ্ধতি যেখানে **একই array বা string এ দুইটা index ব্যবহার করা হয়**।

সাধারণত দুইটি variable ব্যবহার করা হয়:

```
i → শুরু থেকে
j → শেষ থেকে
```

এবং condition হয়

```
while(i < j)
```

---

# Basic Idea

```
i → ← j
```

- `i` শুরু থেকে move করে
- `j` শেষ থেকে move করে
- প্রয়োজন অনুযায়ী swap / check করা হয়

---

# Two Pointer Template

```cpp
int i = 0;
int j = n - 1;

while(i < j)
{
    // operation

    i++;
    j--;
}
```

---

# Example: Reverse Array

### Code

```cpp
#include<iostream>
using namespace std;

int main()
{
    int n;
    cin >> n;

    int arr[n];

    for(int i=0;i<n;i++)
    {
        cin >> arr[i];
    }

    int i = 0;
    int j = n - 1;

    while(i < j)
    {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;

        i++;
        j--;
    }

    for(int i=0;i<n;i++)
    {
        cout << arr[i] << " ";
    }
}
```

---

# Example

Array

```
10 20 30 40 50
```

Step 1

```
i=0 , j=4
swap → 50 20 30 40 10
```

Step 2

```
i=1 , j=3
swap → 50 40 30 20 10
```

Result

```
50 40 30 20 10
```

---

# Two Pointer Use Cases

Two Pointer technique অনেক problem এ ব্যবহার হয়।

### Common Problems

- Reverse Array
- Palindrome Check
- Two Sum
- Remove Duplicates
- Move Zeroes
- Container With Most Water

---



# C ভাষা – স্ট্রিংস 

---

## 1. What is a String?

In C, a **string** হল একটি **character array**, যা **null character (`'\0'`)** দিয়ে শেষ হয়।

**উদাহরণ:**

```c
char name[10] = "Raihan";  // 'R', 'a', 'i', 'h', 'a', 'n', '\0'
```

---

## 2. Declaring Strings

```c
char str1[20];             // খালি স্ট্রিং (user input এর জন্য)
char str2[] = "Hello";     // কম্পাইলার স্বয়ংক্রিয়ভাবে সাইজ নির্ধারণ করে
char str3[6] = {'H','e','l','l','o','\0'}; // স্পষ্ট null character
```

---

## 3. Input and Output of Strings

### Input Methods

**Using `scanf()`**

* ইনপুট স্পেস এ থেমে যায়

```c
char name[20];
scanf("%s", name);
```

**Using `fgets()`**

* পুরো লাইন পড়তে পারে, স্পেসসহ

```c
char name[50];
fgets(name, 50, stdin);
```

### Output Strings

```c
printf("নাম: %s\n", name);
```

---

## 4. Common String Functions (`string.h`)

লাইব্রেরি অন্তর্ভুক্ত করুন:

```c
#include <string.h>
```

| Function            | Purpose                                          |
| ------------------- | ------------------------------------------------ |
| `strlen(s)`         | স্ট্রিং দৈর্ঘ্য বের করে (excluding `'\0'`)       |
| `strcpy(dest, src)` | স্ট্রিং কপি করে `src` থেকে `dest` এ              |
| `strcat(dest, src)` | `src` যোগ করে `dest` এর শেষে                     |
| `strcmp(s1, s2)`    | দুটি স্ট্রিং তুলনা করে (সমান হলে `0` return করে) |
| `strchr(s, c)`      | প্রথম occurrence খুঁজে `c` character এর          |
| `strstr(s1, s2)`    | substring `s2` খুঁজে `s1`-এ                      |

**উদাহরণ:**

```c
char str1[20] = "Hello";
char str2[20] = "World";

strcat(str1, str2);      // str1 = "HelloWorld"
int len = strlen(str1);  // len = 10
```

---

## 5. Important Notes

1. C strings **mutable**, তবে array সাইজ পর্যাপ্ত না হলে buffer overflow হতে পারে।
2. সব স্ট্রিং অপারেশন null character (`'\0'`) এর উপর নির্ভর করে।
3. সবসময় array তে null character রাখার জন্য পর্যাপ্ত স্থান নিশ্চিত করুন।
4. নিরাপদ ইনপুটের জন্য `fgets()` ব্যবহার করুন `scanf()` এর পরিবর্তে।

---

## 6. String vs Char

| Feature         | Char          | String          |
| --------------- | ------------- | --------------- |
| Type            | একক character | character array |
| উদাহরণ          | `'A'`         | `"Hello"`       |
| Null-terminated | না            | হ্যাঁ (`'\0'`)  |
| Storage         | ১ byte        | একাধিক byte     |

**উদাহরণ:**

```c
char letter = 'A';
char name[10] = "Raihan";
```

# C++ Pattern Mastery Guide



---

## ⭐ Basic Star Pattern

```cpp
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        cout << "*";
    }
    cout << endl;
}
```

```
*
**
***
****
*****
```

### 🧠 Explanation (Bangla)

* বাইরের loop (`i`) → কয়টা লাইন হবে
* ভেতরের loop (`j`) → প্রতি লাইনে কয়টা `*` হবে
* প্রতি লাইনে star বাড়ে

---

## 🔁 Reverse Star Pattern

```cpp
for (int i = n; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        cout << "*";
    }
    cout << endl;
}
```

```
*****
****
***
**
*
```

### 🧠 Explanation (Bangla)

* প্রথম লাইনে বেশি `*`
* প্রতি লাইনে কমতে থাকে

---

## 📐 Right-Aligned Triangle

```cpp
for (int i = 1; i <= n; i++) {

    for (int j = 1; j <= n - i; j++) {
        cout << " ";
    }

    for (int j = 1; j <= i; j++) {
        cout << "*";
    }

    cout << endl;
}
```

```
    *
   **
  ***
 ****
*****
```

### 🧠 Explanation (Bangla)

* আগে space print করতে হয়
* তারপর star print
* Space কমে, star বাড়ে

---

## 🔺 Pyramid Pattern

```cpp
for (int i = 1; i <= n; i++) {

    for (int j = 1; j <= n - i; j++) {
        cout << " ";
    }

    for (int j = 1; j <= (2 * i - 1); j++) {
        cout << "*";
    }

    cout << endl;
}
```

```
    *
   ***
  *****
 *******
*********
```

### 🧠 Explanation (Bangla)

* Pyramid এর জন্য star odd number হয় (1,3,5...)
* Space কমে
* Star = (2*i - 1)

---

## 🔻 Inverted Pyramid

```cpp
for (int i = n; i >= 1; i--) {

    for (int j = 1; j <= n - i; j++) {
        cout << " ";
    }

    for (int j = 1; j <= (2 * i - 1); j++) {
        cout << "*";
    }

    cout << endl;
}
```

```
*********
 *******
  *****
   ***
    *
```

### 🧠 Explanation (Bangla)

* Pyramid এর উল্টা version
* Star কমে
* Space বাড়ে

---

## 💎 Diamond Pattern

```cpp
// Upper
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n - i; j++) cout << " ";
    for (int j = 1; j <= (2 * i - 1); j++) cout << "*";
    cout << endl;
}

// Lower
for (int i = n - 1; i >= 1; i--) {
    for (int j = 1; j <= n - i; j++) cout << " ";
    for (int j = 1; j <= (2 * i - 1); j++) cout << "*";
    cout << endl;
}
```

### 🧠 Explanation (Bangla)

* Pyramid + Inverted Pyramid = Diamond
* প্রথমে বাড়ে, তারপর কমে

---

## 🔢 Number Pattern

```cpp
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= i; j++) {
        cout << j << " ";
    }
    cout << endl;
}
```

```
1
1 2
1 2 3
1 2 3 4
```

### 🧠 Explanation (Bangla)

* প্রতি লাইনে number print হয়
* 1 থেকে শুরু করে line অনুযায়ী বাড়ে

---

## ⚡ Pattern Logic (Important)

### ✅ Core Idea

* Outer loop → Line control
* Inner loop → Print control

### 🔥 Formula

* Triangle → `j <= i`
* Reverse → `j <= n - i`
* Pyramid → `2*i - 1`
* Space → `n - i`





