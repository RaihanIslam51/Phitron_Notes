
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


# 📘 Linked List Insert at Head with Visualization


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


void insert_at_head(Node* &head, int val) {
    Node* newNode = new Node(val);
    newNode->next = head;
    head = newNode;
}


void linkedlist_print(Node* head) {
    Node* temp = head;

    while(temp != NULL) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);

    head->next = a;
    a->next = b;

    insert_at_head(head, 100);
    insert_at_head(head, 200);

    linkedlist_print(head);

    return 0;
}
```

---

## 🔹 Visualization (Step by Step)

### 🔸 Step 1: Initial Linked List

```text
head
 ↓
[10] → [20] → [30] → NULL
```

---

### 🔸 Step 2: insert_at_head(head, 100)

```text
newNode = 100

newNode → head

[100] → [10] → [20] → [30] → NULL
 ↑
head
```

## 🔹 Traversal (Print Function)

```text
temp = head

Step 1 → 200
Step 2 → 100
Step 3 → 10
Step 4 → 20
Step 5 → 30
Step 6 → NULL (stop)
```

---

## 🎯 Output

```text
200 100 10 20 30
```

---

## 🎯 Key Idea

* Head সবসময় first node কে point করে
* Insert at head = new node সামনে বসানো
* Pointer দিয়ে সব node connect করা হয়

---

## ✅ Easy Trick

👉 মনে রাখো:

```text
newNode → head
head = newNode
```
# 📘 Linked List: Insert at Tail (with Visualization)

---

👉 Linked List এর **শেষে (last node এ)** নতুন node add করা।

---

## 🔹 Full Code

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

void insert_at_tail(Node* &head, int val) {
    Node* newNode = new Node(val);
      if(head == NULL) {
        head = newNode;
        return;
      }
    Node* temp = head;
    while(temp->next != NULL) {
        temp = temp->next;
     }
    temp->next = newNode;
}

void linkedlist_print(Node* head) {
    Node* temp = head;
   while(temp != NULL) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);

    head->next = a;
    a->next = b;

    insert_at_tail(head, 50);
    insert_at_tail(head, 60);

    linkedlist_print(head);

    return 0;
}
```

---

## 🔹 Visualization (Correct)

### 🔸 Step 1: Initial List

```text
head
 ↓
[10] → [20] → [30] → NULL
```

---

### 🔸 Step 2: insert_at_tail(head, 50)

```text
[10] → [20] → [30] → [50] → NULL
 ↑
head
```

---

### 🔸 Step 3: insert_at_tail(head, 60)

```text
[10] → [20] → [30] → [50] → [60] → NULL
 ↑
head
```

---

## 🔹 How it Works (Easy)

1. new node তৈরি করা হয়
2. temp দিয়ে last node খোঁজা হয়
3. last node এর `next` এ new node বসানো হয়

---

## 🎯 Output (Correct)

```text
10 20 30 50 60
```

---

## 🎯 Key Difference

| Insert Type    | Position |
| -------------- | -------- |
| insert_at_head | শুরুতে   |
| insert_at_tail | শেষে     |

---

## ✅ Easy Trick

👉 মনে রাখো:

```text
temp → last node
temp->next = newNode
```
# 📘 Linked List: Optimized Insert at Tail (O(1))

---

## 🔹 Problem (Normal Approach)

Normal insert at tail এ প্রতি বার:

* পুরো list traverse করতে হয় → **O(n)**

👉 বড় data হলে slow হয়ে যায়

---

## 🔹 Solution (Optimized)

👉 আমরা **tail pointer use করবো**
👉 তাই last node খুঁজতে হবে না

➡️ Time Complexity: **O(1)**

---

## 🔹 Full Code (Optimized Insert at Tail)

```cpp id="k9t2ab"
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


void insert_at_tail(Node* &head, Node* &tail, int val) {
    Node* newNode = new Node(val);
    if(head == NULL) {
        head = newNode;
        // tail = newNode;   
        return;
    }
    tail->next = newNode;
    tail = tail->next;
}


void linkedlist_print(Node* head) {
    Node* temp = head;

    while(temp != NULL) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* tail = new Node(30);

    head->next = a;
    a->next = tail;

    insert_at_tail(head, tail, 10);
    insert_at_tail(head, tail, 20);

    linkedlist_print(head);

    return 0;
}
```

---

## 🔹 Visualization

### 🔸 Step 1: Empty List

```text id="2g8f1q"
head → NULL
tail → NULL
```

---

### 🔸 Step 2: insert 10

```text id="w1p7qz"
head/tail
   ↓
 [10] → NULL
```

---

### 🔸 Step 3: insert 20

```text id="u8k3lm"
head
 ↓
[10] → [20] → NULL
         ↑
        tail
```

---

### 🔸 Step 4: insert 30

```text id="z6x9aa"
head
 ↓
[10] → [20] → [30] → NULL
                  ↑
                 tail
```

---

### 🔸 Step 5: insert 40

```text id="r3m8pt"
[10] → [20] → [30] → [40] → NULL
                          ↑
                         tail
```

---

## 🎯 Output

```text id="v7c9aa"
10 20 30 40
```

---

## 🎯 Complexity Comparison

| Method             | Time Complexity |
| ------------------ | --------------- |
| Normal insert tail | O(n)            |
| Optimized tail     | O(1) 🚀         |

---












# 📘 Linked List: Insert at Any Position (with Visualization)

---

👉 Linked List এর **যেকোনো position এ (middle / specific index)** নতুন node add করা।

---

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


void insert_at_position(Node* &head, int idx, int val) {

    Node* newNode = new Node(val);
    if(idx == 0) {
        newNode->next = head;
        head = newNode;
        return;
    }

    Node* temp = head;
    for(int i = 1; i < idx; i++) {
       //  if(temp == NULL) return;
        temp = temp->next;
    }
    newNode->next = temp->next;
    temp->next = newNode;
}


void linkedlist_print(Node* head) {
    Node* temp = head;

    while(temp != NULL) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);

    head->next = a;
    a->next = b;


    insert_at_position(head, 1, 100); // index 1
    insert_at_position(head, 3, 200); // index 3

    linkedlist_print(head);

    return 0;
}
```

---

## 🔹 Visualization

### 🔸 Step 1: Initial List

```text
[10] → [20] → [30] → NULL
```

---

### 🔸 Step 2: insert_at_position(head, 1, 100)

```text
[10] → [100] → [20] → [30] → NULL
```

👉 100 index 1 এ বসেছে

---

### 🔸 Step 3: insert_at_position(head, 3, 200)

```text
[10] → [100] → [20] → [200] → [30] → NULL
```

👉 200 index 3 এ বসেছে

---

## 🔹 How it Works (Easy)

1. new node তৈরি করা হয়
2. `(idx - 1)` node পর্যন্ত যাওয়া হয়
3. next pointer adjust করা হয়

---

## 🎯 Output

```text
10 100 20 200 30
```

---

## 🎯 Important Notes ⚠️

* `idx = 0` → head এ insert
* invalid position হলে insert হবে না
* pointer linking খুব important

---

## ✅ Easy Trick

👉 মনে রাখো:

```text
newNode->next = temp->next
temp->next = newNode
```

---
# 📘 Linked List Input in C++


আমরা user থেকে input নিবো যতক্ষণ না `-1` আসে।

👉 `-1` ব্যবহার করা হয়েছে stop signal হিসেবে (sentinel value)

---

## 🔹 Complete Code

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

void insert_at_tail(Node* &head, Node* &tail, int val) {
    Node* newNode = new Node(val);
    if(head == NULL) {
        head = newNode;
        tail = newNode;
        return;
    }
    tail->next = newNode;
    tail = newNode;
}

void linkedlist_print(Node* head) {
    Node* temp = head;

    while(temp != NULL) {
        cout << temp->val << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {

    Node* head = NULL;
    Node* tail = NULL;

    int val;
    while(true) {
        cin >> val;
        if(val == -1)
          break;
        insert_at_tail(head, tail, val);
    }
    linkedlist_print(head);

    return 0;
}
```

---

## 🔹 Example

### Input:

```
10 20 30 40 -1
```

### Output:

```
Linked List: 10 20 30 40
```

---

## 🔹 Visualization

```
Input: 10 20 30 40

Step 1: [10] -> NULL  
Step 2: [10] -> [20] -> NULL  
Step 3: [10] -> [20] -> [30] -> NULL  
Step 4: [10] -> [20] -> [30] -> [40] -> NULL  
```

---
# 📘 Linked List Reverse Print in C++

---

Reverse print মানে হলো Linked List-এর data গুলো **উল্টোভাবে print করা**।

👉 Normal:

```
10 20 30 40
```

👉 Reverse:

```
40 30 20 10
```

---

## 🔹 Method 1: Using Recursion (Best & Easy)

Recursion ব্যবহার করে খুব সহজে reverse print করা যায়।

---

## 🔹 Code Implementation

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


void reverse_print(Node* temp) {
   if(temp == NULL)
      return;
    reverse_print(temp->next);
    cout << temp->val << " ";
}


int main() {

    Node* head = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);
    Node* c = new Node(40);

    head->next = a;
    a->next = b;
    b->next = c;

    cout << "Reverse Print: ";
    reverse_print(head);

    return 0;
}
```

---

## 🔹 Output

```
Reverse Print: 40 30 20 10
```

---

## 🔹 How It Works (Bangla)

* Function প্রথমে শেষ node পর্যন্ত যায় (recursion দিয়ে)
* তারপর print শুরু করে **শেষ থেকে**
* তাই output reverse order এ আসে

👉 Flow:

```
10 → 20 → 30 → 40

Call Stack:
reverse(10)
 → reverse(20)
   → reverse(30)
     → reverse(40)
       → reverse(NULL)

Print:
40 30 20 10
```

---

## 🔹 Visualization

```
Original:
[10] -> [20] -> [30] -> [40] -> NULL

Reverse Print Output:
40 ← 30 ← 20 ← 10
```

---






