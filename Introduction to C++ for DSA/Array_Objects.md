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



---

