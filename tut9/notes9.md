## Java Example: Interfaces and Inheritance

### 1. Interface: Restaurant

An interface defines a **contract** that every restaurant must follow.

```java
public interface Restaurant {
    String getName();
    String getSlogan();
}
```

---

### 2. McDonald Class

```java
public class McDonald implements Restaurant {

    @Override
    public String getName() {
        return "McDonald's";
    }

    @Override
    public String getSlogan() {
        return "I'm Lovin' It";
    }
}
```

---

### 3. KFC Class

```java
public class KFC implements Restaurant {

    @Override
    public String getName() {
        return "KFC";
    }

    @Override
    public String getSlogan() {
        return "Finger Lickin' Good";
    }
}
```

---

### 4. Testing the Interface

```java
public class Main {
    public static void main(String[] args) {

        Restaurant restaurant1 = new McDonald();
        Restaurant restaurant2 = new KFC();

        System.out.println(restaurant1.getName());
        System.out.println(restaurant1.getSlogan());

        System.out.println();

        System.out.println(restaurant2.getName());
        System.out.println(restaurant2.getSlogan());
    }
}
```

### Output

```text
McDonald's
I'm Lovin' It

KFC
Finger Lickin' Good
```

---

# Inheritance Example

### 5. Parent Class: Burger

A Burger contains properties common to all burgers.

```java
public class Burger {

    protected String bread;
    protected String filling;
    protected String cheeseType;

    public Burger(String bread, String filling, String cheeseType) {
        this.bread = bread;
        this.filling = filling;
        this.cheeseType = cheeseType;
    }

    public void displayBurger() {
        System.out.println("Bread: " + bread);
        System.out.println("Filling: " + filling);
        System.out.println("Cheese: " + cheeseType);
    }
}
```

---

### 6. Child Class: BigMac

A Big Mac is a Burger, so it inherits all Burger properties and adds its own.

```java
public class BigMac extends Burger {

    private String sauce;
    private String extraFilling;

    public BigMac(
            String bread,
            String filling,
            String cheeseType,
            String sauce,
            String extraFilling) {

        super(bread, filling, cheeseType);

        this.sauce = sauce;
        this.extraFilling = extraFilling;
    }

    public void displayBigMac() {
        displayBurger();

        System.out.println("Sauce: " + sauce);
        System.out.println("Extra Filling: " + extraFilling);
    }
}
```

---

### 7. Testing Inheritance

```java
public class Main {
    public static void main(String[] args) {

        BigMac bigMac = new BigMac(
                "Sesame Bun",
                "Beef Patty",
                "Cheddar",
                "Big Mac Sauce",
                "Lettuce"
        );

        bigMac.displayBigMac();
    }
}
```

### Output

```text
Bread: Sesame Bun
Filling: Beef Patty
Cheese: Cheddar
Sauce: Big Mac Sauce
Extra Filling: Lettuce
```

---

## How to Explain to Students

### Interface

```text
Restaurant
   ↑
implements
   ↑
McDonald, KFC
```

* Restaurant only defines rules.
* McDonald and KFC must provide a name and slogan.
* Interfaces describe **what a class can do**.

### Inheritance

```text
Burger
   ↑
extends
   ↑
BigMac
```

* BigMac automatically gets:

  * bread
  * filling
  * cheeseType

* BigMac adds:

  * sauce
  * extraFilling

* Inheritance describes an **"is-a" relationship**:

  * A BigMac **is a Burger**.

### Simple Memory Trick

* **implements** = "follows the contract"
* **extends** = "inherits from the parent"

```java
McDonald implements Restaurant
BigMac extends Burger
```

That's the simplest restaurant-themed example to demonstrate both concepts in Java.
