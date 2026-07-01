# Recursion in Java 

## 1. What is Recursion?

Recursion means **a function calls itself** to solve a smaller version of the same problem.

### Analogy

Think of standing between two mirrors. Each mirror shows a smaller version of the same image again and again. Recursion works similarly: the same function repeats with smaller input.

---

## 2. Important Parts of Recursion

Every recursive function needs:

### 1. Base Case

The condition where recursion stops.

### 2. Recursive Case

The function calls itself with a smaller or simpler input.

```java
void function(int n) {
    if (n == 0) {
        return; // base case
    }

    function(n - 1); // recursive case
}
```

---

# Example 1: Print Numbers from 1 to N

```java
public class RecursionExample {
    static void printToN(int n) {
        if (n == 0) {
            return;
        }

        printToN(n - 1);
        System.out.println(n);
    }

    public static void main(String[] args) {
        printToN(5);
    }
}
```

### Output

```text
1
2
3
4
5
```

### How it works

```text
printToN(5)
 → printToN(4)
   → printToN(3)
     → printToN(2)
       → printToN(1)
         → printToN(0) stops
```

Then printing happens while returning back:

```text
1 2 3 4 5
```

---

# Example 2: Print Numbers from N to 1

```java
public class RecursionExample {
    static void printReverse(int n) {
        if (n == 0) {
            return;
        }

        System.out.println(n);
        printReverse(n - 1);
    }

    public static void main(String[] args) {
        printReverse(5);
    }
}
```

### Output

```text
5
4
3
2
1
```

---

# Example 3: Fibonacci Using Recursion

Fibonacci sequence:

```text
0, 1, 1, 2, 3, 5, 8, 13...
```

Formula:

```text
fib(n) = fib(n - 1) + fib(n - 2)
```

```java
public class FibonacciExample {
    static int fibonacci(int n) {
        if (n == 0) {
            return 0;
        }

        if (n == 1) {
            return 1;
        }

        return fibonacci(n - 1) + fibonacci(n - 2);
    }

    public static void main(String[] args) {
        System.out.println(fibonacci(6));
    }
}
```

### Output

```text
8
```

### Analogy

To find the 6th Fibonacci number, Java asks:

```text
fibonacci(6)
= fibonacci(5) + fibonacci(4)
```

Then each of those asks smaller questions until reaching `0` or `1`.

---

# Types of Recursion

## 1. Direct Recursion

A function directly calls itself.

```java
static void countDown(int n) {
    if (n == 0) {
        return;
    }

    System.out.println(n);
    countDown(n - 1);
}
```

---

## 2. Indirect Recursion

One function calls another function, and that function calls the first one again.

```java
static void functionA(int n) {
    if (n <= 0) {
        return;
    }

    System.out.println("A: " + n);
    functionB(n - 1);
}

static void functionB(int n) {
    if (n <= 0) {
        return;
    }

    System.out.println("B: " + n);
    functionA(n - 1);
}
```

### Analogy

Two friends passing a ball back and forth until the count reaches zero.

---

## 3. Tail Recursion

Tail recursion means the **recursive call is the last statement** in the function.

```java
static void printTail(int n) {
    if (n == 0) {
        return;
    }

    System.out.println(n);
    printTail(n - 1); // last statement
}
```

### Analogy

Imagine giving instructions one after another and not needing to remember anything after giving the next instruction.

---

## 4. Non-Tail Recursion

In non-tail recursion, some work is still left after the recursive call returns.

```java
static void printNonTail(int n) {
    if (n == 0) {
        return;
    }

    printNonTail(n - 1);
    System.out.println(n); // work happens after recursion
}
```

### Output for `printNonTail(5)`

```text
1
2
3
4
5
```

### Analogy

Like going down stairs first, then counting the steps while coming back up.

---

# Stack Memory in Recursion

Each function call is stored in memory called the **call stack**.

For:

```java
printReverse(3);
```

Stack looks like:

```text
printReverse(3)
printReverse(2)
printReverse(1)
printReverse(0)
```

When base case is reached, functions return one by one.

---

# Common Mistake: Missing Base Case

```java
static void wrongFunction() {
    System.out.println("Hello");
    wrongFunction();
}
```

This never stops and causes:

```text
StackOverflowError
```

---

# Simple Rule for Students

Before writing recursion, ask:

1. What is the smallest problem?
2. When should the function stop?
3. How can I reduce the problem each time?

Example:

```java
static int factorial(int n) {
    if (n == 0) {
        return 1;
    }

    return n * factorial(n - 1);
}
```

For `factorial(5)`:

```text
5 × 4 × 3 × 2 × 1 = 120
```

---

# Summary

Recursion is useful when a problem can be divided into smaller similar problems.

Examples:

```text
Printing numbers
Factorial
Fibonacci
Tree traversal
Searching folders
Backtracking problems
```

Main idea:

```text
Solve a smaller problem again and again until the base case is reached.
```
