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
# 📌 Memory Allocation in C++

Memory allocation বলতে বোঝায় program execution এর সময় variable বা data রাখার জন্য memory reserve করা।

C++ এ memory allocation দুইভাবে হয়:

* 🔹 Static Memory Allocation (Compile Time)
* 🔹 Dynamic Memory Allocation (Run Time)

---

# 🔹 1. Static Memory Allocation (Compile Time)

👉 Program compile হওয়ার সময় memory allocate হয়।

👉 এই memory মূলত থাকে:

* Stack
* stack automatic data clear kore dei ata big problem

---

## 🔸 Stack Memory

👉 Stack memory ব্যবহার হয়:

* Local variables
* Function parameters
* Function call (Call Stack)

### ✨ Features:

* Compile time allocation
* খুব fast
* Automatically manage হয় (LIFO - Last In First Out)

### 📌 Example:

```cpp
#include<iostream>
using namespace std;

int main() {
    int x = 10;  // stack memory
    int y = 20;
    cout << x + y;
}
```

---

```cpp
#include<iostream>
using namespace std;

int x = 100; // global variable

int main() {
    static int y = 50; // static variable
    cout << x + y;
}
```

### 🧠 Explanation:

* Program শুরুতেই allocate হয়
* Program শেষ না হওয়া পর্যন্ত থাকে

---

# 🔹 2. Dynamic Memory Allocation (Run Time)

👉 Program run হওয়ার সময় memory allocate করা হয়।
## Advantace 
1.memory size barano jai
2.function return korleo paoa jai but static jeta paoa jai na

👉 এই memory থাকে:

* Heap Memory

---

## 🔸 Heap Memory

👉 Heap memory manually manage করতে হয়।

### ✨ Features:

* Run time allocation
* Flexible size
* Slow compared to stack
* Manual memory management

---

## 📌 Using `new` and `delete`

### Example:

```cpp
#include<iostream>
using namespace std;

int main() {
    int* ptr = new int; // allocate memory in heap
    *ptr = 25;

    cout << *ptr << endl;

    delete ptr; // free memory
}
```

---

## 📌 Dynamic Array Example:

```cpp
#include<iostream>
using namespace std;

int main() {
    int n;
    cin >> n;

    int* arr = new int[n]; // dynamic array

    for(int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    delete[] arr; // free memory
}
```

---

# 🔥 Stack vs Heap (Important Table)

| Feature         | Stack        | Heap                 |
| --------------- | ------------ | -------------------- |
| Allocation Time | Compile Time | Run Time             |
| Speed           | Fast         | Slow                 |
| Size            | Limited      | Large                |
| Management      | Automatic    | Manual               |
| Risk            | Low          | Memory Leak possible |

---

# ⚠️ Memory Leak

👉 Heap memory free না করলে memory leak হয়।

### ❌ Wrong:

```cpp
int* ptr = new int;
// delete ptr; (missing)
```

### Dynamic array size increse

```cpp
#include<iostream>
using namespace std;

int main() {
    int* a = new int[3];

    for(int i = 0; i < 3; i++){
        cin >> a[i];
    }

    int* b = new int[5];

    
    for(int i = 0; i < 3; i++) {
        b[i] = a[i];
    }

    
    b[3] = 40;
    b[4] = 50;
    delete[] a;

    
    for(int i = 0; i < 5; i++) {
        cout << b[i] << " ";
    }

    return 0;
}
```

---

# 📘 Class & Object (User Defined Data Type)

---

A **Class** হলো একটি **user-defined data type** যা variables (data) এবং functions (behavior) একসাথে রাখে।

👉 সহজভাবে:
**Class = Blueprint (নকশা)**

🧠 উদাহরণ:
“Student” একটি class হতে পারে, যেখানে name, id, marks থাকবে।

---

## 🔹 Syntax of Class

```cpp
class ClassName {
public:
    // data members
    // member functions
};
```

---

## 🔹 What is an Object?

**Object** হলো class এর একটি instance (বাস্তব রূপ)

👉 সহজভাবে:
**Object = বাস্তব জিনিস (Class থেকে তৈরি)**

---

## 🔹 Real Life Example

* Class = Student
* Object = Rahim, Karim

---

## 🔸 Full Example Code (2 Student Data)

```cpp
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;
    float marks;

    void display() {
        cout << "Name: " << name << endl;
        cout << "ID: " << id << endl;
        cout << "Marks: " << marks << endl;
        cout << "----------------------" << endl;
    }
};

int main() {

    // Object create
    Student s1, s2;

    // Student 1 data
    s1.name = "Raihan";
    s1.id = 101;
    s1.marks = 85.5;

    // Student 2 data
    s2.name = "Karim";
    s2.id = 102;
    s2.marks = 90.0;

    // Display data
    s1.display();
    s2.display();

    return 0;
}
```

---

## 🔹 Explanation

* `class Student` → নতুন data type তৈরি
* `name, id, marks` → data members
* `display()` → function
* `Student s1, s2` → 2টি object তৈরি
* `s1.name` → object দিয়ে data access

---

## 🔸 Why Class is User Defined Data Type?

👉 কারণ:

* আমরা নিজেরা নতুন data type তৈরি করি
* যেমন: `int`, `float` built-in
* তেমনি `Student` হলো custom type

```cpp
Student s1, s2;
```

---

## 🔹 Access Specifiers

| Type      | Meaning                         |
| --------- | ------------------------------- |
| public    | সবাই access করতে পারবে          |
| private   | শুধু class এর ভিতরে             |
| protected | derived class access করতে পারবে |

---

---
# 📘 Constructor (OOP Concept)

---

A **Constructor** হলো একটি special function যা **object তৈরি হওয়ার সাথে সাথে automatically call হয়**।

👉 সহজভাবে:
**Constructor = object তৈরি হলে automatic run or call হওয়া function**
N.B : CONSTRUCTOR use korar karon hosce object ta komano jokhon onk student lagbe tokhon use korbo r na hole normally object


---

## 🔹 Key Features of Constructor

* Function name = Class name
* No return type (even not void)
* Automatically called
* Used to initialize object

---

## 🔸 Syntax

```cpp id="c1"
class ClassName {
public:
    ClassName() {
        // initialization code
    }
};
```

---

## 🔸 Example (Default Constructor)

```cpp id="c2"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    Student() {
        cout << "Constructor called!" << endl;
    }
};

int main() {
    Student s1;  // constructor auto call
    return 0;
}
```

---

## 🔹 Explanation (Bangla)

* `Student()` → constructor
* object create হলেই run হয়
* manually call করতে হয় না

---

## 🔸 Parameterized Constructor

👉 যখন constructor এ parameter থাকে

```cpp id="c3"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    Student(string n, int i) {
        name = n;
        id = i;
    }

    void display() {
        cout << name << " " << id << endl;
    }
};

int main() {
    Student s1("Raihan", 101);
    Student s2("Karim", 102);

    s1.display();
    s2.display();

    return 0;
}
```

---

## 🔹 Explanation

* constructor এ value pass করা হয়েছে
* object create করার সময়ই data set হচ্ছে

---

## 🔸 Types of Constructor

### 1️⃣ Default Constructor

No parameter

### 2️⃣ Parameterized Constructor

With parameter

### 3️⃣ Copy Constructor

এক object থেকে অন্য object copy করা

---

## 🔸 Copy Constructor Example

```cpp id="c4"
#include<iostream>
using namespace std;

class Student {
public:
    string name;

    Student(string n) {
        name = n;
    }

    // Copy Constructor
    Student(const Student &s) {
        name = s.name;
    }
};

int main() {
    Student s1("Raihan");
    Student s2 = s1;  // copy

    cout << s2.name << endl;

    return 0;
}
```

---

## 🔹 Why Constructor is Important?

* Object initialization easy করে
* Code clean হয়
* Automatic execution

---
# 📘 `this` Keyword in C++

---

`this` হলো একটি **pointer** যা current object কে নির্দেশ করে।

👉 সহজভাবে:
**this = current object এর address**

---

## 🔹 Why we use `this`?

* Same name variable distinguish করতে
* Current object refer করতে
* Function chaining করতে

---

## 🔸 Basic Syntax

```cpp id="t1"
this->variableName
```

---

## 🔸 Example 1: Same Name Variable Problem Solve

```cpp id="t2"
#include<iostream>
using namespace std;

class Student {
public:
    string name;

    Student(string name) {
        this->name = name; // this->name (class variable)
    }

    void display() {
        cout << name << endl;
    }
};

int main() {
    Student s1("Raihan");
    s1.display();

    return 0;
}
```

---

## 🔹 Explanation

* `name = name` লিখলে confusion হয়
* `this->name` → class variable
* `name` → parameter
  👉 তাই `this` ব্যবহার করা হয়েছে

---

## 🔸 Example 2: Return Current Object (Method Chaining)

```cpp id="t3"
#include<iostream>
using namespace std;

class Test {
public:
    int x;

    Test(int x) {
        this->x = x;
    }

    Test& setX(int x) {
        this->x = x;
        return *this;
    }

    void show() {
        cout << x << endl;
    }
};

int main() {
    Test t1(10);

    t1.setX(20).show(); // chaining

    return 0;
}
```

---

## 🔹 Explanation

* `return *this` → current object return করে
* তাই chain করে function call করা যায়

---

## 🔸 Important Notes

* `this` is a pointer
* `this->x` মানে pointer দিয়ে access
* Only class member function এর ভিতরে use হয়
* Static function এ `this` থাকে না

---
# 📘 Returning Object from Function

---

C++ এ একটি function থেকে **object return করা যায়**, ঠিক যেমন আমরা int, float return করি।

👉 সহজভাবে:
**Function → object return করতে পারে**

---

## 🔸 Example 1: Simple Object Return

```cpp id="r2"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;
};

Student createStudent() {
    Student s;
    s.name = "Raihan";
    s.id = 101;
    return s; // object return
}

int main() {
    Student s1 = createStudent();

    cout << s1.name << " " << s1.id << endl;

    return 0;
}
```

---

## 🔹 Explanation

* `createStudent()` → function
* ভিতরে object `s` তৈরি হয়েছে
* শেষে `return s` → object return করছে
* `s1` এ সেই object store হচ্ছে

---

## 🔸 Example 2: Return Object with Constructor

```cpp id="r3"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    Student(string n, int i) {
        name = n;
        id = i;
    }
};

Student getStudent() {
    return Student("Karim", 102); // temporary object return
}

int main() {
    Student s2 = getStudent();

    cout << s2.name << " " << s2.id << endl;

    return 0;
}
```

---

## 🔹 Explanation

* এখানে সরাসরি constructor দিয়ে object return করা হয়েছে
* Temporary object তৈরি হয়ে return হচ্ছে

---

## 🔸 Example 3: Return Object from Function (Calculation)

```cpp id="r4"
#include<iostream>
using namespace std;

class Number {
public:
    int value;

    Number(int v) {
        value = v;
    }
};

Number add(Number n1, Number n2) {
    return Number(n1.value + n2.value);
}

int main() {
    Number a(10), b(20);

    Number result = add(a, b);

    cout << result.value << endl;

    return 0;
}
```

---

## 🔹 Explanation (Bangla)

* দুইটা object নিয়ে calculation করা হয়েছে
* নতুন object return করা হয়েছে

---

# 📘 Dynamic Object in C++

---

যে object **runtime এ memory allocate করে (`new` keyword দিয়ে)** তৈরি করা হয়, তাকে **Dynamic Object** বলে।

👉 সহজভাবে:
**Dynamic Object = Heap memory তে তৈরি object**

---

## 🔹 Why use Dynamic Object?

* Runtime এ object তৈরি করতে
* Memory efficient করতে
* Large data handle করতে
* Pointer ব্যবহার করে control নিতে

---

## 🔸 Syntax

```cpp id="d1"
ClassName *ptr = new ClassName();
```

---

## 🔸 Example 1: Basic Dynamic Object

```cpp id="d2"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    void display() {
        cout << name << " " << id << endl;
    }
};

int main() {

    // Dynamic object create
    Student *s1 = new Student();

    s1->name = "Raihan";
    s1->id = 101;

    s1->display();

    return 0;
}
```

---

## 🔹 Explanation

* `new Student()` → heap এ object তৈরি
* `s1` → pointer (object এর address ধরে)
* `->` → pointer দিয়ে access

---

## 🔸 Example 2: Dynamic Object with Constructor

```cpp id="d3"
#include<iostream>
using namespace std;

class Student {
public:
    string name;
    int id;

    Student(string n, int i) {
        name = n;
        id = i;
    }

    void show() {
        cout << name << " " << id << endl;
    }
};

int main() {

    Student *s2 = new Student("Karim", 102);

    s2->show();

    return 0;
}
```

---

## 🔹 Explanation 

* Constructor call হচ্ছে `new` এর সাথে
* Direct value pass করা হয়েছে

---

## 🔸 Example 3: Multiple Dynamic Objects

```cpp id="d4"
#include<iostream>
using namespace std;

class Test {
public:
    int x;

    Test(int x) {
        this->x = x;
    }

    void show() {
        cout << x << endl;
    }
};

int main() {

    Test *t1 = new Test(10);
    Test *t2 = new Test(20);

    t1->show();
    t2->show();

    return 0;
}
```

## 🔹 Memory Concept

* Stack → normal object
* Heap → dynamic object (`new`)

---

## 🔹 Real Life Idea

👉 ধরো:

* App run হওয়ার সময় user যত object লাগবে তত create হবে
* আগে থেকে fixed না

---
# 📘 Sort Function in C++ (`sort()`)

---

C++ এ `sort()` হলো একটি **built-in function** যা array বা vector কে **ascending বা descending order এ সাজায়**।


---

## 🔹 Basic Syntax

```cpp
sort(start, end);
```

---

## 🔸 Example 1: Sort Array (Ascending)

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
    int arr[] = {5, 2, 9, 1, 3};
    int n = 5;

    sort(arr, arr + n);

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

### 🔹 Output

```
1 2 3 5 9
```

---

## 🔸 Example 2: Sort Array (Descending)

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

int main() {
    int arr[] = {5, 2, 9, 1, 3};
    int n = 5;

    sort(arr, arr + n, greater<int>());

    for(int i = 0; i < n; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

### 🔹 Output

```
9 5 3 2 1
```

---

## 🔸 Example 3: Sort Vector

```cpp
#include<iostream>
#include<vector>
#include<algorithm>
using namespace std;

int main() {
    vector<int> v = {10, 4, 8, 2};

    sort(v.begin(), v.end());

    for(int x : v) {
        cout << x << " ";
    }

    return 0;
}
```

---

## 🔸 Example 4: Custom Sort (Comparator)

```cpp
#include<iostream>
#include<algorithm>
using namespace std;

bool cmp(int a, int b) {
    return a > b; // descending
}

int main() {
    int arr[] = {7, 1, 5, 3};

    sort(arr, arr + 4, cmp);

    for(int i = 0; i < 4; i++) {
        cout << arr[i] << " ";
    }

    return 0;
}
```

---

## 🔹 Explanation

* `sort(arr, arr+n)` → ascending sort
* `greater<int>()` → descending
* comparator function দিয়ে custom rule বানানো যায়

---

















































