# Java OOP - Classes and Objects

## Overview

Object-Oriented Programming (OOP) is one of the most important programming paradigms in Java. It helps developers model real-world problems using objects and classes. In Java, everything is organized around classes and objects, which makes programs easier to design, extend, and maintain.

This chapter introduces the core fundamentals of OOP:

- Classes
- Objects
- Instance variables
- Methods
- Reference variables
- Object creation
- Object interaction
- Inheritance
- Method overriding

A class acts like a blueprint, while an object is a real runtime instance created from that blueprint. This chapter explains how Java programs are built from objects that hold data and perform actions.

This guide covers:

* **Classes** - blueprints used to create objects
* **Objects** - instances created from classes
* **Instance Variables** - data that represents an object's state
* **Methods** - actions or behaviors an object can perform
* **Reference Variables** - variables that store object references
* **Object Creation** - creating objects using the `new` keyword
* **Object Interaction** - objects communicating with one another
* **Inheritance** - reusing code from another class
* **Method Overriding** - redefining inherited behavior
* **Mini Project: Guessing Game** - building a simple Java application using OOP

---

## Table of Contents

1. [Introduction to OOP](#introduction-to-oop)
2. [Classes](#classes)
3. [Objects](#objects)
4. [State and Behavior](#state-and-behavior)
5. [Instance Variables](#instance-variables)
6. [Methods](#methods)
7. [Reference Variables](#reference-variables)
8. [Creating Objects](#creating-objects)
9. [Object Interaction](#object-interaction)
10. [Inheritance](#inheritance)
11. [Method Overriding](#method-overriding)
12. [Guessing Game Project](#guessing-game-project)
13. [Key Concepts Learned](#key-concepts-learned)
14. [Exercises](#exercises)
15. [Quick Reference](#quick-reference)
16. [Related Topics](#related-topics)
17. [Why This Matters](#why-this-matters)
18. [Additional Resources](#additional-resources)

---

## Introduction to OOP

Object-Oriented Programming (OOP) is a software design approach that organizes code around objects and classes. Instead of thinking only in terms of functions, OOP encourages us to model the real world using entities that have:

- State
- Behavior

For example, a `Dog` has:

- State: name, age, color
- Behavior: bark(), run(), eat()

This makes code more natural, reusable, and manageable.

### Core Principles of OOP

- **Class**: A blueprint or template
- **Object**: An instance of a class
- **State**: The data stored in an object
- **Behavior**: The actions an object can perform
- **Encapsulation**: Hiding internal data and exposing methods
- **Inheritance**: Reusing code from a parent class
- **Polymorphism**: One interface, many behaviors
- **Abstraction**: Showing only essential details

> At runtime, a Java program is nothing more than objects talking to other objects.

---

## Classes

A class is a blueprint for creating objects. It defines what data an object can store and what actions it can perform.

### Key Points

- A class is a template
- It defines instance variables and methods
- It is used to create multiple objects
- It promotes code organization and reuse
- It can be extended by subclasses

### Class Example

```java
class Dog {
    String name;
    int age;

    void bark() {
        System.out.println("Woof!");
    }
}
```

### Explanation

- `Dog` is the class name
- `name` and `age` are instance variables
- `bark()` is a method

### Why Classes Matter

Classes help you represent real-world entities in code. Instead of writing one long program, you break it into smaller reusable units.

> A class describes how to make objects.

---

## Objects

An object is an instance of a class. When you create an object, you are creating a real runtime entity based on the class blueprint.

### Key Points

- Objects are created from classes
- Each object has its own memory space
- Objects store their own state
- Objects can call methods
- Multiple objects can be created from one class

### Example

```java
Dog dog1 = new Dog();
Dog dog2 = new Dog();
```

### Explanation

- `Dog` = class
- `dog1` and `dog2` = object references
- `new Dog()` = creates a new object in memory

### Real-Life Analogy

Think of a class like a blueprint for a car, and an object like the actual car built from that blueprint.

> An object is an instance of a class.

---

## State and Behavior

Every Java object has two fundamental parts:

### 1. State

State is the data stored in an object. In Java, state is usually represented by instance variables.

Example:

```java
class Car {
    String model;
    int speed;
}
```

Here:

- `model` stores the car model
- `speed` stores the current speed

### 2. Behavior

Behavior describes what an object can do. In Java, behavior is defined using methods.

Example:

```java
class Car {
    String model;

    void start() {
        System.out.println("The car is starting...");
    }
}
```

This means a `Car` object can do something: start.

### Relationship Between State and Behavior

- State tells us what an object knows
- Behavior tells us what an object does

This is the heart of OOP.

---

## Instance Variables

Instance variables are variables declared inside a class but outside any method. They belong to each object created from the class.

### Example

```java
class Student {
    String name;
    int age;
    double marks;
}
```

### Characteristics

- Each object has its own copy
- They store object-specific data
- They are initialized with default values if not assigned explicitly

### Example with object values

```java
class Student {
    String name;
    int age;

    void displayInfo() {
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.name = "Alice";
        s1.age = 20;
        s1.displayInfo();
    }
}
```

### Output

```text
Name: Alice
Age: 20
```

### Important Note

Each object has its own separate instance variables. If you create another `Student`, it will have its own `name` and `age` values.

---

## Methods

Methods define the behavior of a class. They are blocks of code that perform a specific task.

### Syntax

```java
returnType methodName(parameters) {
    // code
}
```

### Example

```java
class Dog {
    String name;

    void bark() {
        System.out.println(name + " says woof!");
    }
}
```

### Calling a Method

```java
Dog d = new Dog();
d.name = "Buddy";
d.bark();
```

### Output

```text
Buddy says woof!
```

### Why Methods Are Useful

Methods allow us to:

- organize code
- avoid repetition
- model behavior clearly
- make classes reusable

### Types of Methods

- Instance methods
- Static methods
- Return methods
- Void methods

Example of a return method:

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
}
```

---

## Reference Variables

A reference variable stores the memory address of an object rather than the object itself.

### Example

```java
Dog dog1 = new Dog();
```

Here:

- `dog1` is a reference variable
- `new Dog()` creates the actual object in heap memory
- `dog1` points to that object

### Important Concept

Reference variables do not hold the object directly. They hold a reference to the object in memory.

### Example

```java
Dog d1 = new Dog();
Dog d2 = d1;
```

Now both `d1` and `d2` refer to the same object.

### Why This Matters

This is crucial in Java because object identity and memory sharing work through references.

---

## Creating Objects

Objects are created using the `new` keyword.

### Syntax

```java
ClassName objectName = new ClassName();
```

### Example

```java
class Book {
    String title;
}

public class Main {
    public static void main(String[] args) {
        Book b1 = new Book();
        b1.title = "Java Basics";
        System.out.println(b1.title);
    }
}
```

### What Happens Internally?

When Java executes `new Book()`, it:

1. allocates memory for the object
2. initializes instance variables
3. returns a reference to that object

### Object Creation in Real Life

Think of a factory producing new instances of a product based on a blueprint.

---

## Object Interaction

Objects interact with each other by calling methods. This is one of the most important ideas in OOP.

### Example

```java
class Person {
    String name;

    void introduce() {
        System.out.println("Hi, I am " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Person p1 = new Person();
        p1.name = "Rahim";
        p1.introduce();
    }
}
```

### Output

```text
Hi, I am Rahim
```

### Interacting Between Objects

```java
class Person {
    String name;

    void sayHello() {
        System.out.println("Hello from " + name);
    }
}

class Greeting {
    void greet(Person p) {
        p.sayHello();
    }
}
```

This is called object communication. One object can use another object's public methods.

### Why It Matters

Most real-world programs are built by many objects working together, sending messages through method calls.

---

## Inheritance

Inheritance allows one class to use the properties and methods of another class. The class that inherits is called a subclass, and the class it inherits from is called a superclass.

### Example

```java
class Animal {
    void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Barking...");
    }
}
```

### Usage

```java
Dog d = new Dog();
d.eat();
d.bark();
```

### Output

```text
Eating...
Barking...
```

### Benefits of Inheritance

- code reuse
- cleaner hierarchy
- easier maintenance
- shared behavior across classes

---

## Method Overriding

Method overriding happens when a subclass provides a different implementation of a method already defined in its parent class.

### Example

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}
```

### Usage

```java
Animal a = new Dog();
a.sound();
```

### Output

```text
Dog barks
```

### Why Overriding Matters

It allows specialized behavior in subclasses while keeping the same method name from the parent.

> Method overriding helps subclasses customize inherited behavior.

---

## Guessing Game Project

Now we apply the concepts we learned in a mini project.

### Project Idea

Create a simple guessing game where the computer chooses a random number, and the player tries to guess it.

### Example Design

```java
import java.util.Random;
import java.util.Scanner;

class GuessingGame {
    private int target;

    public GuessingGame() {
        Random random = new Random();
        this.target = random.nextInt(10) + 1;
    }

    public void play() {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Guess a number between 1 and 10");

        while (true) {
            int guess = scanner.nextInt();

            if (guess < target) {
                System.out.println("Too low!");
            } else if (guess > target) {
                System.out.println("Too high!");
            } else {
                System.out.println("You guessed it right!");
                break;
            }
        }
    }
}

public class Main {
    public static void main(String[] args) {
        GuessingGame game = new GuessingGame();
        game.play();
    }
}
```

### What This Project Demonstrates

- class design
- instance variables
- methods
- object creation
- user interaction
- logic and state management

This is a very beginner-friendly OOP project.

---

## Key Concepts Learned

By the end of this chapter, you should understand:

- A class is a blueprint
- An object is an instance of a class
- State is stored in instance variables
- Behavior is implemented by methods
- Object references point to object locations in memory
- Objects communicate through method calls
- Inheritance reuses code
- Method overriding customizes behavior
- OOP helps build maintainable, modular software

---

## Exercises

### Exercise 1

Create a class called `Book` with:

- `title`
- `author`
- `pages`

Then create two objects and print their values.

### Exercise 2

Write a class named `Circle` with:

- `radius`
- `calculateArea()`

### Exercise 3

Create a class `Animal` and a subclass `Cat` that overrides the `sound()` method.

### Exercise 4

Build a simple `Student` class with a method `displayInfo()`.

### Exercise 5

Create a mini project called `Number Guessing Game` using classes and methods.

---

## Quick Reference

### Class

```java
class ClassName {
    // fields
    // methods
}
```

### Object Creation

```java
ClassName object = new ClassName();
```

### Instance Variable

```java
String name;
int age;
```

### Method

```java
void printMessage() {
    System.out.println("Hello");
}
```

### Inheritance

```java
class Child extends Parent {
}
```

### Overriding

```java
@Override
void methodName() {
    // custom implementation
}
```

---

## Related Topics

- Constructors
- Access Modifiers
- Encapsulation
- Polymorphism
- Abstract Classes
- Interfaces
- Arrays and Objects
- Object Memory and Heap

---

## Why This Matters

Understanding classes and objects is the foundation of Java programming. Nearly every Java application is built around OOP principles. Without understanding this concept, you will struggle to write scalable and maintainable code.

This chapter helps you learn how to:

- model real-world entities in code
- split programs into logical units
- create reusable and organized code
- think in terms of objects instead of just instructions

> A Java program is built from objects working together to solve problems.

---

## Additional Resources

- Java official documentation: https://docs.oracle.com/en/java/
- Head First Java (for beginner-friendly OOP explanations)
- Java OOP tutorials on W3Schools, GeeksforGeeks, and freeCodeCamp
- Practice by writing small Java classes like `Student`, `Dog`, `Book`, and `Car`

---

## Final Takeaway

- Class = Blueprint
- Object = Instance of a class
- Instance variables = object state
- Methods = object behavior
- Objects are created using `new`
- Objects communicate through method calls
- Inheritance helps reuse code
- Method overriding allows custom behavior
- OOP makes software easier to design and maintain

This chapter is the starting point of Java OOP. Once you understand classes and objects, the rest of OOP becomes much easier to learn.

---

## Mini Reflection

Ask yourself:

- What is the difference between a class and an object?
- Why are instance variables important?
- How does a method help an object behave?
- Why is object interaction important in Java programs?
- What happens when one class inherits from another?

If you can answer these, you are already thinking like an OOP developer.

---

## Suggested Next Chapter

The next topic after classes and objects is often:

- Constructors
- Encapsulation
- Access Modifiers
- Arrays and Objects

These topics build directly on the concepts introduced in this chapter.

---
