# Methods

## Create a Method

 A method must be declared within a class. It is defined with the name of the method, followed by parentheses **()**. Java provides some pre-defined methods, such as `System.out.println()`, but you can also create your own methods to perform certain actions:

### Example

Create a method inside MyClass:

```java
public class MyClass {
  static void myMethod() {
    // code to be executed
  }
}
```

#### Example Explained

- `myMethod()` is the name of the method
- `static` means that the method belongs to the MyClass class and not an object of the MyClass class. You will learn more about objects and how to access methods through objects later in this tutorial.
- `void` means that this method does not have a return value. You will learn more about return values later in this chapter

## Call a Method

To call a method in Java, write the method's name followed by two parentheses **()** and a semicolon**;**

In the following example, `myMethod()` is used to print a text (the action), when it is called:

### Example

Inside `main`, call the `myMethod()` method:

```java
public class MyClass {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
  }
}

// Outputs "I just got executed!"
```

A method can also be called multiple times:

### Example

```java
public class MyClass {
  static void myMethod() {
    System.out.println("I just got executed!");
  }

  public static void main(String[] args) {
    myMethod();
    myMethod();
    myMethod();
  }
}

// I just got executed!
// I just got executed!
// I just got executed!
```

## Naming Conventions

 Methods should be **verbs**, in mixed case with the **first letter lowercase** and with the first letter of each internal word capitalised.

Examples:

```java
void changeGear(int newValue);
void speedUp(int increment);
void applyBrakes(int decrement);
```

## Parameters and Arguments

Information can be passed to methods as parameter. Parameters act as variables inside the method.

Parameters are specified after the method name, inside the parentheses. You can add as many parameters as you want, just separate them with a comma.

The following example has a method that takes a `String` called **fname** as parameter. When the method is called, we pass along a first name, which is used inside the method to print the full name:

### Example

```java
public class MyClass {
  static void myMethod(String fname) {
    System.out.println(fname + " Refsnes");
  }

  public static void main(String[] args) {
    myMethod("Liam");
    myMethod("Jenny");
    myMethod("Anja");
  }
}
// Liam Refsnes
// Jenny Refsnes
// Anja Refsnes
```

When a **parameter** is passed to the method, it is called an **argument**. So, from the example above: `fname` is a **parameter**, while `Liam`, `Jenny` and `Anja` are **arguments**.

## Multiple Parameters

You can have as many parameters as you like:

### Example

```java
public class MyClass {
  static void myMethod(String fname, int age) {
    System.out.println(fname + " is " + age);
  }

  public static void main(String[] args) {
    myMethod("Liam", 5);
    myMethod("Jenny", 8);
    myMethod("Anja", 31);
  }
}

// Liam is 5
// Jenny is 8
// Anja is 31
```
Note that when you are working with multiple parameters, the method call must have the same number of arguments as there are parameters, and the arguments must be passed in the same order.
## Variable Arguments (Varargs)

**Syntax of varargs :**
A variable-length argument is specified by three periods(…). For Example,

```
public static void fun(int ... a) 
{
   // method body
} 
```

This syntax tells the compiler that fun( ) can be called with zero or more arguments. As a result, here a is implicitly declared as an array of type int[].

### Important points

- - Vararg Methods can also be overloaded but overloading may lead to ambiguity.
  - Prior to JDK 5, variable length arguments could be handled into two ways : One was using overloading, other was using array argument.
  - There can be only one variable argument in a method.
  - Variable argument (varargs) must be the last argument.

- #### Erroneous varargs Examples

- - Specifying two varargs in a single method:

    ```java
    void method(String... gfg, int... q)
    {
        // Compile time error as there are two
        // varargs
    }
    ```

  - Specifying varargs as the first parameter of method instead of last one:

    ```java
    void method(int... gfg, String q)
    {
        // Compile time error as vararg appear
        // before normal argument
    }
    ```

## Return Values

The `void` keyword, used in the examples above, indicates that the method should not return a value. If you want the method to return a value, you can use a primitive data type (such as `int`, `char`, etc.) instead of `void`, and use the `return` keyword inside the method:

### Example

```java
public class MyClass {
  static int myMethod(int x) {
    return 5 + x;
  }

  public static void main(String[] args) {
    System.out.println(myMethod(3));
  }
}
// Outputs 8 (5 + 3)
```

This example returns the sum of a method's **two parameters**:

### Example

```java
public class MyClass {
  static int myMethod(int x, int y) {
    return x + y;
  }

  public static void main(String[] args) {
    System.out.println(myMethod(5, 3));
  }
}
// Outputs 8 (5 + 3)
```

You can also store the result in a variable (recommended, as it is easier to read and maintain):

### Example

```java
public class MyClass {
  static int myMethod(int x, int y) {
    return x + y;
  }

  public static void main(String[] args) {
    int z = myMethod(5, 3);
    System.out.println(z);
  }
}
// Outputs 8 (5 + 3)
```

## A Method with If...Else

It is common to use `if...else` statements inside methods:

### Example

```java
public class MyClass {

  // Create a checkAge() method with an integer variable called age
  static void checkAge(int age) {

    // If age is less than 18, print "access denied"
    if (age < 18) {
      System.out.println("Access denied - You are not old enough!");

    // If age is greater than 18, print "access granted"
    } else {
      System.out.println("Access granted - You are old enough!");
    }

  }

  public static void main(String[] args) {
    checkAge(20); // Call the checkAge method and pass along an age of 20
  }
}

// Outputs "Access granted - You are old enough!"
```

## TODO: WIP

## References

[W3 School Methods](https://www.w3schools.com/java/java_methods.asp)