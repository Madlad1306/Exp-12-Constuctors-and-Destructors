# Constructors and Destructors in C++

## Introduction

In C++, **constructors** and **destructors** are special member functions that manage the lifecycle of objects.

* **Constructors** handle initialization of objects at the time of creation.
* **Destructors** handle cleanup of resources when objects go out of scope.

These ensure that objects start in a valid state and release resources properly when no longer needed.

---

## Constructors

A **constructor** is automatically executed whenever an object of a class is created.

### Key Features

* Name must match the class name.
* No return type (not even `void`).
* Automatically called at object creation.
* Can be **overloaded** with multiple parameter sets.
* If none is defined, the compiler provides a **default constructor**.

---

### Types of Constructors

#### 1. Default Constructor

* Takes no arguments.
* Initializes objects with default/predefined values.

```cpp
class Student {
    int age;
public:
    Student() {
        age = 18;  // default value
    }
};
```

---

#### 2. Parameterized Constructor

* Accepts arguments for custom initialization.

```cpp
class Student {
    int age;
public:
    Student(int a) {
        age = a;
    }
};
```

---

#### 3. Copy Constructor

* Creates a new object as a copy of an existing one.

**Syntax:**

```cpp
ClassName(const ClassName &obj) { /* copy data */ }
```

**Example:**

```cpp
class Student {
    int age;
public:
    Student(int a) { age = a; }
    Student(const Student &s) { age = s.age; } // Copy constructor
};
```

**Usage:**

* Passing objects by value.
* Returning objects from functions.
* Duplicating objects.

---

### Advantages of Constructors

* Automatic and consistent initialization.
* Reduce redundant initialization code.
* Support **constructor overloading** for flexibility.

### Limitations of Constructors

* Cannot be virtual.
* Cannot return values.
* Cannot be inherited (though base constructors can be invoked).
* Cannot be explicitly invoked like normal functions (called only through object creation).

---

## Destructors

A **destructor** is automatically executed when an object goes out of scope or is explicitly deleted.

### Key Features

* Same name as the class, but preceded by `~`.
* Takes no arguments and has no return type.
* Only **one destructor per class** (cannot be overloaded).
* Called in **reverse order of object creation**.

---

### Uses of Destructors

* Free dynamically allocated memory.
* Close files or network connections.
* Release system resources (e.g., locks).
* Debugging/logging lifecycle of objects.

---

### Advantages of Destructors

* Automatic cleanup of resources.
* Prevent memory leaks.
* Simplify resource management.
* Improve stability by handling deallocation gracefully.

---

### Limitations of Destructors

* Called in reverse order in inheritance chains.
* Cannot be overloaded.
* Order of global/static object destruction across files is **undefined**.
* Should not throw exceptions (unsafe).

---

## Conclusion

Constructors and destructors are **fundamental to resource management in C++**.

* Constructors ensure **safe initialization** of objects.
* Destructors ensure **safe cleanup** of resources.
  Together, they enable robust, modular, and reliable object-oriented programs.
