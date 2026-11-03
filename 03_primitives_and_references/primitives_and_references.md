# Java OOP - Primitives and References

## Overview

In Java, variables come in two flavors: **primitive variables** and **reference variables**. Understanding the difference between these two types is essential because everything in Java is built around values and objects.

Primitive variables store actual values directly, while reference variables store a way to access objects in memory.

This chapter introduces:

- Primitive Variables
- Reference Variables
- Variable Declaration
- Variable Naming Rules
- Assignment
- Object References
- Object Creation
- Dot Operator
- Heap Memory
- Arrays
- Object Arrays
- Null References
- NullPointerException
- Garbage Collection

These concepts form the foundation of Java memory management and object-oriented programming.

This guide covers:

* **Primitive Variables** - store actual values
* **Reference Variables** - store object references
* **Variable Declaration** - creating variables with types
* **Variable Naming Rules** - rules for valid identifiers
* **Assignment** - storing values in variables
* **Objects and References** - how objects are accessed
* **Object Creation** - creating objects using the `new` keyword
* **Dot Operator** - accessing object members
* **Heap Memory** - where objects live
* **Arrays** - collections of values or references
* **Object Arrays** - arrays that store references
* **Null References** - references pointing to nothing
* **NullPointerException** - errors caused by null references
* **Garbage Collection** - automatic memory cleanup

---

## Table of Contents

1. [Primitive Variables](#primitive-variables)
2. [Primitive Type Sizes](#primitive-type-sizes)
3. [Reference Variables](#reference-variables)
4. [Variable Declaration](#variable-declaration)
5. [Variable Naming Rules](#variable-naming-rules)
6. [Assignment](#assignment)
7. [Object References](#object-references)
8. [Three Steps of Object Creation](#three-steps-of-object-creation)
9. [Dot Operator](#dot-operator)
10. [Heap Memory](#heap-memory)
11. [Reference Copy vs Object Copy](#reference-copy-vs-object-copy)
12. [Arrays](#arrays)
13. [Arrays of Objects](#arrays-of-objects)
14. [Array Length](#array-length)
15. [Null References](#null-references)
16. [NullPointerException](#nullpointerexception)
17. [Garbage Collection](#garbage-collection)
18. [Complete Dog Example](#complete-dog-example)
19. [Key Concepts Learned](#key-concepts-learned)
20. [Quick Reference](#quick-reference)
21. [Related Topics](#related-topics)
22. [Why This Matters](#why-this-matters)
23. [Final Takeaway](#final-takeaway)

---

## Primitive Variables

Primitive variables store actual values directly.

### Java Primitive Types

```java
byte
short
int
long
float
double
char
boolean
```

### Example

```java
int age = 20;
double cgpa = 3.75;
char grade = 'A';
boolean passed = true;
```

### Key Points

- Store actual values directly
- Fixed memory size
- Not objects
- Faster and memory efficient

### Example

```java
int x = 10;
```

Memory:

```text
x
└── 10
```

The value `10` is stored directly in the variable.

---

## Primitive Type Sizes

Java provides eight primitive data types.

| Type | Size |
|--------|--------|
| byte | 8 bits |
| short | 16 bits |
| int | 32 bits |
| long | 64 bits |
| float | 32 bits |
| double | 64 bits |
| char | 16 bits |
| boolean | JVM dependent |

### Memory Trick

```text
byte  → 8
short → 16
int   → 32
long  → 64
```

Each type doubles in size.

---

## Reference Variables

Reference variables do not store objects directly.

Instead, they store a reference to an object.

### Example

```java
Dog myDog = new Dog();
```

### Key Points

- Store object references
- Point to objects in memory
- Do not contain the actual object
- Used to access objects

### Memory View

```text
myDog
   |
   V
Dog Object
```

### Important Idea

> There is no such thing as an object variable. There are only object reference variables.

---

## Variable Declaration

Every variable in Java must have:

- A type
- A name

### Syntax

```java
Type variableName;
```

### Examples

```java
int age;

double cgpa;

Dog myDog;
```

---

## Variable Naming Rules

Every variable must have a valid identifier.

### Rules

- Must start with:
  - letter
  - underscore (_)
  - dollar sign ($)

- Cannot start with a number

### Valid

```java
age
studentName
_age
$salary
age21
```

### Invalid

```java
21age
1student
class
public
int
```

### Important

Java keywords cannot be used as variable names.

---

## Assignment

Assignment stores a value into a variable.

### Syntax

```java
variable = value;
```

### Example

```java
int x = 10;
```

### Assigning from Variables

```java
int x = 10;
int y = x;
```

### Assigning Expressions

```java
int y = x + 5;
```

### Type Compatibility

Small to large type:

```java
byte b = 10;
int x = b;
```

✅ Allowed

Large to small type:

```java
int x = 10;
byte b = x;
```

❌ Not allowed without casting

---

## Object References

Objects are created using the `new` keyword.

### Example

```java
Dog myDog = new Dog();
```

### Memory View

```text
myDog
   |
   V
Dog Object
```

### Calling Methods

```java
myDog.bark();
```

### Important

The dot operator (`.`) is used to access methods and variables through a reference.

---

## Three Steps of Object Creation

Creating an object involves three steps.

### Step 1: Declare a Reference Variable

```java
Dog myDog;
```

### Step 2: Create an Object

```java
new Dog();
```

### Step 3: Assign the Reference

```java
myDog = new Dog();
```

Or in a single statement:

```java
Dog myDog = new Dog();
```

---

## Dot Operator

The dot operator (`.`) is used to access methods and instance variables through a reference.

### Example

```java
Dog d = new Dog();

d.name = "Buddy";

d.bark();
```

### General Form

```java
reference.member
```

Examples:

```java
d.name

d.bark()

myDogs[0].name

myDogs[0].bark()
```

### Important Idea

A reference variable works like a remote control.

The dot operator tells Java to use the object referenced by the variable.

---

## Heap Memory

Objects live on the heap.

### Example

```java
Dog dog1 = new Dog();
```

Memory:

```text
Stack

dog1
  |
  |
  V

Heap

Dog Object
```

### Key Points

- Objects are stored on the heap
- References are used to access objects
- Multiple references can refer to the same object

Example:

```java
Dog d1 = new Dog();
Dog d2 = d1;
```

Now both references point to the same object.

---

## Reference Copy vs Object Copy

When assigning one reference variable to another, Java copies the reference, not the object.

### Example

```java
Dog d1 = new Dog();

Dog d2 = d1;
```

### Memory View

```text
d1 ------\
          \
           ---> Dog Object
          /
d2 ------/
```

### Important

- No new object is created
- Only the reference is copied
- Both variables refer to the same object

---

## Arrays

An array stores multiple values of the same type.

### Example

```java
int[] nums = new int[5];
```

### Assign Values

```java
nums[0] = 10;
nums[1] = 20;
nums[2] = 30;
```

### Access Values

```java
System.out.println(nums[0]);
```

### Important Point

Arrays are objects.

```java
new int[5]
```

creates an array object.

---

## Arrays of Objects

Arrays can also store object references.

### Example

```java
Dog[] pets = new Dog[3];
```

This creates:

```text
3 Dog reference slots
```

Not:

```text
3 Dog objects
```

### Creating Objects

```java
pets[0] = new Dog();
pets[1] = new Dog();
```

### Memory View

```text
pets

0 ---> Dog Object
1 ---> Dog Object
2 ---> null
```

### Accessing Objects

```java
pets[0].bark();
```

---

## Array Length

Every array has a special property called `length`.

### Example

```java
int[] nums = new int[5];

System.out.println(nums.length);
```

### Output

```text
5
```

### Example

```java
Dog[] pets = new Dog[3];

System.out.println(pets.length);
```

Output:

```text
3
```

### Why It Matters

Length is commonly used in loops.

```java
for(int i = 0; i < pets.length; i++) {

}
```

---

## Null References

A reference variable can refer to nothing.

### Example

```java
Dog d = null;
```

### Meaning

```text
d refers to no object
```

### Memory View

```text
d
 |
 V

null
```

---

## NullPointerException

A NullPointerException occurs when a reference variable refers to null and you try to access an object through it.

### Example

```java
Dog d = null;

d.bark();
```

### Result

```text
NullPointerException
```

### Why?

Because no object exists for the reference variable to use.

### Correct Usage

```java
Dog d = new Dog();

d.bark();
```

---

## Garbage Collection

Java automatically removes unused objects from memory.

This process is called:

```text
Garbage Collection (GC)
```

### Example

```java
Book b = new Book();
Book c = new Book();

b = c;
```

After assignment:

```text
Object 1
```

has no references.

It becomes:

```text
Eligible for Garbage Collection
```

### Important Rule

An object becomes eligible for garbage collection when no references point to it.

---

## Complete Dog Example

```java
class Dog {

    String name;

    public static void main(String[] args) {

        Dog dog1 = new Dog();

        dog1.bark();
        dog1.name = "Bart";

        Dog[] myDogs = new Dog[3];

        myDogs[0] = new Dog();
        myDogs[1] = new Dog();
        myDogs[2] = dog1;

        myDogs[0].name = "Fred";
        myDogs[1].name = "Marge";

        System.out.print("last dog's name is ");
        System.out.println(myDogs[2].name);

        int x = 0;

        while (x < myDogs.length) {
            myDogs[x].bark();
            x = x + 1;
        }
    }

    public void bark() {
        System.out.println(name + " says Ruff!");
    }

    public void eat() {
    }

    public void chaseCat() {
    }
}
```

### Output

```text
null says Ruff!
last dog's name is Bart
Fred says Ruff!
Marge says Ruff!
Bart says Ruff!
```

### Concepts Demonstrated

- Reference variables
- Object creation
- Arrays of objects
- Reference assignment
- Dot operator
- Method invocation
- Array length
- Loops

---

## Key Concepts Learned

By the end of this chapter, you should understand:

- Primitive variables store actual values
- Reference variables store object references
- Objects live on the heap
- Arrays are objects
- Object arrays store references
- References can be null
- Multiple references can point to the same object
- Reference assignment copies references, not objects
- Dot operator is used to access object members
- Arrays provide the length property
- Null references can cause NullPointerException
- Unreachable objects become eligible for garbage collection

---

## Quick Reference

### Primitive Variable

```java
int x = 10;
```

### Reference Variable

```java
Dog d = new Dog();
```

### Array

```java
int[] nums = new int[5];
```

### Object Array

```java
Dog[] pets = new Dog[3];
```

### Object Creation

```java
Dog d = new Dog();
```

### Reference Copy

```java
Dog d2 = d1;
```

### Null Reference

```java
Dog d = null;
```

### Dot Operator

```java
d.bark();
d.name = "Tom";
```
- understand garbage collection

> Every Java program depends on primitives, references, objects, and memory management.
>
> 

---

## Final Takeaway

- Primitive variables store actual values.
- Reference variables store references to objects.
- Objects live on the heap.
- Arrays are objects.
- Object arrays store references.
- The `new` keyword creates objects.
- The dot operator accesses object members.
- Multiple references can point to the same object.
- `null` means no object is referenced.
- Calling a method on a null reference causes a NullPointerException.
- Unreachable objects become eligible for garbage collection.
- Understanding references is essential for mastering Java OOP and memory management.

---

*Last Modified: November 1, 2026*
