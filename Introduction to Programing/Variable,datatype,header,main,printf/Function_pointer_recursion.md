

## 🔹 What is Call Stack?

**Call Stack** হলো একটি data structure (LIFO - Last In First Out) যা program run করার সময় function call গুলো track করে।

👉 যখন একটি function call হয় → stack এ push হয়
👉 function শেষ হলে → stack থেকে pop হয়

---

## 🔹 Example (C++)

```cpp
#include <iostream>
using namespace std;

void gelo() {
    cout << "Gelo Function" << endl;
}

void mello() {
    gelo();
    cout << "Mello Function" << endl;
}

void hello() {
    mello();
    cout << "Hello Function" << endl;
}

int main() {
    hello();
    cout << "Main Function" << endl;
}
```

---

## 🔹 Execution Flow (Box Style)

```
┌────────────┐
│   main()   │
└─────┬──────┘
      ↓
┌────────────┐
│  hello()   │
└─────┬──────┘
      ↓
┌────────────┐
│  mello()   │
└─────┬──────┘
      ↓
┌────────────┐
│  gelo()    │
└────────────┘
```

---

## 🔹 Call Stack Operation

```
Push → main()
Push → hello()
Push → mello()
Push → gelo()

Pop → gelo()
Pop → mello()
Pop → hello()
Pop → main()
```

---

## 🔹 Output

```
Gelo Function
Mello Function
Hello Function
Main Function
```

## 🔹 What is Recursion?

Recursion হলো এমন একটি programming technique যেখানে একটি function নিজেকেই call করে problem solve করে।

👉 সহজভাবে:
**Function নিজেই নিজেকে repeat করে call করে যতক্ষণ না একটি stop condition (base case) পাওয়া যায়।**

---

## 🔹 Basic Structure

```cpp
return_type function_name(parameters){

    // Base Case (Stopping Condition)
    if(condition){
        return;
    }

    // Work (optional)
    
    // Recursive Call
    function_name(updated_parameters);
}
```

---

## 🔹 Key Concepts

### ✅ 1. Base Case

* recursion থামানোর condition
* না থাকলে infinite recursion হবে ❌

### ✅ 2. Recursive Call

* function নিজেকে call করে

### ✅ 3. Call Stack

* প্রতিটি function call stack-এ জমা হয়
* return হওয়ার সময় একে একে বের হয়

---

## 🔹 Example 1: Forward Printing

```cpp
#include<iostream>
using namespace std;

void hello(int i){

    if(i == 5){
        return;
    }

    cout << i << " ";
    hello(i + 1);
}

int main(){
    hello(1);
}
```

### 📌 Output

```
1 2 3 4
```

👉 আগে print → পরে call
➡️ Forward Output

---

## 🔹 Example 2: Reverse Printing (Backtracking)

```cpp
#include<iostream>
using namespace std;

void hello(int i){

    if(i == 5){
        return;
    }

    hello(i + 1);
    cout << i << endl;
}

int main(){
    hello(1);
}
```

### 📌 Output

```
4
3
2
1
```

👉 আগে call → পরে print
➡️ Reverse Output (Backtracking)

---

## 🔹 Example 3: Array Traversal using Recursion

```cpp
#include<iostream>
using namespace std;

void printArray(int arr[], int n, int i){

    if(i == n){
        return;
    }

    cout << arr[i] << endl;
    printArray(arr, n, i + 1);
}

int main(){
    int n;
    cin >> n;

    int arr[n];

    for(int i = 0; i < n; i++){
        cin >> arr[i];
    }

    printArray(arr, n, 0);
}
```

---

## 🔹 Example 4: Reverse Array Print

```cpp
void printReverse(int arr[], int n, int i){

    if(i == n){
        return;
    }

    printReverse(arr, n, i + 1);
    cout << arr[i] << endl;
}
```

---

## 🔹 Example 5: Sum of Array using Recursion

```cpp
int sumArray(int arr[], int n, int i){

    if(i == n){
        return 0;
    }

    return arr[i] + sumArray(arr, n, i + 1);
}
```

---

## 🔹 Example 6: Find Maximum Element

```cpp
int maxArray(int arr[], int n, int i){

    if(i == n-1){
        return arr[i];
    }

    int restMax = maxArray(arr, n, i + 1);
    return max(arr[i], restMax);
}
```

---

## 🔹 Execution Flow (Call Stack)

```
hello(1)
 → hello(2)
   → hello(3)
     → hello(4)
       → hello(5) ❌ stop

Return Phase:
hello(4) → print 4
hello(3) → print 3
hello(2) → print 2
hello(1) → print 1
```

---
# 2D Arrays 

---

**Defination** 2D array হল এমন একটি array যার মধ্যে আরও arrays থাকে। এটি ডেটা row এবং column আকারে সংরক্ষণ করে।

**Syntax:**

```cpp
data_type array_name[row_size][column_size];
```

**Example:**

```cpp
int marks[3][4]; // 3 rows, 4 columns
```

---

## 2. Initialization

```cpp
int marks[3][4] = {
    {85, 90, 78, 88},
    {80, 85, 80, 75},
    {90, 88, 92, 95}
};
```

**:** প্রতিটি `{}` একটি row এর মান। Column গুলো সেই row এর ভিতরে থাকে।

---

## 3. Input in 2D Array

```cpp
for(int i = 0; i < 3; i++){
    for(int j = 0; j < 4; j++){
        cin >> marks[i][j];
    }
}
```

**:** প্রতিটি উপাদান ইনপুট করতে nested loop ব্যবহার করা হয়।

---

## 4. Output in 2D Array

```cpp
for(int i = 0; i < 3; i++){
    for(int j = 0; j < 4; j++){
        cout << marks[i][j] << " ";
    }
    cout << endl;
}
```

**:** প্রতিটি উপাদান প্রদর্শনের জন্য nested loop ব্যবহার করা হয়।

---

## 5. Visual Representation (i, j)

| i\j | 0  | 1  | 2  | 3  |
| --- | -- | -- | -- | -- |
| 0   | 85 | 90 | 78 | 88 |
| 1   | 80 | 85 | 80 | 75 |
| 2   | 90 | 88 | 92 | 95 |

* `marks[0][0] = 85` → row 0, column 0
* `marks[1][2] = 80` → row 1, column 2
* `marks[2][3] = 95` → row 2, column 3

---

## 6. Common Operations on 2D Array
### Print Specific Row

```cpp
int r = 1; // 2nd row
for(int j = 0; j < cols; j++){
    cout << marks[r][j] << " ";
}
cout << endl;
```
### Print Specific Column

```cpp
int c = 2; // 3rd column
for(int i = 0; i < rows; i++){
    cout << marks[i][c] << " ";
}
cout << endl;
```

### 6.1 Traverse (Loop through all elements)

```cpp
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        cout << marks[i][j] << " ";
    }
    cout << endl;
}
```

### 6.2 Sum of All Elements

```cpp
int sum = 0;
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        sum += marks[i][j];
    }
}
cout << "Sum of all elements: " << sum;
```

### 6.3 Row-wise Sum

```cpp
for(int i=0; i<rows; i++){
    int rowSum = 0;
    for(int j=0; j<cols; j++){
        rowSum += marks[i][j];
    }
    cout << "Sum of row " << i << " = " << rowSum << endl;
}
```

### 6.4 Column-wise Sum

```cpp
for(int j=0; j<cols; j++){
    int colSum = 0;
    for(int i=0; i<rows; i++){
        colSum += marks[i][j];
    }
    cout << "Sum of column " << j << " = " << colSum << endl;
}
```

### 6.5 Find Maximum Element

```cpp
int maxVal = marks[0][0];
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        if(marks[i][j] > maxVal)
            maxVal = marks[i][j];
    }
}
cout << "Maximum element = " << maxVal;
```

### 6.6 Find Minimum Element

```cpp
int minVal = marks[0][0];
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        if(marks[i][j] < minVal)
            minVal = marks[i][j];
    }
}
cout << "Minimum element = " << minVal;
```

### 6.7 Search for a Value

```cpp
int key;
cin >> key;
bool found = false;
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        if(marks[i][j] == key){
            cout << "Found at: [" << i << "][" << j << "]" << endl;
            found = true;
        }
    }
}
if(!found) cout << "Not Found!";
```

### 6.8 Transpose of a Matrix

```cpp
int transpose[cols][rows];
for(int i=0; i<rows; i++){
    for(int j=0; j<cols; j++){
        transpose[j][i] = marks[i][j];
    }
}

for(int i=0; i<cols; i++){
    for(int j=0; j<rows; j++){
        cout << transpose[i][j] << " ";
    }
    cout << endl;
}
```

### 6.9 Addition of Two 2D Arrays

```cpp
int a[2][2] = {{1,2},{3,4}};
int b[2][2] = {{5,6},{7,8}};
int sum[2][2];
for(int i=0;i<2;i++){
    for(int j=0;j<2;j++){
        sum[i][j] = a[i][j] + b[i][j];
        cout << sum[i][j] << " ";
    }
    cout << endl;
}
```

### 6.10 Multiplication of Two 2D Arrays

```cpp
int a[2][2] = {{1,2},{3,4}};
int b[2][2] = {{5,6},{7,8}};
int result[2][2] = {0};
for(int i=0;i<2;i++){
    for(int j=0;j<2;j++){
        for(int k=0;k<2;k++){
            result[i][j] += a[i][k] * b[k][j];
        }
        cout << result[i][j] << " ";
    }
    cout << endl;
}
```






