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



