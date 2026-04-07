# 📘 Strings in C++

---

C++ এ **string** হলো character-এর sequence যা text represent করে।

👉 সহজভাবে:
**String = character এর array + extra features**

C++ এ string 2 ধরনের হয়:

1. **C++ string class** → `std::string`

---

---

## 🔸 Example 1: Basic String

```cpp id="s2"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Hello";
    cout << s << endl;
    return 0;
}
```

### 🔹 Output

```
Hello
```

---

## 🔸 Example 2: Input String

```cpp id="s3"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string name;
    cout << "Enter your name: ";
    getline(cin, name); // space allowed
    cout << "Hello, " << name << endl;
    return 0;
}
```

---

## 🔸 String Functions / Methods

| Function              | Description               |
| --------------------- | ------------------------- |
| `length()` / `size()` | String length             |
| `empty()`             | Check if empty            |
| `clear()`             | Clear string              |
| `append()`            | Add string at end         |
| `insert()`            | Insert at position        |
| `erase()`             | Remove characters         |
| `replace()`           | Replace substring         |
| `substr()`            | Extract substring         |
| `find()`              | Search substring          |
| `compare()`           | Compare two strings       |
| `c_str()`             | Convert to C-style string |
| `+`                   | Concatenate               |
| `[]`                  | Access character          |

---

## 🔸 Example 3: String Length, Access

```cpp id="s4"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Raihan";
    cout << "Length: " << s.length() << endl;

    for(int i=0; i<s.length(); i++){
        cout << s[i] << " ";
    }

    return 0;
}
```

### 🔹 Output

```
Length: 6
R a i h a n
```

---

## 🔸 Example 4: String Concatenation

```cpp id="s5"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string first = "Hello";
    string second = "World";

    string result = first + " " + second;
    cout << result << endl;

    return 0;
}
```

### 🔹 Output

```
Hello World
```

---

## 🔸 Example 5: Substring & Find

```cpp id="s6"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Programming";

    cout << s.substr(0, 6) << endl; // 0 index থেকে 6 char
    cout << s.find("gram") << endl; // substring index

    return 0;
}
```

### 🔹 Output

```
Progra
3
```

---

## 🔸 Example 6: Compare Strings

```cpp id="s7"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s1 = "Apple";
    string s2 = "Banana";

    if(s1.compare(s2) == 0)
        cout << "Equal" << endl;
    else
        cout << "Not Equal" << endl;

    return 0;
}
```

### 🔹 Output

```
Not Equal
```

---

## 🔹 Explanation


---

## 🔹 Key Points

* `+` → concatenate
* `[]` → access char
* `.length()` / `.size()` → length
* `.substr()` → substring
* `.find()` → substring search
* `.compare()` → compare

---

# 📘 String Modifiers in C++

---

**String modifiers** হলো এমন কিছু function যেগুলো string এর **value change (modify)** করে।

👉 সহজভাবে:
**Modify = string পরিবর্তন করা**

---

## 🔹 Common String Modifier Functions

| Function      | Description                     |
| ------------- | ------------------------------- |
| `append()`    | string এর শেষে add করে          |
| `insert()`    | নির্দিষ্ট position এ insert করে |
| `erase()`     | কিছু অংশ delete করে             |
| `replace()`   | অংশ পরিবর্তন করে                |
| `clear()`     | পুরো string empty করে           |
| `push_back()` | শেষে একটি character add করে     |
| `pop_back()`  | শেষ character remove করে        |

---

## 🔸 Example 1: `append()`

```cpp id="m1"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Hello";

    s.append(" World");
  s.insert(3, "l"); // position 3 এ "l" insert

    cout << s << endl;

    return 0;
}
```

### 🔹 Output

```
Hello World
```

---

# 📘 String Iteration in C++ (With `begin()` & `end()`)

---

**String iteration** মানে হলো string এর প্রতিটি character এক এক করে access করা।

👉 সহজভাবে:
**Iteration = একে একে সব character ঘোরা**

---

## 🔹 What are `begin()` and `end()`?

* `begin()` → string এর **first character এর pointer/iterator**
* `end()` → string এর **last character এর পরের position**

👉 গুরুত্বপূর্ণ:

* `end()` কখনো direct access করা যায় না
* এটা loop stop করার জন্য use হয়

---

## 🔸 Example: Basic Understanding

```cpp id="b1"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "ABC";

    cout << *s.begin() << endl;  // first character
    cout << *(s.end() - 1) << endl; // last character

    return 0;
}
```

### 🔹 Output

```
A
C
```

---

## 🔹 Explanation

* `*s.begin()` → first character
* `s.end()` → last এর পরের address
* তাই last পেতে `end() - 1` করতে হয়

---

## 🔸 Method: Iterator দিয়ে Loop

```cpp id="b2"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Raihan";

    for(string::iterator it = s.begin(); it != s.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

---

## 🔸 Reverse Iteration (use more) 

```cpp id="b3"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s = "Hello";

    for(auto it = s.end() - 1; it >= s.begin(); it--) {
        cout << *it << " ";
    }

    return 0;
}
```

### 🔹 Output

```
o l l e H
```

---
# 📘 String Input with Space in C++

---

`cin >>` ব্যবহার করলে string input নেওয়ার সময় **space পর্যন্তই পড়ে**, এরপর stop হয়ে যায়।

👉 Example:

```cpp
string name;
cin >> name;
```

### ❌ Input:

```
Raihan Islam
```

### ❌ Output:

```
Raihan
```

---

## 🔹 Solution: Use `getline()`

👉 `getline()` পুরো line (space সহ) input নেয়

---

## 🔸 Syntax

```cpp
getline(cin, variableName);
```

---

---

## 🔸 Multiple Word Input

```cpp
#include<iostream>
#include<string>
using namespace std;

int main() {
    string sentence;

    getline(cin, sentence);

    cout << sentence << endl;

    return 0;
}
```

---
# 📘 StringStream in C++ (`stringstream`)

---

`stringstream` হলো C++ এর একটি class যা **string কে stream (input/output) এর মতো ব্যবহার করতে দেয়**।

👉 সহজভাবে:
**stringstream = string কে cin/cout এর মতো ব্যবহার করা**


## 🔸 Syntax

```cpp
stringstream ss(stringName);
```

---



## 🔸 Example 3: Split String (Very Important 🔥)

```cpp id="ss3"
#include<iostream>
#include<sstream>
using namespace std;

int main() {
    string s = "I love C++ programming";
    

    stringstream ss(s);
    string word;

    while(ss >> word) {
        cout << word << endl;
    }

    return 0;
}
```

### 🔹 Output

```
I
love
C++
programming
```

---

## 🔹 Explanation

* `ss >> word` → space অনুযায়ী word আলাদা করে
* loop দিয়ে সব word পাওয়া যায়

---

## 🔸 Example 4: Sum of Numbers from String

```cpp id="ss4"
#include<iostream>
#include<sstream>
using namespace std;

int main() {
    string s = "10 20 30";
    int x, sum = 0;

    stringstream ss(s);

    while(ss >> x) {
        sum += x;
    }

    cout << sum << endl;

    return 0;
}
```

### 🔹 Output

```
60
```

---

## 🔹 Important Notes

* `>>` → extract data
* `<<` → insert data
* space automatically handle করে
* parsing এর জন্য খুব powerful

---
# 📘 String Constructor in C++

---

## 🔹 What is String Constructor?

C++ এ `string` class এর **constructor** ব্যবহার করে আমরা বিভিন্নভাবে string initialize করতে পারি।

👉 সহজভাবে:
**Constructor দিয়ে string create & initialize করা হয়**

---

## 🔹 Common Types of String Constructor

| Type                  | Description           |
| --------------------- | --------------------- |
| Default               | Empty string তৈরি করে |
| Direct Initialization | সরাসরি value assign   |
| Copy Constructor      | অন্য string copy করে  |
| Repeated Character    | একই character বারবার  |
| Substring Constructor | অন্য string এর অংশ    |

---

## 🔸 1️⃣ Default Constructor

```cpp id="sc1"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s;
    cout << "Value: " << s << endl;
    cout << "Size: " << s.size() << endl;
    return 0;
}
```

### 🔹 Output

```
Value:
Size: 0
```

👉 empty string তৈরি হয়

---

## 🔸 2️⃣ Direct Initialization

```cpp id="sc2"
string s = "Hello";
```

অথবা

```cpp id="sc3"
string s("Hello");
```

---

## 🔸 3️⃣ Copy Constructor

```cpp id="sc4"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s1 = "Raihan";
    string s2(s1); // copy

    cout << s2 << endl;

    return 0;
}
```

---

## 🔸 4️⃣ Repeated Character Constructor

```cpp id="sc5"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s(5, 'A'); // 5 times 'A'

    cout << s << endl;

    return 0;
}
```

### 🔹 Output

```
AAAAA
```

---

## 🔸 5️⃣ Substring Constructor

```cpp id="sc6"
#include<iostream>
#include<string>
using namespace std;

int main() {
    string s1 = "Programming";

    string s2(s1, 0, 6); // index 0 থেকে 6 char

    cout << s2 << endl;

    return 0;
}
```

### 🔹 Output

```
Progra
```

---

## 🔹 Explanation

* `string s;` → empty string
* `string s("Hello")` → value assign
* `string s2(s1)` → copy
* `string(5, 'A')` → repeat char
* `string(s1, start, length)` → substring

---


---
# 📘 String Sort & Range-Based For Loop in C++

---

C++ এ string কে **character অনুযায়ী sort** করা যায় `sort()` function ব্যবহার করে।

---

## 🔸 Syntax

```cpp
sort(s.begin(), s.end());
```

👉 এটা string কে **ascending order (A → Z)** এ sort করে

---

## 🔸 Example 1: Ascending Sort

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
    string s = "dcba";

    sort(s.begin(), s.end());

    cout << s << endl;

    return 0;
}
```

### 🔹 Output

```
abcd
```

---

# 🔄 Range-Based For Loop

এটা একটি **easy loop system** যা container (string, array, vector) সহজে iterate করতে সাহায্য করে।

👉 Syntax:

```cpp
for(dataType var : container)
```

---

## 🔸 Example 4: Basic Range Loop

```cpp
#include<iostream>
using namespace std;

int main() {
    string s = "Hello";

    for(char c : s) {
        cout << c << " ";
    }

    return 0;
}
```

### 🔹 Output

```
H e l l o
```


# 📘 Reverse Function

---

C++ এ `reverse()` হলো একটি built-in function যা **array, string, vector ইত্যাদি উল্টো (reverse)** করে দেয়।

👉 সহজভাবে:
**reverse = সামনে থেকে পিছনে করে দেওয়া**

---

## 🔹 Syntax

```cpp id="rvs2"
reverse(start, end);
```

👉 Example:

```cpp id="rvs3"
reverse(s.begin(), s.end());
```

---

## 🔸 Example 1: Reverse String

```cpp id="rvs4"
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
    string s = "hello";

    reverse(s.begin(), s.end());

    cout << s << endl;

    return 0;
}
```

### 🔹 Output

```id="rvs5"
olleh
```

---

## 🔸 Example 2: Reverse Array

```cpp id="rvs6"
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
    int arr[] = {1, 2, 3, 4, 5};

    reverse(arr, arr + 5);

    for(int i = 0; i < 5; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

### 🔹 Output

```id="rvs7"
5 4 3 2 1
```

---
# 📘 Copy Dynamic Object Example in C++

---

```cpp
#include<bits/stdc++.h>
using namespace std;

class footballer {
public:
    string country;
    int jersey;

    footballer(string country, int jersey) {
        this->country = country;
        this->jersey = jersey;
    }
};

int main() {

    footballer* messi = new footballer("Argentina", 10);
    footballer* ronaldo = new footballer("Portugal", 7);

    *messi = *ronaldo;  // object copy

    delete ronaldo;

    cout << messi->country << " " << messi->jersey << endl;

    return 0;
}
```

---

## 🔹 Output

```
Portugal 7
```

---

## 🔹 Step-by-Step Explanation (Bangla)

### ✅ Step 1: Dynamic Object Create

```cpp
footballer* messi = new footballer("Argentina", 10);
footballer* ronaldo = new footballer("Portugal", 7);
```

* `messi` → Argentina, 10
* `ronaldo` → Portugal, 7

---

### ✅ Step 2: Copy Operation

```cpp
*messi = *ronaldo;
```

👉 এখানে:

* `*messi` → messi object
* `*ronaldo` → ronaldo object

👉 এর মানে:
**ronaldo এর data messi তে copy হচ্ছে**

---

### 🔹 After Copy:

* `messi` → Portugal, 7
* `ronaldo` → Portugal, 7

---

### ✅ Step 3: Delete Object

```cpp
delete ronaldo;
```

👉 `ronaldo` object delete হয়ে গেছে
👉 কিন্তু `messi` safe আছে (কারণ এটা আলাদা memory)

---

### ✅ Step 4: Output

```cpp
cout << messi->country << " " << messi->jersey;
```

👉 Output:

```
Portugal 7
```

---

## 🔹 Important Concept 🔥

### 👉 This is NOT pointer copy

```cpp
*messi = *ronaldo;
```

✔️ Object copy (value copy)
❌ Pointer copy না

---

### ❌ Wrong (Pointer Copy)

```cpp
messi = ronaldo;
```

👉 Problem:

* দুইটা pointer একই address point করবে
* delete করলে crash হতে পারে

---

## 🔹 Why this code is SAFE?

* এখানে pointer না, object copy হয়েছে
* class এ pointer member নেই
* তাই shallow copy issue নাই

---

## 🔹 When it becomes DANGEROUS ⚠️

👉 যদি class এর ভিতরে pointer থাকে:

```cpp
int *data;
```

👉 তখন:

* shallow copy হবে
* same memory share করবে
* crash / memory leak হতে পারে

---







