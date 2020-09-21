# Classes

## Naming Rules And Conventions

### Rules

- The only allowed characters for identifiers are all alphanumeric characters([**A-Z**],[**a-z**],[**0-9**]), ‘**$**‘(dollar sign) and ‘**_**‘ (underscore).For example “geek@” is not a valid java identifier as it contain ‘@’ special character.
- Identifiers should **not** start with digits(**[0-9]**). For example “123geeks” is a not a valid java identifier.
- Java identifiers are **case-sensitive**.
- **Reserved** **Words** can’t be used as an identifier. For example “int while = 20;” is an invalid statement as while is a reserved word. There are **53** reserved words in Java.

### Conventions

* There is no limit on the length of the identifier but it is advisable to use an optimum length of 4 – 15 letters only.
* Class names should be nouns.
* In mixed case with the first letter of each internal word capitalized.
* Try to keep your class names simple and descriptive. 
* Use whole words-avoid acronyms and abbreviations (unless the abbreviation is much more widely used than the long form, such as URL or HTML).

## Class Definition

```java
modifier class myClass { // Class header

// Field
    
// Constructor (if you skip this line, compiler inserts a default constructor)
	modifier myClass(type parameters, ...) {
        
    }
// Method declarations

};
```

### List Of Modifiers

* Access modifiers: `public`, `protected`, and `private`
* Modifier requiring override: `abstract`
* Modifier restricting to one instance: `static`
* Modifier prohibiting value modification: `final`
* Modifier forcing strict floating point behavior: `strictfp`
* Annotations: `@` 

## Creating an Object

```java
public class MyClass {
  int x = 5;

  public static void main(String[] args) {
    MyClass myObj = new MyClass();
    System.out.println(myObj.x);
  }
}
```

## Constructors

 A constructor in Java is a **special method** that is used to initialize objects. The constructor is called when an object of a class is created. It can be used to set initial values for object attributes.

```java
// Create a MyClass class
public class MyClass {
  int x;  // Create a class attribute

  // Create a class constructor for the MyClass class
  public MyClass() {
    x = 5;  // Set the initial value for the class attribute x
  }

  public static void main(String[] args) {
    MyClass myObj = new MyClass(); // Create an object of class MyClass (This will call the constructor)
    System.out.println(myObj.x); // Print the value of x
  }
}

// Outputs 5
```
* Note that the constructor name must match the class name, and it cannot have a return type (like void).

* Also note that the constructor is called when the object is created.

* All classes have constructors by default: if you do not create a class constructor yourself, Java creates one for you. However, then you are not able to set initial values for object attributes.

## Class Variables

### Class Field Default Values

| **Data Type**          | **Default Value (for fields)** |
| ---------------------- | ------------------------------ |
| byte                   | 0                              |
| short                  | 0                              |
| int                    | 0                              |
| long                   | 0L                             |
| float                  | 0.0f                           |
| double                 | 0.0d                           |
| char                   | '\u0000'                       |
| String (or any object) | null                           |
| boolean                | false                          |
### How To Get The Value In a Field

 The name of a Java field is used to refer to that field from your code. Here is an example:

```java
Customer customer = new Customer();

customer.city = "New York";

System.out.println(customer.city);
// output : "New York"
```
## The `new` keyword and Constructors

 The Java new keyword is used to create an instance of the class. In other words, it instantiates a class by allocating memory for a new object and returning a reference to that memory. We can also use the new keyword to create the array object.
```java
public class NewExample2 { 
    NewExample2() { 
    System.out.println("Invoking Constructor"); 
    } 
   
    public static void main(String[] args) { 
        NewExample2 obj= new NewExample2(); 
    } 
 }
```
**Output:**

````
Invoking Constructor
```
---
```java
public class DefaultExample {
   static String name;
   static int age;
   DefaultExample() {
      name = "Krishna";
      age = 25;
   }
   public static void main(String args[]) {
      new DefaultExample();
      System.out.println(DefaultExample.name); System.out.println(DefaultExample.age);
   }
}
```
**Output: **

```
Krishna
25
```
## The `this` keyword

### Using `this` with a Field

 The most common reason for using the `this` keyword is because a field is shadowed by a method or constructor parameter.

For example, the `Point` class was written like this

```java
public class Point {
    public int x = 0;
    public int y = 0;
        
    // Constructor
    public Point(int a, int b) {
        x = a;
        y = b;
    }
}
```

but it could have been written like this:

```java
public class Point {
    public int x = 0;
    public int y = 0;
        
    // Constructor
    public Point(int x, int y) {
        this.x = x;
        this.y = y;
    }
}
```

Each argument to the constructor shadows one of the object's fields — inside the constructor **`x`** is a local copy of the constructor's first argument. To refer to the `Point` field **`x`**, the constructor must use `this.x`.

## Constructor Overloading

 Constructor overloading is a technique in Java in which a class can have any number of constructors that differ in parameter list. The compiler differentiates these constructors by taking into account the number of parameters in the list and their type.

Examples of valid constructors for class Account are

```java
Account (int a);
Account (int a,int b);
Account (String a,int b);
Account (int b,String a); // It works
Account (String b, int c); // It doesn't work!
```
### The this() method for Constructor Overloading

```java
public class OverloadingExample2
{
   private int rollNum;
   OverloadingExample2()
   {
      rollNum =100;
   }
   OverloadingExample2(int rnum)
   {
      this();
      /*this() is used for calling the default  
       * constructor from parameterized constructor.
       * It should always be the first statement 
       * inside constructor body.
       */
      rollNum = rollNum+ rnum;
   }
   public int getRollNum() {
	  return rollNum;
   }
   public void setRollNum(int rollNum) {
	  this.rollNum = rollNum;
   }
   public static void main(String args[])
   {
	   OverloadingExample2 obj = new OverloadingExample2(12);
       System.out.println(obj.getRollNum());
    }
}
```

**Output:**

`112`


As you can see in the above program that we called the parameterized constructor during object creation. Since we have this() placed in parameterized constructor, the default constructor got invoked from it and initialized the variable `rollNum`.

## References

[Java Class Naming Conventions](https://www.oracle.com/java/technologies/javase/codeconventions-namingconventions.html)

[Java Identifier Rules](https://www.geeksforgeeks.org/java-identifiers/)

[Java Constructors](https://beginnersbook.com/2013/03/constructors-in-java/)

[Creating an Object](https://www.w3schools.com/java/java_classes.asp)

[Java Class Variables](https://docs.oracle.com/javase/tutorial/java/javaOO/classvars.html)

[The `new` keyword](https://www.javatpoint.com/new-keyword-in-java)

[Initialize Class Variables](https://www.tutorialspoint.com/can-we-initialize-static-variables-in-a-default-constructor-in-java)

[The `this` keyword](https://docs.oracle.com/javase/tutorial/java/javaOO/thiskey.html)

[Constructor Overloading](https://www.guru99.com/java-constructors.html)
