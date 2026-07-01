# Interprogramming – Java Tutorial Notes

## 1. Motivation

### Why Do We Use Methods, Classes, and Variables?

When programs become large, writing everything in one block becomes:

* Hard to read
* Hard to debug
* Hard to reuse

Java organizes programs using:

* **Classes**
* **Methods**
* **Variables**

This makes programs:

* Cleaner
* Easier to maintain
* Reusable

---

## Real-Life Analogy

Think of a **car factory**:

* One department builds engines
* Another paints the car
* Another installs wheels

Each part has a specific task, but together they build one car.

Java programs work the same way:

* Methods do tasks
* Variables store information
* Classes organize everything together

---

# 2. Methods, Procedures, and Functions in Java

In Java, the word **method** is commonly used instead of “function.”

A method is a reusable block of code.

---

# A. Method Without Return Value (Procedure-like)

This method performs an action but returns nothing.

### Example

```java id="t34bn1"
public class Greeting {

    static void greet(String name) {
        System.out.println("Hello " + name);
    }

    public static void main(String[] args) {
        greet("Anna");
    }
}
```

---

## Explanation

* `void` means no value is returned
* The method only performs an action

---

## Analogy

A **school bell**:

* It performs an action
* Nothing comes back

---

# B. Method With Return Value (Function-like)

This method calculates something and returns a value.

### Example

```java id="l2mk8d"
public class Calculator {

    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {

        int result = add(3, 4);

        System.out.println(result);
    }
}
```

---

## Explanation

* `int` means the method returns an integer
* `return` sends the result back

---

## Analogy

A **vending machine**:

* Input money + selection
* Output snack

Input → Process → Output

---

# C. Object Methods

Methods can belong to objects.

### Example

```java id="4d9ez7"
class Dog {

    void bark() {
        System.out.println("Woof!");
    }
}

public class Main {

    public static void main(String[] args) {

        Dog dog1 = new Dog();

        dog1.bark();
    }
}
```

---

## Explanation

* `bark()` belongs to the `Dog` class
* Objects of Dog can use it

---

## Analogy

A smartphone:

* Camera app takes pictures
* Music app plays music

The abilities belong to the phone.

---

# Method Summary

| Type                  | Returns Value? | Example        |
| --------------------- | -------------- | -------------- |
| Procedure-like Method | No             | `void greet()` |
| Function-like Method  | Yes            | `int add()`    |
| Object Method         | Depends        | `dog.bark()`   |

---

# 3. Local Variables and Class Variables

Variables store data.

---

# A. Local Variable

A local variable exists only inside a method.

### Example

```java id="4y9zv8"
public class Example {

    static void test() {

        int x = 10;

        System.out.println(x);
    }

    public static void main(String[] args) {
        test();
    }
}
```

---

## Explanation

* `x` only exists inside `test()`
* Outside the method, Java cannot access it

---

## Analogy

A hotel room key:

* Temporary
* Only works during your stay

---

# B. Class Variable

A class variable belongs to the whole class and is shared.

### Example

```java id="u6fd8j"
class Student {

    static String schoolName = "Green School";
}

public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();
        Student s2 = new Student();

        System.out.println(s1.schoolName);
        System.out.println(s2.schoolName);
    }
}
```

---

## Explanation

* `schoolName` is shared by all students
* Only one copy exists

---

## Analogy

A school uniform:

* Shared identity for all students

---

# Local Variable vs Class Variable

| Local Variable                    | Class Variable           |
| --------------------------------- | ------------------------ |
| Exists inside method              | Exists inside class      |
| Temporary                         | Shared                   |
| Each method call creates new copy | One copy for all objects |

---

# 4. Static Methods and Static Variables

In Java, `static` means:

> Belongs to the class itself, not to an object.

---

# A. Static Variable

### Example

```java id="4rwef3"
class Counter {

    static int count = 0;

    Counter() {
        count++;
    }
}

public class Main {

    public static void main(String[] args) {

        new Counter();
        new Counter();

        System.out.println(Counter.count);
    }
}
```

---

## Explanation

* Every object increases the same variable
* Shared among all objects

---

## Analogy

A museum visitor counter:

* Everyone increases the same number

---

# B. Static Method

### Example

```java id="x7n4qp"
class MathTools {

    static int multiply(int a, int b) {

        return a * b;
    }
}

public class Main {

    public static void main(String[] args) {

        System.out.println(MathTools.multiply(3, 5));
    }
}
```

---

## Explanation

* No object needed
* Called directly using class name

---

## Analogy

A calculator in a classroom:

* Anyone can use it
* It does not belong to one student

---

# Why Use Static Methods?

Use static methods when:

* No object data is needed
* The method is general utility code

Examples:

* Math calculations
* Unit conversion
* Validation

---

# Complete Java Example

```java id="7g1t5q"
class BankAccount {

    // Static/Class Variable
    static String bankName = "ABC Bank";

    // Instance Variables
    String owner;
    double balance;

    // Constructor
    BankAccount(String owner, double balance) {

        this.owner = owner;
        this.balance = balance;
    }

    // Object Method
    void deposit(double amount) {

        balance += amount;
    }

    // Static Method
    static void bankRules() {

        System.out.println("Minimum balance is 100.");
    }
}

public class Main {

    public static void main(String[] args) {

        BankAccount acc1 =
            new BankAccount("John", 500);

        acc1.deposit(200);

        BankAccount.bankRules();

        System.out.println(acc1.balance);

        System.out.println(BankAccount.bankName);
    }
}
```

---

# Key Takeaways

## Methods

* Methods are reusable blocks of code
* Some return values, others only perform actions

## Variables

* Local variables are temporary
* Class/static variables are shared

## Static

* Static methods belong to the class
* Static variables are shared by all objects

---

# Simple Analogy Summary

| Java Concept       | Real-Life Analogy   |
| ------------------ | ------------------- |
| Method             | Worker doing a task |
| Method with Return | Vending machine     |
| Void Method        | School bell         |
| Object Method      | Smartphone feature  |
| Local Variable     | Hotel key           |
| Class Variable     | School uniform      |
| Static Variable    | Visitor counter     |
| Static Method      | Shared calculator   |


---
# Slides notes 
# Extended Java Tutorial Notes – Interprogramming / Subprograms

Based on the lecture slides 

---

# 1. What Are Subprograms?

A **subprogram** (Unterprogramm) is a reusable block of instructions that solves a specific task. 

In Java, subprograms are called **methods**.

Examples:

* Calculating an average
* Printing text
* Reading user input
* Sorting numbers

---

# Why Are Methods Important?

Methods help programmers:

* Avoid repeating code
* Make programs easier to read
* Split large problems into smaller tasks
* Reuse functionality

---

# Black Box Principle

The slides describe methods as **Black Boxes**. 

## Idea

A user of the method:

* Knows the inputs
* Knows the outputs
* Does NOT need to know internal implementation details

---

## Real-Life Analogy

Think of a **coffee machine**.

You:

* Press buttons (input)
* Receive coffee (output)

You do NOT need to understand:

* Internal pipes
* Heating systems
* Electronics

Methods work the same way.

---

# Interface vs Implementation

## Interface

Defines:

* What the method does
* Which parameters it needs
* Which value it returns

## Implementation

The internal code inside the method.

---

## Example

```java id="mx7aa2"
static int square(int x) {
    return x * x;
}
```

### Interface

```java id="ax2mna"
int square(int x)
```

### Implementation

```java id="jlwm7x"
{
    return x * x;
}
```

---

# Good Method Design Rules

From the slides: 

## A good method should:

1. Have a simple interface
2. Be easy to understand
3. Hide implementation details
4. Be independent from the larger system

---

# Readability and Comments

Methods should be documented clearly. 

---

## Example with JavaDoc

```java id="8lw0yi"
/**
 * Calculates the square of a number.
 * @param x input number
 * @return square of x
 */
static int square(int x) {
    return x * x;
}
```

---

# Analogy

Comments are like instructions in a recipe book:

* Ingredients = parameters
* Final dish = return value

---

# 2. Types of Methods

The slides divide methods into: 

| Type                         | Description |
| ---------------------------- | ----------- |
| Methods with return value    | Functions   |
| Methods without return value | Procedures  |

---

# A. Methods Without Return Value

These methods only perform actions.

### Example

```java id="2ag5ff"
static void sayHello() {
    System.out.println("Hello!");
}
```

---

## Explanation

* `void` means no result is returned
* The method only executes instructions

---

## Analogy

A light switch:

* You press it
* The room lights up
* Nothing is returned

---

# B. Methods With Return Value

### Example

```java id="ebx9ka"
static int add(int a, int b) {
    return a + b;
}
```

---

## Explanation

The method:

1. Receives values
2. Processes them
3. Returns a result

---

## Analogy

A calculator:

* Input numbers
* Receive result

---

# 3. Java Method Structure

From the slides: 

```java id="0w2onm"
<modifier> <returnType> <methodName>(parameters) {

    // method body
}
```

---

# Example Breakdown

```java id="4r2hms"
public static int multiply(int a, int b) {

    return a * b;
}
```

| Part         | Meaning          |
| ------------ | ---------------- |
| public       | access modifier  |
| static       | belongs to class |
| int          | return type      |
| multiply     | method name      |
| int a, int b | parameters       |

---

# 4. Modifiers

Modifiers define:

* Who can use the method
* How the method belongs to the class



---

# Access Modifiers

| Modifier    | Accessible From        |
| ----------- | ---------------------- |
| public      | Everywhere             |
| private     | Only inside same class |
| protected   | Package + subclasses   |
| no modifier | Same package           |

---

# Real-Life Analogy

Think of a house:

| Modifier        | Analogy                   |
| --------------- | ------------------------- |
| public          | Public park               |
| private         | Personal bedroom          |
| protected       | Family room               |
| package-private | Apartment building access |

---

# Example

```java id="1r0kgx"
private static void secretMethod() {
    System.out.println("Secret");
}
```

Only methods inside the same class can call it.

---

# 5. Parameters

Parameters are inputs for methods. 

---

# Example

```java id="bdvr9q"
static void printSum(int a, int b) {

    System.out.println(a + b);
}
```

### Method Call

```java id="79mrl4"
printSum(3, 5);
```

---

# Important Rule

Each parameter needs:

* Its own type
* Its own name

Correct:

```java id="fgj1xm"
(int x, int y)
```

Wrong:

```java id="2q7x9w"
(int x, y)
```

---

# Analogy

Ordering pizza:

* Size
* Toppings
* Crust type

Each input must be specified clearly.

---

# 6. Method Calls

From the slides: 

---

# Calling a Method in Same Class

```java id="a8f79x"
add(3, 4);
```

# Calling a Static Method from Another Class

```java id="hn0z5e"
Math.sqrt(25);
```

---

# Analogy

Calling a friend:

* Same house → just call name
* Different city → use full address

---

# 7. Parameter Passing (Call-by-Value)

Java uses **call-by-value**. 

---

# Primitive Types Example

```java id="e2tkk1"
static void change(int x) {
    x = 100;
}

public static void main(String[] args) {

    int a = 5;

    change(a);

    System.out.println(a);
}
```

Output:

```text
5
```

---

# Why?

Java copies the value into the method.

Changing `x` does NOT change `a`.

---

# Analogy

Photocopy of homework:

* Teacher writes on copy
* Original remains unchanged

---

# 8. Arrays and References

Arrays behave differently because array variables store references. 

---

# Example

```java id="tb1lf7"
static void setZero(int[] arr) {

    arr[0] = 0;
}

public static void main(String[] args) {

    int[] numbers = {5, 6, 7};

    setZero(numbers);

    System.out.println(numbers[0]);
}
```

Output:

```text
0
```

---

# Explanation

The method receives a copy of the reference,
but both references point to the SAME array.

---

# Analogy

Two people holding the same TV remote:

* Both control the same television

---

# 9. Local Variables

Local variables exist only inside methods. 

---

# Example

```java id="5xg2g6"
static void test() {

    int x = 10;

    System.out.println(x);
}
```

`x` disappears after the method ends.

---

# Analogy

A hotel key card:

* Temporary
* Works only during your stay

---

# 10. Class Variables (Static Variables)

Class variables belong to the class itself. 

---

# Example

```java id="ghd1sx"
class Counter {

    static int count = 0;
}
```

Shared among all objects.

---

# Analogy

Scoreboard in a stadium:

* One shared display
* Everyone sees same score

---

# 11. Lifetime of Variables

From the slides: 

---

# Local Variables

Created:

* When method starts

Destroyed:

* When method ends

---

# Static Variables

Created:

* When program starts

Destroyed:

* When program ends

---

# Analogy

| Variable Type | Analogy                 |
| ------------- | ----------------------- |
| Local         | Temporary visitor badge |
| Static        | Permanent building sign |

---

# 12. Return Values

Methods can return results using `return`. 

---

# Example

```java id="jxt5di"
static int max(int a, int b) {

    if (a > b)
        return a;

    return b;
}
```

---

# Early Return

A method can stop immediately using `return`.

```java id="r9cybd"
static int find(int[] arr, int value) {

    for (int i = 0; i < arr.length; i++) {

        if (arr[i] == value)
            return i;
    }

    return -1;
}
```

---

# Analogy

Searching for keys:

* Once found, stop searching immediately

---

# 13. Side Effects

A side effect means:

> A method changes something outside itself.



---

# Dangerous Example

```java id="n2fx4v"
static int number = 1;

static void sideEffect() {

    number = 5;
}
```

The method changes global state.

---

# Why Side Effects Are Dangerous

They can:

* Cause hidden bugs
* Make debugging difficult
* Create unexpected behavior

---

# Analogy

Someone secretly changing your calculator settings:

* Results suddenly become incorrect
* Hard to understand why

---

# 14. Pure Functions (No Side Effects)

Good methods:

* Only use parameters
* Only return results
* Do not change global variables

---

# Example

```java id="ozmbuj"
static String reverse(String text) {

    String result = "";

    for (int i = text.length() - 1; i >= 0; i--) {

        result += text.charAt(i);
    }

    return result;
}
```

---

# Advantages of Pure Functions

They are:

* Easier to test
* Easier to debug
* Predictable
* Reusable

---

# Final Summary

## Methods

* Reusable code blocks
* Improve structure and readability

## Parameters

* Inputs for methods
* Passed using call-by-value

## Variables

* Local variables exist temporarily
* Static variables exist globally

## Static

* Belongs to class
* Shared by all objects

## Return Values

* Sent back using `return`

## Side Effects

* Can modify external state
* Should be minimized

---

# Ultimate Analogy Table

| Java Concept    | Real-Life Analogy          |
| --------------- | -------------------------- |
| Method          | Worker performing a task   |
| Parameter       | Ingredients in recipe      |
| Return value    | Finished meal              |
| Local variable  | Temporary note             |
| Static variable | School scoreboard          |
| Interface       | Restaurant menu            |
| Implementation  | Kitchen process            |
| Call-by-value   | Photocopy                  |
| Array reference | Shared remote control      |
| Side effect     | Secretly changing settings |
