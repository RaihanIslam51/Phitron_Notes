
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

# 📘 Pointer Reference in C++

---

Pointer reference মানে হলো **pointer ব্যবহার করে function এর মাধ্যমে original variable change করা**।

👉 এটা এক ধরনের **pass by address**

---

## 🔸 Example Code

```cpp
#include<iostream>
using namespace std;

void changePointer(int* p) {
    *p = 100;
}

int main() {
    int a = 10;
    int* p = &a;

    cout << "Before: " << *p << endl;

    changePointer(p);

    cout << "After: " << *p << endl;


}
```
---
Before: 10
After: 100
---
