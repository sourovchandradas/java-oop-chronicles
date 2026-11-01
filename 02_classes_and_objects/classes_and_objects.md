# Java OOP - Classes and Objects

## Overview

Object-Oriented Programming (OOP) is one of the most important programming paradigms in Java. It helps developers model real-world problems using objects and classes. In Java, code is built around classes and objects, which makes programs easier to design, understand, and maintain.

This chapter introduces the core concepts of OOP:

- Classes
- Objects
- State
- Behavior
- Instance variables
- Methods
- Reference variables
- Object creation
- Object interaction
- Inheritance
- Method overriding

A class acts like a blueprint, while an object is the actual runtime instance created from that blueprint. The main idea behind OOP is simple: real-world things can be represented as objects that hold information and perform actions.

This guide covers:

* **Classes** - blueprints used to create objects
* **Objects** - instances created from classes
* **State** - the data an object stores
* **Behavior** - the actions an object can perform
* **Instance Variables** - variables that define object state
* **Methods** - blocks of code that define behavior
* **Reference Variables** - variables that point to objects
* **Object Creation** - creating objects using the `new` keyword
* **Object Interaction** - objects communicating with each other
* **Inheritance** - reusing code from another class
* **Method Overriding** - changing inherited behavior
* **Mini Project: Guessing Game** - using OOP concepts in a real program

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

Object-Oriented Programming (OOP) is a programming paradigm that organizes code around objects and classes instead of only functions and variables.

In OOP, we model real-world entities using objects. Each object can have:

- **State** — information it stores
- **Behavior** — actions it can perform

For example, a `Dog` object may have:

- State: `name`, `age`, `color`
- Behavior: `bark()`, `run()`, `eat()`

This design makes programs:

- easier to understand
- easier to maintain
- easier to extend
- more reusable

### Core OOP Concepts

- Class
- Object
- Instance Variable
- Method
- Reference Variable
- Inheritance
- Method Overriding
- Object Interaction

> At runtime, a Java program is really a collection of objects working together.

---

## Classes

A class is a blueprint or template for creating objects. It defines the data (state) and behavior (methods) that objects of that class will have.

### Key Points

- A class is like a blueprint
- It defines instance variables and methods
- It is used to create many objects
- It helps organize code
- It can be reused and extended

### Example

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

- `Dog` = class
- `name` = instance variable
- `age` = instance variable
- `bark()` = method

### Why Classes Matter

Classes allow us to group related data and behavior in one place. Instead of writing everything in one huge program, we break it into smaller, meaningful pieces.

> A class describes how to create objects.

---

## Objects

An object is an instance of a class. It is a real runtime entity created from the class blueprint.

### Key Points

- An object is created from a class
- Each object has its own state
- Objects can perform methods
- Multiple objects can be created from the same class
- Objects live in memory

### Example

```java
Dog dog1 = new Dog();
Dog dog2 = new Dog();
```

### Explanation

- `Dog` = class
- `dog1` = first object
- `dog2` = second object
- `new Dog()` = creates a new object in memory

### Real-Life Analogy

Think of a class like a blueprint for a car. The object is the actual car built from that blueprint. Two cars can be built from the same design but still have different properties like color and engine size.

> An object is an instance of a class.

---

## State and Behavior

Every object in Java has two important aspects:

### 1. State

State represents the data stored in an object. In Java, this is usually stored in instance variables.

Example:

```java
class Car {
    String model;
    int speed;
}
```

Here:

- `model` stores the name of the car
- `speed` stores the current speed

### 2. Behavior

Behavior describes what an object can do. Behavior is defined by methods.

Example:

```java
class Car {
    String model;

    void start() {
        System.out.println("The car is starting...");
    }
}
```

This means a `Car` object can do something: `start()`.

### Relationship Between State and Behavior

- State tells us what an object knows
- Behavior tells us what an object does

This is one of the core ideas behind OOP.

---

## Instance Variables

Instance variables are variables declared inside a class but outside any method. They belong to each object of the class.

### Example

```java
class Student {
    String name;
    int age;
    double marks;
}
```

### Characteristics

- Each object gets its own copy
- They store object-specific data
- They usually represent the object's state
- They are created when the object is created

### Example with Object Values

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

### Important Point

Each object has its own copy of the instance variables. If you create two `Student` objects, they can hold different values.

---

## Methods

Methods define the behavior of a class. They are blocks of code that perform a task.

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

Methods help us:

- organize logic
- avoid repeated code
- represent real actions
- give objects behavior

### Types of Methods

- Instance methods
- Static methods
- Returning methods
- Void methods

### Example of a Returning Method

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }
}
```

---

## Reference Variables

A reference variable stores the address or reference of an object, not the object itself.

### Example

```java
Dog dog1 = new Dog();
```

Here:

- `dog1` is the reference variable
- `new Dog()` creates the object
- `dog1` points to the object in memory

### Important Idea

Reference variables point to objects in the heap memory. They do not contain the entire object directly.

### Example

```java
Dog d1 = new Dog();
Dog d2 = d1;
```

Now both `d1` and `d2` refer to the same object.

### Why This Matters

This is one of the fundamental ideas in Java. Objects are managed through references, which is why Java is very efficient and flexible when working with object data.

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

### Output

```text
Java Basics
```

### What Actually Happens?

When Java executes `new Book()`, it:

1. allocates memory for the object
2. initializes its instance variables
3. returns a reference to that object

This is how Java creates new data objects during runtime.

---

## Object Interaction

Objects interact with each other through method calls. This is one of the most important ideas in OOP.

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

### Example of Two Objects Working Together

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

Here, the `Greeting` object is telling another object to perform a task by calling its method.

### Why This Matters

Most real programs are built from many objects communicating with each other. This is how large systems are designed.

---

## Inheritance

Inheritance allows one class to reuse the properties and methods of another class. The class that inherits is called the subclass, and the class it inherits from is called the superclass.

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
- cleaner structure
- easier maintenance
- better organization of related classes

### Why It Matters

Without inheritance, we would need to rewrite the same code again and again for similar classes.

---

## Method Overriding

Method overriding happens when a subclass provides a different implementation of a method already defined in its superclass.

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

It allows subclasses to customize inherited behavior while keeping the same method name.

> Method overriding allows specialized behavior in subclasses.

---

## Guessing Game Project

Now let’s apply the concepts we have learned to a small project.

### Project Idea

Create a guessing game in which the computer chooses a random number and the player tries to guess it.

### Example Code

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

### What This Project Shows

- class design
- instance variables
- methods
- object creation
- user interaction
- state management
- simple game logic

This project is a great beginner-friendly example of OOP in action.

---

## Key Concepts Learned

By the end of this chapter, you should understand:

- A class is a blueprint
- An object is an instance of a class
- State is stored in instance variables
- Behavior is implemented using methods
- Objects are created with `new`
- Objects interact through method calls
- Inheritance promotes code reuse
- Method overriding customizes behavior
- OOP makes software easier to design and maintain

---

## Exercises

### Exercise 1

Create a class called `Book` with:

- `title`
- `author`
- `pages`

Then create two objects and print their values.

### Exercise 2

Create a class called `Circle` with:

- `radius`
- `calculateArea()`

### Exercise 3

Create a class `Animal` and a subclass `Cat` that overrides the `sound()` method.

### Exercise 4

Create a class `Student` with:

- `name`
- `age`
- `displayInfo()`

### Exercise 5

Build a simple number guessing game using OOP.

---

## Quick Reference

### Class Declaration

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
    System.out.println("Hello!");
}
```

### Inheritance

```java
class Child extends Parent {
}
```

### Method Override

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
- Memory Management in Java

---

## Why This Matters

Understanding classes and objects is the foundation of Java programming. Almost every real Java application is built using OOP principles.

This chapter helps you learn how to:

- model real-world entities in code
- organize code into meaningful units
- create reusable software components
- think in terms of objects instead of only instructions

> Java programs are built from objects that work together to solve problems.

---

## Additional Resources

- Java Official Documentation: https://docs.oracle.com/en/java/
- Head First Java
- W3Schools Java OOP Tutorials
- GeeksforGeeks Java OOP Guide
- FreeCodeCamp Java Tutorials

---

## Final Takeaway

- Class = Blueprint
- Object = Instance of a class
- Instance variables = state
- Methods = behavior
- `new` creates object instances
- Objects interact through method calls
- Inheritance promotes reuse
- Method overriding allows custom behavior
- OOP helps build maintainable, scalable software

This chapter is only the beginning of Java OOP. Once you understand classes and objects, the rest of object-oriented design becomes much easier to learn.

---

## Mini Reflection

Ask yourself:

- What is the difference between a class and an object?
- Why are instance variables important?
- Why do methods matter in OOP?
- How do objects communicate with each other?
- Why is inheritance useful?
- What is method overriding?

If you can answer these, you are already thinking in an OOP way.

---

## Suggested Next Chapter

After this chapter, the next topics you may study are:

- Constructors
- Encapsulation
- Access Modifiers
- Static Members
- Polymorphism

These topics build directly on the foundation taught in this chapter.

---
