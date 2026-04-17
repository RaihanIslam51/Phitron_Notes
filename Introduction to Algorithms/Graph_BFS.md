# Graph

গ্রাফ হলো একটি **নন-লিনিয়ার ডাটা স্ট্রাকচার** যেখানে কিছু **নোড (Vertex)** এবং তাদের মধ্যে **সংযোগ (Edge)** থাকে। বিভিন্ন সম্পর্ক দেখানোর জন্য গ্রাফ ব্যবহার করা হয়। যেমন: রাস্তার মানচিত্র, সামাজিক যোগাযোগ মাধ্যম, কম্পিউটার নেটওয়ার্ক ইত্যাদি।

## গাণিতিক প্রকাশ

**G = (V, E)**

* **V** = সকল নোডের সমষ্টি
* **E** = সকল সংযোগের সমষ্টি

## উদাহরণ

```text
    A ----- B
    |       |
    |       |
    C ----- D
```

এখানে A, B, C, D হলো নোড এবং রেখাগুলো হলো সংযোগ।

## Type of Graph

### 1. Undirected Graph

যে গ্রাফে সংযোগের কোনো নির্দিষ্ট দিক থাকে না। দুই পাশ থেকেই যাওয়া যায়।

```text
A ----- B
|       |
C ----- D
```

### 2. Directed Graph

যে গ্রাফে সংযোগের নির্দিষ্ট দিক থাকে। এক নোড থেকে অন্য নোডে তীর চিহ্ন দিয়ে পথ দেখানো হয়।

```text
A → B
↓   ↓
C → D
```

### 3. Weighted Graph

যে গ্রাফে প্রতিটি সংযোগের সাথে মান, দূরত্ব বা খরচ দেওয়া থাকে।

```text
A --5-- B
|       |
2       3
|       |
C --4-- D
```

### 4. Unweighted Graph

যে গ্রাফে সংযোগের সাথে কোনো মান দেওয়া থাকে না।

### 5. Cyclic Graph

যে গ্রাফে ঘুরে আবার আগের নোডে ফিরে আসা যায়।

```text
A → B → C
↑       ↓
└───────┘
```

### 6. Acyclic Graph

যে গ্রাফে কোনো চক্র বা ঘুরে আসার পথ নেই।

```text
A → B → C
```

### 7. Complete Graph

যে গ্রাফে প্রতিটি নোড অন্য সব নোডের সাথে যুক্ত থাকে।

### 8. Tree

এটি এমন একটি গ্রাফ যা সংযুক্ত এবং এতে কোনো চক্র নেই।

```text
    A
   / \
  B   C
 / \
D   E
```

# Adjacency Matrix কি?

Adjacency Matrix হলো Graph কে 2D array / matrix আকারে সংরক্ষণ করার একটি পদ্ধতি।

এখানে:

Row = Source Node
Column = Destination Node
যদি দুই node এর মধ্যে connection থাকে = 1
connection না থাকলে = 0

                Adjacency Matrix Representation


Graph:

                        (A)
                       /   \
                      /     \
                     /       \
                   (B)-------(C)
                    | \       |
                    |  \      |
                    |   \     |
                    |    \    |
                   (D)---(E)--(F)



Adjacency Matrix:

          A  B  C  D  E  F
       --------------------
A   |    0  1  1  0  0  0
B   |    1  0  1  1  1  0
C   |    1  1  0  0  0  1
D   |    0  1  0  0  1  0
E   |    0  1  0  1  0  1
F   |    0  0  1  0  1  0



Meaning:
0 = No Connection
1 = Connected


Row Meaning:
A row = A node connected with B, C
B row = B node connected with A, C, D, E
C row = C node connected with A, B, F
D row = D node connected with B, E
E row = E node connected with B, D, F
F row = F node connected with C, E


Column Meaning:
Each column also represents connection to that node.


Properties:
✔ Matrix size = V × V
✔ For 6 vertices = 6 × 6 matrix
✔ Diagonal always 0 (self-loop না থাকলে)
✔ Undirected graph হলে matrix symmetric


# Graph Traversal
## BFS (Breadth First Search)

এক স্তর করে নোড ভিজিট করে। Queue ব্যবহার করা হয়।

## DFS (Depth First Search)

গভীরে গিয়ে নোড ভিজিট করে। Stack বা Recursion ব্যবহার করা হয়।

## Important Algorithom

Dijkstra Algorithm (সবচেয়ে ছোট পথ বের করতে)
Bellman Ford Algorithm
Prim Algorithm
Kruskal Algorithm
Topological Sort

## Real live use Graph

Google Maps
Facebook বন্ধুত্ব সম্পর্ক
কম্পিউটার নেটওয়ার্ক
ওয়েব পেজ সংযোগ
গেমে পথ খোঁজা


# Adjacency Matrix underivted graph 


* Row = Source Node
* Column = Destination Node
* `1` = Connected
* `0` = Not Connected

## Graph Visualization

```text
    0 ----- 1
    |       |
    |       |
    2 ----- 3
```

## Matrix Representation

```text
      0 1 2 3
    ---------
0 |   0 1 1 0
1 |   1 0 0 1
2 |   1 0 0 1
3 |   0 1 1 0
```

## C++ Code

```cpp
#include <iostream>
#include <cstring>
using namespace std;

int main() {
    int n, e;
    cout << "Enter number of nodes and edges: ";
    cin >> n >> e;

    int adj_mat[n][n];
    memset(adj_mat, 0, sizeof(adj_mat));

      for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) 
            if(i==j){
              adj_mat[i][j]=1;
           
        }

    for (int i = 0; i < e; i++) {
        int a, b;
        cin >> a >> b;
        adj_mat[a][b] = 1;
        adj_mat[a][b] = 1;
    }

    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            cout << adj_mat[i][j] << " ";
        }
        cout << endl;
    }

    return 0;
}
```

## Sample Input

```text
4 4
0 1
0 2
1 3
2 3
```

## Sample Output

```text
1 1 1 0
1 1 0 1
1 0 1 1
0 1 1 1
```

# Adjacency List Representation of Graph (C++)

## Introduction

Graph হলো একটি **non-linear data structure**, যেখানে nodes (vertices) এবং তাদের মধ্যে edges (connections) থাকে।

Adjacency List হলো Graph represent করার একটি efficient পদ্ধতি, যেখানে প্রতিটি node এর সাথে তার connected nodes list আকারে রাখা হয়।

---

# Graph Visualization

```text
        0
       / \
      1   2
       \   \
        3---4
```

Vertices: 0, 1, 2, 3, 4

Edges:
(0-1), (0-2), (1-3), (2-4), (3-4)

---

# Adjacency List

Adjacency List হলো এমন একটি structure যেখানে:

* প্রতিটি node এর পাশে তার neighbor nodes রাখা হয়
* List আকারে store করা হয়

---

# Adjacency List Representation
 index  a store

```text

0 -> 1 2
1 -> 0 3
2 -> 0 4
3 -> 1 4
4 -> 2 3
```

---

# How it Works (Bangla Explanation)

* Node 0 connected with 1 and 2 → তাই লেখা `0 -> 1 2`
* Node 1 connected with 0 and 3 → তাই লেখা `1 -> 0 3`
* Node 2 connected with 0 and 4 → তাই লেখা `2 -> 0 4`

এভাবে প্রতিটি node এর neighbors list আকারে store করা হয়।

---

# C++ Implementation

```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, e;

    cout << "Enter number of nodes and edges: ";
    cin >> n >> e;

    vector<int> adj_list[n];

    cout << "Enter edges (u v):" << endl;

    for (int i = 0; i < e; i++) {
        int u, v;
        cin >> u >> v;

        // Undirected Graph
        adj_list[u].push_back(v);
        adj_list[v].push_back(u);
    }

    cout << "\nAdjacency List:\n";

    for (int i = 0; i < n; i++) {
        cout << i << " -> ";

        for (int j = 0; j < adj_list[i].size(); j++) {
            cout << adj_list[i][j] << " ";
        }

        cout << endl;
    }

    return 0;
}
```

---

# Sample Input

```text
5 5
0 1
0 2
1 3
2 4
3 4
```

---

# Sample Output

```text
0 -> 1 2
1 -> 0 3
2 -> 0 4
3 -> 1 4
4 -> 2 3
```

---

# Edge list
```cpp
#include <iostream>
#include <vector>
using namespace std;

int main() {
    int n, e;

    cout << "Enter number of nodes and edges: ";
    cin >> n >> e;

    // Edge List using vector
    vector<pair<int, int>> edges;

    cout << "Enter edges (u v):" << endl;

    for (int i = 0; i < e; i++) {
        int u, v;
        cin >> u >> v;

        edges.push_back({u, v});
    }

    cout << "\nEdge List:\n";

    for (int i = 0; i < edges.size(); i++) {
        cout << "(" << edges[i].first << ", " << edges[i].second << ")\n";
    }

    return 0;
}
```








