# Constructors and Destructors in C++

## Overview
In C++, **constructors** and **destructors** are special member functions that play an essential role in **object lifecycle management**.  
- A **constructor** is automatically invoked when an object of a class is created. Its primary purpose is to initialize object data members.  
- A **destructor**, on the other hand, is automatically invoked when the object goes out of scope or is explicitly deleted. Its primary role is to release resources such as memory, file handles, or network connections.  

Together, constructors and destructors ensure **proper initialization** and **clean-up of resources**, making C++ a powerful language for system-level and application development.

---

## Theory

### Constructors
- A **constructor** is a special member function that has the **same name as the class**.
- It is called automatically when an object is created.
- Constructors **do not have a return type** (not even `void`).
- They can be **overloaded**, meaning a class can have multiple constructors with different parameter lists.

#### Types of Constructors
1. **Default Constructor**  
   - Takes no parameters.  
   - Initializes objects with default values.
  
 ```cpp
   class Example {
   public:
       Example() {
           cout << "Default constructor called!" << endl;
       }
   };
```

2. **Parameterized Constructor**  
   - Accepts arguments to initialize objects with specific values.

```cpp
class Example {
    int x;
public:
    Example(int val) {
        x = val;
        cout << "Parameterized constructor: " << x << endl;
    }
};
```

3. **Copy Constructor**  
   - Initializes an object by copying data from another object of the same class.

```cpp
class Example {
    int x;
public:
    Example(int val) { x = val; }
    Example(const Example &obj) { x = obj.x; } // Copy constructor
};
```


### Destructors
A **Destructor** in C++ is a special member function of a class that is automatically invoked when an object goes out of scope or is explicitly deleted.  
Its main purpose is to **release resources** such as memory, file handles, or network connections that were acquired during the lifetime of the object.  
Destructors ensure that no memory leaks or resource mismanagement occur when objects are destroyed.

---

- A destructor has the **same name as the class**, but it is preceded by a **tilde (~)** symbol.  
- It **does not return any value** and **does not take parameters**.  
- A class can have **only one destructor** (no overloading allowed).  
- It is called **automatically** by the compiler in the reverse order of object creation (last created object is destroyed first).  

---

### Syntax
```cpp
class ClassName {
public:
    // Constructor
    ClassName() {
        cout << "Constructor called!" << endl;
    }

    // Destructor
    ~ClassName() {
        cout << "Destructor called!" << endl;
    }
};
```
  
