# C++ Array (অ্যারে)

**Array** হলো একই ধরনের অনেকগুলো data একসাথে একটি variable এর মধ্যে সংরক্ষণ করার উপায়।

উদাহরণ  
৫ জন ছাত্রের মার্কস:

```
80 75 90 85 70
```

এগুলো আলাদা variable এ না রেখে **Array** ব্যবহার করা যায়।

---

# Array Declaration

Array তৈরি করার নিয়ম

```
data_type array_name[size];
```

Example

```cpp
int marks[5];
```

---

# Array Initialization

```cpp
int marks[5] = {80,75,90,85,70};
```

---

# Array Index

Array এর index **0 থেকে শুরু হয়**।

```
marks[0] = 80
marks[1] = 75
marks[2] = 90
marks[3] = 85
marks[4] = 70
```

---

# Array Input (Loop ব্যবহার করে)

```cpp
#include<iostream>
using namespace std;

int main()
{
    int arr[5];

    for(int i=0;i<5;i++)
    {
        cin >> arr[i];
    }

    return 0;
}
```

---

# Array Output (Loop ব্যবহার করে)

```cpp
for(int i=0;i<5;i++)
{
    cout << arr[i] << " ";
}
```

---

# Array Sum Operation

Array এর সব সংখ্যার যোগফল বের করা।

```cpp
int sum = 0;

for(int i=0;i<5;i++)
{
    sum = sum + arr[i];
}

cout << sum;
```

---

# Even Number from Array

```cpp
for(int i=0;i<5;i++)
{
    if(arr[i] % 2 == 0)
    {
        cout << arr[i] << " ";
    }
}
```

---

# Odd Number from Array

```cpp
for(int i=0;i<5;i++)
{
    if(arr[i] % 2 != 0)
    {
        cout << arr[i] << " ";
    }
}
```

---

# Maximum Number from Array

```cpp
int max = arr[0];

for(int i=1;i<5;i++)
{
    if(arr[i] > max)
    {
        max = arr[i];
    }
}

cout << max;
```

---

# Minimum Number from Array

```cpp
int min = arr[0];

for(int i=1;i<5;i++)
{
    if(arr[i] < min)
    {
        min = arr[i];
    }
}

cout << min;
```

---

# Reverse Array

```cpp
for(int i=4;i>=0;i--)
{
    cout << arr[i] << " ";
}
```

---

# Full Example (Input + Output + Sum)

```cpp
#include<iostream>
using namespace std;

int main()
{
    int arr[5];
    int sum = 0;

    for(int i=0;i<5;i++)
    {
        cin >> arr[i];
    }

    for(int i=0;i<5;i++)
    {
        cout << arr[i] << " ";
        sum = sum + arr[i];
    }

    cout << endl;
    cout << "Sum = " << sum;

    return 0;
}
```

---

# Array Operations Summary

| Operation | কাজ |
|------|------|
| Input | array এ data নেওয়া |
| Output | array এর data print করা |
| Sum | সব সংখ্যার যোগ |
| Even | জোড় সংখ্যা বের করা |
| Odd | বিজোড় সংখ্যা বের করা |
| Max | সবচেয়ে বড় সংখ্যা |
| Min | সবচেয়ে ছোট সংখ্যা |
| Reverse | উল্টোভাবে print |

---