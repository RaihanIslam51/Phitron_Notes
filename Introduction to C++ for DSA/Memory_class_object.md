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
