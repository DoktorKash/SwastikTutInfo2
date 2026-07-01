# Java Method and Constructor Overloading

## 1. Big Idea: What is Overloading?

**Overloading** means using the **same name** for different methods or constructors, as long as Java can tell the difference from the **parameters**.

Think of the word **“open”** in real life:

* Open a door
* Open a book
* Open an app
* Open your eyes

Same word: **open**
Different situations: Java understands by the context.

In Java, the “context” is the method’s **parameter list**.

---

## 2. Human Class Example

Let us start with a simple `Human` class.

```java
public class Human {
    String name;
    int age;

    public Human() {
        this.name = "Unknown";
        this.age = 0;
    }

    public Human(String name) {
        this.name = name;
        this.age = 0;
    }

    public Human(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("Hi, I am " + name + ".");
    }

    public void introduce(String greeting) {
        System.out.println(greeting + ", I am " + name + ".");
    }

    public void introduce(String greeting, String city) {
        System.out.println(greeting + ", I am " + name + " from " + city + ".");
    }
}
```

---

## 3. Constructor Overloading

A **constructor** creates an object.

Here we have three constructors with the same name:

```java
public Human()
public Human(String name)
public Human(String name, int age)
```

This is called **constructor overloading**.

Example:

```java
Human h1 = new Human();
Human h2 = new Human("Amit");
Human h3 = new Human("Sara", 20);
```

Java decides which constructor to use by looking at the arguments.

Analogy:

Ordering coffee:

```text
Coffee()
Coffee(size)
Coffee(size, sugar)
```

Same idea: coffee, but different information given.

---

## 4. Method Overloading

A **method** does an action.

These methods are overloaded:

```java
public void introduce()
public void introduce(String greeting)
public void introduce(String greeting, String city)
```

Example:

```java
Human h = new Human("Amit", 18);

h.introduce();
h.introduce("Hello");
h.introduce("Hello", "Delhi");
```

Output:

```text
Hi, I am Amit.
Hello, I am Amit.
Hello, I am Amit from Delhi.
```

Java chooses the correct method based on how many arguments are passed.

---

## 5. Student Class Extending Human

Now we create a child class called `Student`.

A student **is a human**, but also has a `studentID`.

```java
public class Student extends Human {
    int studentID;

    public Student() {
        super();
        this.studentID = 0;
    }

    public Student(String name) {
        super(name);
        this.studentID = 0;
    }

    public Student(String name, int age) {
        super(name, age);
        this.studentID = 0;
    }

    public Student(String name, int age, int studentID) {
        super(name, age);
        this.studentID = studentID;
    }

    public void study() {
        System.out.println(name + " is studying.");
    }

    public void study(String subject) {
        System.out.println(name + " is studying " + subject + ".");
    }

    public void study(String subject, int hours) {
        System.out.println(name + " is studying " + subject + " for " + hours + " hours.");
    }
}
```

---

## 6. Using the Student Class

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        Student s2 = new Student("Riya");
        Student s3 = new Student("Riya", 19);
        Student s4 = new Student("Riya", 19, 101);

        s4.introduce();
        s4.introduce("Good morning");
        s4.introduce("Good morning", "Mumbai");

        s4.study();
        s4.study("Java");
        s4.study("Java", 2);
    }
}
```

Possible output:

```text
Hi, I am Riya.
Good morning, I am Riya.
Good morning, I am Riya from Mumbai.
Riya is studying.
Riya is studying Java.
Riya is studying Java for 2 hours.
```

---

## 7. Overloading by Number of Parameters

Java can overload methods if the number of parameters is different.

```java
public void study() {
    System.out.println("Studying.");
}

public void study(String subject) {
    System.out.println("Studying " + subject);
}

public void study(String subject, int hours) {
    System.out.println("Studying " + subject + " for " + hours + " hours.");
}
```

Here Java sees:

```text
study()
study(String)
study(String, int)
```

These are all different.

---

## 8. Overloading by Type of Parameters

Java can also overload methods if the parameter types are different.

```java
public void setID(int studentID) {
    this.studentID = studentID;
}

public void setID(String studentIDText) {
    this.studentID = Integer.parseInt(studentIDText);
}
```

Example:

```java
Student s = new Student("Amit", 20);

s.setID(101);
s.setID("102");
```

Java understands:

```text
setID(int)
setID(String)
```

Even though the method name is the same, the parameter type is different.

Analogy:

A teacher can accept a student ID in two forms:

```text
Give me your ID number: 101
Give me your ID written on paper: "101"
```

Same purpose, different input type.

---

## 9. Overloading by Order of Parameters

Java can overload methods if the order of parameter types is different.

```java
public void register(String name, int age) {
    System.out.println("Name: " + name + ", Age: " + age);
}

public void register(int age, String name) {
    System.out.println("Age: " + age + ", Name: " + name);
}
```

Example:

```java
register("Riya", 19);
register(19, "Riya");
```

Java sees these as different:

```text
register(String, int)
register(int, String)
```

But be careful: this can make code confusing for humans.

---

## 10. What Does Not Count as Overloading?

Changing only the return type is **not** overloading.

This is wrong:

```java
public int getAge() {
    return age;
}

public String getAge() {
    return "Age: " + age;
}
```

Java will give an error because both methods have the same name and same parameters:

```text
getAge()
getAge()
```

Return type alone is not enough.

Correct version:

```java
public int getAge() {
    return age;
}

public String getAgeText() {
    return "Age: " + age;
}
```

---

## 11. Full Example: Human.java

```java
public class Human {
    String name;
    int age;

    public Human() {
        this.name = "Unknown";
        this.age = 0;
    }

    public Human(String name) {
        this.name = name;
        this.age = 0;
    }

    public Human(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public void introduce() {
        System.out.println("Hi, I am " + name + ".");
    }

    public void introduce(String greeting) {
        System.out.println(greeting + ", I am " + name + ".");
    }

    public void introduce(String greeting, String city) {
        System.out.println(greeting + ", I am " + name + " from " + city + ".");
    }
}
```

---

## 12. Full Example: Student.java

```java
public class Student extends Human {
    int studentID;

    public Student() {
        super();
        this.studentID = 0;
    }

    public Student(String name) {
        super(name);
        this.studentID = 0;
    }

    public Student(String name, int age) {
        super(name, age);
        this.studentID = 0;
    }

    public Student(String name, int age, int studentID) {
        super(name, age);
        this.studentID = studentID;
    }

    public void study() {
        System.out.println(name + " is studying.");
    }

    public void study(String subject) {
        System.out.println(name + " is studying " + subject + ".");
    }

    public void study(String subject, int hours) {
        System.out.println(name + " is studying " + subject + " for " + hours + " hours.");
    }

    public void setID(int studentID) {
        this.studentID = studentID;
    }

    public void setID(String studentIDText) {
        this.studentID = Integer.parseInt(studentIDText);
    }
}
```

---

## 13. Full Example: Main.java

```java
public class Main {
    public static void main(String[] args) {
        Human h1 = new Human();
        Human h2 = new Human("Amit");
        Human h3 = new Human("Sara", 20);

        h1.introduce();
        h2.introduce("Hello");
        h3.introduce("Good morning", "Berlin");

        Student s1 = new Student();
        Student s2 = new Student("Riya");
        Student s3 = new Student("Riya", 19);
        Student s4 = new Student("Riya", 19, 101);

        s4.introduce();
        s4.study();
        s4.study("Java");
        s4.study("Java", 2);

        s4.setID(202);
        s4.setID("303");
    }
}
```

---

## 14. Key Rules of Overloading

1. Same method or constructor name.
2. Different parameter list.
3. Difference can be:

   * number of parameters
   * type of parameters
   * order of parameter types
4. Return type alone does not create overloading.
5. Overloading happens at compile time.

---

## 15. Simple Classroom Analogy

Imagine a student asks a teacher:

```text
Explain()
Explain(topic)
Explain(topic, example)
Explain(topic, example, language)
```

The word is always **Explain**, but the teacher gives a different answer depending on the information provided.

That is overloading.

Same method name, different inputs.
