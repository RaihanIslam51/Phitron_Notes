# 🔄 Type Casting in C++

Type Casting হলো একটি প্রক্রিয়া যেখানে একটি data type কে অন্য একটি data type-এ convert করা হয়।

👉 সহজভাবে:
এক ধরনের ডেটাকে অন্য ধরনের ডেটায় রূপান্তর করা।

📍 উদাহরণ:
- `int → float`
- `float → int`
- `char → int`

---

Type Casting সাধারণত ২ ধরনের:

## 🔹 1. Implicit Type Casting (Automatic Type Conversion)

👉 Compiler নিজে থেকেই data type convert করে দেয়।

### 📍 Example:
```cpp
#include<iostream>
using namespace std;

int main(){
    int a = 10;
    float b = 5.5;

    float result = a + b;

    cout << result; // Output: 15.5
}
```
## 🔹 2. Explicit Type Casting (Manual Type Conversion)

👉 Programmer নিজে data type convert করে।

📍 Syntax:
```cpp
(type) value;

```

## 🔢 setprecision কী? (C++)

setprecision হলো C++-এর একটি formatting tool, যা ব্যবহার করা হয় floating point number (decimal number) কত ঘর পর্যন্ত দেখানো হবে তা নির্ধারণ করতে।
```cpp
#include<iostream>
#include<iomanip>
using namespace std;

int main(){
    float num = 3.14159265;

    cout <<fixed << setprecision(4) << num;
}
```
### ✅ Explanation (ব্যাখ্যা):
মোট 4টি significant digit দেখাবে
তাই 3.14159265 → 3.142

# 🔀 Ternary Operator in C++

---

Ternary Operator হলো একটি **short form of if-else statement**  
যেটা এক লাইনে condition check করে result return করে।

👉 একে `Conditional Operator` ও বলা হয়  
👉 এটি code ছোট ও concise করতে সাহায্য করে

---

## 🧠 Syntax (গঠন)

```cpp
condition ? expression1 : expression2;
```
```cpp
#include<iostream>
using namespace std;

int main(){
    int a = 10, b = 20;

    int max = (a > b) ? a : b;

    cout << "Max = " << max;
}

#include<iostream>
using namespace std;

int main(){
    int n = 7;

    (n % 2 == 0) ? cout << "Even" : cout << "Odd";
}

```
### 🧠 Output:
Max = 20
✅ Explanation:
condition: a > b → false
তাই b return হয়েছ
oেdd 

# 🔀 Switch Case in C++

---

`switch case` হলো একটি **multi-way decision making statement**  
যা একাধিক condition এর মধ্যে থেকে একটি execute করে।

👉 এটি `if-else if-else` এর alternative  
👉 যখন একই variable এর উপর multiple condition check করতে হয়, তখন ব্যবহার করা হয়

---

## 🧠 Syntax (গঠন)

```cpp
switch(expression){
    case value1:
        // code
        break;

    case value2:
        // code
        break;

    ...

    default:
        // code
}
```
### 🧾 Explanation (ব্যাখ্যা)
expression → যেটা check করা হবে
case → possible value
break → case শেষ হলে switch থেকে বের হয়ে যায়
default → কোন case match না করলে execute হয়

```cpp
#include<iostream>
using namespace std;

int main(){
    int day = 3;

    switch(day){
        case 1:
            cout << "Saturday";
            break;

        case 2:
            cout << "Sunday";
            break;

        case 3:
            cout << "Monday";
            break;

        default:
            cout << "Invalid Day";
    }
}
```
output : Monday

# 🔢 min, max, swap in C++

---

C++-এ `min`, `max`, এবং `swap` হলো built-in functions  
যেগুলো `<algorithm>` library এর মধ্যে থাকে।

👉 এগুলো ব্যবহার করে সহজেই:
- ছোট সংখ্যা বের করা (min)
- বড় সংখ্যা বের করা (max)
- দুইটি variable এর মান অদল-বদল করা (swap)

---

## 📦 Required Library

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

int main(){
    int a = 10, b = 20;

    cout << min(a, b); // Output: 10
    cout << min({10, 5, 20, 3}); // Output: 3
n   cout << max(a, b); // Output: 20

    swap(a, b);

    cout << "a = " << a << endl;
    cout << "b = " << b << endl;
}
```
| Feature | Built-in swap | Manual swap   |
| ------- | ------------- | ------------- |
| Code    | Short         | বড়            |
| Easy    | খুব সহজ       | একটু বেশি কাজ |
| Safe    | বেশি          | কম            |

⚠️ Important Notes (গুরুত্বপূর্ণ বিষয়)
<algorithm> include করতে হবে
min, max একই type এর value নেয়
swap variable এর value exchange করে
min/max multiple value নিতে {} ব্যবহার করা যায়

# 🔤 String in C++

---

String হলো **characters (অক্ষর)** এর একটি sequence বা ধারাবাহিকতা।

👉 সহজভাবে:
একটি word, sentence বা text কে string বলা হয়।

📍 Example:
- "Hello"
- "Raihan"
- "C++ Programming"

---

## 📦 Required Library

```cpp
#include<iostream>
#include<string>
using namespace std;

int main(){
    string name = "Raihan";

    cout << name;
}


```
``cpp
string name;
cin >> name;
```
⚠️ Problem:
space এর পরে input নেয় না

👉 Example:
Input: Raihan Islam
Output: Raihan

```cpp
string name;
getline(cin, name);
```
✅ Advantage:
full line (space সহ) input নেয়

🔹 String Length
```cpp
📌 size() / length()
string str = "Hello";
cout << str.length(); // Output: 5

```


🔹 Access Character (Character Access)
```cpp
string str = "Hello";

cout << str[0]; // H
cout << str[1]; // e
```
🔹 String Concatenation (String যোগ করা)
🔸 Using +
```cpp
string a = "Hello";
string b = "World";

string c = a + " " + b;

cout << c; // Hello World
```
🔹 String Functions (Important Functions)
🔸 1. append()
```cpp
string a = "Hello";

a.append(" World");

cout << a; // Hello World

string str = "Hello";

str.clear();

cout << str; // empty

```














































