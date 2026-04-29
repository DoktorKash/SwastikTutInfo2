# Tutorial 1 Info 2

**Course:** Praktische Informatik 2  
**University:** Eberhard Karls Universität Tübingen   
**Tutor:** Swastik Kashyap  
**Date:** 22.04.2026

### Organisation

* The programming language used in this course is **Java**, and our preferred IDE is **IntelliJ IDEA**.

* Homework assignments will be managed through **GitHub** and completed using **IntelliJ IDEA**. Submissions must be made by your assigned teams (more information regarding *Klausurzulassung* can be found below).

* Attendance in the tutorials is not mandatory, but it is **highly recommended** to participate regularly.

#### Klausurzulassung
In order to get the permission to participate in the exam you need the following:
- Complete at least 50% of the homeworks with correct auto checks (*green tick marks*)
- Every student must present their Solution to any one task of the Homework at least __twice__ during the course of the tutorials

### Smart use of AI



### Discussion Points  
- What is a function?  
- What are input and output?  

---

### What is Syntax?  

**Syntax** describes the *rules* for how a program must be written so that the computer can understand it, similar to grammar in a spoken language.  
If something is written in the wrong order or structure, the computer won’t understand it and will throw a **syntax error**.  

🍔 **Analogy – Ordering at McDonald’s:**  
Imagine you go to McDonald’s and place an order.  
The **function** is like *McDonald’s itself* — it’s where your request is processed.  
The **input** is what you say at the counter, for example:  
> “**One Big Mac menu, please**”

Here:  
- “**One**” = the *quantity*  
- “**Big Mac**” = the *product name*  
- “**Menu**” = the *category* (it could also be “single item”)  

If you say it **in this order**, the employee understands you.  
But if you say:  
> “**Big Mac please one menu**”  
it would be confusing — the employee wouldn’t know what you mean.  

Programming syntax works the same way:  
Only if the *order and structure* are correct can the computer understand what you want and produce the correct **output**.  

🍟 **In short:**  
- **Syntax** = correct order and spelling  
- **Function** = the process that happens in the background  
- **Output** = the result you get  

### Data types
## What Are Data Types in Java? 🎒

Think of a **data type** as a label that tells Java **what kind of value** you want to store and **how much space** it needs.

Just like in real life, you use different containers for different things:

* A **water bottle** for water 💧
* A **wallet** for money 💵
* A **photo album** for pictures 📸

Java does the same with data.

---

## Example: Student Backpack 🎒

Imagine a student going to university with a backpack:

```java
int age = 21;
double height = 1.78;
char grade = 'A';
boolean passedExam = true;
String name = "Alex";
```

Each variable stores a different kind of information:

* `age` → whole number
* `height` → decimal number
* `grade` → single letter
* `passedExam` → yes/no
* `name` → text

---

# Two Main Categories of Data Types in Java

## 1. Primitive Data Types ⚡

These are the **basic built-in types** in Java.
They store **actual values directly**.

Think of them as ready-made boxes.

### Java Primitive Types:

| Type      | Example   | Meaning          |
| --------- | --------- | ---------------- |
| `int`     | `5`       | whole number     |
| `double`  | `3.14`    | decimal number   |
| `char`    | `'a'`     | single character |
| `boolean` | `true`    | true / false     |
| `byte`    | `100`     | small integer    |
| `short`   | `2000`    | short integer    |
| `long`    | `999999L` | large integer    |
| `float`   | `2.5f`    | decimal          |

### Example 🍕

```java
int pizzaSlices = 8;
boolean hungry = true;
char size = 'L';
double price = 12.99;
```

---

## 2. Non-Primitive Data Types 📦

These are more advanced types that store **references to objects**, not the raw value directly.

Think of them like a **remote control** pointing to the TV instead of being the TV.

### Examples:

* `String`
* Arrays
* Classes
* Objects
* Interfaces

### Fun Example 🎮

```java
String playerName = "Mario";
int[] scores = {10, 20, 30};
```

* `String` stores text
* `int[]` stores multiple numbers
* They are objects/reference types

---

# Primitive vs Non-Primitive (Easy Memory Trick)

## Primitive = Basic Ingredients 🍳

* egg
* milk
* flour

Simple and direct.

## Non-Primitive = Full Meal 🍔

* burger
* pizza
* sandwich

Made of many things, more complex.

---

# Key Differences

| Primitive           | Non-Primitive                |
| ------------------- | ---------------------------- |
| stores actual value | stores reference/address     |
| lowercase names     | usually capitalized names    |
| built into Java     | created by Java/library/user |
| fixed size          | can grow/change              |



