# C প্রোগ্রামে Header File এবং Main Function

## 1. Header File

```c
#include <stdio.h>
```

`stdio.h` এর পূর্ণ অর্থ **Standard Input Output**।
এই header file ব্যবহার করা হয় ইনপুট ও আউটপুট সংক্রান্ত ফাংশন ব্যবহার করার জন্য, যেমন `printf()` এবং `scanf()`।

### Header File কেন ব্যবহার করা হয়

* পূর্বে তৈরি করা **library function** ব্যবহার করার জন্য
* ইনপুট এবং আউটপুট অপারেশন করার জন্য
* কোডকে আরও **সংগঠিত ও সহজে ব্যবহারযোগ্য** করার জন্য

---

## 2. Main Function (Program Body)

```c
#include <stdio.h>

int main() {
    printf("Hello world");
    return 0;
}
```

### Main Function কেন প্রয়োজন

`main()` হলো C প্রোগ্রামের **entry point** বা শুরু হওয়ার জায়গা।
যখন একটি প্রোগ্রাম চালু হয়, তখন execution প্রথমে `main()` ফাংশন থেকেই শুরু হয়।

---
# C প্রোগ্রামে Variable, Data Type, Memory Unit এবং Variable Naming Rules

---

# 1. Variable কি

**Variable** হলো এমন একটি জায়গা যেখানে আমরা কোনো **value বা data সংরক্ষণ (store)** করি।
সহজভাবে বললে, Variable হলো একটি **container বা bag (ব্যাগ)** এর মতো যেখানে আমরা বিভিন্ন ধরনের তথ্য রাখি।

### সহজ উদাহরণ

ধরো তুমি বাজারে গেলে —

* মাছ কিনলে → মাছ রাখার জন্য **একটা ব্যাগ** লাগবে
* তেল কিনলে → তেল রাখার জন্য **একটা বোতল** লাগবে

এখানে,

* **ব্যাগ বা container** → Variable
* **যে ধরনের জিনিস রাখা হচ্ছে** → Data Type

অর্থাৎ **Variable হলো ব্যাগের মতো**, আর **Data Type হলো সেই ব্যাগের ধরন বা পাত্র**।

---

# 2. Data Type কি

**Data Type** নির্ধারণ করে একটি variable এ **কোন ধরনের data রাখা যাবে**।

### সাধারণ Data Type

| Data Type | ব্যবহার       |
| --------- | ------------- |
| `int`     | পূর্ণসংখ্যা   |
| `float`   | দশমিক সংখ্যা  |
| `char`    | একটি অক্ষর    |
| `bool`    | true বা false |

---

# 3. Data Type Limitation

প্রতিটি data type এর একটি **নির্দিষ্ট সীমা (limit)** থাকে।

| Data Type       | সীমা (প্রায়)           |
| --------------- | ---------------------- |
| `int`           | −10⁹ থেকে +10⁹         |
| `float`         | প্রায় ±10³⁸ পর্যন্ত    |
| `long long int` | প্রায় −10¹⁸ থেকে +10¹⁸ |
| `char`          | −128 থেকে +127         |

---

# 4. Variable Naming Rules

C প্রোগ্রামে variable নাম দেওয়ার সময় কিছু নিয়ম মানতে হয়।

### নিয়মগুলো

1. **Variable নাম letter (a-z, A-Z) অথবা underscore (_) দিয়ে শুরু হতে হবে**

✔️ সঠিক

```
age
_total
price
```

---

2. **Variable নামের মধ্যে number থাকতে পারে**

✔️ সঠিক

```
age1
student2
price2024
```

---

3. **Variable নামের মধ্যে space দেওয়া যাবে না**

✔️ সঠিক

```
totalPrice
student_age
```

---

4. **Special character ব্যবহার করা যাবে না**

✔️ সঠিক

```
price
age
student
```

---

5. **C এর keyword variable নাম হিসেবে ব্যবহার করা যাবে না**

যেমন:

```
int
float
return
if
while
```

---

6. **Variable নাম অর্থপূর্ণ হওয়া ভালো**

✔️ ভালো উদাহরণ

```
studentAge
totalPrice
productCount
```

---

# 5. উদাহরণ কোড

```c
#include <stdio.h>

int main() {

    int age = 20;
    float price = 10.5;
    char grade = 'A';
    long long int population = 1000000000000;

    printf("%d\n", age);
    printf("%f\n", price);
    printf("%c\n", grade);
    printf("%lld\n", population);

    return 0;
}
```

---

# 6. Memory Unit

কম্পিউটারে সব তথ্য **Binary (0 এবং 1)** আকারে সংরক্ষণ করা হয়।

| Unit          | সমান     |
| ------------- | -------- |
| **1 bit**     | 0 অথবা 1 |
| **8 bit**     | 1 byte   |
| **1024 byte** | 1 KB     |
| **1024 KB**   | 1 MB     |
| **1024 MB**   | 1 GB     |

---

# C++ Operator (অপারেটর)

**Operator** হলো এমন একটি চিহ্ন যা দুই বা ততোধিক সংখ্যার (Operand) মাঝে বসে কোনো কাজ সম্পন্ন করে।

উদাহরণ:

```
5 + 3
```

এখানে  
- `5` এবং `3` = Operand  
- `+` = Operator  

অর্থাৎ **Operator দুইটি সংখ্যার মাঝে বসে গণনা বা তুলনা করার কাজ করে।**

---

# 1. Arithmetic Operator (গাণিতিক অপারেটর)

Arithmetic Operator ব্যবহার করা হয় **গাণিতিক হিসাব করার জন্য**।

| Operator | নাম | কাজ | উদাহরণ |
|--------|------|------|------|
| `+` | Addition | যোগ | 5 + 3 = 8 |
| `-` | Subtraction | বিয়োগ | 5 - 3 = 2 |
| `*` | Multiplication | গুণ | 5 * 3 = 15 |
| `/` | Division | ভাগ | 6 / 3 = 2 |
| `%` | Modulus | ভাগশেষ বের করা | 5 % 2 = 1 |
| `++` | Increment | মান ১ বাড়ায় | a++ |
| `--` | Decrement | মান ১ কমায় | a-- |

উদাহরণ:

```cpp
int a = 10;
int b = 5;

cout << a + b;
cout << a - b;
cout << a * b;
cout << a / b;
cout << a % b;
```

---

# 2. Relational Operator (তুলনামূলক অপারেটর)

Relational Operator ব্যবহার করা হয় **দুইটি মান তুলনা করার জন্য**।

এগুলোর ফলাফল হয় `true (1)` অথবা `false (0)`।

| Operator | অর্থ | উদাহরণ |
|--------|------|------|
| `==` | সমান | a == b |
| `!=` | সমান নয় | a != b |
| `>` | বড় | a > b |
| `<` | ছোট | a < b |
| `>=` | বড় অথবা সমান | a >= b |
| `<=` | ছোট অথবা সমান | a <= b |

উদাহরণ:

```cpp
int a = 10;
int b = 5;

cout << (a > b);
cout << (a < b);
cout << (a == b);
```

---

# 3. Logical Operator (লজিক্যাল অপারেটর)

Logical Operator ব্যবহার করা হয় **একাধিক শর্ত একসাথে যাচাই করার জন্য**।

| Operator | নাম | কাজ |
|--------|------|------|
| `&&` | Logical AND | দুইটিই true হলে true ,একটি true হলেই flase |
| `//` | Logical OR | একটি true হলেই true, দুইটিই flase হলে false  |
| `!` | Logical NOT | true কে false করে |

উদাহরণ:

```cpp
int a = 10;
int b = 5;

cout << (a > 5 && b < 10);
cout << (a > 20 || b < 10);
cout << !(a > b);
```

---

# সংক্ষেপে

C++ Operator তিন ধরনের:

1. **Arithmetic Operator** → গাণিতিক হিসাব করার জন্য  
2. **Relational Operator** → দুইটি মান তুলনা করার জন্য  
3. **Logical Operator** → একাধিক শর্ত যাচাই করার জন্য


# C++ Conditional Statement (Condition / শর্ত)

**Conditional Statement** ব্যবহার করা হয় যখন কোনো **শর্ত (condition)** অনুযায়ী আলাদা আলাদা কাজ করতে হয়।

উদাহরণ  
যদি বৃষ্টি হয় → ছাতা নিবো  
না হলে → বাইরে যাবো

- `if`
- `else if`
- `else`
- `nested if`

---

# 1️⃣ if Statement

`if` ব্যবহার করা হয় যখন **একটি শর্ত সত্য (true) হলে কোনো কাজ করতে হবে**।

### Syntax

```cpp
if(condition)
{
    code
}
```

### Example

```cpp
int age = 20;

if(age >= 18)
{
    cout << "You are adult";
}
```

রাহিম সিনেমা দেখতে যাবে।  
সিনেমা হলে ঢুকতে হলে বয়স **১৮ বা তার বেশি হতে হবে**।

```
যদি বয়স ≥ 18 হয় → সিনেমা দেখতে পারবে
```

---

# 2️⃣ if else Statement

যখন **শর্ত সত্য হলে এক কাজ এবং মিথ্যা হলে অন্য কাজ করতে হয়** তখন `if else` ব্যবহার করা হয়।

### Syntax

```cpp
if(condition)
{
    code
}
else
{
    code
}
```

### Example

```cpp
int age = 15;

if(age >= 18)
{
    cout << "You can vote";
}
else
{
    cout << "You cannot vote";
}
```

ভোট দেওয়ার জন্য বয়স **১৮ বছর হতে হবে**।

```
যদি বয়স ≥ 18 → ভোট দিতে পারবে  
না হলে → ভোট দিতে পারবে না
```

---

# 3️⃣ else if Statement

যখন **একাধিক শর্ত পরীক্ষা করতে হয়** তখন `else if` ব্যবহার করা হয়।

### Syntax

```cpp
if(condition1)
{
}
else if(condition2)
{
}
else
{
}
```

### Example

```cpp
int marks = 75;

if(marks >= 80)
{
    cout << "Grade A";
}
else if(marks >= 60)
{
    cout << "Grade B";
}
else
{
    cout << "Fail";
}
```

একটি স্কুলে মার্কস অনুযায়ী গ্রেড দেওয়া হয়।

```
৮০ বা বেশি → Grade A  
৬০ বা বেশি → Grade B  
এর নিচে → Fail
```

---

# 4️⃣ Nested if (Nested Condition)

যখন **একটি if এর ভিতরে আরেকটি if থাকে**, তখন তাকে **Nested if** বলে।

### Syntax

```cpp
if(condition1)
{
    if(condition2)
    {
        code
    }
}
```

### Example

```cpp
int age = 20;
bool ticket = true;

if(age >= 18)
{
    if(ticket == true)
    {
        cout << "You can enter cinema hall";
    }
}
```

সিনেমা হলে ঢুকতে দুইটা শর্ত আছে:

```
১. বয়স ≥ 18
২. টিকেট থাকতে হবে
```

দুইটিই সত্য হলে → ঢুকতে পারবে।

---

# সহজভাবে মনে রাখো

| Statement | কাজ |
|------|------|
| `if` | একটি শর্ত পরীক্ষা করে |
| `if else` | true হলে এক কাজ, false হলে অন্য কাজ |
| `else if` | অনেক শর্ত পরীক্ষা করে |
| `nested if` | একটি if এর ভিতরে আরেকটি if |

---


