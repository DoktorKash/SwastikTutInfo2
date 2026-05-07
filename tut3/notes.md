## Tutorial 3

# Arrays Notes (with Examples, Analogies, Questions & Answers)

---

# 1. What is an Array?

An **array** is a collection of items of the **same data type** stored together under one name.

Instead of creating many separate variables:

```java
int mark1 = 80;
int mark2 = 75;
int mark3 = 90;
```

We can use an array:

```java
int[] marks = {80, 75, 90};
```

---

# Real-Life Analogy for Arrays

Think of an array like a row of lockers.

* Each locker stores one value.
* Every locker has a number called an **index**.
* The first locker starts at index `0`.

Example:

| Index | Value |
| ----- | ----- |
| 0     | 80    |
| 1     | 75    |
| 2     | 90    |

So:

```java
marks[0]
```

means:

> “Get the value from locker 0”

Output:

```java
80
```

---

# 2. What is a Reference Variable?

Arrays are stored in memory.

The array variable itself does NOT store all the values directly.

Instead, it stores the **address/location** of the array in memory.

This variable is called a **reference variable**.

Example:

```java
int[] numbers = {1, 2, 3};
```

Here:

* `numbers` is a **reference variable**
* It points to the array in memory

Analogy:

Think of:

* the array as a house
* the reference variable as the house address

The address helps us find the house.

---

# 3. What Does Initialising Mean?

**Initialising** means giving values to variables or arrays.

Example:

```java
int x = 5;
```

`x` is initialised with value `5`.

Array initialisation:

```java
int[] nums = {10, 20, 30};
```

The array is created and given values immediately.

---

# 4. Declaring vs Initialising Arrays

## Declaring an Array

```java
int[] arr;
```

This only creates the reference variable.

No actual array yet.

---

## Creating the Array

```java
arr = new int[5];
```

This creates an array of size 5.

Default values:

```java
[0, 0, 0, 0, 0]
```

---

## Declaring + Initialising Together

```java
int[] arr = {1, 2, 3, 4};
```

---

# 5. 1D Arrays (One-Dimensional Arrays)

A **1D array** is like a single row.

Example:

```java
int[] numbers = {10, 20, 30, 40};
```

Visual:

| Index | 0  | 1  | 2  | 3  |
| ----- | -- | -- | -- | -- |
| Value | 10 | 20 | 30 | 40 |

---

# 6. Using For Loops with 1D Arrays

For loops are commonly used to:

* print values
* calculate totals
* search for items
* update values

---

## Example 1: Printing All Elements

```java
int[] numbers = {10, 20, 30, 40};

for(int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

---

## How it Works

| i | numbers[i] |
| - | ---------- |
| 0 | 10         |
| 1 | 20         |
| 2 | 30         |
| 3 | 40         |

---

## Output

```java
10
20
30
40
```

---

# Question & Answer

## Question 1

What does this print?

```java
int[] arr = {5, 10, 15};

for(int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

## Answer

```java
5
10
15
```

---

# Example 2: Finding the Sum

```java
int[] nums = {2, 4, 6, 8};

int sum = 0;

for(int i = 0; i < nums.length; i++) {
    sum = sum + nums[i];
}

System.out.println(sum);
```

---

## Step-by-Step

| i | nums[i] | sum |
| - | ------- | --- |
| 0 | 2       | 2   |
| 1 | 4       | 6   |
| 2 | 6       | 12  |
| 3 | 8       | 20  |

---

## Output

```java
20
```

---

# Question & Answer

## Question 2

What is the final value of `sum`?

```java
int[] arr = {1, 3, 5};

int sum = 0;

for(int i = 0; i < arr.length; i++) {
    sum += arr[i];
}
```

## Answer

```java
9
```

---

# 7. 2D Arrays (Two-Dimensional Arrays)

A **2D array** is like a table or grid.

Analogy:

* 1D array = one row of lockers
* 2D array = many rows and columns

Example:

```java
int[][] grid = {
    {1, 2, 3},
    {4, 5, 6}
};
```

Visual:

|       | Col 0 | Col 1 | Col 2 |
| ----- | ----- | ----- | ----- |
| Row 0 | 1     | 2     | 3     |
| Row 1 | 4     | 5     | 6     |

---

# Accessing Elements in 2D Arrays

```java
grid[0][1]
```

means:

* row 0
* column 1

Output:

```java
2
```

---

# 8. Using Nested For Loops with 2D Arrays

A **nested loop** means:

* one loop inside another loop

Usually:

* outer loop = rows
* inner loop = columns

---

# Example 1: Printing a 2D Array

```java
int[][] grid = {
    {1, 2, 3},
    {4, 5, 6}
};

for(int row = 0; row < grid.length; row++) {

    for(int col = 0; col < grid[row].length; col++) {

        System.out.print(grid[row][col] + " ");
    }

    System.out.println();
}
```

---

# Output

```java
1 2 3
4 5 6
```

---

# How the Loops Work

## First Row

| row | col | value |
| --- | --- | ----- |
| 0   | 0   | 1     |
| 0   | 1   | 2     |
| 0   | 2   | 3     |

---

## Second Row

| row | col | value |
| --- | --- | ----- |
| 1   | 0   | 4     |
| 1   | 1   | 5     |
| 1   | 2   | 6     |

---

# Question & Answer

## Question 3

What does this print?

```java
int[][] nums = {
    {7, 8},
    {9, 10}
};

for(int r = 0; r < nums.length; r++) {

    for(int c = 0; c < nums[r].length; c++) {

        System.out.print(nums[r][c] + " ");
    }

    System.out.println();
}
```

---

## Answer

```java
7 8
9 10
```

---

# Example 2: Finding Total in 2D Array

```java
int[][] values = {
    {1, 2},
    {3, 4}
};

int total = 0;

for(int r = 0; r < values.length; r++) {

    for(int c = 0; c < values[r].length; c++) {

        total += values[r][c];
    }
}

System.out.println(total);
```

---

# Calculation

```text
1 + 2 + 3 + 4 = 10
```

---

# Output

```java
10
```

---

# Question & Answer

## Question 4

What is the output?

```java
int[][] arr = {
    {2, 2},
    {2, 2}
};

int total = 0;

for(int i = 0; i < arr.length; i++) {

    for(int j = 0; j < arr[i].length; j++) {

        total += arr[i][j];
    }
}

System.out.println(total);
```

---

## Answer

```java
8
```

---

# 9. Important Array Concepts

## Array Length

```java
arr.length
```

Gives number of elements.

Example:

```java
int[] nums = {1,2,3};

System.out.println(nums.length);
```

Output:

```java
3
```

---

# 10. Common Mistake: Index Out of Bounds

Wrong:

```java
int[] arr = {1,2,3};

System.out.println(arr[3]);
```

Why wrong?

* Last index is 2
* Index 3 does not exist

Correct indexes:

```text
0 1 2
```

---

# 11. Enhanced For Loop (For-Each Loop, note sure if this is discussed in the Lectures, dont use in exam if it has not been discussed there)

Simpler way to loop through arrays.

Example:

```java
int[] nums = {10, 20, 30};

for(int value : nums) {
    System.out.println(value);
}
```

Output:

```java
10
20
30
```

---

# 12. Summary

## Arrays

* Store multiple values of same type
* Indexed starting from 0

## Reference Variable

* Stores address of array in memory

## Initialising

* Giving values to variables/arrays

## 1D Arrays

* Single row of data

## 2D Arrays

* Rows and columns (tables)

## For Loops

Used to:

* print values
* calculate totals
* search data
* update data

## Nested Loops

Needed for 2D arrays:

* outer loop → rows
* inner loop → columns


## Game


##### Printing the game with emojis
```java
    static void printWorld() {
        System.out.println("\n--- KARTE ---");
        for (int y = 0; y < GRID_SIZE; y++) {
            for (int x = 0; x < GRID_SIZE; x++) {
                if (!discovered[x][y]) {
                    System.out.print("██ ");
                } else {
                    switch (world[x][y]) {
                        case PLAYER   -> System.out.print("🔴 ");
                        case GRASS    -> System.out.print("🌱 ");
                        case WATER    -> System.out.print("🌊 ");
                        case MOUNTAIN -> System.out.print("⛰️ ");
                        case BOUNDARY -> System.out.print("🧱 ");
                    }
                }
            }
            System.out.println();
        }
        System.out.println("-------------");
    }


```

##### Moving player 
```java
    static void movePlayer(String input) {
        int tx = playerX;
        int ty = playerY;
        if (input.equals("w")) ty--;
        else if (input.equals("s")) ty++;
        else if (input.equals("a")) tx--;
        else if (input.equals("d")) tx++;
        else return;
        if (tx < 0 || ty < 0 || tx >= GRID_SIZE || ty >= GRID_SIZE) return;

        Tile target = world[tx][ty];
        if (target == Tile.GRASS) {
            world[playerX][playerY] = Tile.GRASS;
            world[tx][ty] = Tile.PLAYER;
            playerX = tx;
            playerY = ty;
        }
    }
```

#### Updating based on movement
```java
static void updateVisibility() {
        if (playerX < 0 || playerX >= GRID_SIZE || playerY < 0 || playerY >= GRID_SIZE)
            return;

        discovered[playerX][playerY] = true;

        if (playerX + 1 < GRID_SIZE)
            discovered[playerX + 1][playerY] = true;

        if (playerX - 1 >= 0)
            discovered[playerX - 1][playerY] = true;

        if (playerY + 1 < GRID_SIZE)
            discovered[playerX][playerY + 1] = true;

        if (playerY - 1 >= 0)
            discovered[playerX][playerY - 1] = true;
    }
```