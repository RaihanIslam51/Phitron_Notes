# 🌳 Binary Tree

Binary Tree হলো একটি **non-linear data structure**, যেখানে প্রতিটি node সর্বোচ্চ **২টি child** রাখতে পারে।

👉 এই ২টি child হলো:

* Left child (বাম দিকের সন্তান)
* Right child (ডান দিকের সন্তান)

📝 সহজভাবে বললে: একটি node থেকে সর্বোচ্চ দুইটি শাখা বের হতে পারে।

---

## 🧠 Basic Terminology

| Term    | বাংলা ব্যাখ্যা                 |
| ------- | ------------------------------ |
| Root    | গাছের একদম উপরের node          |
| Parent  | যে node এর নিচে অন্য node থাকে |
| Child   | parent এর নিচে থাকা node       |
| Leaf    | যে node এর কোনো child নেই      |
| Subtree | পুরো tree এর একটি অংশ          |

---

## 🧱 Node Structure (C++)

```cpp
class Node {
public:
    int val;
    Node* left;
    Node* right;

    Node(int val) {
        this->val = val;
        this->left = NULL;
        this->right = NULL;
    }
};
```

📝 **ব্যাখ্যা:**

* `val` → node এর মান (data) সংরক্ষণ করে
* `left` → বাম পাশের child এর address রাখে
* `right` → ডান পাশের child এর address রাখে

---

## 🌳 Creating the Binary Tree

```cpp
int main(){
Node* root = new Node(10);
Node* a = new Node(20);
Node* b = new Node(30);
Node* c = new Node(40);
Node* d = new Node(50);
Node* e = new Node(60);
```

📝 **ব্যাখ্যা:**

* এখানে আমরা ৬টি node তৈরি করেছি
* `new` ব্যবহার করে memory তে node গুলো তৈরি করা হচ্ছে

---

## 🔗 Connecting Nodes

```cpp
root->left = a;
root->right = b;

a->left = c;

b->left = d;
b->right = e;

}
```

📝 **ব্যাখ্যা:**

* 10 এর বামে 20, ডানে 30
* 20 এর বামে 40
* 30 এর বামে 50, ডানে 60

---

## 🌲 Tree Visualization

```
        10
       /  \
     20    30
    /     /  \
  40     50   60
```

📝 **ব্যাখ্যা:**

* 10 হলো root
* 20 ও 30 হলো তার child
* 40, 50, 60 হলো leaf node

---

# 🌳 Tree Traversal (Pre-order, In-order, Post-order)

Tree Traversal মানে হলো **tree এর প্রতিটি node একবার করে visit করা** একটি নির্দিষ্ট নিয়ম অনুসরণ করে।

---

## 🔄 Types of Traversal

Binary Tree traversal মূলত ৩ ধরনের:

1. Pre-order
2. In-order
3. Post-order

---

## 🌲 Example Tree

```
        10
       /  \
     20    30
    /     /  \
  40     50   60
```

---

# 🔵 Pre-order Traversal

## 📌 Rule:

👉 Root → Left → Right

## 💻 Code:

```cpp
void preOrder(Node* root) {
    if(root == NULL) return;

    cout << root->val << " ";
    preOrder(root->left);
    preOrder(root->right);
}
```

## 📝 ব্যাখ্যা:

* প্রথমে root visit করা হয়
* তারপর বাম দিকে যাওয়া হয়
* শেষে ডান দিকে যাওয়া হয়

## ▶️ Output:

```
10 20 40 30 50 60
```

---

# 🟢 In-order Traversal

## 📌 Rule:

👉 Left → Root → Right

## 💻 Code:

```cpp
void inOrder(Node* root) {
    if(root == NULL) return;

    inOrder(root->left);
    cout << root->val << " ";
    inOrder(root->right);
}
```

## 📝 ব্যাখ্যা:

* প্রথমে বাম দিকে যাওয়া হয়
* তারপর root print করা হয়
* শেষে ডান দিকে যাওয়া হয়

## ▶️ Output:

```
40 20 10 50 30 60
```

---

# 🔴 Post-order Traversal

## 📌 Rule:

👉 Left → Right → Root

## 💻 Code:

```cpp
void postOrder(Node* root) {
    if(root == NULL) return;

    postOrder(root->left);
    postOrder(root->right);
    cout << root->val << " ";
}
```

## 📝 ব্যাখ্যা:

* প্রথমে বাম subtree visit করা হয়
* তারপর ডান subtree
* সবশেষে root print করা হয়

## ▶️ Output:

```
40 20 50 60 30 10
```

---

## 🎯 Summary Table

| Traversal  | Rule                | Output            |
| ---------- | ------------------- | ----------------- |
| Pre-order  | Root → Left → Right | 10 20 40 30 50 60 |
| In-order   | Left → Root → Right | 40 20 10 50 30 60 |
| Post-order | Left → Right → Root | 40 20 50 60 30 10 |

---

## 🚀 Final কথা

* Pre-order → root আগে
* In-order → root মাঝখানে
* Post-order → root শেষে

👉 এই ৩টা traversal recursion বোঝার জন্য খুব গুরুত্বপূর্ণ এবং interview তে অনেক আসে।

```cpp
#include <iostream>
using namespace std;


class Node {
public:
    int val;
    Node* left;
    Node* right;

    Node(int val) {
        this->val = val;
        this->left = NULL;
        this->right = NULL;
    }
};

// Pre-order Traversal (Root → Left → Right)
void preOrder(Node* root) {
    if (root == NULL) return;

    cout << root->val << " ";
    preOrder(root->left);
    preOrder(root->right);
}

// In-order Traversal (Left → Root → Right)
void inOrder(Node* root) {
    if (root == NULL) return;

    inOrder(root->left);
    cout << root->val << " ";
    inOrder(root->right);
}

// Post-order Traversal (Left → Right → Root)
void postOrder(Node* root) {
    if (root == NULL) return;

    postOrder(root->left);
    postOrder(root->right);
    cout << root->val << " ";
}

int main() {

    // Tree create
    Node* root = new Node(10);
    Node* a = new Node(20);
    Node* b = new Node(30);
    Node* c = new Node(40);
    Node* d = new Node(50);
    Node* e = new Node(60);

    // Connection
    root->left = a;
    root->right = b;

    a->left = c;

    b->left = d;
    b->right = e;

    // Output
    cout << "Pre-order: ";
    preOrder(root);
    cout << endl;

    cout << "In-order: ";
    inOrder(root);
    cout << endl;

    cout << "Post-order: ";
    postOrder(root);
    cout << endl;

    return 0;
}
```
# 🌳 Level Order Traversal (BFS) in Binary Tree

Level Order Traversal holo ekta **Breadth First Search (BFS)** technique, jekhane tree ke **level by level** visit kora hoy.

👉 Mane:

* Root first
* Tarpor 1st level
* Tarpor 2nd level
* এভাবে নিচে নামতে থাকে

---

## 🌲 Example Tree

```
        10
       /  \
     20    30
    /     /  \
  40     50   60
```

---

## 📌 Level Order Rule

👉 Left to Right order e **level by level** print korte hoy

---

## 🧠 Idea (Logic)

Level order traversal korte amra use kori:

👉 **Queue (FIFO)**

Steps:

1. Root ke queue te push korbo
2. Front theke node ber korbo
3. Tar children (left, right) queue te push korbo
4. Repeat until queue empty

---

## 💻 C++ Code (Level Order Traversal)

```cpp

void levelOrder(Node* root) {

    queue<Node*> q;
    q.push(root);

    while (!q.empty()) {
        Node* f = q.front();
        q.pop();

        cout << f->val << " ";

        if (f->left != NULL) {
            q.push(f->left);
        }

        if (f->right != NULL) {
            q.push(f->right);
        }
    }
}



```

---

## ▶️ Output

```
Level Order Traversal: 10 20 30 40 50 60
```

---

## 🧾 Step-by-Step Flow

```
Queue: [10]

10 print → push (20, 30)
Queue: [20, 30]

20 print → push (40)
30 print → push (50, 60)
Queue: [40, 50, 60]

40 → 50 → 60 print
```

---

## 🎯 Summary

| Traversal   | Method | Data Structure |
| ----------- | ------ | -------------- |
| Pre-order   | DFS    | Recursion      |
| In-order    | DFS    | Recursion      |
| Post-order  | DFS    | Recursion      |
| Level Order | BFS    | Queue          |

---

## 🚀 Final Note

👉 Level Order traversal interview e onek important
👉 BFS concept Graph er jonnoo base

---

# Binary tree input :






























