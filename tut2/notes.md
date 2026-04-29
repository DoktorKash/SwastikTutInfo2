# Java Control Flow Notes 

## What is Control Flow?

Control flow means **the order in which a program runs instructions**.

Java usually runs code **top to bottom**, but with control flow we can:

* make decisions → `if`
* repeat code → `for`
* repeat while condition is true → `while`

### Side note
- The questions files for the Praesenzblatt are in the [material repository](https://github.com/pi-tuebingen/material) (this is a link, you can click on it) under **tutorium**

---

# 1. IF Statement (Decision Making)

Use `if` when you want Java to choose.

## Syntax

```java
if (condition) {
    // code runs if condition is true
}
```

## Example 1: Positive Number

```java
int num = 5;

if (num > 0) {
    System.out.println("Positive number");
}
```

### Output:

```java
Positive number
```

---

## Example 2: if else

```java
int age = 16;

if (age >= 18) {
    System.out.println("Adult");
} else {
    System.out.println("Minor");
}
```

### Output:

```java
Minor
```

---

## Example 3: if else if

```java
int marks = 75;

if (marks >= 90) {
    System.out.println("Grade A");
} else if (marks >= 70) {
    System.out.println("Grade B");
} else {
    System.out.println("Grade C");
}
```

---

# 2. FOR Loop (Repeat Fixed Times)

Use `for` when you know **how many times** to repeat.

## Syntax

```java
for (start; condition; update) {
    // repeated code
}
```

---

## Example 1: Print 1 to 5

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

### Output:

```java
1
2
3
4
5
```

---

## Example 2: Even Numbers

```java
for (int i = 2; i <= 10; i += 2) {
    System.out.println(i);
}
```

### Output:

```java
2
4
6
8
10
```

---

## Example 3: Countdown

```java
for (int i = 5; i >= 1; i--) {
    System.out.println(i);
}
```

---

# 3. WHILE Loop

Use `while` when you repeat **until condition becomes false**.

## Syntax

```java
while (condition) {
    // code repeats
}
```

---

## Example 1: Print 1 to 5

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

---

## Example 2: Countdown

```java
int i = 5;

while (i >= 1) {
    System.out.println(i);
    i--;
}
```

---

# Difference Between for and while

| for loop                                 | while loop                        |
| ---------------------------------------- | --------------------------------- |
| Used when number of repetitions is known | Used when repetitions are unknown |
| Cleaner for counting                     | Better for conditions             |

---

# Real Life Examples

## if Example

```java
int password = 1234;

if (password == 1234) {
    System.out.println("Access granted");
}
```

---

## for Example

```java
for (int i = 1; i <= 3; i++) {
    System.out.println("Welcome");
}
```

---

## while Example

```java
int battery = 100;

while (battery > 0) {
    System.out.println("Battery: " + battery);
    battery -= 20;
}
```

---

# Common Mistakes

## 1. Forgetting braces

Wrong:

```java
if (x > 5)
System.out.println("Hi");
```

Better:

```java
if (x > 5) {
    System.out.println("Hi");
}
```

---

## 2. Infinite while loop

Wrong:

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
}
```

(never ends)

Correct:

```java
int i = 1;

while (i <= 5) {
    System.out.println(i);
    i++;
}
```

---

# Practice Questions

## if

1. Check if number is even or odd
2. Check if age is adult or child

## for

1. Print 1 to 10
2. Print multiplication table of 5

## while

1. Print 10 to 1
2. Print even numbers until 20

---

# Quick Summary

```java
if      -> decision
for     -> repeat fixed times
while   -> repeat while condition true
```

---

# Mini Combined Example

```java
for (int i = 1; i <= 5; i++) {

    if (i % 2 == 0) {
        System.out.println(i + " is even");
    } else {
        System.out.println(i + " is odd");
    }

}
```

### Output

```java
1 is odd
2 is even
3 is odd
4 is even
5 is odd
```

---
# Java Pattern Questions Notes

## What are Pattern Questions?

Pattern questions use **loops (`for`, `while`)** to print shapes using:

* `*`
* numbers
* letters
* spaces

They help students practice:

* nested loops
* rows and columns
* logic building

---

# Important Rule

## Outer loop = Rows

## Inner loop = Columns / Items in each row

Example:

```java id="aq6k70"
for (int i = 1; i <= 3; i++) {      // rows

    for (int j = 1; j <= 4; j++) {  // columns
        System.out.print("*");
    }

    System.out.println();
}
```

Output:

```java id="z36jvw"
****
****
****
```

---

# Pattern Type 1: Square Pattern

## Question

Print:

```java id="2xnnho"
****
****
****
****
```

## Answer

```java id="53r7i6"
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= 4; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

---

# Pattern Type 2: Increasing Triangle

## Question

Print:

```java id="6i7k7w"
*
**
***
****
```

## Answer

```java id="8o0j2q"
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

---

# Pattern Type 3: Reverse Triangle

## Question

Print:

```java id="6q6ff9"
****
***
**
*
```

## Answer

```java id="55jqdy"
for (int i = 4; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }
    System.out.println();
}
```

---

# Pattern Type 4: Number Triangle

## Question

Print:

```java id="45t7o9"
1
12
123
1234
```

## Answer

```java id="2g9ak5"
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(j);
    }
    System.out.println();
}
```

---

# Pattern Type 5: Same Number Rows

## Question

Print:

```java id="a9hyj4"
1
22
333
4444
```

## Answer

```java id="1fvx0f"
for (int i = 1; i <= 4; i++) {
    for (int j = 1; j <= i; j++) {
        System.out.print(i);
    }
    System.out.println();
}
```

---

# Pattern Type 6: Right Aligned Triangle

## Question

Print:

```java id="ly7cld"
   *
  **
 ***
****
```

## Answer

```java id="vv7v54"
for (int i = 1; i <= 4; i++) {

    for (int s = 1; s <= 4 - i; s++) {
        System.out.print(" ");
    }

    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }

    System.out.println();
}
```

---

# Pattern Type 7: Pyramid

## Question

Print:

```java id="7tn44u"
   *
  ***
 *****
*******
```

## Answer

```java id="gcrp9e"
for (int i = 1; i <= 4; i++) {

    for (int s = 1; s <= 4 - i; s++) {
        System.out.print(" ");
    }

    for (int j = 1; j <= (2 * i - 1); j++) {
        System.out.print("*");
    }

    System.out.println();
}
```

---

# Pattern Type 8: Reverse Number Triangle

## Question

Print:

```java id="m0x9kz"
1234
123
12
1
```

## Answer

```java id="bqq6bo"
for (int i = 4; i >= 1; i--) {
    for (int j = 1; j <= i; j++) {
        System.out.print(j);
    }
    System.out.println();
}
```

---

# Practice Questions (Without Answers)

1. Print:

```java id="gnlxot"
*****
*****
*****
```

2. Print:

```java id="ui9b2v"
1
22
333
4444
55555
```

3. Print:

```java id="0xq7xx"
*****
****
***
**
*
```

4. Print:

```java id="z5dc1y"
A
AB
ABC
ABCD
```

5. Print pyramid of height 5

---

# Shortcut Logic

## Triangle Increasing

```java id="zbfj4c"
inner loop <= i
```

## Triangle Decreasing

```java id="ftv92v"
inner loop <= rows - i + 1
```

## Pyramid Stars

```java id="ukl3cb"
2*i - 1
```

---

# Full Example 

```java id="hkw7b5"
for (int i = 1; i <= 5; i++) {

    for (int j = 1; j <= i; j++) {
        System.out.print("*");
    }

    System.out.println();
}
```

Output:

```java id="n5r4ys"
*
**
***
****
*****
```
---
## Extra Help / YouTube Tutorials

- [Resolving merge conflicts](https://www.jetbrains.com/help/idea/resolve-conflicts.html)
- [Youtube link for solving merge conflict](https://youtu.be/WgipWkaU2MM?si=bb2MPshZEpBgyNXt)

- [Java playlist for extra help (recommended to watch on 2x speed)](https://www.youtube.com/watch?v=rZ41y93P2Qo&list=PL9gnSGHSqcnr_DxHsP7AW9ftq0AtAyYqJ)
---

# Final Tip 

Whenever solving pattern:

1. Count rows
2. Count columns
3. Find what changes each row
4. Use nested loops

# PU answers
for each question you can make a seperate file, i saw that you have still not started with how functions are written so the solutions can be used in the **main** function of each file.
For e.g. for the first question's solution you can make a Chess java class like we discussed today and just put the following solution code in the main method of that file.

### Ans 1
```java
    int n = 4;
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {

            int value = (i + j) % 2 == 0 ? 1 : 0;
            System.out.print(value);

            if (j < n - 1) {
                System.out.print(" ");
            }
        }
        System.out.println();
    }

```



### Ans 2
``` java
    int n = 12;
    boolean primality = true;
    if (n < 2) {
        primality = false;
    }
    for (int i = 2; i < n; i++) {
        if (n % i == 0) {
            primality = false;
            break;
        }
    }
    System.out.println(primality);
```
### Ans 3
```java
    int n = 5;
    double sum = 0.0;
    double factorial = 1.0;

    for (int k = 0; k <= n; k++) {
        if (k > 0) {
            factorial *= k;
        }
        sum += 1.0 / factorial;
    }

    System.out.println(sum);

```
