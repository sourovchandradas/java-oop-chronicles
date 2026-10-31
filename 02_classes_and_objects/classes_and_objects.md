# Java OOP - Classes and Objects

## Overview

Object-Oriented Programming (OOP) is one of the fundamental programming paradigms used in Java programming language. This documentation introduces the core building blocks of OOP: classes, objects, instance variables, and methods.

A class acts as a blueprint for creating objects, while objects represent real-world entities that contain both data (state) and behavior. Through practical examples and projects, this documentation demonstrates how Java programs are built using objects that interact with one another.

This documentation also introduces object creation, reference variables, object interaction, inheritance, and method overriding, providing a solid foundation for understanding more advanced OOP concepts later in Java.

This guide covers:

* **Classes** - blueprints used to create objects
* **Objects** - instances created from classes
* **Instance Variables** - data that represents an object's state
* **Methods** - behaviors that an object can perform
* **Reference Variables** - variables that store object references
* **Object Creation** - creating objects using the `new` keyword
* **Object Interaction** - objects communicating through method calls
* **Inheritance** - acquiring properties and behaviors from another class
* **Method Overriding** - redefining inherited behavior
* **Mini Project: Guessing Game** - applying OOP concepts in a complete Java application

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

Object-Oriented Programming (OOP) is a programming paradigm that organizes software around classes and objects. A class acts as a blueprint, while an object is an instance created from that blueprint.

Each object contains:

- **State** (Instance Variables)
- **Behavior** (Methods)

OOP enables developers to model real-world entities, promote code reusability, and build maintainable software. Objects communicate with one another through method calls to perform tasks and solve problems.

### Core Concepts

- Class
- Object
- Instance Variable
- Method
- Reference Variable
- Object Creation
- Inheritance
- Method Overriding
- Object Interaction

> At runtime, a Java program is nothing more than objects talking to other objects.
>
> 

## Classes

A class is a blueprint or template used to create objects. It defines the state (instance variables) and behavior (methods) that objects of that type will have.

### Key Points

- Acts as a blueprint for creating objects
- Defines an object's instance variable/state and method/behavior
- Contains instance variables and methods
- Used to create multiple object instances
- Promotes code organization and reusability
- Can inherit from another class
- Can serve as a superclass or subclass

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

## Explanation

* **Dog** = Class (Blueprint)
* **name** = Instance Variable (State)
* **age** = Instance Variable (State)
* **bark()** = Method (Behavior)

> **Takeway**
> A class describes how to make objects.
> 

---


















## Why This Matters

Understanding classes and objects is essential for becoming an effective Java developer. Nearly every Java application is built using Object-Oriented Programming principles.

This chapter teaches how to model real-world entities using classes, create and manage objects, define behaviors through methods, and organize programs using object interactions. These concepts serve as the foundation for advanced topics such as polymorphism, encapsulation, abstraction, design patterns, and software architecture.

Most importantly, this chapter introduces the idea that:

> At runtime, a Java program is nothing more than objects talking to other objects.
>
> 

---

## Key Takeaway

* Class = Blueprint
* Object = Instance of a Class
* Instance Variables = State (What an object knows)
* Methods = Behavior (What an object does)
* Objects live on the Heap
* Objects communicate through method calls
* Inheritance promotes code reuse
* Method Overriding allows specialized behavior
* OOP helps build maintainable and extensible software

---
