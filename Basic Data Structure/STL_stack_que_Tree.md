# 📘 STL `list` Constructor in C++

---

`list` হলো C++ STL-এর একটি **doubly linked list** container
যেখানে element গুলো memory-তে contiguous না হয়ে pointer দিয়ে connected থাকে।

👉 সুবিধা:

* Fast insertion & deletion
* Doubly linked list libery

---

# 🔸 1️⃣ Empty Constructor

```cpp
list<int> l;
```

🔍 Explanation (Bangla):

* একটি empty list তৈরি হয়
* পরে `push_back()` বা `push_front()` দিয়ে data add করা যায়

---

# 🔸 2️⃣ Size Constructor

```cpp
list<int> l(5);
```

🔍 Explanation:

* 5 টা element থাকবে
* default value = `0` (int type হলে)

👉 Output:

```
0 0 0 0 0
```

---

# 🔸 3️⃣ Size + Value Constructor

```cpp
list<int> l(5, 10);
```

🔍 Explanation:

* 5 টা element
* প্রতিটা value = 10

👉 Output:

```
10 10 10 10 10
```

---

# 🔸 4️⃣ Copy Constructor

```cpp
list<int> l1 = {1, 2, 3};
list<int> l2(l1);
```

🔍 Explanation:

* `l1` এর সব data `l2` তে copy হবে
* deep copy তৈরি হয়

---

# 🔸 5️⃣ Range Constructor + print

```cpp
list<int> l1 = {1, 2, 3, 4, 5};
list<int> l2(l1.begin(), l1.end());

for(auto it = l.begin(); it != l.end(); it++) {
 cout << *it << " ";
 }
```

🔍 Explanation:

* iterator ব্যবহার করে copy করা হয়
* চাইলে partial range ও copy করা যায়

---

# 🔸 6️⃣ Initializer List Constructor

```cpp
list<int> l = {10, 20, 30};
```

🔍 Explanation:

* সরাসরি value দিয়ে list initialize করা যায়
* modern এবং সহজ method

---

# 🔹 Full Example Code

```cpp
#include<iostream>
#include<list>
using namespace std;

int main() {

    // Empty
    list<int> l1;

    // Size
    list<int> l2(5);

    // Size + Value
    list<int> l3(5, 10);

    // Initializer
    list<int> l4 = {1, 2, 3};

    // Copy
    list<int> l5(l4);

    // Range
    list<int> l6(l4.begin(), l4.end());

    // Print example (l3)
    for(int val : l3) {
        cout << val << " ";
    }

    return 0;
}
```

---

# 🔥 Summary

| Constructor Type | Syntax                     | Description                |
| ---------------- | -------------------------- | -------------------------- |
| Empty            | `list<int> l;`             | Empty list                 |
| Size             | `list<int> l(n);`          | n elements (default value) |
| Size + Value     | `list<int> l(n, val);`     | n elements with value      |
| Copy             | `list<int> l2(l1);`        | Copy list                  |
| Range            | `list<int> l(begin, end);` | Copy using iterator        |
| Initializer      | `list<int> l = {...};`     | Direct initialize          |
---

# 📦 Capacity Functions in C++ STL `list`

---
Capacity functions ব্যবহার করা হয় container-এর
**size, empty অবস্থা** ইত্যাদি জানার জন্য।

---

# 🔸 1️⃣ `size()`

```cpp id="sz12aa"
list<int> l = {10, 20, 30};

cout << l.size();
```

🔍 Explanation (Bangla):

* list-এ কয়টা element আছে তা return করে

👉 Output:

```id="out11"
3
```

---

# 🔸 2️⃣ `empty()`

```cpp id="em45bb"
list<int> l;

if(l.empty()) {
    cout << "List is empty";
}
```

🔍 Explanation:

* list খালি কিনা check করে
* empty হলে `true` return করে

---

# 🔸 3️⃣ `clear() and reize()`

```cpp id="mx78cc"
list<int> l;

cout << l.clear();
```

🔍 Explanation:

* list a kono value thake na

---

# 🔹 Full Example Code

```cpp id="full99"
#include<iostream>
#include<list>
using namespace std;

int main() {

    list<int> l = {1, 2, 3};

    cout << "Size: " << l.size() << endl;

    if(l.empty()) {
        cout << "Empty" << endl;
    } else {
        cout << "Not Empty" << endl;
    }

    cout << "Max Size: " << l.max_size() << endl;

    return 0;
}
```
# ✏️ Modifier Functions in C++ STL `list`

---

Modifier functions ব্যবহার করা হয় list-এর **data change, add, delete, update** করার জন্য।

---

# 🔸 1️⃣ `push_back()`

```cpp
list<int> l;
l.push_back(10);
l.push_back(20);
```

🔍 Explanation (Bangla):

* list-এর শেষে element add করে

👉 Output: `10 20`

---

# 🔸 2️⃣ `push_front()`

```cpp
l.push_front(5);
```

🔍 Explanation:

* list-এর শুরুতে element add করে

👉 Output: `5 10 20`

---

# 🔸 3️⃣ `pop_back()`

```cpp
l.pop_back();
```

🔍 Explanation:

* শেষের element delete করে

---

# 🔸 4️⃣ `pop_front()`

```cpp
l.pop_front();
```

🔍 Explanation:

* প্রথম element delete করে

---

# 🔸 5️⃣ `insert() any position`

```cpp
list<int> l={10.20.30};
list<int> l2={100.200.300};

cout<<*next(l.brgin(),2); //output 30 and 2 hosce index number

l.insert(next(l.brgin(),2), 100); //output 10,20,100,30

//multiple inser list
l.insert(next(l.brgin(),2), 100,l2.begin(),l2.end());

for(int val : l){
 cout<<val;
}
```

🔍 Explanation:

* specific position-এ element add করে

---

# 🔸 6️⃣ `erase()`

```cpp

l.erase(next(l.brgin(),2));
//multipe remove
2.erase(next(l.brgin(),2),next(l.brgin(),3));

```

🔍 Explanation:

* specific position-এর element delete করে

---

# 🔸 7️⃣ `clear()`

```cpp
l.clear();
```

🔍 Explanation:

* পুরো list empty করে

---

# 🔸 8️⃣ `replace()`

```cpp
list<int> l = {1, 2, 3};

l.replace(l.begin(),l.end(),20,100);
```

🔍 Explanation:

🔸 replace() কী করে?

👉 replace() হলো <algorithm> এর function
👉 এটা old value → new value দিয়ে replace করে

👉 Output: `10,100,30`

---

# 🔸 9️⃣ `assign()`

```cpp
list<int> l;
l.assign(3, 7);
```

🔍 Explanation:

* নতুন value দিয়ে পুরো list replace করে

👉 Output: `7 7 7`

---

# 🔸 🔟 `remove()`

```cpp
list<int> l = {1, 2, 3, 2};

l.remove(2);
```

🔍 Explanation:

* specific value-এর সব element delete করে

👉 Output: `1 3`

---
```cpp
➤ Sort
l.sort();

➤ Reverse
l.reverse();

➤ Unique (remove duplicate)  //sorted pasapasi  value(10,10.10.20,20)
l.unique();

```

---

## 🔹 1️⃣ `find()` Function

```cpp id="a1b2c3"
#include<iostream>
#include<list>
#include<algorithm>
using namespace std;

int main() {

    list<int> l = {10, 20, 30, 40};

    auto it = find(l.begin(), l.end(), 30);

    if(it != l.end()) {
        cout << "Found: " << *it << endl;
    } else {
        cout << "Not Found";
    }

    return 0;
}
```

🔍 Explanation (Bangla):

* `find()` function `<algorithm>` থেকে আসে
* value খুঁজে iterator return করে
* না পেলে `l.end()` return করে

---

# 🔥 Summary Table

| Function       | কাজ             |
| -------------- | --------------- |
| `push_back()`  | শেষে add        |
| `push_front()` | শুরুতে add      |
| `pop_back()`   | শেষে delete     |
| `pop_front()`  | শুরুতে delete   |
| `insert()`     | position-এ add  |
| `erase()`      | position delete |
| `clear()`      | সব delete       |
| `resize()`     | size change     |
| `assign()`     | নতুন data set   |
| `remove()`     | value delete    |

---
# 📘 C++ STL `list` – Element Access & Iteration

---

Element access মানে হলো list-এর **first, last বা specific element access করা**

---

# 🔸 1️⃣ `front()` – First Element

```cpp
list<int> l = {10, 20, 30};

cout << l.front();
```

🔍 Explanation (Bangla):

* list-এর **প্রথম element** return করে

👉 Output:

```
10
```

---

# 🔸 2️⃣ `back()` – Last Element

```cpp
cout << l.back();
```

🔍 Explanation:

* list-এর **শেষ element** return করে

👉 Output:

```
30
```

---

# ⚠️ Important Note

* `list`-এ **index access (l[0], l[1]) নাই** ❌
* কারণ এটি linked list (random access support করে না)

---

# 🔹 Iteration (Traversal)

Iteration মানে হলো list-এর সব element একে একে access করা

---

# 🔸 1️⃣ Using Iterator (begin & end)

```cpp
#include<iostream>
#include<list>
using namespace std;

int main() {

    list<int> l = {10, 20, 30, 40};

    for(list<int>::iterator it = l.begin(); it != l.end(); it++) {
        cout << *it << " ";
    }

    return 0;
}
```

---

# 🔸 2️⃣ Using Auto Iterator (Easy)

```cpp
for(auto it = l.begin(); it != l.end(); it++) {
    cout << *it << " ";
}
```

---

# 🔸 3️⃣ Range-Based For Loop (Best & Short)

```cpp
for(int val : l) {
    cout << val << " ";
}
```

---

# 🔸 4️⃣ Reverse Iteration

```cpp
for(auto it = l.rbegin(); it != l.rend(); it++) {
    cout << *it << " ";
}
```

👉 Output: reverse order

---

#🔁 Singly Linked List Reverse Function (C++)

```cpp
void reverse_linked_list(Node* &head,Node* &tail, Node* temp)
{
   it(temp->next == NULL){
   head == temp;
   return;
 }
 reverse_linked_list(head,temp->next);
 temp->next->next =temp
 temp->next=NULL;
 tail =temp;

}
```















































# 📘 Stack Implementation using Vector & Class (C++)

---
Stack হলো C++ STL-এর একটি LIFO (Last In First Out) data structure
👉 শেষ যে element ঢুকবে, সেটাই আগে বের হবে

এই প্রজেক্টে আমরা STL `stack` ব্যবহার না করে
👉 `vector` + `class` দিয়ে **custom stack implementation** করেছি

👉 Stack follows:

* **LIFO (Last In First Out)**

---

# 🔸 Class Definition

```cpp id="cls1"
#include<iostream>
#include<vector>
using namespace std;

class myStack {
public:
    vector<int> v;

    void push(int val) {
        v.push_back(val);
    }

    void pop() {
        v.pop_back();
    }

    int top() {
        return v.back();
    }

    int size() {
        return v.size();
    }

    bool empty() {
        return v.empty();
    }
};

int main() {

    myStack s;

    s.push(10);
    s.push(20);
    s.push(30);

    cout << s.top() << endl;
    s.pop();
    cout << s.top() << endl;
    s.pop();
    cout << s.top() << endl;
    s.pop();

    if(!s.empty()) 
        cout << s.top()<<endl;

      if(!s.empty()) 
        cout << s.pop()<<endl;
    return 0;
}
```

👉 Output:

```cpp id="vec2"
Push → 10, 20, 30

Stack:
[30]
[20]
[10]

Pop → 30 removed
Pop → 20 removed
Pop → 10 removed

Stack → empty
```

👉 Stack logic:

| Operation | Vector ব্যবহার |
| --------- | -------------- |
| push      | `push_back()`  |
| pop       | `pop_back()`   |
| top       | `back()`       |
| size      | `size()`       |
| empty     | `empty()`      |


# ⚠️ Important Notes

* `vector` ব্যবহার করে dynamic stack তৈরি করা হয়েছে
* Stack শুধুমাত্র **top element access** করতে পারে
* empty check না করলে program crash করতে পারে ❌

---
# 📘 Stack Implementation (Vector + Class) with User Input & Output in C++

---

এই প্রোগ্রামে আমরা `vector` + `class` ব্যবহার করে
👉 একটি **custom stack** তৈরি করেছি
👉 এবং user input নিয়ে stack operations দেখানো হয়েছে

---

# 🔸 Full Code (User Input + Output)

```cpp
#include<iostream>
#include<vector>
using namespace std;

class myStack {
public:
    vector<int> v;

    void push(int val) {
        v.push_back(val);
    }

    void pop() {
        v.pop_back();
    }

    int top() {
        return v.back();
    }

    int size() {
        return v.size();
    }

    bool empty() {
        return v.empty();
    }
};

int main() {

    myStack s;
    int n
    cin >> n;

    for(int i = 0; i < n; i++) {
        int x;
        cin >> x;
        s.push(x);
    }
    while(!s.empty()) {
        cout << s.top() <<endl;
        s.pop();
    }

    return 0;
}
```

---

# 🔹 Sample Input

```txt
10 20 30
```

---

# 🔹 Sample Output

```txt
Top element: 30

Popping all elements:
30 20 10 

Stack is now empty
```

---

# 🔍 Explanation

👉 User প্রথমে number of elements দেয়
👉 তারপর elements input নেয়

👉 Stack এ push হয়:

```
10 → 20 → 30
```

👉 Top = 30

👉 Pop করলে বের হবে:

```
30 → 20 → 10
```

👉 কারণ Stack = **LIFO**

---


# 📘 Stack Implementation using `list` in C++

---

এই প্রজেক্টে আমরা STL `stack` ব্যবহার না করে
👉 `list` (doubly linked list) দিয়ে **custom stack** তৈরি করবো

👉 Stack follows:

* **LIFO (Last In First Out)**


# 🔸 Stack Class using `list`

```cpp id="lststk1"
#include<iostream>
#include<list>
using namespace std;

class myStack {
public:
    list<int> l;

    void push(int val) {
        l.push_back(val); 
    }

    void pop() {
        l.pop_back();
    }

    int top() {
        return l.back();
    }
    int size() {
        return l.size();
    }
    bool empty() {
        return l.empty();
    }
};
int main() {

    myStack s;
    int n;
    cin >> n;
    for(int i = 0; i < n; i++) {
        int x;
        cin >> x;
        s.push(x);
    }
     while(!s.empty()) {
        cout << s.top() <<endl;
        s.pop();
    }

    return 0;
}
```

---

# 🔹 Sample Input

```txt id="inlst"
 4
10 20 30 40
```

---

# 🔹 Sample Output

```txt id="outlst"
 40
40 30 20 10 

Stack is now empty
```

---

# 🔍 Explanation (Bangla)

👉 `list` ব্যবহার করে stack বানানো হয়েছে

👉 Logic:

```txt id="vislst"
Top (back side)
 ↓
40
30
20
10
```

👉 `push_back()` → element add
👉 `pop_back()` → element remove
👉 `back()` → top element

---

# 🔥 Key Functions

| Function  | কাজ            |
| --------- | -------------- |
| `push()`  | element add    |
| `pop()`   | element remove |
| `top()`   | last element   |
| `size()`  | total element  |
| `empty()` | check empty    |

---

# ⚠️ Important Notes

* Stack = **LIFO**
* `list` internally linked list
* vector এর মতো contiguous না ❌
* insertion/deletion efficient ✔️

---


# 📘 Stack using STL `stack` in C++ (use)

---

C++ STL-এ built-in `stack` container আছে
👉 নিজে implement করার দরকার নেই
👉 directly use করা যায়

👉 Stack follows:

* **LIFO (Last In First Out)**


# 🔸 Full Example Code

```cpp id="stl8"
#include<iostream>
#include<stack>
using namespace std;

int main() {

    stack<int> s;
    int n;
    cin >> n;

    cout << "Enter elements:\n";
    for(int i = 0; i < n; i++) {
        int x;
        cin >> x;
        s.push(x);
    }

    while(!s.empty()) {
        cout << s.top() << " ";
        s.pop();
    }

    return 0;
}
```

---

# 🔹 Sample Input

```txt id="stlin"
Enter number of elements: 3
Enter elements:
10 20 30
```

---

# 🔹 Sample Output

```txt id="stlout"
Top element: 30

Stack elements (Top to Bottom):
30 20 10 

Stack is now empty
```

---

# 🔍 Explanation (Bangla)

👉 STL `stack` internally use করে:

* default → `deque` container

👉 Logic:

```txt id="stlvis"
Top
 ↓
30
20
10
```

👉 `push()` → add
👉 `pop()` → remove
👉 `top()` → last element

---

# 🔥 Summary Table

| Function  | কাজ         |
| --------- | ----------- |
| `push()`  | element add |
| `pop()`   | remove      |
| `top()`   | top element |
| `size()`  | count       |
| `empty()` | check       |

---

# ⚠️ Important Notes

* Stack-এ শুধু top access করা যায় ❌ (no index)
* `pop()` কিছু return করে না
* empty check না করলে error হতে পারে

---

## ✅ Conclusion

👉 STL `stack` use করলে
✔ easy implementation
✔ less code
✔ efficient operations

🚀 Competitive programming & interview-এ খুব useful

---


# 📘 Queue Data Structure (Linked List Implementation)

A Queue is a linear data structure that follows **FIFO (First In First Out)** principle.

👉 Bangla Explanation:
Queue হলো এমন একটি ডেটা স্ট্রাকচার যেখানে যে data আগে ঢোকে, সেটাই আগে বের হয় (First Come First Serve).

Example:
- Bank line
- Ticket counter line

---

## 📌 FIFO Principle
FIFO means:

First Element Inserted → First Element Removed

👉 Bangla:
যে element আগে ঢুকবে, সেটাই আগে বের হবে।

---

## 📌 Operations of Queue

### 1️⃣ Enqueue (push)
Add element at the **rear (tail)**.

👉 Bangla:
Queue-এর শেষে নতুন element যোগ করা হয়।

---

### 2️⃣ Dequeue (pop)
Remove element from the **front (head)**.

👉 Bangla:
Queue-এর সামনে থেকে element remove করা হয়।

---

### 3️⃣ Front
Returns the first element.

👉 Bangla:
সবচেয়ে সামনে থাকা element দেখায়।

---

### 4️⃣ Back
Returns the last element.

👉 Bangla:
সবচেয়ে পেছনের element দেখায়।

---

### 5️⃣ Empty
Checks if queue is empty or not.

👉 Bangla:
Queue খালি কিনা সেটা check করে।

---

### 6️⃣ Size
Returns number of elements in queue.

👉 Bangla:
Queue-তে কতগুলো element আছে তা জানায়।



## 📌 Structure of Node

```cpp
#include <iostream>
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



class myQueue {
public:
    Node* head = NULL;
    Node* tail = NULL;
    int sz = 0;

    void push(int val) {
        Node* newNode = new Node(val);
           sz++;
        if (head == NULL) {
            head = newNode;
            tail = newNode; 
            return;
        }
        tail->next = newNode;
        tail = newNode;
    }

  
    void pop() {
        Node* deleteNode = head;
        head = head->next;
        delete deleteNode;
        sz--;
        if (head == NULL) {
            tail = NULL;
        }
    }

    int front() {
        return head->val;
    }

    int back() {
        return tail->val;
    }

    bool empty() {
        return head == NULL;
    }

    int size() {
        return sz;
    }
};

int main() {
    myQueue q;
    int n;
    cin >> n;
    for (int i = 0; i < n; i++) {
        int val;
        cin >> val;
        q.push(val);
    }

    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
    return 0;
}
```
## ➕ After push operations
```cpp
push(10)
head → [10] → NULL
tail ────────┘

push(20)
head → [10] → [20] → NULL
                 tail

push(30)
head → [10] → [20] → [30] → NULL
                          tail

push(40)
head → [10] → [20] → [30] → [40] → NULL
                                   tail

push(50)
head → [10] → [20] → [30] → [40] → [50] → NULL
                                            tail
```
## ❌ After pop operations (printing)
```cpp
pop() → remove 10
head → [20] → [30] → [40] → [50]

pop() → remove 20
head → [30] → [40] → [50]

pop() → remove 30
head → [40] → [50]

pop() → remove 40
head → [50]

pop() → remove 50
Queue EMPTY (NULL)


Front → 10 → 20 → 30 → 40 → 50 → Rear

Front → 20 → 30 → 40 → 50
Front → 30 → 40 → 50
Front → 40 → 50
Front → 50
EMPTY
```

#  📘 Queue using Doubly Linked List (C++)
```cpp
#include <iostream>
using namespace std;

class Node {
public:
    int val;
    Node* next;
    Node* prev;

    Node(int val) {
        this->val = val;
        this->next = NULL;
        this->prev = NULL;
    }
};

class Queue {
public:
    Node* head = NULL; // front
    Node* tail = NULL; // rear
    int sz = 0;

    void push(int val) {
        Node* newNode = new Node(val);
        sz++;

        if (head == NULL) {
            head = newNode;
            tail = newNode;
            return;
        }
        tail->next = newNode;
        newNode->prev = tail;
        tail = newNode;
    }

    void pop() {
        Node* delNode = head;
        head = head->next;

        if (head != NULL) {
            head->prev = NULL;
        } else {
            tail = NULL;
        }

        delete delNode;
        sz--;
    }
    int front() {
        return head->val;
    }
    int back() {  
        return tail->val;
    }
    bool empty() {
        return head == NULL;
    }
    int size() {
        return sz;
    }
};

int main() {
    Queue q;
    int n;
    cin >> n;
    for (int i = 0; i < n; i++) {
        int val;
        cin >> val;
        q.push(val);
    }
    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
    cout << endl;
    return 0;
}

```
# Queue using STL List (C++)
```cpp
#include <iostream>
#include <list>
using namespace std;

class Queue {
public:
    list<int> l;

    void push(int val) {
        l.push_back(val);
    }
    void pop() {
            l.pop_front();
        }
    }

   
    int front() {
        return l.front();
    }
    int back() {
        return l.back();
    }

    bool empty() {
        return l.empty();
    }

    int size() {
        return l.size();
    }
};

int main() {
    Queue q;

    int n;
    cin >> n;
    for (int i = 0; i < n; i++) {
        int val;
        cin >> val;
        q.push(val);
    }
    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }

    cout << endl;

    return 0;
}
```
# 📘 Queue using STL (queue)
```cpp
#include <iostream>
#include <queue>
using namespace std;

int main() {
    queue<int> q;
    int n;
    cin >> n;
    for (int i = 0; i < n; i++) {
        int val;
        cin >> val;
        q.push(val);
    }

    while (!q.empty()) {
        cout << q.front() << " ";
        q.pop();
    }
    cout << endl;

    return 0;
}
```
















































