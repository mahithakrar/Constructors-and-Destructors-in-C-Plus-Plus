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

# Program Summary

## 1.Student Information Program
This program demonstrates the use of **constructors** and **class encapsulation** in C++.  
- A `Student` class is defined with attributes such as `name`, `PRN`, `branch`, `division`, and `fee`.  
- The **default constructor** is used to take input from the user.  
- A `display()` function is used to show the entered details.  

This program highlights the concept of **object-oriented programming (OOP)** by using **data abstraction, constructors, and member functions**.

---

## Theory
1. **Classes and Objects**  
   - A class is a user-defined data type that encapsulates variables (data members) and functions (member functions).  
   - Objects are instances of a class.  

2. **Constructor**  
   - The program uses a **default constructor** to take input values when an object is created.  
   - This ensures that the `Student` object is properly initialized.  

3. **Member Function**  
   - The `display()` function is used to output the student’s details.  

4. **Encapsulation**  
   - Data members (`name`, `PRN`, `branch`, `divi`, `fee`) are private by default.  
   - Access is provided through public functions (`Student()` and `display()`).  

---

## Algorithm
1. **Start the program.**  
2. Define a `Student` class with data members:  
   - `name` (string)  
   - `PRN` (int)  
   - `branch` (string)  
   - `divi` (char)  
   - `fee` (double)  
3. Create a **default constructor** that:  
   - Prompts the user to enter student details.  
   - Reads input values and stores them in class data members.  
4. Define a `display()` function that prints the stored student details.  
5. In the `main()` function:  
   - Create an object `s` of class `Student`.  
   - The constructor is automatically invoked to take input.  
   - Call the `display()` function to show the details.  
6. **End the program.**  

---
  
## 2.Student Information Program(Constructor Outside Class)
This program demonstrates the use of **constructors** and **member functions defined outside a class** in C++.  
- The `Student` class has attributes like `name`, `PRN`, `branch`, `division`, and `fee`.  
- The **default constructor** is defined outside the class using the **scope resolution operator (::)** and is responsible for taking input.  
- A `display()` function is also defined outside the class and is used to output the stored details.  
This program highlights important **OOP principles** like **encapsulation, abstraction, and modularity**.

---

## Theory
1. **Scope Resolution Operator (::)**  
   - Allows defining member functions outside the class while still associating them with the class.  
   - Improves readability and keeps the class declaration clean.  

2. **Default Constructor**  
   - A constructor with no arguments.  
   - Here, it takes input for student details immediately when an object is created.  

3. **Encapsulation**  
   - Data members (`name`, `PRN`, `branch`, `divi`, `fee`) are private by default.  
   - They can only be accessed and manipulated via public member functions.  

4. **Abstraction**  
   - The user interacts with the object (`Student s;`) without knowing the implementation details of input and display functions.  

---

## Algorithm
1. **Start the program.**  
2. Define a `Student` class with data members:  
   - `name` (string)  
   - `PRN` (int)  
   - `branch` (string)  
   - `divi` (char)  
   - `fee` (double)  
3. Declare a **default constructor** and a `display()` function inside the class.  
4. Define the constructor outside the class using the **scope resolution operator (::)**:  
   - Prompt the user to enter values for `name`, `PRN`, `branch`, `divi`, and `fee`.  
   - Store these values in the respective data members.  
5. Define the `display()` function outside the class using `::` to print all details.  
6. In the `main()` function:  
   - Create an object `s` of type `Student`.  
   - The constructor is automatically called to take input.  
   - Call `s.display()` to print student details.  
7. **End the program.**  

---

## 3.Parameterized Constructor Example

This program demonstrates the use of a **parameterized constructor** in C++.  
- A class `Practice` is created with two data members `a` and `b`.  
- A **parameterized constructor** initializes these values when the object is created.  
- The `display()` function prints the values of `a` and `b`.  
This program highlights the importance of **constructors with arguments** for initializing objects with specific values.

---

## Theory
1. **Parameterized Constructor**  
   - A constructor that takes one or more parameters to initialize an object.  
   - Allows different objects of the same class to be initialized with **different values**.  

2. **Encapsulation**  
   - Data members `a` and `b` are private by default.  
   - Initialization is done via the constructor, and output is handled by the `display()` function.  

3. **Object Initialization**  
   - Instead of assigning values separately after creating the object, values are passed directly at the time of object creation.  

---

## Algorithm
1. **Start the program.**  
2. Define a class `Practice` with two integer data members: `a` and `b`.  
3. Define a **parameterized constructor** that:  
   - Takes two parameters `m` and `n`.  
   - Assigns them to `a` and `b` respectively.  
4. Define a `display()` function to print the values of `a` and `b`.  
5. In the `main()` function:  
   - Create an object `p` of type `Practice` with values `(1,2)`.  
   - The constructor initializes `a=1` and `b=2`.  
   - Call `p.display()` to output the values.  
6. **End the program.**  

---

## Conclusion
Constructors and destructors are essential features of C++ that manage the **lifecycle of objects**:
- **Constructors** ensure that objects are created in a **valid and initialized state** by assigning values to data members at the time of object creation.  
- **Destructors** guarantee proper **resource cleanup** when objects go out of scope, preventing issues such as memory leaks and dangling pointers.  
- Together, they provide **automatic initialization and destruction**, making programs more **robust, efficient, and maintainable**.  
By using constructors and destructors effectively, developers can write C++ programs that are **object-oriented, resource-safe, and easier to manage in real-world applications**.
