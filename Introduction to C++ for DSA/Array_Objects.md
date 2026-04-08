# 📘 Array of Objects in C++

---

**Array of Objects** মানে হলো একই class এর একাধিক object একসাথে array আকারে রাখা।

👉 সহজভাবে:
**Object গুলাকে array তে store করা**

---

## 🔹 Why use Array of Objects?

* একাধিক data একসাথে manage করতে
* clean & structured code লিখতে
* real-life data (student, product, etc.) handle করতে

---

## 🔸 Syntax

```cpp
ClassName arrayName[size];
```

👉 Example:

```cpp
Student s[3];
```
## 🔹 Memory Visualization (Concept)

```
Index     Object        Data
--------------------------------
s[0]  →  Student  →  name, id
s[1]  →  Student  →  name, id
s[2]  →  Student  →  name, id
```

---

## 🔹 More Detailed View

```
s[0] → [ name = "Raihan" | id = 101 ]
s[1] → [ name = "Karim"  | id = 102 ]
s[2] → [ name = "Sumon"  | id = 103 ]
```

---
---

## 🔸 Example 1: Basic Array of Objects

```cpp


#include<iostream>
using namespace std;

class student{
public:
    string name;
    int marks;
    int roll;
}; 

int main() {
    int n;
    cin >> n;

    student a[n];

    // input
    for(int i = 0; i < n; i++){
        cin.ignore();
        getline(cin,a[i].name); //space shoho name ar jonno
        cin >>  a[i].marks >> a[i].roll;
    }

    // output
    for(int i = 0; i < n; i++){
        cout << a[i].name << " " 
             << a[i].marks << " " 
             << a[i].roll << endl;
    }

    return 0;
}
```
nb . construct use kori object a short korar jonno r akhane direct acces korteci lagbe na

## 🔸 Example 3: Array of Objects with Constructor

```cpp
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    Student() {} // default constructor

    Student(string n, int i) {
        name = n;
        id = i;
    }

    void show() {
        cout << name << " " << id << endl;
    }
};

int main() {
    Student s[2] = {
        Student("Raihan", 101),
        Student("Karim", 102)
    };

    for(int i = 0; i < 2; i++) {
        s[i].show();
    }

    return 0;
}
```
# 📘 Min & Max Operation on Array of Objects in C++

---

## 🔹 Problem Idea

একটি student array দেওয়া আছে, আমাদের কাজ:

* **Maximum marks student খুঁজে বের করা**
* **Minimum marks student খুঁজে বের করা**

---

## 🔸 Given Structure

```cpp
class student{
public:
    string name;
    int marks;
    int roll;
};
```

---

## 🔸 Full Code (Min & Max)

```cpp id="mm1"
#include<iostream>
using namespace std;

class student{
public:
    string name;
    int marks;
    int roll;
}; 

int main() {
    int n;
    cin >> n;

    student a[n];

    // input
    for(int i = 0; i < n; i++){
        cin.ignore();
        getline(cin, a[i].name);
        cin >> a[i].marks >> a[i].roll;
    }

    // assume first student is min & max
    student minStudent = a[0];
    student maxStudent = a[0];

    // finding min & max
    for(int i = 1; i < n; i++){
        if(a[i].marks < minStudent.marks){
            minStudent = a[i];
        }

        if(a[i].marks > maxStudent.marks){
            maxStudent = a[i];
        }
    }

    // output
    cout << "Min Marks Student:\n";
    cout << minStudent.name << " "
         << minStudent.marks << " "
         << minStudent.roll << endl;

    cout << "\nMax Marks Student:\n";
    cout << maxStudent.name << " "
         << maxStudent.marks << " "
         << maxStudent.roll << endl;

    return 0;
}
```

---

## 🔹 Explanation (Bangla)

### ✅ Step 1: Input নেওয়া

* `getline()` → name (space সহ)
* `cin >>` → marks & roll

---

### ✅ Step 2: Initial ধরা

```cpp
student minStudent = a[0];
student maxStudent = a[0];
```

👉 প্রথম student কে min & max ধরা হয়েছে

---

### ✅ Step 3: Loop দিয়ে compare

```cpp
if(a[i].marks < minStudent.marks)
```

👉 ছোট marks → update min

```cpp
if(a[i].marks > maxStudent.marks)
```

👉 বড় marks → update max

---

### ✅ Step 4: Output

👉 শেষে min & max student print করা হয়েছে

---

## 🔹 Visualization

```text
Students:
[Raihan, 85]
[Karim, 90]
[Sumon, 70]

Min → Sumon (70)
Max → Karim (90)
```

---


# 📘 Sort Array of Objects in C++

---

আমরা একটি **array of objects (student)** কে sort করতে চাই
👉 যেমন: marks অনুযায়ী ascending / descending

---

## 🔸 Class Structure

```cpp id="so1"
class student{
public:
    string name;
    int marks;
    int roll;
};
```

---

## 🔹 Why Comparator Needed?

👉 C++ সরাসরি object compare করতে পারে না
👉 তাই আমরা **custom comparator function** ব্যবহার করি

---

## 🔸 Example 1: Sort by Marks (Ascending)

```cpp id="so2"
#include<iostream>
#include<algorithm>
using namespace std;

class student{
public:
    string name;
    int marks;
    int roll;
};

bool cmp(student a, student b){
    return a.marks < b.marks; // ascending
}

int main() {
    int n;
    cin >> n;

    student a[n];

    // input
    for(int i = 0; i < n; i++){
        cin.ignore();
        getline(cin, a[i].name);
        cin >> a[i].marks >> a[i].roll;
    }

    // sort
    sort(a, a + n, cmp);

    // output
    for(int i = 0; i < n; i++){
        cout << a[i].name << " "
             << a[i].marks << " "
             << a[i].roll << endl;
    }

    return 0;
}
```

---

## 🔹 Explanation 

### ✅ Comparator Function

```cpp id="so3"
return a.marks < b.marks;
```

👉 ছোট marks আগে আসবে → ascending order

---

## 🔸 Example 2: Sort by Marks (Descending)

```cpp id="so4"
bool cmp(student a, student b){
    return a.marks > b.marks;
}
```

👉 বড় marks আগে → descending

---

## 🔸 Example 3: Sort by Multiple Condition 🔥

👉 marks same হলে roll দিয়ে sort

```cpp id="so5"
bool cmp(student a, student b){
    if(a.marks == b.marks){
        return a.roll < b.roll; // tie breaker
    }
    return a.marks > b.marks;
}
```

---

## 🔹 Visualization

```text id="so6"
Before Sort:
[Raihan, 85]
[Karim, 90]
[Sumon, 70]

After Sort (Ascending):
[Sumon, 70]
[Raihan, 85]
[Karim, 90]
```





---

