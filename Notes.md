# ☕ Java - James Gosling

> Started in 1991 -> Oak -> 1995 -> Java (breed of Coffee)

- Java is _statically typed_, so variable type must be declared before use.
- Use `var` (Java 10+) for type inference.
- Java is a compiled language, so you must compile your code before you can run it.

## Features

- Simple
- Platform Independent
- Object-Oriented Programming (OOP)
- Architectural Neutral
- Secure
- Robust
- Portable
- High Performance
- Faster
- Distributed
- Multithreaded
- Dynamic
- Interpreted

- Java is everywhere
- Write Once, Run Anywhere **(WORA)**

**Sun Microsystems**

> -> Java -> owned by Oracle -> So, Java is a product of Oracle.

`Platform` : it is an environment where you can run your programs.

`Library`: Java Library is a collection of pre-defined classes.

> - To Compile a Java File → `javac FileName.java`
> - To Run a Java File → `java FileName`

### Interpreter & Compiler

Java is a compiled language, so you must compile your code before you can run it.

    > Java Code -> Java Compiler (javac) -> Java Virtual Machine (JVM) -> Java Bytecode (JVM) -> Executable Code (OS)

JVM has an Interpreter which is known as **Just-In-Time** (JIT) compiler.

    > Java Code -> Compile (Compiler) -> Bytecode -> Independent

> Hello.java -> javac Hello.java -> Hello.class

> Hello.class -> Java Virtual Machine (JVM) -> Executable Code (OS)

> - **JVM** : Dependent on OS
> - **Bytecode** : Independent

Class files are **bytecode** files. Java files are **source code** files.

### Java Installation

- Download Java 17 (LTS) from Adoptium Temurin
- Install it normally
- Check installation: `java -version`

> - **JDK** : Java Development Kit - to develop code
> - **JRE** : Java Runtime Environment - to run code

Class file -> Class loader -> Byte Code verifier -> Interpreter -> Runtime -> Hardware

### Java Naming Conventions

- Class name starts with a capital letter
- Method name starts with a lowercase letter
- Variable name starts with a lowercase letter

> - **PascalCase** : `HelloWorld`
> - **CamelCase** : `helloWorld`
> - **SnakeCase** : `hello_world`

### `public static void main(String[] args)` explained

```java
class Demo{
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- Save this file as `Demo.java`
- To compile: `javac Demo.java`
- To run: `java Demo`

#### Parameters used

- `class` keyword is used to declare a class in java.
- `public` keyword is an access modifier which represets visibility, it means it is visible to all.
- `static` is a keyword, if we declare any method as static , it is known as static method. The core advantage of static method is that there is no need to create an object to invoke the static method.
  The **main** method is executed by the JVM, so it doesn't require to create object to inovke the main method. So it saves memory.
- `void` keyword is used to declare the return type of the method; it means it doesn't return any value.
- `main` represents the entry point of the program.
- `String[] args` is used to accept command-line arguments.
- `System.out.println()` is used to print the output on the console. `System` is a class in the java.lang package. The `out` is a static variable in the `System` class, and is an insurance of java.io.PrintStream. The `println()` method is used to print the output on the console. The `println` is a method of java.io.PrintStream; this method is overloaded to print message to output destination, which is typically a console or a file.

> ❓ **Difference between print and println**
> ➡ `print` method doesn't add a new line character at the end of the output, while `println` method adds a new line character at the end of the output.
> The `println()` method can also be used without parameters, to position the cursor on the next line.

> ❓ **What happens at compile time?**
> ➡ At compile time, java file is compiled by Java Compiler (it does not interact with OS) and converts java code into bytecode.

    Java Code (Demo.java) →  Compiler  →  Bytecode (Demo.class)

The compiler reads the source code and generates bytecode from it. The bytecode is then stored in a file with the same name as the source file, but with a `.class` extension.

> ❓ **What happens at run time?**
> ➡ The JVM reads the bytecode and executes it.

> ❓ **Can you save a java source file by other name than the class name?**
> ➡ Yes, if the class is not public. It is explained by the example below:

```java
class Demo{
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

- Save this file as `Simple.java`

        Simple.java → Compiler  →  Bytecode (Demo.class)

- To compile: `javac Simple.java`
- To run/execute: `java Demo`

> ❓ **Can you have multiple classes in a java source file?**
> ➡ Yes.

![Multiple Classes Example](./resources/multiple-classes.png)

## 2. Differences Between JDK, JRE and JVM
JDK (Java Development Kit) provides tools and libraries to develop Java applications, working with JRE and JVM. JRE (Java Runtime Environment) offers the libraries and JVM needed to run Java programs. JVM (Java Virtual Machine) executes the compiled Java bytecode on the system.

![JDK, JRE and JVM](/resources/jvm.png)

> 📝: Java bytecode can run on any machine with a JVM, but JVM implementations are platform-dependent for each operating system.

### JDK (Java Development Kit)
JDK is a software development kit used to build Java applications. It contains the JRE and a set of development tools.

- Includes compiler (javac), debugger, and utilities like jar and javadoc.
- Provides the JRE, so it also allows running Java programs.
- Required by developers to write, compile, and debug code.

**Components of JDK:**

- JRE (JVM + libraries)
- Development tools (compiler, jar, javadoc, debugger)

**Note:**
- JDK is only for development (it is not needed for running Java programs)
- JDK is platform-dependent (different version for windows, Linux, macOS)

#### Working of JDK:
- **Source Code (.java)**: Developer writes a Java program.
- **Compilation**: The JDK’s compiler (javac) converts the code into bytecode stored in .class files.
- **Execution**: The JVM executes the bytecode, translating it into native instructions.

### JRE (Java Runtime Environment)
JRE provides an environment to run Java programs but does not include development tools. It is intended for end-users who only need to execute applications.

- Contains the JVM and standard class libraries.
- Provides all runtime requirements for Java applications.
- Does not support compilation or debugging.

**Note:**
- JRE is only for running applications, not for developing them.
- It is platform-dependent (different builds for different OS).

#### Working of JRE:
- **Class Loading**: Loads compiled .class files into memory.
- **Bytecode Verification**: Ensures security and validity of bytecode.
- **Execution**: Uses the JVM (interpreter + JIT compiler) to execute instructions and make system calls.

### JVM (Java Virtual Machine)
JVM is the core execution engine of Java. It is responsible for converting bytecode into machine-specific instructions.

- Part of both JDK and JRE.
- Performs memory management and garbage collection.
- Provides portability by executing the same bytecode on different platforms.

**Note:**
- JVM implementations are platform-dependent.
- Bytecode is platform-independent and can run on any JVM.
- Modern JVMs rely heavily on Just-In-Time (JIT) compilation for performance.

#### Working of JVM

![jvm_working](/resources/jvm_working.png)

1. **Loading**: Class loader loads bytecode into memory.
2. **Linking**: Performs verification, preparation, and resolution.
3. **Initialization**: Executes class constructors and static initializers.
4. **Execution**: Interprets or compiles bytecode into native code.

### JDK vs JRE vs JVM
| Aspect              | JDK                                      | JRE                                      | JVM                                                   |
|---------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------------------|
| **Purpose**             | Used to develop Java applications         | Used to run Java applications             | Executes Java bytecode                                |
| **Platform Dependency** | Platform-dependent (OS specific)          | Platform-dependent (OS specific)          | JVM is OS-specific JVM, but bytecode is platform-independent |
| **Includes**            | JRE + Development tools (javac, debugger, etc.) | JVM + Libraries (e.g., rt.jar)            | ClassLoader, JIT Compiler, Garbage Collector          |
| **Use Case**            | Writing and compiling Java code           | Running a Java application on a system               | Converts bytecode into native machine code            |

## 3. Data Types

Java has two main categories of data types:

> - **Primitive** (store actual values, fixed size in memory)
> - **Non-Primitive (Reference)** (store addresses/references to objects)

### Primitive Data Types

1. **Integer Types**

   - `byte` → 1 byte (8-bit)
   - `short` → 2 bytes (16-bit)
   - `int` → 4 bytes (32-bit)
   - `long` → 8 bytes (64-bit)

2. **Floating-Point Types**

   - `float` → 4 bytes (32-bit, decimal, ~7 digits precision)
   - `double` → 8 bytes (64-bit, decimal, ~15 digits precision)

3. **Boolean Type**

   - `boolean` → 1 bit (value is `true` or `false`)

4. **Character Type**
   - `char` → 2 bytes (16-bit, Unicode character)

### Non-Primitive Data Types

- Strings
- Arrays
- Classes
- Interfaces

**Example**

```java
public class DataTypeExample {
    public static void main(String[] args) {
        byte b = 100;
        int age = 25;
        double salary = 55000.50;
        char grade = 'A';
        boolean isJavaFun = true;

        System.out.println("Byte: " + b);
        System.out.println("Age: " + age);
        System.out.println("Salary: " + salary);
        System.out.println("Grade: " + grade);
        System.out.println("Java is fun? " + isJavaFun);
    }
}
```

- `char` : Use single quotes
- `String` : Use double quotes

📖 **Important Rule – You Cannot Change the Type of a Variable**  
Once a variable is declared with a type, it cannot change to another type later in the program.

**Example**

```java
int myNum = 5;       // myNum is an int
// myNum = "Hello";  // ❌ Error: cannot assign a String to an int

String myText = "Hi"; // myText is a String
// myText = 123;      // ❌ Error: cannot assign a number to a String
```

> ❓ _What is the difference between primitive and reference data types?_
> ➡ Primitive stores **actual value**. Reference stores **address of the object in heap memory**.

## 4. Operators

Operator in java is a symbol that performs an operation on one or more operands.

### Java Operator Precedence

When a calculation contains more than one operator, Java follows order of operations rules to decide which part to calculate first.

For example, multiplication happens before addition:

Example:

```java
int result1 = 2 + 3 * 4;     // 2 + 12 = 14
int result2 = (2 + 3) * 4;   // 5 * 4 = 20

System.out.println(result1); // 14
System.out.println(result2); // 20
```

🤨 Why Does This Happen?  
In 2 + 3 \* 4, the multiplication is done first, so the answer is 14.

If you want the addition to happen first, you must use parentheses: (2 + 3) \* 4, which gives 20.

> 📝: Always use parentheses ( ) if you want to make sure the calculation is done in the order you expect. It also makes your code easier to read.

![Java Operator Precedence](./resources/precedence.png)

**Order of Operations**
Here are some common operators, from highest to lowest priority:

- () - Parentheses
- \*, /, % - Multiplication, Division, Modulus
- +, - - Addition, Subtraction
- <,>, >=, <= - Comparison
- ==, != - Equality
- && - Logical AND
- || - Logical OR
- = - Assignment

```java
class Output{
    public static void main(String[] args) {
        int a =3 , c=4;
        boolean b = true;
        System.out.println("b= " + b);
        b = false;
        System.out.println("b= " + b);
        if(b)
          System.out.println("b= " + b);
        b = true;
        if(b)
          System.out.println("b= " + b);
        if(b)
         System.out.println("b= " + b);
    }
}
```

Output:

```
b= true
b= false
b= true
b= false
```

> ❓ _What is the difference between `==` and `=`?_
> ➡ `==` checks if two values are equal, while `=` assigns a value to a variable.

```java
int  a = 5;
int b = a ++;

System.out.println(a); // 6
System.out.println(b); // 5
```

```java
int a = 29;
a--;
a -= ++a;
System.out.println(a); // 0
```

```java
int a = 8;
int b = ++a + (--a) + a
System.out.println(a); // 8
System.out.println(b); // 25
```

## 5. Java OOP

OOP stands for **Object-Oriented Programming**.

Procedural programming is about writing procedures or methods that perform operations on the data, while object-oriented programming is about creating objects that contain both data and methods.

Object-oriented programming has several advantages over procedural programming:

- OOP is faster and easier to execute

- OOP provides a clear structure for the programs

- OOP helps to keep the Java code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug

- OOP makes it possible to create full reusable applications with less code and shorter development time

> 📝: The "**Don't Repeat Yourself**" (DRY) principle is about reducing the repetition of code. You should extract out the codes that are common for the application, and place them at a single place and reuse them instead of repeating it.

Object-Oriented Programming is a methodology or paradigm to design a program using classes and objects. It simplifies the software development and maintenance. Main Concepts - **Inheritance**, **Polymorphism**, **Abstraction**, **Encapsulation**.

![OOP](./resources/OOPsConcept.gif)

### Key Features of OOP in Java:
- Structures code into logical units (classes and objects)
- Keeps related data and methods together (encapsulation)
- Makes code modular, reusable and scalable
- Prevents unauthorized access to data
- Follows the DRY (Don’t Repeat Yourself) principle

### What are Classes and Objects?

Classes and objects are the two main aspects of object-oriented programming.

Look at the following illustration to see the difference between class and objects:

- class : Fruit
- objects : Apple, Banana, Mango

So, a class is a template for objects, and an object is an instance of a class.

When the individual objects are created, they inherit all the variables and methods from the class.

Everything in Java is associated with classes and objects, along with its `attributes` and `methods`. For example: in real life, a car is an object. The car has attributes, such as weight and color, and methods, such as drive and brake.

A Class is like an object constructor, or a "blueprint" for creating objects.

**Properties of Java Classes**

- Class is not a real-world entity. It is just a template or blueprint, or a prototype from which objects are created.
- A class itself does not occupy memory for its attributes and methods until an object is instantiated.
- A Class in Java can contain Data members, methods, a Constructor, Nested classes, and interfaces.

> 📝: Objects (non-primitive types) are always allocated on the heap, while their reference variables are stored on the stack.

**Object Instantiation (Declaring Objects)**

When an object of a class is created, the class is said to be instantiated. All the instances share the attributes and the behavior of the class. But the values of those attributes, i.e. the state are unique for each object. A single class may have any number of instances.

---

`String[] args` is a parameter. It is a variable that is passed to the method. It is used to store the command-line arguments passed to the program.

```java
class abc {
    public static void main(String[] args) {

    }
}
```

### Why `main` uses `String[] args` (and not int[], float[], etc.)

1. **Command-line arguments are always text**

   - When you run a Java program from the terminal, everything after the class name is passed as **plain strings**.
   - Example:
     ```bash
     java MyApp 10 20
     ```
     The JVM receives `"10"` and `"20"` (strings), not numbers.

2. **Strings are universal**

   - Using `String[]` allows the program to accept any kind of input — numbers, words, file paths, flags like `-help`, etc.
   - If the parameter type were `int[]`, you couldn’t pass non-numeric input like `"hello"`.

3. **Conversion to other types is possible**

   - Strings can be converted to the required type inside the program:
     ```java
     int x = Integer.parseInt(args[0]);
     double y = Double.parseDouble(args[1]);
     ```
   - This gives flexibility: one program can handle multiple input formats.

4. **Defined by the JVM specification**
   - The JVM only looks for the method signature:
     ```java
     public static void main(String[] args)
     ```
   - If you use `int[]`, `float[]`, or any other type, the JVM will not recognize it as the entry point.

✅ **In summary:**  
Command-line input always comes in as text. `String[] args` ensures Java can accept any kind of input, and the program can later parse those strings into numbers or other data types as needed.

### Advantage of OOPs over Procedure-Oriented Programming Language
Object-oriented programming (OOP) offers several key advantages over procedural programming:
- By using objects and classes, you can create reusable components, leading to less duplication and more efficient development.
- It provides a clear and logical structure, making the code easier to understand, maintain, and debug.
- OOP supports the DRY (Don't Repeat Yourself) principle.This principle encourages minimizing code repetition, leading to cleaner, more maintainable code. Common functionalities are placed in a single location and reused, reducing redundancy.
- By reusing existing code and creating modular components, OOP allows for quicker and more efficient application development

### Disadvantages of OOPs
- OOP has concepts like classes, objects, inheritance etc. For beginners, this can be confusing and takes time to learn.
- If we write a small program, using OOP can feel too heavy. We might have to write more code than needed just to follow the OOP structure.
- The code is divided into different classes and layers, so in this, finding and fixing bugs can sometimes take more time.
- OOP creates a lot of objects, so it can use more memory compared to simple programs written in a procedural way.

## 6. Variables in Java

Variables are containers to store data in memory. Each variable has a name, type and value. It is the basic unit of storage in a program. Java has 4 types of variables.

- `Local Variables`: Declared inside a method, constructor, or block. Accessible only within that block.
- `Instance Variables`: Declared inside a class but outside any method. Each object of the class has its own copy.
- `Static Variables`: Declared with the static keyword inside a class. Shared by all objects of the class.
- `Final Variables`: Declared with final keyword. Value cannot be changed once assigned.

```java
class A {
    // Instance variable (belongs to each object)
    int a;

    // Static variable (shared by all objects)
    static int b;

    // Final variable (cannot be changed)
    final int c = 10;

    void m() {
        int d=5;   // Local variable (belongs to a method, must be initialized before use)
        System.out.println("Local variable d: " + d);
    }
}

class XYZ {
    public static void main(String[] args) {
        A obj1 = new A();  // Creating first object of class A
        A obj2 = new A();  // Creating second object of class A

        // Instance variable: each object has its own copy
        obj1.a = 20;
        obj2.a = 50;

        // Static variable: shared among all objects
        A.b = 100;

        // Printing values
        System.out.println("obj1.a = " + obj1.a); // 20
        System.out.println("obj2.a = " + obj2.a); // 50
        System.out.println("Static variable b = " + A.b); // 100
        System.out.println("Final variable c = " + obj1.c); // 10

        obj1.m(); // prints local variable
    }
}
```

Output:

```
obj1.a = 20
obj2.a = 50
Static variable b = 100
Final variable c = 10
Local variable d: 5
```

📝 This way you clearly demonstrate:

    - Instance variable → different for each object.
    - Static variable → shared across all objects.
    - Final variable → constant (cannot change once set).
    - Local variable → lives inside a method.

### Instance Variables & Static Variables

> 📝: We can use an `instance` variable only through the object of the class in which it is defined. **Instance variables** have default values. For numbers, the default value is 0; for booleans, it is False; and for Object refrences it is Null.

```java
class abc {
    int a; // instance variable
    public static void main(String[] args) {
        System.out.println(a); // displays 0
    }
}

class xyz {
 public static void main(String[] args) {
     abc a1 = new abc();
     a1.display(); // calling instance method

     abc a2 = new abc();
     a2.a = 10;
     a2.display(); // display 10
 }
}
```

```java
class abc{
    int  a; // instance variable
    public static void main(String[] args) {
        System.out.println(a); // displays 0
    }
}
```

📝: We can't access instance variable without object in `main()` even if both are present in the same class. To access an instance variable in `main()`:

    abc a1 = new abc(); // creating object of class abc
    System.out.println(a1.a);  // accessing instance variable using object

```java
class xyz {
    static int a; // static variable
    public static void main(String[] args) {
        System.out.println(a); // accessing static variable directly
    }
}
```

📝: However, if the instance variable is declared `static`, we can directly (without an object) access that variable in the `main()`.

❓ **Why do we need abc obj = new abc();?**

- `a` is an instance variable → it belongs to each object of the class.
- To access an instance variable inside a static method (like `main`), you must first create an object of that class.
- That’s why `obj.a` works: you created an object (`obj`) and then accessed its variable.

❓ **What if you don’t create an object?**

If you write just `System.out.println(a);`, it won’t compile.

You’ll get:

`non-static variable a cannot be referenced from a static context`

Because `main` is static and cannot directly access non-static members (like `a`) without an object.

creating an object (`new abc()`) is necessary here because `a` is an instance variable.
If you want to avoid creating an object, you’d need to make `a` static.

> 📝: **Static** variable retains the values. **Instance** variables have their won memories, so the values get overwritten.

> 📝: **Static (Class)** variables and **Instance** variables both are member variables because they are both associated with a specific class, but the difference between them is `Class (Static)` variables only have one copy that is shared by all the different objects of a class, whereas every object has it's own personal copy of an `instance`.

```java
class abc {
   static int a; // Static variables default to 0 if not explicitly initialized.
   public static void main(String[] args) {
       abc a1 = new abc();
       a1.a = 10; // This sets the class variable `a` to 10.
       System.out.println(a1.a); // 10

       abc a2 = new abc();
       a2.a = 5; // Even though we used a2, `a` is static → same variable is updated.
       System.out.println(a2.a); // 5

       abc a3 = new abc(); // Creates another object, but static variable `a` is still shared.
       System.out.println(a3.a); // 5
       a3 = a1; // Just makes a3 refer to the same object as a1. But since `a` is static, it doesn’t matter.

       System.out.println(a1.a); // 5

       System.out.println(new abc().a); // 5 // Even with a brand-new object, static variable is still the same.
   }
}
```

Output:

```
10
5
5
5
5
5
```

⚡ So the key takeaway:

- **Static variables are shared across all instances.**
- Changing them via any object (or even class name `abc.a`) updates the single shared copy.

## 7. Loops

`for`, `while`, `do-while`, `foreach`

### for loop

Used when you know beforehand how many times you want to run the loop.

```java
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

Output:

```
1
2
3
4
5
```

### foreach loop (Enhanced For Loop)

Syntax: `for(Type var:array) { }`

The `foreach` loop is used to traverse array or collection (i.e. for accessing array). It works on elements basis not index. It returns elements one by one in the defined variable.

```java
for (int i : arr) {
    System.out.println(i);
}
```

Output:

```
1
2
3
4
5
```

### while loop

Used when the number of iterations is unknown and depends on a condition.

```java
int i = 0;
while (i < arr.length) {
    System.out.println(arr[i]);
    i++;
}
```

Output:

```
1
2
3
4
5
```

### do-while loop

Similar to `while`, but executes the code at least once before checking condition.

```java
int i = 0;
do {
    System.out.println(arr[i]);
    i++;
} while (i < arr.length);
```

Output:

```
1
2
3
4
5
```

📝 **Difference between while and do-while:**

- `while` → checks condition first, may run 0 times.
- `do-while` → executes at least once before checking condition.

## 8. Arrays

Array is a collection of similar data types. Arrays are used to store multiple values in a single variable.

```java
int[] numbers = new int[5]; // Declaration + Memory allocation
numbers[0] = 10;            // Assigning values
numbers[1] = 20;

int[] values = {1, 2, 3, 4, 5}; // Declaration + Initialization in one step
```

### Array declaration

```java
int arr[] = new int[3];
int arr1[] = {10, 20, 30, 40};
int arr2[] = new int[]{10, 20, 30, 40};

char a[] = new char[3];
new char[] = {'A', 'B', 'C'};
```

### Multidimensional Arrays

```java
int arr[][] = {{10, 20}, {10, 20, 30}, {30, 40, 4, 5, 6}, {2}};

int len = arr[0].length;
System.out.println(arr[1][1]);  // prints 20
System.out.println(arr[1][2]);  // prints 30
```

```java
for(int i = 0; i < arr.length; i++) {
   for(int j = 0; j < arr[i].length; j++) {
      System.out.println(arr[i][j]);
   }
}

int arr[][] = new int[][] {{10, 20, 30, 40}, {10, 5}}
```

```java
int arr[][] = new int[3][3];
arr[0] = new int [10];
arr[1] = new int [20];
arr[2] = new int [30];
```

> 📖 Arrays are **fixed in size** (cannot be resized after creation).

Default values:

- `int` → 0
- `boolean` → false
- `Object` → null

> Arrays in Java are objects stored in heap memory.

**❓ Difference between Array and ArrayList**

- Array → Fixed size, can hold primitives and objects.
- ArrayList → Dynamic size, only holds objects (wrapper classes needed for primitives).

### Array Operations: Reversing and Summing Arrays

```java
// Class to perform array operations
class Arr {

    // Method to reverse an array
    int[] rev(int a[]) {
        // Initialize two pointers: i from start, j from end
        for (int i = 0, j = a.length - 1; i < j; i++, j--) {
            int temp = a[i];   // Swap the elements at i and j
            a[i] = a[j];
            a[j] = temp;
        }
        return a;  // Return the reversed array
    }

    // Static method to add two arrays element-wise
    static int[] sum(int a[], int a1[]) {
        // Create a new array to store the sum
        int c[] = new int[a.length];
        for (int i = 0; i < a.length; i++) {
            c[i] = a[i] + a1[i];   // Add corresponding elements
        }
        return c;   // Return the resultant array
    }
}

// Main class
class xyz {
    public static void main(String[] args) {
        // Create an object of Arr to use non-static methods
        Arr s1 = new Arr();
        
        // Reverse the first array {3,2,1} → {1,2,3}
        int A[] = s1.rev(new int[]{3, 2, 1});
        
        // Reverse the second array {1,2,3} → {3,2,1}
        Arr s2 = new Arr();
        int B[] = s2.rev(new int[]{1, 2, 3});
        
        // Add the two reversed arrays element-wise
        // A = {1,2,3}, B = {3,2,1} → C = {4,4,4}
        int C[] = Arr.sum(A, B);

        // Reverse the sum array again
        Arr s3 = new Arr();
        int result[] = s3.rev(C);

        // Print the final reversed array
        // Since arrays printed directly won't show elements,
        // we use Arrays.toString() for readable output
        System.out.println(java.util.Arrays.toString(result));
    }
}
```
Output:
```
[4, 4, 4]
```
🧭 **Quick Real-World Analogy**

Reversing an array is like flipping a line of people — the person at the start goes to the end, and vice versa.
Adding arrays is like combining two teams’ scores position-wise — first player’s score + first player’s score, and so on.

🔹 **1. Arrays in Java**

> Arrays are fixed-size, indexed, and homogeneous data structures.

- Syntax for declaration:

        int[] arr = new int[5];
        int[] arr = {1, 2, 3, 4};

- Index starts at **0 and ends at length - 1**.

🔹 **2. Reversing an Array**

**Logic**: Swap the first element with the last, second with the second-last, and so on until the middle is reached.

    for (int i = 0, j = arr.length - 1; i < j; i++, j--) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

🧩 Concept Used:
- Two-pointer approach (start and end)
- Array element swapping

🔹 **3. Summing Two Arrays**

**Logic**: Add corresponding elements of two arrays and store in a third array.
Example:

    A = [1, 2, 3]
    B = [4, 5, 6]
    C = [5, 7, 9]

**Code:**

    for (int i = 0; i < a.length; i++) {
        c[i] = a[i] + a1[i];
    }

🧩 **Concept Used**:
- Iteration over arrays using `for` loop
- Element-wise operation
- Returning an array

🔹 **4. Returning Arrays from Methods**

Arrays can be returned just like **primitive data types**.

- Example:

        int[] rev(int a[]) { ... return a; }

- The returned array holds changes because **arrays are passed by reference** (not by value).

🔹 5. Static vs Non-static Methods

- Static methods (like `sum()`) can be called without creating an object:

    Arr.sum(A, B);

- Non-static methods (like `rev()`) require an object:

    Arr obj = new Arr();
    obj.rev(A);

❓ **Explain how arrays are passed to methods in Java.**
➤ Arrays are passed by reference, meaning the method can modify the original array.

❓ **Can arrays of different lengths be added?**
➤ Not directly — it will cause `ArrayIndexOutOfBoundsException`. You must handle it manually.

❓ **What happens if you return an array from a method — does it create a copy or return a reference?**
➤ It returns a reference to the same array object in memory.

---

📝 **Data Types**

- `byte` : 1 byte
- `char` : 2 bytes
- `int` : 4 bytes
- `float` : 4 bytes
- `long` : 8 bytes
- `double` : 8 bytes
- `boolean` : 1 byte
- `short` : 2 bytes
- `String` : 2 bytes per character
- `Object` : 4 bytes

> 📝: **Primitive data types are stored in stack and objects are stored in heap.**

> 📝: **Primitive data types are faster than objects.**

📝: Arrays are faster than ArrayList.

📝: Wrapper classes are faster than primitive data types.

## 9. Functions (methods)

A function (in Java, commonly called a **method**) is a block of code that performs a specific task. Methods help in _code reusability_ and _modularity_.

### Structure of a Method

```java
 accessModifier keyword returnType functionName(parameterList) {
    function body;
}
```

```java
    returnType functionName(parameterList) {
        function body;
    }
```

**Example:**

```java
class abc {
    void display{ // function declaration
        System.out.println("Function body");
    }
}

class xyz {
    public static void main(String[] args) {
        abc a1 = new abc(); // creating object of class abc
        a1.display(); // function call
    }
}
```

> 📝: We can't declare two functions having same name & same signature in a class or it'll generate `compile time error`.

> 📝: We can't call a function before it is declared.

```java
class abc{
    int a;
    void display{
        System.out.println(a);
    }
}

class xyz{
    public static void main(String[] args) {
        abc a1 = new abc();
        a1.a = 23;
        a1.display(); // displays 23

        new abc().display(); // displays 0
        abc a2 = new abc();
        a2.display(); // displays 0
    }
}
```

Output:

```
23
0
0
```

> 📝: Non-static member can be accessed in a static function but vice versa is not possible.

```java
class abc{
    int a, b; // instance variable
    void display() {
        int c = 10, d =20; // local variable
        a = c;
        b = d;
    }
    void output() {
        System.out.println(a + " " + b);
    }
}

class xyz {
    public static void main(String[] args) {
        abc a1 = new abc();
        a1.display(); // initializes a and b
        abc a2 = new abc();
        a2.output();  // prints 0 0
        a1.output();  // prints 10 20
    }
}

```

First `display()` is called by using `a1` object of class `abc`, it will set the values of `a` and `b` as 10, 20 respectively.
Then `output()` is called by `a2` object of class `abc`. It will print the values of `a` and `b` which are 0, 0 respectively.
At last, `output()` is called which displays `a`, `b` as set by `display()` function which is 10, 20 respectively.

Output:

```
0 0
10 20
```

📝: Methods **must be defined inside a class** in Java.

- `main()` is also a method (entry point of program).

- Methods can be:

  - With return value (e.g., `int add()` returns a number).

  - Without return value (`void greet()` just performs an action).

> 📝 Method Signature → Consists of method name and parameter list.

Example: `add(int a, int b)` is the method signature.

📝 **Difference between Function and Method:**

- In general programming → "Function" = **block of reusable code.**
- In Java → **functions are always inside a class, so they’re called methods.**

> 📝: **Method overloading** allows a class to have multiple methods with the same name but different parameter lists.

> 📝: **Constructor overloading** allows a class to have multiple constructors with different parameter lists.

> 📝: **Method overriding** allows a subclass to provide a different implementation for a method that is already defined in the superclass.

### Java Scope
In Java, variables are only accessible inside the region where they are created. This is called **scope**.

#### Method Scope
Variables declared directly inside a method are available anywhere in the method following the line of code in which they were declared:
```java  
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    int x = 100;

    // Code here CAN use x
    System.out.println(x);
  }
}
```

#### Block Scope
A block of code refers to all of the code between curly braces `{ }`.

Variables declared inside a block of code are only accessible by the code between the curly braces, and only after the line in which the variable was declared:
```java
public class Main {
  public static void main(String[] args) {

    // Code here CANNOT use x

    { // This is a block

      // Code here CANNOT use x

      int x = 100;

      // Code here CAN use x
      System.out.println(x);

    } // The block ends here

    // Code here CANNOT use x

  }
}
```
> 📝 : A block of code can stand alone, or be part of an `if`, `while`, or `for` statement. In a `for` loop, the variable declared in the loop header (like `int i = 0`) only exists inside the loop.

#### Loop Scope
Variables declared inside a for loop only exist inside the loop:
```java
public class Main {
  public static void main(String[] args) {

    for (int i = 0; i < 5; i++) {
      System.out.println(i); // i is accessible here
    }

    // i is NOT accessible here
  }
}
```
- The `for` loop has its own block (`{ ... }`).
- The variable `i` declared in the loop header (`int i = 0`) is only accessible inside that loop block.
- Once the loop ends, `i` is destroyed, so you can't use it outside.

Why this matters:

Loop variables are not available outside the loop.

You can safely reuse the same variable name (`i`, `j`, etc.) in different loops in the same method:
```java
public class Main {
  public static void main(String[] args) {

    for (int i = 0; i < 3; i++) {
      System.out.println("Loop 1: " + i);
    }

    for (int i = 0; i < 2; i++) {
      System.out.println("Loop 2: " + i);
    }
  }
}
```
#### Class Scope
Variables declared inside a class but outside any method have class scope (also called fields). These variables can be accessed by all methods in the class:
```java
public class Main {
  int x = 5; // Class variable

  public static void main(String[] args) {
    Main myObj = new Main();
    System.out.println(myObj.x); // Accessible here
  }
}
```

### Recursion
Recursion is the technique of making a function call itself. This technique provides a way to break complicated problems down into simpler problems which are easier to solve.

**Recursion Example**
Adding two numbers together is easy to do, but adding a range of numbers is more complicated. In the following example, recursion is used to add a range of numbers together by breaking it down into the simple task of adding two numbers:
```java
public class Main {
  public static int sum(int k) {
    if (k > 0) {
      return k + sum(k - 1);
    } else {
      return 0;
    }
  }

  public static void main(String[] args) {
    int result = sum(10);
    System.out.println(result);
  }
}
```

When the `sum()` method is called, it adds parameter `k` to the sum of all numbers smaller than `k` and returns the result. When `k` becomes 0, the method just returns 0. When running, the program follows these steps:

10 + sum(9)
10 + ( 9 + sum(8) )
10 + ( 9 + ( 8 + sum(7) ) )
...
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + sum(0)
10 + 9 + 8 + 7 + 6 + 5 + 4 + 3 + 2 + 1 + 0
Since the method does not call itself when `k` is 0, the program stops there and returns the result.

**Halting Condition**

Just as loops can run into the problem of infinite looping, recursive methods can run into the problem of infinite recursion. Infinite recursion is when the method never stops calling itself. Every recursive method should have a halting condition, which is the condition where the method stops calling itself. In the previous example, the halting condition is when the parameter `k` becomes 0.

It is helpful to see a variety of different examples to better understand the concept. In this example, the method adds a range of numbers between a start and an end. The halting condition for this recursive method is when **end** is not greater than **start**:

Use recursion to add all numbers from 5 to 10 (5+6+7+8+9+10):
```java
public class Main {
  public static int sum(int start, int end) {
    if (end > start) {
      return end + sum(start, end - 1);
    } else {
      return end;
    }
  }

  public static void main(String[] args) {
    int result = sum(5, 10);
    System.out.println(result);
  }
}
```
> Be careful with recursion: it's easy to accidentally write a method that never stops or uses too much memory. But when written correctly, recursion can be both efficient and elegant.

**Countdown with Recursion:** 
This example demonstrates how to use recursion to create a countdown function:
```java
public class Main {
  static void countdown(int n) {
    if (n > 0) {
      System.out.print(n + " ");
      countdown(n - 1);
    }
  }

  public static void main(String[] args) {
    countdown(5);
  }
}
```
The method calls itself with `n - 1` until `n` becomes `0`.

**Calculate Factorial with Recursion**
This example uses a recursive method to calculate the factorial of 5:
```java
public class Main {
  static int factorial(int n) {
    if (n > 1) {
      return n * factorial(n - 1);
    } else {
      return 1;
    }
  }

  public static void main(String[] args) {
    System.out.println("Factorial of 5 is " + factorial(5));
  }
}
```
Factorial means multiplying a number by every number below it, down to 1. For example, the factorial of 5 is: 5 * 4 * 3 * 2 * 1 = 120. By definition, 0! is also 1.

### Returning Object from a Method

A function can return any data type, including class objects.

```java
    class abc{
        static xyz getObj() { 
            return new xyz(); // returns xyz object
        }
    }

    class xyz {
        int sum(int a, int b) {
            return a + b;
        }
    }

    class mno {
       public static void main(String[] args) {
        // Direct call — object returned by getObj() is used immediately
        System.out.println(abc.getObj().sum(10, 20));

        /* Equivalent approach:
        xyz x1 = abc.getObj();  // getObj() returns xyz object
        int c = x1.sum(10, 20);
        System.out.println(c);
        */
        }
    }
```

Output:

```
30
```
- `getObj()` returns a **new object** of class `xyz`.
- The expression `abc.getObj()` returns that object reference, which can be used directly to call methods of `xyz`.
- This technique helps **avoid explicit object creation** in the calling method.

📝: The **return type** of the method must match the **class type** of the object being returned.
e.g., `static xyz getObj()` → must return a `xyz` object.

📝: You can either:
- **store the returned object in a variable**, or
- **use it directly in a chained method call** (`abc.getObj().sum(10, 20)`).

📝: Static methods can return objects even though they belong to the class (not an instance).

### ⚙️ Static Context Notes

Static methods can also return objects, even though they belong to the class (not an instance).

> 📝: Static methods can't access **instance variables** without an object.

```java
class abc {
    int a;
    static xyz getObj() {
        System.out.println(a); // ❌ error — cannot access instance variable
        return new xyz();
    }
}
```
> 📝: Static variable **cannot be declared in local scope** (inside methods).

**Example: Static Variable Behavior**
```java
class abc{
    static int a;
    public static void main(String[] args) {
        abc a1 = new abc();
        a1.a = 90; // changes static variable
        abc a2 = new abc();
        a2.a = 40; // overwrites previous value
        a1.display(); // prints 40
    }
    void display() {
        System.out.println(a);
    }
}
```
Output:
```
40
```

> 📝: Static variable retains the previous value of the recent object.
> 📝: Instance variables can't be declared in local scope.

#### 💬 Key Takeaways

- **Static variable** → shared by all objects; retains last updated value.
- **Instance variable** → unique for each object; requires an object to access.
- **Static variable / method** → can be accessed using class name (`ClassName.var` or `ClassName.method()`).
- **Instance variable / method** → requires an object reference (`obj.var` or `obj.method()`).

## 10. `this` Keyword

The `this` keyword is a reference variable in Java that refers to the current object of a class.
It is used to avoid ambiguity, call constructors, and pass the current object as an argument.

```java
class abc {
    int a, b; // instance variable
    void display() {
        int a = 10, b = 20; // local variable
        this.a = a; // this keyword is used to access instance variables // 'this.a' refers to instance variable
        this.b = b;  // assigns local b to instance b
    }
    void output() {
        System.out.println(a + " " +b);
    }
}

class xyz {
    public static void main(String[] args) {
        abc a1 = new abc();
        a1.display(); // initializes instance variables a and b using local values
        a1.output(); // prints: 10 20

        abc a2 = new abc();// again assigns values
        a2.output();   // prints: 10 20
    }
}
```

- Without `this`:
  The local variables `a` and `b` would shadow (hide) the instance variables, leaving the instance variables uninitialized (default `0`).

- With `this`:
  We explicitly tell Java:

> "Assign the value of the local variable `a` to the instance variable `a` of this object."

That’s why `a1.output()` prints 10 20 instead of 0 0.

Output:

```
 10  20
 10  20
```

📝: `this` variable holds the value of the current object.
The `this` keyword can be used to refer current class instance variable. If there is ambiguity between the instance variables and parameteres, `this` keyword resolves the problem of ambguity.

> 📝:The keyword `this` is used only within instance methods or constructors.

- `this` cannot be used inside `static` methods (since static methods do not belong to an object).

- `this` is **automatically added by the compiler** when accessing instance variables, but we use it explicitly when needed for clarity.

### this variable

![this variable](./resources/this-variable.png)]

```java
class xyz {
    int a, b;
    void display(int a, int b) {
        this.a = a;
        this.b = b;
    }
    void output() {
        System.out.println(a + " " + b);
    }
}

class mno{
    public static void main(String[] args) {
        xyz x1 = new xyz();
        x1.display(10, 20);
        x1.output(); // prints 10 20
    }
}
```

Output:

```
10 20
```

> 📝: In Java, `this` is a reference variable that refers to the current object.

- By the use of `this` keyword, we can refer to any member of the current object within an instance method or constructor.
- `this`keyword can be used to refer to the current object, and it always acts as a reference to an object in which method was invoked.
- There are various uses of `this` keyword in Java. These are:
  - `this` can be used to refer current instance variable. [Example: `this.a;`]
  - `this` can be used to invoke current instance method (implicity). [Example: `this.display();`]
  - `this` can be used to invoke current class constructor. [Example: `this();`]

## 11. Types of functions

| Type                                        | Description                                                   | Example                                                                    |
| ------------------------------------------- | ------------------------------------------------------------- | -------------------------------------------------------------------------- |
| 1. Without arguments & without return value | Method does not take any input, and does not return anything. | `java\nvoid greet() {\n    System.out.println("Hello!");\n}\n`             |
| 2. Without arguments & with return value    | Method does not take input, but returns a value.              | `java\nint getNumber() {\n    return 10;\n}\n`                             |
| 3. With arguments & without return value    | Method takes input, but does not return anything.             | `java\nvoid printSum(int a, int b) {\n    System.out.println(a + b);\n}\n` |
| 4. With arguments & with return value       | Method takes input and also returns a value.                  | `java\nint add(int a, int b) {\n    return a + b;\n}\n`                    |

### Parameterized functions

```java
class abc {
    int c;
    void display(int a, int b) {
        c = a + b;
        System.out.println(c);
    }
}

class xyz {
    public static void main(String[] args) {
        abc a1 = new abc();
        a1.display(10, 20); // prints 30
        System.out.println(a1.c); // prints 30
    }
}
```

Output:

```
30
30
```

📝: Parameters are added to a constructor in the same way that they are added to a method, just declare them inside the paranthesis after constructor's name.

#### Passing Array as an Argument in a function

```java
class abc {
    int c;
    void display(int a[])
    {
        for(int i = 0; i < a.length; i++)
            c += a[i];
        System.out.println(c);
    }
}

class xyz {
    public static void main(String[] args) {
        // int arr[] = {10, 20, 30, 40};
        abc a1 = new abc();
        a1.display(new int[]{10, 20, 30, 40});  // prints 100
        System.out.println(a1.c);  // prints 100
    }
}
```

Output:

```
100
100
```

> 📝: Java doesn't support **default arguments**, like C++.

## 12. Method Overloading (Compile Time Polymorphism)

Same function name & different parameters are called **method overloading**.

> 📝: **Compile Time Polymorphism** is a feature of Java that allows a single method name to be used for multiple different functions with different parameters.

```java
class xyz {
    void display(int a, int b) {
        int c = a + b;
        System.out.println(c);
    }
    void display(int a){
        System.out.println(a);
    }
}

class mno{
    public static void main(String[] args) {
        xyz x1 = new xyz();
        x1.display(10, 20); // prints 30
        xyz x2 = new xyz();
        x1.display(30); // prints 30
    }
}
```

Output:

```
30
30
```

## 13. var args

Variable length Arguments

**Syntax:** `typeName... parameterName`

```java
class xyz{
    void sum(int... arr) { // var args
        int sum = 0;
        for(int k:arr) {
            sum += k;
        }
        System.out.println(sum);
    }
}

class mno{
    public static void main(String... args) { // we can use var args here as well
        xyz x1 = new xyz();
        x1.sum(10, 20, 30); // prints 60
         x1.sum(10, 20, 30, 40); // prints 100

    }
}
```

Output:

```
60
100
```

- `int... arr` → means **zero or more `int` arguments**.

- Inside the method, Java treats `arr` like a normal array.

- You can only have **one varargs parameter** in a method, and it must be the last parameter.

```java
void display(String msg, int... nums) { ... } // ✅ valid
void display(int... nums, String msg) { ... } // ❌ invalid
```

## 14. Passing Object as Argument

In Java, we can pass objects as **arguments** to methods. Since everything in Java is pass-by-value, what actually gets passed is the **reference (address)** of the object, not the actual object itself.

```java
class xyz{
    void sum(){
        System.out.println("hello");
    }
}

class mno{
    xyz x1; // Reference of class xyz

    void output(xyz x1) { // takes xyz object as argument
        this.x1 = x1;     // assign to instance variable
        x1.sum();         // call method of xyz
    }
}

class pqr{
    public static void main(String... args) {
        xyz kk = new xyz(); // create object of xyz
        mno m1 = new mno(); // create object of mno
        m1.output(kk); // pass object kk of class xyz to output()
    }
}
```

Output:

```
hello
```

- When we write `m1.output(kk);`, the reference of object `kk` is passed.
- Inside the method `output(xyz x1)`, the parameter `x1` now refers to the same object as `kk`.
- This means changes made to `x1` inside the method will affect the original object `kk`.

> 📝: Objects are passed by **reference value** → meaning the reference (memory address) is copied, so both variables point to the same object in heap memory.

--

- When you pass an object to a method, what’s actually passed is the **reference (address)** of the object.

- This means:
  - The method can call the object’s methods.
  - The method can modify the object’s fields (since it has the reference).

## 15. Passing Array of Objects to a method

```java
class abc{
    String s;
    void display(){
        System.out.println(s);
    }
    void callObjectArray(abc a1[]) {
        a1[0].display();
        a1[1].display();
    }
    public static void main(String... args) {
        abc a1 = new abc();
        a1.s = "A";
        abc a2 = new abc();
        a2.s = "B";
        abc a3 = new abc();

        // Method 1: Using an array reference
        // Passing pre-created array of objects
        /*  abc arr[] = new abc[2];
            arr[0] = a1;
            arr[1] = a2;
            a3.callObjectArray(arr);
        */

       // Method 2: Passing anonymous array of objects
       // Passing array of objects directly (inline)
       a3.callObjectArray(new abc[]{a1, a2}); // passing array of objects
    }
}
```

- An array can store **objects** just like primitives.
- `new abc[]{a1, a2}` is an **anonymous array** — you don’t store it in a variable, just directly pass it.
- Inside the method, you can use the array just like any normal array.
- Useful in scenarios like:

  - Passing multiple students (objects) to a method.
  - Processing a list of employees, products, etc.

- Arrays in Java can hold objects (references), not just primitive values.
- When you pass an array of objects, you’re passing the **reference** to that array (so changes inside the method affect the original array).
- You can either:
  - Create the array beforehand and pass it.
  - Or directly pass a **new array literal** in the method call (`new abc[]{obj1, obj2}`).

> 📝: Arrays in Java are objects, not primitives.

> 📝: If we declare the function callObjectArray as static method, we won't need an object and we can call the function as: `abc.callObjectArray(new abc[] {a1, a2});`

## 16. Returning Value by a Method

The `return` keyword has a specific meaning in Java compiler. It is only used with a method to specify if that method will return certain value to the calling method.
`return` keyword forces the method to retrun value to the calling method of a particular type.

```java
    class abc {
    int display(int a, int b) {
        return a + b;
    }

    public static void main(String... args) {
        abc a1 = new abc();
        int c = a1.display(10, 20);
        System.out.println(c);

        // Alternatively:
        System.out.println(new abc().display(10, 20));
    }
}
```

- `a1.display(10, 20)` → calls the instance method and returns `30`.
- `new abc().display(10, 20)` → creates a temporary object and immediately calls the method on it.
- Both print `30`, but the second one does not store any reference to the object.

Output:

```
30
30
```

> 📝: We can't overload a function even if its return type is different, but it contains same signature.

❌ Example: Invalid Overloading (Different Return Type Only)

```java
    class abc{
        int display(int a, int b){
             return a + b;
        }
        float display(int a, int b){
             return a + b;
        }
    }
```

In the above class `abc`, even if the return type of the two `display()` functions is different, we can't define two functions having same name, unless its signature is different.

**Why is this invalid?**

- Both methods have the **same name** (`display`) and **same parameter list** (`int, int`).
- Java identifies methods by their **name and parameter list only** (not return type).
- The compiler cannot decide which method to call, since both look identical at call time.

🧩 error: method display(int,int) is already defined in class abc

✅ Example: Valid Overloading (Different Parameters)
```java
class abc {
    int display(int a, int b) {
        return a + b;
    }

    float display(float a, float b) {
        return a + b;
    }
}
```
Now the compiler can distinguish between the two methods because the **parameter types differ** (`int vs. float`).

> 📝: In Java, **method signature = method name + parameter list**

> Return type is not part of the method signature.

## 17. To print an array element by element

When you print an array directly in Java (e.g., `System.out.println(arr);`),
it doesn’t print the elements — instead, it prints the **memory address** (like `[C@15db9742`).
This is because arrays in Java are **objects**, not primitive values.

To print elements **one by one**, you must **traverse (iterate)** the array using a loop.

```java
 class abc{
    char[] display(String s) // defining array of char type
    {
        char ar[] = new char[s.length()];
        for(int i = 0; i < ar.length(); i++)
        {
            ar[i] = s.charAt(i); // returns a char value at given index no
        }
        return ar;
    }
    public static void main(String... args) {
        abc a1 = new abc();
        char am[] = a1.display("hello");
        // System.out.println(am); // would print memory reference, not characters
        for(char p: am){ // for-each loop to print each character
            System.out.println(p);
        }
    }
 }
```
Output:
```
h
e
l
l
o
```

- **Arrays are objects** in Java, so printing them directly prints the reference (like `[C@hashcode`).
- To view individual elements, use a loop (`for`, `for-each`, or `while`).
- `String.charAt(index)` returns the character at a specific position.
- You can return an array from a method just like any other object.
- `for (char p : am)` is a for-each loop, introduced in Java 5, ideal for reading array elements sequentially.

- The method `charAt(int index)` returns the character at the specified index.
The index value should lie between `0` and `length() - 1` (the length of the string minus 1).

- `.length` → **Property** (not method) used to find the size of **an array**.
Example:
```java
int size = arr.length;
```

- `.length()` → **Method** used to find the length of a **String**.
Example:
```java
int len = str.length();
```

This distinction avoids confusion between Strings and Arrays — both have “length,” but one uses a _method_ and the other a _field_.

> 📝: If you want to **print an array without loops** (for debugging), use: `System.out.println(Arrays.toString(am));` (but remember to `import java.util.Arrays;`)

## 18. Passing Objects as arguments

In Java, you can **pass objects as parameters** to methods just like variables.

When you pass an object to a method, its **reference** (memory address) is passed, not the actual copy of the object.

This means that changes made to the object inside the method affect the original object (since both refer to the same memory location).

```java
    class pqr {
        void sum(){
            System.out.println("World");
        }
    }
    class xyz{
        void sum(){
            System.out.println("Hello");
        }
    }
    class mno {
    xyz x1; // Reference to xyz class object
    pqr p1; // Reference to pqr class object

    // Method accepts two objects as parameters
    void output(xyz x1, pqr p1) {
        // 'this' keyword refers to current object of mno
        this.x1 = x1; // assign parameter reference to instance variable
        this.p1 = p1; // assign parameter reference to instance variable

        x1.sum(); // calls xyz.sum()
        p1.sum(); // calls pqr.sum()
    }
}

class abc {
    public static void main(String... args) {
        xyz kk = new xyz();   // create object of xyz
        mno m1 = new mno();   // create object of mno
        m1.output(kk, new pqr()); // passing object references to output()
    }
}
```
Output:
```
Hello
World
```

Explanation:

- `m1.output(kk, new pqr());`
→ The method `output()` is called with two **object arguments**:
one existing object (`kk` of `xyz`) and one anonymous object (`new pqr()`).
→ kk (object of xyz) and new pqr() (new object of pqr) are passed as **references**.
- Inside `output(xyz x1, pqr p1)`:
→ The parameters `x1` and `p1` now refer to the **same memory** locations as the objects `kk` and `new pqr()` created in `main()`.
- Inside the method:
  - `this.x1 = x1;` → assigns the `xyz` object reference to instance variable x1.
  - `this.p1 = p1;` → assigns the `pqr` object reference to instance variable p1.
  - Then `x1.sum()` prints "Hello" and `p1.sum()` prints "World".

 💬 **Important Concepts:**
- Java is **pass-by-value**, even for objects — but the _value passed_ is the **reference** to the object.
So both caller and callee refer to the _same_ object in memory.

- This means that **modifying an object inside a method** will reflect in the calling method,
because both point to the same memory address.

- If you create a **new object** inside the method and reassign the parameter, it won’t affect the original reference outside the method.

- When an **object** is passed to a method, Java passes the **reference value** (address in memory).
This means:
  - The method can call the object’s methods.
  - The method can modify the object’s fields.

- **Objects are never passed by value** (_copy of the object_) —
only the reference is copied and passed.

- You can pass:
  - Pre-created objects (`kk`), or
  - Anonymous objects (`new pqr()`).

📘 **Key Takeaways:**

✅ You can pass multiple objects as arguments in a single method.

✅ The method can call functions of those objects or even modify their data.

⚠️ Remember: both the caller and callee share the same memory reference.

📝 If you modify the object inside the method, the change reflects outside too — since both refer to the same object in the heap.

## 19. String

String is basically an object that represents sequence of char values.

```java
class abc{
    public static void main(String... args) {
        String s = "1234hello";
        String str = s + "hello"; 
        System.out.println(str); // displays 1234hellohello
    }
}
```

Output:

```
1234hellohello
```

Explanation:
- `String s = "1234hello";` → creates a string object `s` with value "1234hello".
- `String str = s + "hello";` → creates a new string object `str` by concatenating `s` and "hello".
- `System.out.println(str);` → prints the value of `str`, which is "1234hellohello".

💬 **Important Concepts:**

- String is a **class** that represents a sequence of characters.
- Strings are **immutable**, which means they cannot be changed once created.
- String objects are created using double quotes.
- String concatenation is done using the `+` operator. The `+` operator concatenates strings.

```java
String str = "hello";

int len = str.length();     // returns length of the string (5)
char ch = str.charAt(3);    // returns the character at index 3 → 'l'

System.out.println("Length: " + len);
System.out.println("Character at index 3: " + ch);
```

- `str.length()` → returns an int representing the number of characters in the string.
- `str.charAt(index)` → returns the character at the given index (0-based).

        - For "hello",
                charAt(0) → 'h'
                charAt(1) → 'e'
                charAt(2) → 'l'
                charAt(3) → 'l'
                charAt(4) → 'o'

- The valid index range is `0` to `length() - 1`.

```java
String st = "Welcome";
for(int i=0; i < st.length(); i++) // length() returns the length of the string
{
    System.out.println(st.charAt(i)); // prints each character
}
```

Output:
```
W
e
l
c
o
m
e
```

```java
String st = "Welcome";
char arr[] = new char[st.length()]; // array of char type
for(int i=0; i < st.length(); i++)
{
    arr[i] = st.charAt(i); // returns a char value at given index no
    System.out.println(p); // prints each character
}
```
Output:
```
W
e
l
c
o
m
e
```
![String](./resources/Strings.jpg)

- String : Immutable
- StringBuffer : Mutable
- StringBuilder : Mutable
- StringJoin : Mutable

**Immutable** → cannot change the object once created (`String`)

**Mutable** → can modify contents without creating new object (`StringBuffer`, `StringBuilder`, `StringJoiner`)

**Thread-safety** → `StringBuffer` is synchronized (safe in multithreading), others are not.

        int b = arr.length // to calculate length of an array

```java
class abc{
    int a = 10;
    String ss = "hello";
    public static void main(String... args) {
        abc a1 = new abc();
        System.out.println(a1.a);
        System.out.println(a1.ss);
    }
}
```
📝: As instance variable requires an object to be able to access it throughout any method in the class; we aren't able to access the instance variable in a static method directly (using variable's name only).

As static methods don't require objects for their invokation and instance variable can't be accessed without an object.

📝: Instance variables can be accessed directly by calling the variable name inside the class. However, within static menthods (when instance variables are given accessibility), they should be called using the fully qualified name. `ObjectReference.VariableName`

📝: `substring(int beginIndex)` returns a new string that is a substring of this string.
`substring(int beginIndex, int endIndex)` returns a new string that is a substring of this string. The substring includes the characters at the specified beginIndex and excludes the character at endIndex. Thus, the length of the returned substring is `endIndex - beginIndex`.

```java
class abc{
    public static void main(String... args) {
        String s = "1234hello";
        String sst = s + "hello";
        s = s + "hello"; // concatenate String s
        System.out.println(sst);
        System.out.println(s);
    }
}
```

### String Concatenation  

In Java, string concatenation forms a new string that is combination of multiple strings.
There are two ways to concatenate strings in Java:
- `+` operator
- `concat()` method

- After a string literal, all the `+` will be treated as string concatenation operator.

> ⚠ : Java uses the `+` operator for **both addition and concatenation**.
Numbers are added. Strings are concatenated.

### To print a string character by character

You can use a `for loop` with `charAt()` method.

```java
class abc {
    public static void main(String... args) {
        String s = "Arigatou!";
        for(int i = 0; i < s.length(); i++)
        {
            System.out.println(s.charAt(i));
        }
    }
}
```
Output:
```
A
r
i
g
a
t
o
u
!
```

### To store a string into an array

```java
class abc {
    public static void main(String... args) 
    {
        String s = "Sakura";
        char ar[] = new char[s.length()];
        for(int i = 0; i < ar.length; i++)
        {
            ar[i] = s.charAt(i);
            System.out.println(ar[i]);
        }
    }
}
```
Output:
```
S
a
k
u
r
a
```

## 20. Wrapper Class

A wrapper class is a class whose object **wraps** or contains a primitive data types.
When we create an 'object' to a wrapper class, it contains a field and in this field, we can store a primitive data type.
In other words, we can wrap a primitve value into a wrapper class.

❓ **Why there is need for wrapper classes?**
➤ Wrapper classes are used to convert any data types into an  object. The primitve data types are not objects; they do not belong to any class; they are defined in the language itself. Sometimes, it is required to convert data types into objects in Java language.

> 📝: Wrapper class is defined in `java.lang.*` package.

The eight classes of `java.lang.package` are known as wrapper classes in Java.

![Wrapper Classes](./resources/WrapperClasses.png)

- **Purpose**:
Wrapper classes "wrap" primitive values into objects so they can be stored in classes like `ArrayList`, `HashMap`, etc.

- **Autoboxing:**
Automatic conversion of a primitive to its wrapper class.

        Integer num = 5;  // int → Integer automatically

- **Unboxing:**
Automatic conversion of a wrapper object back to its primitive.

        int x = num;  // Integer → int automatically

- **All wrapper classes are immutable** — once created, their value cannot be changed.

- In Java, the wrapper classes — `Byte`, `Short`, `Integer`, `Long`, `Float`, and `Double` are subclasses of the abstract class `Number`.
![Wrapper Classes](./resources/WrapperClasses2.png)

- Number is an abstract class in `java.lang` package.
- It provides **methods to convert numeric values** to different primitive types.
- Subclasses of `Number` represent **numeric wrapper classes**.

- **The wrapper classes are not thread-safe.**

📝: Wrapper class in Java provides the mechanism to convert a primitive data type into an object and vice versa.

- Number → Abstract superclass for numeric wrapper classes.

- The classes `Character` and `Boolean` are not subclasses of `Number` because they represent non-numeric data types.

## 21. Boxing, Unboxing, Autoboxing

### Boxing

**Encapsulating value in an object.** Converting primitive data types into object is called boxing, and this is taken care by the compiler. Therefore, while using a wrapper class you just need to pass the value of the primitive data type to the constructor of the wrapper class.

```java
class Demo {
    public static void main(String[] args) {
        int a; 
        Integer b = new Integer(10); // boxes int into an Integer object (manual boxing)
        System.out.println(b);         // prints 10 (toString() of Integer)
        System.out.println(b.intValue()); // unboxes Integer to primitive int
 }
}
```
**Explanation**

- `int a;` → **Declares a primitive variable** `a` (but here it’s unused).
- `Integer b = new Integer(10);` → **Creates a wrapper object** for the primitive value 10.
  - This is **manual boxing** (before Java 5).

  - In modern Java (Java 9+), using new Integer(10) is **deprecated** — use autoboxing instead:

            `Integer b = 10;`  // autoboxing (preferred)

- `System.out.println(b);` → Prints `10`, since `Integer.toString()` returns the numeric value as a string.
- `b.intValue()` → Converts (unboxes) the wrapper object `b` back to a primitive `int`.

### Unboxing

**Converting a wrapper object back to a primitive value.** Unboxing is done automatically by the compiler. This is called **autoboxing**.

    int b = a.intValue(); // unboxing 

```java
class Demo {
    public static void main(String[] args) {
        Integer a = new Integer(10);  // manual boxing (deprecated in modern Java)
        int b = a.intValue();         // explicit unboxing
        System.out.println(b);        // prints 10

        // OR (preferred - auto-unboxing)
        Integer x = 20;   // autoboxing
        int y = x;        // auto-unboxing
        System.out.println(y);  // prints 20
    }
}
```

**Explanation:**

- `Integer a = new Integer(10);` → creates an **Integer object** with value `10`.
- `a.intValue()` → **explicitly converts** the wrapper object `a` into primitive `int`.
- `int y = x;` → **auto-unboxing** — Java automatically converts the wrapper `Integer` to primitive `int`.

⚙️**Key Notes**

- Unboxing is the **reverse** of boxing/autoboxing.
- It happens automatically when:
  - Assigning a wrapper object to a primitive variable.
  - Using a wrapper in arithmetic operations.

            Integer num = 50;
            int result = num + 10;  // auto-unboxed → 60

- **All wrapper classes** (`Integer`, `Double`, `Float`, etc.) support unboxing.

### Autoboxing

Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their corresponding object wrapper classes. It is done when you assign a primitive value to a variable of a wrapper class or when you use a primitive value in an arithmetic operation.
For example, converting an `int` to an `Integer`, a `double` to a `Double`, and so on.

```java
    int a = 10;
    Integer a = 10;  // autoboxing

    int b = a;  // auto-unboxing
    // casting object into primitive type automatically done by compiler
```

```java
    int a = 5; 
    // Integer b = a;  
    Integer b = Integer.valueOf(a); 
```
`valueOf()` method is used to convert a primitive type to a wrapper object. It is a static method of the `Integer` class.

```java
    // String to primitive type
    String s = "20";
    int i = Integer.parseInt(s);
```
`parseInt()` method is used to convert a string to a primitive integer value.

```java
    String s = "20.5";
    double d = Double.parseDouble(s);
```
`parseDouble()` method is used to convert a string to a primitive double value.

```java
    String s = "hello";
    int i = Integer.parseInt(s); // ❌ runtime error - // throws NumberFormatException
```
💡 Reason: `"hello"` cannot be parsed into a number.
The `Integer.parseInt()` method expects a numeric string like `"10"` or `"123"`.

**String to Class Type:**
```java
   class Demo {
    public static void main(String[] args) {
        String s = "123";   // numeric string

        // String → int (primitive)
        int num = Integer.parseInt(s);
        System.out.println(num);  // 123

        // String → Integer (class type)
        Integer obj = Integer.valueOf(s);
        System.out.println(obj);  // 123
    }
}   
```
- `Integer.parseInt(String s)` → returns primitive int
- `Integer.valueOf(String s)` → returns Integer object

✅ Works only if `s` contains numeric characters (e.g., `"10"`, `"200"`).

❌ Throws `NumberFormatException` if `s` contains non-numeric characters.

**Primitive to String:**
```java
   int a = 5;                            // primitive int
    String s1 = Integer.toString(a);       // int → String
    System.out.println(s1);                // prints "5"

    Integer b = 9;                         // Wrapper class object
    String s2 = Integer.toString(b);       // Integer → String
    System.out.println(s2);                // prints "9"
```
- `Integer.toString()` is an **overloaded method** that can take either an `int` or an `Integer` object.
- This conversion is useful when you need to display numeric values as text or concatenate them with strings.

| Conversion Type        | Method Used                 | Example                |
| ---------------------- | --------------------------- | ---------------------- |
| int → String           | `Integer.toString(int)`     | `Integer.toString(5)`  |
| Integer → String       | `Integer.toString(Integer)` | `Integer.toString(a)`  |
| any primitive → String | `String.valueOf(primitive)` | `String.valueOf(10.5)` |
| quick conversion       | `+ ""`                      | `num + ""`             |

- Wrapper classes bridge the gap between **primitive types** and **objects**.
- **Autoboxing** → primitive → wrapper
- **Unboxing** → wrapper → primitive
- **All wrapper classes are immutable** and belong to the `java.lang` package.
- Numeric wrappers inherit from Number, providing conversion methods like `intValue()`, `doubleValue()`, etc.
- Wrapper classes are **not thread-safe**.

> 📝: Autoboxing and unboxing feature converts primitive into object and object into primitive automatically. The automatic conversion of **primitive into object** is known as `autoboxing` and vice-versa `unboxing`.

**Primitive to Wrapper**: `AUTOBOXING`
```java
    class Wrap1 {
        public static void main(String[] args) {
            int a = 10;
            Integer i = Integer.valueOf(a); // converting int to Integer
            Integer j = a; // autoboxing, now compiler will write Integer.valueOf(a) internally
            System.out.println(a+ " " + i + " " + j);
        }
    }
```
Output:

```
10 10 10
```
Explanation:

- `Integer.valueOf(a)` → explicit boxing (manual conversion)
- `Integer j = a;` → implicit boxing (autoboxing)
- `System.out.println()` automatically calls `toString()` on `Integer` objects, so all print as numbers.

**Wrapper to Primitive**: `UNBOXING`
```java
    class Wrap2 {
        public static void main(String[] args) {
            Integer a = new Integer(3);
            int i = a.intValue(); // converting Integer to int
            int j = a; // unboxing, now compiler will write a.intValue() internally
            System.out.println(a+ " " + i + " " + j);
        }
    }
```
Output:
```
3 3 3
```
Explanation:
1. `Integer a = new Integer(3);`
- Creates an **Integer object** `a` wrapping the primitive value `3`.
- This is manual boxing (explicit object creation).

2. `int i = a.intValue();`
- **Explicit unboxing**: Converts the `Integer` object a to primitive int using intValue() method.

3. `int j = a;`
- **Auto-unboxing**: Compiler automatically converts `Integer` to `int` behind the scenes (`a.intValue()` is called internally).

4. `System.out.println(a + " " + i + " " + j);`
- Prints all three values:

  - `a` → the `Integer` object, automatically converted to string via `toString()`.
  - `i` → primitive int.
  - `j` → primitive int from auto-unboxing.

> 📝: Autoboxing/unboxing lets you mix primitives and wrapper objects seamlessly in expressions.

## 22. String Class

The `String` class in Java is used to create and manipulate sequences of characters. It is one of the most commonly used classes in Java. Objects of the String class are **immutable**, which means they **cannot be changed once created.**

### Key Features of the String Class

**1. Immutable**

Immutable means that once a String object is created, its value cannot be changed.

Example:
```java
public class Main {
    public static void main(String[] args) {
        String text = "hello";
        text.charAt(0) = 'H';  // compile-time error
    }
}
```
**Explanation**: The line `text.charAt(0) = 'H';` causes a compile-time error because `charAt(0)` returns a read-only char, not a variable. String is immutable in Java, you cannot modify its characters directly.

**2. Thread-Safe**

String in Java is thread-safe because it is immutable, allowing safe access by multiple threads without synchronization.

**3. Supports Various Utility Methods**

String is a predefined final class in Java present in java.lang package. It provides various methods to create, manipulate, and compare strings, like `length()`, `charAt()`, `concat()`, `equals()`, etc.

Example:
```java
import java.io.*;
​
class Demo {
    public static void main (String[] args) {
    String str = "hello geeks";
    System.out.println("Length of String-> "+str.length()); 
    System.out.println("Changed String -> "+str.toUpperCase());
    }
}
```
Output:
```
Length of String-> 11
Changed String ->HELLO GEEKS
```

**4. Implements Interfaces**
The String class in Java implements three important interfaces.

 1. **CharSequence**: Allows access to characters in the string using `charAt()`, `length()`, etc.

 2. **Comparable<String>**: Enables comparing two strings lexicographically using `compareTo()`

 3. **Serializable**: Allows string objects to be converted into a byte stream

### String Constructors in Java

In Java, String constructors are used to create new String objects from different sources like character arrays, byte arrays, or another string. Although strings in Java are usually created using string literals, the String class also provides constructors for more control.

Let us check these constructors using a example demonstrating the use of them.

**Example of String Constructor:**
Below is the implementation of string constructors in Java.
```java
import java.io.*;
​
class Geeks {
    public static void main(String[] args) {
        
        // Constructor 1: Creating string using new keyword
        String str1 = new String("Hello Java");
        System.out.println("String using new keyword: " + str1);
​
        // Constructor 2: Creating string from character array
        char[] charArray = { 'J', 'A', 'V', 'A' };
        String str2 = new String(charArray);
        System.out.println("String from char array: " + str2);
​
        // Constructor 3: Creating string from byte array
        byte[] byteArray = { 72, 101, 108, 108, 111 };
        String str3 = new String(byteArray);
        System.out.println("String from byte array: " + str3);
    }
}
```
Output:
```
String using literal: GeeksforGeeks
String using new keyword: Hello Java
String from char array: JAVA
String from byte array: Hello
```

## 23. Character Class

Java provides a wrapper class `Character` in `java.lang` package. An object of type `Character` contains a single field, whose type is `char`. The Character class offers a number of useful class (i.e., static) methods for manipulating characters. You can create a `Character` object with the `Character` constructor.

**Creating a Character object:**

    Character ch = new Character('a');

The above statement creates a Character object which contains '`a`' of type char. There is only one constructor in the Character class that expects an argument of char data type.

If we pass a primitive char into a method that expects an object, the compiler automatically converts the char to a Character class object. This feature is called **Autoboxing** and **Unboxing**.

> 📝: The **Character class is immutable** like String class i.e once it's object is created, it **cannot be changed**.

### Methods in Character Class  

The methods of Character class are as follows:

**1. boolean isLetter(char ch)**: This method is used to determine whether the specified char value(ch) is a letter or not. The method will return true if it is letter([A-Z],[a-z]), otherwise return false. In place of character, we can also pass ASCII value as an argument as char to int is implicitly typecasted in java.

**Syntax:**

    boolean isLetter(char ch)

**Parameters:**

**ch** - a primitive character

**Returns**: It returns true if ch is an alphabet, otherwise, return false

**Example**:
```java
// Java program to demonstrate isLetter() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.isLetter('A'));
​
        System.out.println(Character.isLetter('0'));
    }
}
```
Output:
```
true
false
```

**2. boolean isDigit(char ch)**: This method is used to determine whether the specified char value(ch) is a digit or not. Here also we can pass ASCII value as an argument.

**Syntax:**

    boolean isDigit(char ch)

**Parameters:**
**ch** - a primitive character

**Returns**: It returns true if ch is a digit, otherwise, return false

**Example:**
```java
// Java program to demonstrate isDigit() method
​
public class Test {
    public static void main(String[] args)
    {
        // print false as A is character
        System.out.println(Character.isDigit('A'));
​
        System.out.println(Character.isDigit('0'));
    }
}
```
Output:
```
false
true
```

**3. boolean isWhitespace(char ch)**: It determines whether the specified char value(ch) is white space. Whitespace includes space, tab, or newline.

**Syntax:**

    boolean isWhitespace(char ch)

**Parameters:**

ch - a primitive character
Returns: It returns true if ch is whitespace, otherwise, returns false.

Example:
```java
// Java program to demonstrate isWhitespace() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.isWhitespace('A'));
        System.out.println(Character.isWhitespace(' '));
        System.out.println(Character.isWhitespace('\n'));
        System.out.println(Character.isWhitespace('\t'));
​
        // ASCII value of tab
        System.out.println(Character.isWhitespace(9));
​
        System.out.println(Character.isWhitespace('9'));
    }
}
```
Output:
```
false
true
true
true
true
false
```

**4. boolean isUpperCase(char ch)**: It determines whether the specified char value(ch) is uppercase or not.

**Syntax:**

    boolean isUpperCase(char ch)

**Parameters:**
**ch** - a primitive character

**Returns**: It returns true if ch is upper case, otherwise, returns false.

Example:
```java
// Java program to demonstrate isUpperCase() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.isUpperCase('A'));
        System.out.println(Character.isUpperCase('a'));
        System.out.println(Character.isUpperCase(65));
    }
}
```
Output:
```
true
false
true
```

**5. boolean isLowerCase(char ch)**: It determines whether the specified char value(ch) is lowercase or not.

**Syntax:**

    boolean isLowerCase(char ch)

**Parameters**:

**ch** - a primitive character

**Returns**: It returns true if ch is lower case, otherwise, returns false.

**Example:**
```java
// Java program to demonstrate isLowerCase() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.isLowerCase('A'));
        System.out.println(Character.isLowerCase('a'));
        System.out.println(Character.isLowerCase(97));
    }
}
```
Output:
```
false
true
true
```

**6. char toUpperCase(char ch)**: It returns the uppercase of the specified char value(ch). If an ASCII value is passed, then the ASCII value of its uppercase will be returned.

**Syntax:**

    char toUpperCase(char ch)

**Parameters:**

**ch** - a primitive character

**Returns:** It returns the uppercase form of the specified char value.

**Example:**
```java
// Java program to demonstrate toUpperCase() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.toUpperCase('a'));
        System.out.println(Character.toUpperCase(97));
        System.out.println(Character.toUpperCase(48));
    }
}
```
Output:
```
A
65
48
```

**7. char toLowerCase(char ch)**: It returns the lowercase of the specified char value(ch).

**Syntax**:

    char toLowerCase(char ch)

**Parameters:**

**ch** - a primitive character

**Returns:** It returns the lowercase form of the specified char value.

Example:
```java
// Java program to demonstrate toLowerCase() method
​
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.toLowerCase('A'));
        System.out.println(Character.toLowerCase(65));
        System.out.println(Character.toLowerCase(48));
    }
}
```
Output:
```
a
97
48
```

**8. toString(char ch):** It returns a String class object representing the specified character value(ch) i.e a one-character string. Here we cannot pass ASCII value.

**Syntax:**

    String toString(char ch)

**Parameters:**

**ch** - a primitive character

**Returns:** It returns a String object.

**Example:**
```java
// Java program to demonstrate toString() method

```java
public class Test {
    public static void main(String[] args)
    {
        System.out.println(Character.toString('x'));
        System.out.println(Character.toString('Y'));
    }
}
```
Output:
```
x
Y
```
---
1. **valueOf()**

    Returns an `Integer` object holding the value of the specificed primitive.

2. **toString()**

    Returns a `String` object representation of the specified int or Integer.

3. **parseInt()**
    The `parseInt()` method in the `Integer` class is used to convert a string into a primitive `int`.

    It is a **static method** — meaning it belongs to the `Integer` class and can be called without creating an object.

    - Commonly used for converting **numeric input strings** (like from user input, files, or APIs) into integers.

    - Always ensure the string contains only digits (and an optional minus sign for negatives).

4. **doubleValue()**

    This method returns the value of this `Integer` as a double.

5. **floatValue()**
    This method returns the value of this `Integer` as a double.

6. **intValue()**
    This method returns the value of this `Integer` as an `int`.

7. **longValue()**
    This method returns the value of this `Integer` as a long.

❓ **Why Java is not a pure object oriented language?**

▶ Java is not a pure object-oriented language **because it supports primitive data types** such as `int`, `byte`, `short`, `long`, `float`, `double`, `char`, and `boolean`. These are **not objects**, but rather **basic data types** that exist for performance and memory efficiency.

In a **pure OOP language** (like Smalltalk), **everything is an object** — including numbers, booleans, and even control structures.
However, in Java, primitives are treated differently and do not require object wrappers to perform basic operations.
```java
int a = 10;           // primitive, not an object
Integer b = 20;       // wrapper class object
System.out.println(a + b);  // works due to autoboxing/unboxing
```
Java is **object-based** and **object-oriented**, but not **purely object-oriented** because it includes **non-object primitives** for efficiency.

❓ **Is String is a wrapper class in Java?**
▶ No. String is not a wrapper class, simply because there is no parallel primitive type that it wraps.

![wrapper-methods](./resources/wrapper-methods.png)

All wrapper classes in Java (`Byte`, `Short`, `Integer`, `Long`, `Float`, `Double`, `Character`, `Boolean`) are **immutable** and belong to the package java.lang.
They help in converting between **primitive types and objects**, enabling use in **collections**, **generics**, etc.

## 24. Date class

The `Date` class encapsulates the current date and time.

> Standard Time of Java : 1970, 1 Jan, 00:00:00 GMT (midnight)

> Java calculates any amount of time in milliseconds.
> `import java.util.*;` package contains Date class.

➡ Date ➡ Calendar ➡ Simple Date-Time Format

```java
import java.util.*;
class abc {
    public static void main(String[] args) {
        Date d = new Date(); // Create a new Date object representing the current date and time
        System.out.println(d);  // Print the Date object
        // Default toString() gives a readable format like: // Sat Oct 18 17:30:41 IST 2025
        }
    }
```
Output:
```
Wed Oct 22 13:45:12 IST 2025
```
- `java.util.Date` represents **date** and **time**.
- `new Date()` creates a Date object with the **current system date and time**.
- Printing a `Date` object directly calls its `toString()` **method**, which shows the date in a human-readable format.

> The class `Date` represents a specific instant in time, with millisecond precision.

The class **Date** represents a specific instant in time, with millisecond precision. The Date class of `java.util` package implements **Serializable**, **Cloneable** and **Comparable** interface. It provides constructors and methods to deal with date and time with java. Constructors

- **Date()** : Creates date object representing current date and time.
- **Date(long milliseconds)** : Creates a date object for the given milliseconds since January 1, 1970, 00:00:00 GMT.
- **Date(int year, int month, int date)**
- **Date(int year, int month, int date, int hrs, int min)**
- **Date(int year, int month, int date, int hrs, int min, int sec)**
- **Date(String s)**

> 📝 : The last 4 constructors of the Date class are Deprecated.

```java
// Java program to demonstrate constuctors of Date
import java.util.*;
​
public class Main
{
    public static void main(String[] args)
    {
        Date d1 = new Date(); // uses the default constructor to get the current system date and time.
        System.out.println("Current date is " + d1);
        Date d2 = new Date(2323223232L); // creates a date object representing 2323223232 milliseconds after January 1, 1970.
        System.out.println("Date represented is "+ d2 );
    }
}
```
Output:
```
Current date is Wed Oct 22 13:45:12 IST 2025
Date represented is Thu Jan 27 12:53:43 IST 1970
```
⚠️ Note: The `Date(long millis)` constructor interprets the long value as **milliseconds since epoch (Jan 1, 1970)**.

### Important Methods

- **boolean after(Date date)** : Tests if current date is after the given date.
- **boolean before(Date date)** : Tests if current date is before the given date.
- **int compareTo(Date date)** : Compares current date with given date. Returns 0 if the argument Date is equal to the Date; a value less than 0 if the Date is before the Date argument; and a value greater than 0 if the Date is after the Date argument.
- **long getTime()** : Returns the number of milliseconds since January 1, 1970, 00:00:00 GMT represented by this Date object.
- **void setTime(long time)** : Changes the current date and time to given time.

```java
// Program to demonstrate methods of the java.util.Date class
import java.util.*;

public class Main {
    public static void main(String[] args) {

        // Creating Date objects
        // ⚠️ The following constructor is deprecated (year starts from 1900, month from 0)
        Date d1 = new Date(2000, 11, 21); // Deprecated way
        Date d2 = new Date();              // Current system date and time
        Date d3 = new Date(2010, 1, 3);    // Deprecated way

        // Check if d3 comes after d1
        boolean a = d3.after(d1);
        System.out.println("Date d3 comes after date d1: " + a);

        // Check if d3 comes before d2
        boolean b = d3.before(d2);
        System.out.println("Date d3 comes before date d2: " + b);

        // Compare two dates (returns 0 if equal, <0 if before, >0 if after)
        int c = d1.compareTo(d2);
        System.out.println("Comparison result of d1 and d2: " + c);

        // Get milliseconds since January 1, 1970 (Epoch time)
        System.out.println("Milliseconds from Jan 1, 1970 to d1: " + d1.getTime());

        // Set a new time in milliseconds
        System.out.println("Before setting: " + d2);
        d2.setTime(204587433443L);
        System.out.println("After setting: " + d2);
    }
}
```
The Date(int year, int month, int date) constructor adds 1900 to the year and treats month as 0-indexed.

That’s why new Date(2000, 11, 21) → Dec 21, 3900.

Always prefer `java.time.LocalDate`, `Instant`, or `Calendar` for modern, accurate date handling.
Output:
```
Date d3 comes after date d1: true
Date d3 comes before date d2: false
Comparison result of d1 and d2: 1
Milliseconds from Jan 1, 1970 to d1: 60935500800000
Before setting: Sat Oct 18 17:30:41 UTC 2025
After setting: Fri Jun 25 21:50:33 UTC 1976
```

- `Date.after(Date when)` → returns `true` if this date is after the given date.
- `Date.before(Date when)` → returns `true` if this date is before the given date.
- `Date.compareTo(Date anotherDate)` → compares two dates chronologically.
- `Date.getTime()` → returns time in milliseconds since epoch (`01-01-1970 00:00:00 UTC`).
- `Date.setTime(long time)` → sets the date object using milliseconds since epoch.

> 💡 **Modern alternative:** Use `java.time.LocalDate`, `LocalDateTime`, or `Instant` (Java 8+) instead of the deprecated constructors of Date.

### Calendar Class

- Package: `java.util.Calendar`
- It’s an **abstract class** used to work with dates and times more flexibly than `Date`.
- You **cannot instantiate it directly**; you use `Calendar.getInstance()` to get a concrete subclass object (usually `GregorianCalendar`).

```java
    import java.util.*;
    class abc{
        // Get an instance of Calendar (returns GregorianCalendar by default)
        Calendar c = Calendar.getInstance();

        // Retrieve the current date of the month (1 to 31)
        int j = c.get(Calendar.DATE); // Get the current date // int constant passed in the get() method
        // j has the range of 1 to 31
    }
```
- `Calendar.getInstance()` returns a **Calendar object initialized to the current date and time.**
- `Calendar.DATE` is a **constant** representing the day of the month.
- Months in `Calendar` are **zero-based**: January = 0, February = 1, ..., December = 11.
- `get()` can also retrieve **YEAR, MONTH, HOUR, MINUTE, SECOND**, etc.

> 📝: `final` keyword is used to declare a variable constant.

- The `get()` fetches current time-date from the OS.
```java
    int month = c.get(Calendar.MONTH); // 0 = January, 11 = December
    int year  = c.get(Calendar.YEAR);  // Current year

    int j = c.get(Calendar.DATE); // Get the current date
    int k = c.get(Calendar.HOUR); // Get the current hour

    int l = c.get(Calendar.AM_PM); // 0 = AM, 1 = PM

    int n = c.get(Calendar.MONTH); // displays 9 
    // because months are zero-indexed, so October → 9
```

> **`TimeZone`** is passed in the `getInstance()`, if we don't pass time, it'll return default time.
```java
import java.util.*;
class abc{
    public static void main(String... args) {
        String arr[] = TimeZone.getAvailableIDs();
        for(String id : arr){
            TimeZone tz = TimeZone.getTimeZone(id);
            Calendar c = Calendar.getInstance(tz);
            System.out.println(c.get(Calendar.HOUR) + ":" + c.get(Calendar.MINUTE) + ":" + c.get(Calendar.SECOND) + " " + id);
        }
    }
}
```
Output:
```
 7:35:10 Asia/Kolkata
9:05:10 Asia/Tokyo
23:35:10 America/New_York
4:35:10 Europe/London
...
```

**Explanation:**

1. `TimeZone.getAvailableIDs()`
→ Returns an array of all valid time zone IDs (like `"Asia/Kolkata"`, `"America/New_York"`, `"Europe/London"`, etc.).

2. `TimeZone tz = TimeZone.getTimeZone(id);`
→ Gets a `TimeZone` object corresponding to each ID.

3. `Calendar c = Calendar.getInstance(tz);`
→ Creates a `Calendar` instance for that specific time zone.

4. `c.get(Calendar.HOUR)` etc.
→ Extracts the hour, minute, and second according to that time zone.

5. `System.out.println(...)`
→ Prints the time along with the time zone ID.

The exact output depends on:
- Your system’s clock
- The time when you run the program
- The number of available time zones in your Java runtime

▶ **Code to print/calculate the execution time of the program:**
```java
long l = System.getCurrentMillSeconds(); // return the current time in milliseconds

long e = System.getCurrentMillSeconds(); // return the current time in milliseconds

// double totalTime = l - e; 
// System.out.println("Execution time: " + totalTime + " milliseconds");
System.out.println("Execution time: " + (e - l) + " milliseconds");
```

### Factory Method
>
> 📝: A method which is static, and returns the object of the same class.
- It is often used to **control object creation**, apply **caching**, or **encapsulate complex instantiation logic**.
```java  
class Car {
    private String model;

    // Private constructor to control object creation
    private Car(String model) {
        this.model = model;
    }

    // Factory method: static method that returns Car objects
    public static Car createCar(String model) {
        return new Car(model);
    }

    public void display() {
        System.out.println("Car model: " + model);
    }
}

public class Main {
    public static void main(String[] args) {
        // Using factory method to create objects
        Car c1 = Car.createCar("BMW");
        Car c2 = Car.createCar("Audi");

        c1.display();
        c2.display();
    }
}
```
Output:
```
Car model: BMW
Car model: Audi
```

**Key Points:**

- The **constructor can be private** to prevent direct object creation.
- The **static factory method** controls how objects are created.
- Can **return cached objects**, **subclass objects**, or objects with **specific configurations**.
- Helps **encapsulate object creation logic** and can make code cleaner.

## 25. String Handling

```java
    String s = "welcome";

    byte arr[] = s.getBytes();
    // returns byte code of the given String. in other words, it returns sequence of bytes.

    for(int b: arr) // here Implicit Casting is done automatically
    System.out.println((char)b); // Explicit Casting
```

```java
String s = "Welcome";
String s1 = "Welcome";

System.out.println(s.equals(s1)); // compares String s and s1
System.out.println(s == s1); // compares the object of s and s1
```
Output:
```
true
true
```
**Explanation:**

🔹 **`equals()` method**

- In the `String` class, `.equals()` is **overridden** to compare **the actual content** (the sequence of characters).

- So `s.equals(s1)` → compares `"Welcome"` with `"Welcome"`, and returns **true**.

🔹 **`==` operator**

- The `==` operator compares **object references** — i.e., whether both variables refer to the **same object in memory**.

- In Java, **string literals** like `"Welcome"` are **interned** — meaning they are stored in a special pool called the **String Constant Pool (SCP)**.

- If you create two strings with the same literal value, both references point to the **same object** in the SCP.

Hence,
`System.out.println(s == s1);` → returns true, because both `s` and `s1` refer to the same `"Welcome"` object in the pool.

🧪 **Additional note:**

If you had created the strings using `new`, the result would differ:
```java
String s = new String("Welcome");
String s1 = new String("Welcome");

System.out.println(s.equals(s1)); // true (content is same)
System.out.println(s == s1);      // false (different memory objects)
```

Here, `==` returns `false` because both strings are **different objects** even though their contents match. Because new String() explicitly creates **two different objects** in heap memory — even though they hold the same text.

> 📝: **Conclusion:** Use `.equals()` to compare the content of two `String` objects, and use `==` to compare **object references**.

→ **equalsIgnoreCase()**

```java
String s = "Welcome";
String s1 = "welcome";

// Compares the content of the strings with case sensitivity.
System.out.println(s.equals(s1)); // "Welcome" vs "welcome" → the first character 'W' vs 'w' differ.

// Compares the content of the strings ignoring case.
System.out.println(s.equalsIgnoreCase(s1)); // "Welcome" vs "welcome" → all characters match if you ignore case.
```
Output:
```
false
true
```

→ **contains()**

```java
String s = "Welcome";
boolean b = s.conatin("el"); // true
boolean b = s.conatin("El"); // false
```

→ **indexOf()**
if the character isn't present then it returns -1 or else it'll return the index of the character.

- indexOf(ch)

        int j = s.indexOf('e'); // returns 1
        int j = s.indexOf('E'); // returns -1

- indexOf(ch, int fromIndex)

        int j = s.indexOf('l', 2); // returns 3
leave starting 2 indices and then search for that character.

→ **lastIndexOf()**

    int j = s.lastIndexOf('e');    

- Returns the **index of the last occurrence** of the specified character in the string.
- Indexing in Java strings starts from 0.

| Character | Index |
| --------- | ----- |
| W         | 0     |
| e         | 1     |
| l         | 2     |
| c         | 3     |
| o         | 4     |
| m         | 5     |
| e         | 6     |

- The character `'e'` occurs at index `1` and `6`.
- `lastIndexOf('e')` returns the **last occurrence**, which is **6**.

Output:
```
6
```
→ **split()**
splits the string and returns an array of substrings based on the specified delimiter.

```java
String s = "Welcome to Java";
String[] arr = s.split(" "); // splits the string into substrings based on spaces.
```
Output:
```
["Welcome", "to", "Java"]
```

→ **toUpperCase()** and **toLowerCase()**

```java
String s = "Welcome";
String s1 = s.toUpperCase(); 
String s2 = s.toLowerCase(); 
```
Output:
```
WELCOME
welcome
```

→ **toCharArray()**

    char arr [] = s.toCharArray();

- The method toCharArray() converts the string into a character array.

- Each character in the string becomes an element in the array, in the same order.  

```java
String s = "Welcome";
char arr[] = s.toCharArray();

System.out.println(Arrays.toString(arr));
```
Output:
```
['W', 'e', 'l', 'c', 'o', 'm', 'e']
```
- `arr[0]` → `'W'`

- `arr[1]` → `'e'`

- `arr[6]` → `'e'`

This is useful when you want to **manipulate individual characters** of a string.

→ **trim()**
removes whitespaces from right or left side of the string.

    String s = s.trim();

→ **startsWith()** and **endsWith()**

```java
String s = "Hello World";
boolean b = s.startsWith("Hello"); // true
boolean b = s.endsWith("d"); // true
```
→ **isEmpty()**

    boolean b = s.isEmpty();

→ **replace()**

    **replace('original character' , 'new character');**

```java
String s = "Welcome";
String s1 = s.replace('e', 'E'); // 'e' will be replaced with 'E'
```
Output:
```
WelcomE
```

→ **concat()**

```java
String s = "Welcome";
String s1 = " to Java";
String s2 = s.concat(s1);
```
Output:
```
Welcome to Java
```

→ **compareTo()**

compareTo() is a **case-sensitive** method.

    **int c = s.compareTo(String anotherString);** // returns 0 if equal, <0 if before, >0 if after

It compares strings on the basis of Unicode value of each character in the Strings.

    int s = s1.compareTo(s2);

- if `s1 > s2` → returns 1
- if `s1 < s2` → returns -1
- if `s1 == s2` → returns 0

⚙️ **Special Case :  When One String is Empty**

If one of the strings is empty:

- `"abc".compareTo("")` → returns **positive** (equal to the length of `"abc"`)

- `"".compareTo("abc")` → returns **negative** (equal to `-3`)

If you compare string with blank or empty string, it returns length of the string. If second string is empty, result would be poisitive. If the first string is empty, result would be negative.

```java
class abc{
    public static void main(String[] args) {
        String s1 = "Hibino";
        String s2 = "";
        String s3 = "Kafka";
        System.out.println(s1.compareTo(s2));
        System.out.println(s2.compareTo(s3));
    }
}
```
Output:
```
6
-5
```

**Explanation:**

1. s1.compareTo(s2) → "Hibino".compareTo("")
    - Since s2 is empty, the result = length of s1 = 6 → +6

2. s2.compareTo(s3) → "".compareTo("Kafka")
    - Since s2 is empty, the result = -length of s3 = -5

→ **split()**
The mthod `split()` is used for splitting a String into its substrings based on the given delimiter/regular expression(regex).

```java
class SplitExample{
    public static void main(String[] args) {
        String s1 = "Java string split method";
        String[] words = s1.split("\\s"); // splits the string into substrings based on whitespaces.
        for(String w : words) {
            System.out.println(w);
        }
    }
}
```
Output:
```
Java
string
split
method
```
---
> `indexOf()` method returns index of given character value or substring. If it is not found, it returns -1. The index counter starts from 0.

> `lastIndexOf()` method returns index of last occurrence of given character value or substring. If it is not found, it returns -1. The index counter starts from 0.

## 26. Typecasting

Assigning a value of one data type to a variable of another data type is called **Typecasting**.
In Java, type casting is classified into two types:
1. Widening Casting (Implicit)
    - Also known as **automatic type conversion**.
    - Occurs when a smaller data type is converted to a larger data type.
    - No explicit casting is required.

Conversion order:

    byte → short → int → long → float → double

2. Narrowing Casting (Explicitly done)

    - Must be done manually by the programmer.
    - May lead to **data loss** or **precision loss**.

Conversion order:

    double → float → long → int → short → byte

## 27. Java Scanner Class

The `Scanner` class is used to get user input, and it is found in the `java.util` package.

The Java `Scanner` class breaks the input into tokens using a delimiter that is whitespace by default. It provides many mthods to read and parse various primitve values.

    Scanner sc = new Scanner(System.in);

- String `next()` → returns the next token in the input as a string.
- String `nextLine()` → it moves the scanner position to the next line and returns the value as a string.
- byte `nextByte()` → it scans the next token in the input as a byte.
- short `nextShort()` → it scans the next token in the input as a short.

Similarly, we have following functions:
- int `nextInt()`
- long `nextLong()`
- float `nextFloat()`
- double `nextDouble()`

➡ **to get input from console**
```java
import java.util.Scanner;
class ScannerTest1{
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in); // create a Scanner object
        System.out.println("Enter your age : ");
        int age = sc.nextInt();
        System.out.println("Enter your name : ");
        String name = sc.nextLine();
        System.out.println("Enter your fee : ");
        double fee = sc.nextDouble();
        System.out.println("Age : " + age + "\nName : " + name + "\nFee : " + fee);
        sc.close(); // close the scanner
    }
}
```
Output:
```
Enter your age : 
25
Enter your name : 
Mikasa
Enter your fee : 
5000.0
Age : 25
Name : Mikasa
Fee : 5000.0
```

➡ **Scanner class with delimiter:**
The `\s` represents whitespace.

```java
import java.util.*;
class ScannerTest2{
    public static void main(String... args) {
        String input = "10 tea 20 coffee 30 tea biscuits";
        Scanner sc = new Scanner(input).useDelimiter("\\s");
        System.out.println(s.nextInt());
        System.out.println(s.next());
        System.out.println(s.nextInt());
        System.out.println(s.next());
        s.close();
    }
}
```
Output:
```
10
tea
20
coffee
```

➡ **join() function**

In JDK 8, there's a new function `join()` introduced.
It is a **static function** which is called as `String.join()` (using the classname)

    String.join(String delimiter, String... elements)

```java
class JoinExample{
    public static void main(String[] args) {
        String ss = String.join(" ", "Java", "is", "great");
        System.out.println(ss); 
    }
}
```
Output:
```
Java is great
```

The `java.lang.String.join()` method concatenates the given elements with the given delimiter and returns the concatenated string.

## 28. Email Validation

```java
import java.util.*;
class EmailValidation {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in); // create Scanner object for user input
        System.out.println("Enter your email : ");
        String email = sc.nextLine(); // take email input from user

        // basic checks: does it start or end with '.'
        boolean b = email.endsWith(".");
        boolean b1 = email.startsWith(".");

        // find the position of the last '.'
        int l = email.lastIndexOf(".");

        // count number of '@' symbols
        int atCount = 0;
        for (int i = 0; i < email.length(); i++) {
            if (email.charAt(i) == '@') {
                atCount++;
            }
        }

        // flag to mark invalid cases
        boolean inValid = false;

        // invalid if contains double dots, ".@" or "@."
        if (email.contains("..") || email.contains("@.") || email.contains(".@")) {
            inValid = true;
        }

        // split email into username and domain using '@'
        String divs[] = email.split("@");
        String uN = divs[0]; // username part
        String dN = divs[1]; // domain name part

        // validation conditions:
        // - must have exactly one '@'
        // - username should not end with '.'
        // - must not contain invalid patterns
        if ((atCount == 1) && (uN.endsWith(".") == false) && (inValid == false)) {
            System.out.println("\n'Valid email address'\n");
        } else {
            System.out.println("\n'Invalid email address'\n");
        }

        // display extracted username and domain
        System.out.println("Username : " + uN);
        System.out.println("Domain Name : " + dN);

        sc.close(); // close the scanner
    }
}
```

1. `Scanner` class - used for user input from console.

2. **String methods used:**

- `endsWith()`, `startsWith()` → to check beginning/end characters.
- `contains()` → to check for invalid patterns.
- `split("@")` → separates username and domain.
- `charAt()` → used in loop to count `@` symbols.

3. **Logic:**

- Valid emails have **exactly one '@'**.
- Cannot start or end with `.`.
- Cannot have sequences like `..`, `@.`, or `.@`.
- `lastIndexOf(".")` — gives position of last `.` (can be used for checking domain endings if needed).

4. **Potential improvements:**

- Add check to ensure domain contains a `.` (like `gmail.com`).
- Use regex for more advanced validation later.

## 29. Switch-Case Statement
Apart from the if-else blocks, there are also switch cases where you can define multiple cases based on a single switch.

```java
import java.util.Scanner;

public class Main {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("What is the first operand? ");
        int a =scanner.nextInt();

        // consumes the dangling newline character
        scanner.nextLine();

        System.out.print("What is the second operand? ");
        int b = scanner.nextInt();

        // consumes the dangling newline character
        scanner.nextLine();

        System.out.print("What operation would you like to perform? ");
        String operation = scanner.nextLine();

        switch (operation) {
            case "sum":
                System.out.printf("%d + %d = %d", a, b, a+b);
                break;
            case "sub":
                System.out.printf("%d - %d = %d", a, b, a-b);
                break;
            case "mul":
                System.out.printf("%d * %d = %d", a, b, a*b);
                break;
            case "div":
                if (b == 0) {
                    System.out.print("Can't divide by zero!");
                } else {
                    System.out.printf("%d / %d = %d", a, b, a / b);
                }
                break;
            default:
                System.out.printf("Invalid Operation!");
        }
        scanner.close();
    }
}
```
This is a very simple calculator program. The program prompts the user for two numbers and then asks what operation they would like to perform.

Every switch-case statement will have one switch and multiple cases. When you say `case "sum"`, the program checks whether the value of the switch or the `operation` variable in this is `sum` or not.

If it matches, the case body will execute. If none of the cases match, the `default` case will be executed.

And about that `break` statement. It does what it sounds like: stops the program from going into the next case.

If you remove the `break` statements, all the cases will be executed one after the other until the `default` case has been reached.

## 30. StringBuffer Class
The StringBuffer class in Java represents a sequence of characters that can be modified, which means we can change the content of the StringBuffer without creating a new object every time. It represents a mutable sequence of characters.

- StringBuffer is a mutable String.
- StringBuffer is a different class from String class.
- `java.lang.StringBuffer` extends (or inherits from) `Object` class.

```java
    StringBuffer b = "hello"; // error
    StringBuffer b = new StringBuffer("hello");
```
- Whenever we initialize an object of StringBuffer, it reserves 
16 bytes of memory for the object.

```java
    StringBuffer b = new StringBuffer();
    System.out.println(b.capacity()); // 16
```
- `capacity()` returns the number of characters that the buffer can hold.

```java
    StringBuffer b = new StringBuffer(100);
    System.out.println(b.capacity()); // 100
```

> Note: The default capacity of StringBuffer is 16 characters.

> 📝: Java StringBuffer class is `thread-safe`, i.e., multiple threads cannot access it simultaneously. So, it is safe and will result in an order.

```java
StringBuffer b = new StringBuffer("hello");
System.out.println(b.capacity()); // calculates the total allocated capacity // will display 21 (i.e., 16 + 5 bytes of hello)
System.out.println(b.length()); // returns the number of characters in the buffer
```

**Explanation:**

1. `capacity()`
- When you create a StringBuffer with an initial string,
Java allocates **16 extra characters of space** in addition to the string’s length.
- Formula:

        capacity = 16 + initialString.length()

- So for `"hello"` → length = 5 → capacity = 16 + 5 = **21**.

2. `length()`
- Returns the **number of characters currently stored** in the buffer.
- `"hello"` has 5 characters → b.length() = **5**.
---
- Unicode escape sequences in Java always start with \u followed by **4 hexadecimal digits**.
- These sequences are **replaced before compilation**, meaning they can even appear in identifiers (though that’s not recommended).

```java
char a = '\u0024'; // Unicode for $
char rupee = '\u20B9'; // Unicode for ₹

b.append("World"); // Concatenates String // will display hello World

System.out.println(b.charAt(2)); // returns character at given index
```

> 📝: `Object` class is the **super class** of all the classes. `toString()` is the function of the **Object** class.

    String ss = b.toString();

`toString()` converts StringBuffer into String class type.

→ `setCharAt(int index)` used to return the character at the given index.

```java
b.setCharAt(2, 'H'); // will display heHlo (replaced l with H on the index 2)
```

→ `b.setLength()` used to set the length of the StringBuffer.

```java
b.setLength(5); // set length of the StringBuffer to 5
```

→ insert(int offset, String s) insert the specified string with this string at the specified position. The `insert()` method is overloaded like `insert(int, char)`, `insert(int, int)`, `insert(int boolean)`, `insert(int ,float)`, `insert(int, double)`, etc. 
```java
    b.insert(3, "hello"); 
    System.out.println(b); // will display hehhello World
```

→ `reverse()` used to reverse the StringBuffer.
→ `capacity()` is used to calculate the total allocated capacity.

```java
    b.reverse(); // will display dlroW olleh
    System.out.println(b.capacity()); // will display 21
```
→ `ensureCapacity(int minimumCapacity)` used to ensure that the capacity of the StringBuffer is at least the specified minimum capacity.

```java
    b.ensureCapacity(100); // will ensure that the capacity of the StringBuffer is at least 100
    System.out.println(b.capacity()); // will display 100
```

→ `delete(int startIndex, int endIndex)` is used to delete the string from specified startIndex to endIndex.
The substring begins at the specified start and extends to the character at the index before the end (endIndex-1) or the end of the sequence if no such character exists.
```java
    b = new StringBuffer("hehhello");
    b.delete(2, 5); // will delete the substring from index 2 to index 5
    System.out.println(b); // will display hehello
```

→ `deleteCharAt(int index)` is used to delete the character at the specified position(index) in the sequence. This sequence is shortened by one `char`.
```java
    b = new StringBuffer("hehhello");
    b.deleteCharAt(2); // will delete the character at index 2
    System.out.println(b); // will display hehello
```
→ `replace(int startIndex, int endIndex, String str)` is used to replace the string from startIndex to endIndex with the specified string.

→ `indexOf(String str)` returns the index within this string of the first occurrence of the specified substring, or -1 if there is no such occurrence.
```java
    System.out.println(b.indexOf("h")); // will display 0
    System.out.println(b.indexOf("l")); // will display 3
```

→ `lastIndexOf(String str)` returns the index within this string of the last occurrence of the specified substring, or -1 if there is no such occurrence.
→ `substring(int beginIndex)` returns a new `String` that is a substring of this string beginning at the specified beginIndex.
→ `substring(int beginIndex, int endIndex)` returns a new `String` that is a substring of this string beginning at the specified beginIndex and ending at the specified endIndex.

```java
    System.out.println(b.substring(2)); // will display hhello
    System.out.println(b.substring(2, 5)); // will display hhe
```

> Note: The `append()` method is used to add a string to the end of the StringBuffer.

```java
    b.append("World");
    System.out.println(b); // will display hehhello World
```

The `java.lang.StringBuffer` class is a **thread-safe**, **mutable** sequence of characters.
- A StringBuffer is like a String, but it is **mutable**(can be modified).
- They are safe for use by multiple threads. 
- Every StringBuffer has a **default capacity of 16 characters**.

### Features of StringBuffer Class:

The key features of StringBuffer class are listed below:

- Unlike String, we can modify the content of the StringBuffer without creating a new object.
- All methods of StringBuffer are synchronized, making it safe to use in multithreaded environments.
- Ideal for scenarios with frequent modifications like append, insert, delete, or replace operations.

### Advantages of using StringBuffer

The advanatages of StringBuffer class are listed below:

- **Mutable**: StringBuffer are mutable it means that we can change the content after the object has been created, on the other hand String are immutable once it created it can not be modified.
- **Efficient**: Since StringBuffer objects are mutable, it is suitable in scenarios where we need to modify the string multiple times. If we do the same thing with string, everytime a new object is created and the old one is deleted, which is very bad in terms of performance and memory.

> Note: Both String and StringBuffer objects are thread safe, but in different ways.  On the other hand immutable objects like String are thread-safe because their state can not be modified once they are created.

### Disadvantage of StringBuffer

- **Slower in single-threaded programs**: It's synchronized, meaning it ensures thread safety by allowing only one thread to access it at a time. However, in single-threaded environments, this synchronization is unnecessary and slows down performance compared to non-synchronized classes like StringBuilder.
- **Less efficient than StringBuilder**: For non-threaded use cases, StringBuilder is faster and has similar functionality. Also, StringBuffer operations like `append()` or `insert()` make the code longer compared to using simple '`+`' with String.

## 31. StringBuilder Class

StringBuilder class is used to create **mutable (modifiable) string**. It is same as StringBuffer class expect that it is **non-synchronized**. It is faster than StringBuffer class. Is is available since JDK 1.5.

![StringBuilder vs StringBuffer](/resources/StringBuilder.png)

### StringBuilder vs String vs StringBuffer
![StringBuilder vs String vs StringBuffer](/resources/StringComparisons.png)

### When to Use Which one?

- If a string is going to remain constant throughout the program, then use the String class object because a String object is **immutable**.
- If a string can change (for example: lots of logic and operations in the construction of the string) and will only be accessed from a **single thread**, using a StringBuilder is good enough.
- If a string **can change** and will be accessed from **multiple threads**, use a StringBuffer because StringBuffer is synchronous, so you have **thread-safety**.
- If you don't want thread-safety than you can also go with StringBuilder class as it is not synchronized.

**Conclusion:**
- Objects of String are immutable, and objects of StringBuffer and StringBuilder are mutable.
- StringBuffer and StringBuilder are similar, but StringBuilder is faster and preferred over StringBuffer for single-threaded program. If thread-safety is needed, then StringBuffer is used.

### Reversing a String using StringBuilder class
```java
import java.util.Scanner;
class ReverseString{
    public static void main(String[] args) {
        System.out.println("Enter a string to reverse: ");
        Scanner read = new Scanner(System.in);
        String str = read.nextLine();
        StringBuilder sb = new StringBuilder();
        for(int i = str.length()-1; i >= 0; i--) {
            sb.append(str.charAt(i));
        }
        System.out.println(sb.toString());
    }
}
```
**Output:**
```
Enter a string to reverse: 
Hello
olleH
```
 ✨ **Alternate Method:** use `reverse()` of StringBuilder.
```java 
StringBuilder sb = new StringBuilder();
System.out.println(sb.reverse().toString());
```

## 32. Mutable String
- A mutable string is a string that can be **modified (changed)** after it is created.
- In Java, the `String` class creates **immutable** objects — meaning once a string object is created, it **cannot be changed**.
- If you modify it (like concatenating or replacing characters), a **new object** is created in memory, and the old one is discarded.
- To handle cases where you need to **modify strings frequently**, Java provides two mutable alternatives:
    - `StringBuffer`
    - `StringBuilder`

🔹 **Why Mutable Strings?**

Mutable strings are useful when:

- You need to **append**, **insert**, **delete**, or **replace** characters many times.
- You’re working with **loops** that build long strings (e.g., file I/O, text formatting, JSON building, etc.)

Creating many immutable `String` objects would waste memory and CPU cycles due to constant creation and garbage collection.

🔹 Difference Between `String`, `StringBuffer`, and `StringBuilder`
| Feature       | String                    | StringBuffer                    | StringBuilder                   |
| ------------- | ------------------------- | ------------------------------- | ------------------------------- |
| Mutability    | ❌ Immutable               | ✅ Mutable                       | ✅ Mutable                       |
| Thread Safety | ✅ Thread-safe (immutable) | ✅ Thread-safe (synchronized)    | ❌ Not thread-safe               |
| Performance   | Slower for concatenation  | Slower (due to synchronization) | Fastest (no synchronization)    |
| Use Case      | When data won’t change    | When thread safety is needed    | When thread safety isn’t needed |

```java 
// Immutable String
String s = "Hello";
s.concat(" World");
System.out.println(s); // Output: Hello (not modified)

// Mutable StringBuffer
StringBuffer sb = new StringBuffer("Hello");
sb.append(" World");
System.out.println(sb); // Output: Hello World
```

- Use `String` when text **does not change often**.
- Use `StringBuilder` when text changes **frequently and no thread-safety** is required.
- Use `StringBuffer` when **multiple threads** might access/modify the string concurrently.

## 33. Substring
A part of a string is called a **substring** — a smaller section or “slice” of the original string.
In Java, substring extraction is done using the `substring()` method of the `String` class.

A part of String is called **Substring**. In other words, Substring is a subset of another String. In case of substring `startIndex` in inclusive and `endIndex` is exclusive.

You can get substring from the given string object by one of two methods:
1. `substring(int startIndex)` returns new String object containing the substring of the given String from specified `startIndex`(inclusive).
2. `substring(int startIndex, int endIndex)` returns new String object containing the substring of the given String from specified `startIndex`(inclusive) to `endIndex`(exclusive).

```java
String s = "hello";
System.out.println(0,2); // Output: he
// 0 → 'h' (included), 2 → 'l' (excluded)
//  In above substring, 0 points to h but 2 points to e (because endIndex is exclusive). 
```
In the above example, the substring method returns a substring of the given String from index 0(inclusive) to index 2(exclusive).

```java
class TestSubstring{
    public static void main(String... args){
        String s = "SachinTendulkar";
        System.out.println(s.substring(6)); // Tendulkar
        System.out.println(s.substring(0,6)); // Sachin
    }
}
```

`substring()` is useful in:
- Parsing filenames or extensions
- Extracting usernames or domains from emails
- Tokenizing or pattern-based string operations

## 34. Constructor
Constructor is a special method which is used to initialize the object. It is called automatically when object is created.
- Constructor is always declared with class name.

        <class_name>() {}

- Similar to functions, but they have no return type.
- It is used for object initialization.
- If you don't create a constructor and create an object; it'll be created by default constructor.

```java
ABC(){ // default constructor
    a = 10; 
}
```
> 📝: Everytime an object is created using `new()` keyword, atleast one constructor is called. It is called a **default constructor**.

## 35. Types of Constructors in Java
There are Four types of constructors in Java
![constructors](/resources/constructors_in_java.webp)

#### **1. Default Constructor**
A default constructor has no parameters. It’s used to assign default values to an object. If no constructor is explicitly defined, Java provides a default constructor.

```java
class Test{
    int a;
    Test(){
        a = 10;
    }
}
```
Output:
```
Default constructor
```

> 📝: It is not necessary to write a constructor for a class because the Java compiler automatically creates a default constructor (a constructor with no arguments) if your class doesn’t have any.

> 📝: Default constructor is used to provide the default values to the object like 0, null etc depending on the type.

> Default constructor is also called **no-arg constructor**. 

#### **2. Parameterized Constructor**
A constructor that has parameters is known as parameterized constructor. If we want to initialize fields of the class with our own values, then use a parameterized constructor.
- used to provide different values to the distinct objects.
```java
class ABC{
    int a, b;
    ABC(int a, int b){
        this.a = a;
        this.b = b;
    }
    output(){
        System.out.println(a + " " + b);
    }
}
```

A **parameterized constructor** allows you to initialize object fields with **specific values at the time of object creation**, rather than using default ones.

```java
class abc{
    String on;
    abc(String on){
        this.on = on;
    }
    String rev(){
        String m = "";
        for(int i = on.length()-1; i >= 0; i--){
            m += on.charAt(i); // obtaining characters of the original String individually from end by using charAt() and concatenating them to a new String by using the "+" operator
        }
        return m;
    }
    public static void main(String... args){
        abc a = new abc("Radha");
        System.out.println(a.rev());
    }
}
```

1. **Difference between default and parameterized constructor**

   | Type          | Definition                                                        | Example                       |
   | ------------- | ----------------------------------------------------------------- | ----------------------------- |
   | Default       | Provided automatically by Java if no other constructor is defined | `Student() {}`                |
   | Parameterized | Defined by the user with parameters                               | `Student(String n, int a) {}` |

2. **Using `this` keyword**

   - The `this` keyword differentiates between instance variables and local parameters when they share the same name.

     ```java
     class Box {
         int length;
         Box(int length) {
             this.length = length;
         }
     }
     ```

3. **Overloading constructors**

   - A class can have **multiple constructors** with different parameter lists.

     ```java
     class Box {
         int l, b, h;
         Box() { l = b = h = 0; }                 // Default
         Box(int x) { l = b = h = x; }            // Cube
         Box(int l, int b, int h) {               // Cuboid
             this.l = l; this.b = b; this.h = h;
         }
     }
     ```

4. **Constructor chaining**

   - One constructor can call another using `this()`.

     ```java
     class Example {
         Example() {
             this(10);
             System.out.println("Default constructor");
         }
         Example(int x) {
             System.out.println("Parameterized constructor with value: " + x);
         }
         public static void main(String[] args) {
             new Example();
         }
     }
     ```

     **Output:**

     ```
     Parameterized constructor with value: 10
     Default constructor
     ```

5. **No return type**

   - A constructor **never has a return type**, not even `void`.
   - If you add one, it becomes a **method**, not a constructor.

---

❓: **Can a constructor return a value?**
   → No, constructors don’t return any value, not even `void`.

❓: **Can we overload constructors in Java?**
   → Yes, by changing the number or type of parameters.

❓: **What happens if no constructor is defined in a class?**
   → Java automatically provides a default constructor.

❓: **Can a constructor call another constructor?**
   → Yes, using `this()` keyword.

❓: **What is the purpose of `this` in parameterized constructors?**
   → To differentiate between instance variables and parameters.

❓: **Can constructors be `static`, `final`, or `abstract`?**
   → No, constructors cannot have these modifiers.

❓: **Can a constructor call a method?**
   → Yes, but it should be used carefully since the object might not be fully constructed yet.


#### **3. Copy Constructor in Java**
Unlike other constructors copy constructor is passed with another object which copies the data available from the passed object to the newly created object.
```java
class Test{
    int a;
    Test(Test t){
        this.a = t.a;
    }
}
```
Output:
```
Copy constructor
```

> 📝:  Java does not provide a built-in copy constructor like C++. We can create our own by writing a constructor that takes an object of the same class as a parameter and copies its fields.

## 36. Access Modifiers
Access Modifiers in Java define the **visibility (scope)** of classes, methods, and variables across different parts of a program.
They help achieve **encapsulation**, ensuring that sensitive data or methods are protected from unintended access.

There are 4 types of access modifiers available in Java: 
![Access Modifiers](/resources/aAccess-Modifiers.webp)

| Modifier                   | Within Class | Same Package | Subclass (same pkg) | Subclass (different pkg) | Other Packages |
| -------------------------- | ------------ | ------------ | ------------------- | ------------------------ | -------------- |
| **private**                | ✅            | ❌            | ❌                   | ❌                        | ❌              |
| **default** *(no keyword)* | ✅            | ✅            | ✅                   | ❌                        | ❌              |
| **protected**              | ✅            | ✅            | ✅                   | ✅                        | ❌              |
| **public**                 | ✅            | ✅            | ✅                   | ✅                        | ✅              |

(✅ = Accessible, ❌ = Not Accessible)

### 1. Private Access Modifier

- Declared using `private` keyword.
- Accessible **only within the same class**.
- Cannot be accessed outside the class (even by subclass).
```java
class A {
    private int data = 40;
    private void msg() { System.out.println("Hello Java"); }
}

public class Test {
    public static void main(String[] args) {
        A obj = new A();
        // System.out.println(obj.data);  // ❌ Compile-time error
        // obj.msg();                     // ❌ Compile-time error
    }
}
```

✅ **Use Case**:
Encapsulation — to protect sensitive data and internal logic from outside interference.

### 2. Default Access Modifier (Package-private)

- If **no access modifier** is specified, it is default.
- Accessible **within the same package** only.
```java
// File: pack1/A.java
package pack1;
class A {
    void msg() { System.out.println("Hello from A"); }
}

// File: pack1/B.java
package pack1;
class B {
    public static void main(String[] args) {
        new A().msg(); // ✅ Same package → Accessible
    }
}
```

But if another class tries to access `A` from **another package**,
it will get ❌ **Compile-time error**.

### 3. Protected Access Modifier

- Declared using `protected` keyword.
- Accessible **within the same package and in subclasses of other packages (via inheritance)**.
```java
package pack1;
public class A {
    protected void msg() { System.out.println("Hello from A"); }
}

package pack2;
import pack1.A;
class B extends A {
    public static void main(String[] args) {
        B obj = new B();
        obj.msg(); // ✅ Accessible through inheritance
    }
}
```

✅ **Use Case**:
When you want subclasses (even in different packages) to access certain members,
but still keep them hidden from non-subclass outsiders.

### 4. Public Access Modifier

- Declared using `public` keyword.
- Accessible **from anywhere** in the project.
```java
package pack1;
public class A {
    public void msg() { System.out.println("Hello from A"); }
}

package pack2;
import pack1.A;
class B {
    public static void main(String[] args) {
        A obj = new A();
        obj.msg(); // ✅ Accessible globally
    }
}
```

✅ Use Case:
When members/methods are meant to be **shared and reused globally**.

---

Comparison Table of Access Modifiers in Java
| **Access Level**  | **Modifier** | **Accessible Within**     |
| ----------------- | ------------ | ------------------------- |
| Most Restrictive  | `private`    | Same class only           |
| ↓                 | *default*    | Same package              |
| ↓                 | `protected`  | Same package + subclasses |
| Least Restrictive | `public`     | Everywhere                |

![Access-Modifiers](/resources/AccessModifiers.webp)

💡 **Conceptual Notes :**
- Access modifiers **cannot** be applied to **local variables**.
- **Top-level classes** can only be declared as:
    - public
    - default (no modifier)
- **Protected** members are visible outside package **only through inheritance**.
- Proper usage ensures **data hiding, security, and modularity** in code.

### When to Use Each Access Modifier in Real-World Projects
- **Private**: The idea should be use as restrictive access as possible, so private should be used as much as possible.
- **Default (Package-Private)**: Often used in package-scoped utilities or helper classes.
- **Protected**: Commonly used in inheritance-based designs like framework extensions.
- **Public**: This is used for API endpoints, service classes, or utility methods shared across different parts of an application.

| Modifier      | Scope                | Example Usage                 |
| ------------- | -------------------- | ----------------------------- |
| **private**   | Class-only           | Sensitive data like passwords |
| **default**   | Package-only         | Internal helpers              |
| **protected** | Package + Subclasses | Base class features           |
| **public**    | Global               | APIs, library classes         |

## 37. Getter and Setter Methods in Java
Getter and Setter methods are **used to access and modify private data members** of a class.
They form the foundation of **Encapsulation**, one of the four pillars of Object-Oriented Programming (OOP).

### Why Use Getters and Setters?

In Java, we make class fields **private** to restrict direct access.
But sometimes we still need **controlled access** — that’s where getters and setters come in.

✅ **Getter (Accessor)** → retrieves value

✅ **Setter (Mutator)** → updates value safely


### **Encapsulation Concept**

Encapsulation = **Data Hiding + Controlled Access**

- Data is kept private.
- Access is provided via public methods (getters/setters).
- Allows validation before updating variables.

```java
class Student {
    // private data members
    private String name;
    private int age;

    // getter method for name
    public String getName() {
        return name;
    }

    // setter method for name
    public void setName(String name) {
        this.name = name;
    }

    // getter method for age
    public int getAge() {
        return age;
    }

    // setter method for age with validation
    public void setAge(int age) {
        if(age > 0)
            this.age = age;
        else
            System.out.println("Invalid age!");
    }
}

public class Test {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("Asha");
        s.setAge(20);

        System.out.println("Name: " + s.getName());
        System.out.println("Age: " + s.getAge());
    }
}
```
 **Output**

```
Name: Ankita
Age: 22
```
🔸 **Key Points**

| Concept               | Description                                       |
| --------------------- | ------------------------------------------------- |
| **Encapsulation**     | Wrapping data and methods together.               |
| **Private Variables** | Hidden from outside classes.                      |
| **Getters**           | Used to read the private data.                    |
| **Setters**           | Used to modify private data.                      |
| **Validation**        | We can add logic to check input before assigning. |

### **Advantages of Using Getters and Setters**

1. **Encapsulation** – hides the internal implementation.
2. **Control** – you can validate data before setting values.
3. **Flexibility** – allows changes to implementation without breaking code.
4. **Readability** – consistent naming conventions (`getX()`, `setX()`).

⚙️ **Java Naming Conventions**

| Type           | Naming Rule          | Example      |
| -------------- | -------------------- | ------------ |
| Getter         | `get` + VariableName | `getName()`  |
| Setter         | `set` + VariableName | `setName()`  |
| Boolean Getter | `is` + VariableName  | `isActive()` |

**Example: Boolean Field**
```java
class Lamp {
    private boolean isOn;

    public boolean isOn() {   // getter for boolean
        return isOn;
    }

    public void setOn(boolean isOn) {
        this.isOn = isOn;
    }
}
```
🚀 **Real-World Use**

- Commonly used in **Java Beans**, **POJOs**, and **model classes**.
- IDEs like Eclipse or IntelliJ can auto-generate them (`Alt + Insert` → Getters/Setters).

📋 **Summary Table**

| **Access Type** | **Purpose**             | **Method Example**                 |
| --------------- | ----------------------- | ---------------------------------- |
| **Getter**      | Access private variable | `public String getName()`          |
| **Setter**      | Modify private variable | `public void setName(String name)` |
| **Validation**  | Restrict invalid data   | `if(age > 0) this.age = age;`      |

🧩 **In Short**

> “Getters and Setters are the gatekeepers of your private data.”

They protect your fields, control changes, and keep your code safe, modular, and maintainable.


## 38. Constructor Overloading
A private constructor cannot be accessed from outside the class. It is commonly used in:

- **Singleton Pattern**: To ensure only one instance of a class is created.
- Utility/Helper Classes: To prevent instantiation of a class containing only static methods.

```java
class GFG {

    // Private constructor
    private GFG(){
        
        System.out.println("Private constructor called");
    }

    // Static method
    public static void displayMessage(){
        
        System.out.println("Hello from GFG class!");
    }
}

class Main{
    
    public static void main(String[] args){
        
        // GFG u = new GFG(); // Error: constructor is private
       GFG.displayMessage();
    }
}
```
Output:
```
Hello from GFG class!
```

📝:If there is no constructor in a class, compiler automatically creates a default constructor.

```java
ABC() {} // default constructor
ABC(int a, int b) {retrun a + b;} // Parameterized constructor
```
> If we have defined any parameterized constructor, then compiler will not create default constructor, and vice versa; if we don't define any constructor, the compiler creates the default constructor by default during compilation.

> **Recursive Constructor calling is invalid in Java.**

![constructors](/resources/constructor.png)

Demonstration of **constructor parameterization and method overriding** (`toString()`)
```java
class abc{
    String name;
    int roll;

     // Parameterized constructor
    abc(String name, int roll) {
        this.name = name;
        this.roll = roll;
    }

    // Overriding toString() method from Object class
    public String toString(){ 
        return name + " " + roll;
    }
    public static void main(String[] args) {
        abc a1 = new abc("ABC", 1);
        System.out.println(a1); // compiler automatically calls a1.toString()
    }
}
```
**Concept Breakdown**

🔹 **Parameterized Constructor**

- Accepts parameters to initialize the object directly at creation.
- The `this` keyword differentiates instance variables from parameters.

```java
abc(String name, int roll) {
    this.name = name; // refers to instance variable
    this.roll = roll;
}
```

🔹 **Overriding `toString()`**

- Every Java class implicitly extends `java.lang.Object`.

- The `Object` class has a default `toString()` method that returns:

  ```
  <ClassName>@<HexadecimalHashCode>
  ```

  Example: `abc@7a81197d`

- By **overriding `toString()`**, we can define what should be printed when we display an object.

```java
public String toString() {
    return name + " " + roll;
}
```
Now, instead of showing the hashcode, it prints the actual object data.

---

Output:
```
ABC 1
```
---
- `System.out.println(a1);` automatically calls `a1.toString()`.
- Overriding `toString()` makes debugging and logging much more readable.
- Common practice in Java Beans, POJOs, and model classes.

---

⚙️ **Related Concepts:**

- **Default `toString()` Behavior Example:**

  ```java
  class Student {
      int id = 1;
  }
  public class Test {
      public static void main(String[] args) {
          Student s = new Student();
          System.out.println(s); // prints Student@<hashcode>
      }
  }
  ```

- **Why Override?**
  - To display meaningful info instead of memory address.
  - Improves readability and debugging output.

❓ **Why do we override `toString()` in Java?**
 → To provide a customized string representation of an object that reflects its state, instead of the default memory address.

---

> 📝: If you wnat to represent any object as a string, `toString()` method is used. The `toString()` method returns the string representation of the object.

> 📝: If you print any object, java compiler internally invokes the `toString()` method on the object.

> By overriding, the `toString()` method of the Object class, we can return values of the object, so we don't need to write much code.

## 39. ASCII (American Standard Code for Information Interchange)
**ASCII** stands for **American Standard Code for Information Interchange**.
It is a **character encoding standard** used to represent text (letters, digits, symbols, and control characters) in computers and other digital devices.

The ASCII pronounced 'ask-ee', is strictly a seven-bit code based on the English alphabet. ASCII codes are used to represent alphanumeric data. The code was first published as a standard in `1967`. 

- Each **character** (A–Z, a–z, 0–9, symbols, etc.) is assigned a **unique numeric code** between `0` and `127`.
- These numbers are stored and processed as **binary values (0s and 1s)** inside the computer.
- ASCII ensures that computers and devices can **exchange and interpret text** consistently.

💻 **ASCII Range**
| Type                     | Decimal Range | Characters/Examples                          |
| ------------------------ | ------------- | -------------------------------------------- |
| **Control Characters**   | 0 – 31        | `\n` (newline), `\t` (tab), etc              |
| **Printable Characters** | 32 – 126      | Letters, digits, punctuation                 |
| **Extended ASCII**       | 128 – 255     | Includes extra symbols, used by some systems |

To summarize, the range of ASCII values for capital letters spans from 65 to 90, while for small letters, it extends from 97 to 122. Allocated in alphabetical sequence, the values for "A" and "Z" are 65 and 90, respectively, in uppercase. Similarly, the values for "a" and "z" in lowercase are 97 and 122, respectively.

![ascii](/resources/ASCII.png)

**Examples**

| Character   | ASCII Decimal | ASCII Binary |
| ----------- | ------------- | ------------ |
| `A`         | 65            | 01000001     |
| `a`         | 97            | 01100001     |
| `0`         | 48            | 00110000     |
| ` ` (space) | 32            | 00100000     |
| `!`         | 33            | 00100001     |

🧩 **ASCII in Java**

In Java, every character (`char`) is internally represented as a **Unicode value**,
but the first 128 Unicode values are **identical to ASCII**.

```java
class ASCIIExample {
    public static void main(String[] args) {
        char ch = 'A';
        int asciiValue = ch;  // Implicit typecasting char → int
        System.out.println("Character: " + ch);
        System.out.println("ASCII value: " + asciiValue);
    }
}
```

**Output:**

```
Character: A
ASCII value: 65
```

🔁 **Reverse Conversion (int → char)**

You can also convert an ASCII code back to its character using **type casting**:

```java
class ASCIIReverse {
    public static void main(String[] args) {
        int code = 97;
        char ch = (char) code; // Explicit typecasting int → char
        System.out.println("Character: " + ch);
    }
}
```

**Output:**

```
Character: a
```
---
🔸 **char to ASCII**
```java
char ch = 'a';
int asciiValue = (int) ch; // Explicit typecasting char → int
System.out.println("ASCII value: " + asciiValue); // 97
```

🔸 **ASCII to char**
```java
int code = 65;
char ch = (char) code; // Explicit typecasting int → char
System.out.println("Character: " + ch); // A
```

🔸 **ASCII to String**
```java
int num [] = {65,120,98};
String str = null;
for(int i: num){
    str = Character.toString((char)i); // Explicit typecasting int → char
    System.out.println(str); // A, x, b
}
```

🔸 **String to ASCII**
```java
String test = "ABCD";
for(int i=0; i<test.length(); i++){
    char c = test.charAt(i); // extracting ASCII from string
    System.out.println(c); // 65, 66, 67, 68
}
```

🔸 **Character arithmetic**
 ```java
char ch1, ch2;
ch1 = 88;      // ASCII 88 → 'X'
ch2 = 'Y';     // ASCII 89
ch2++;         // Increment character (Y → Z)
System.out.println(ch1 + " " + ch2); // Character arithmetic example
```
✅ Explanation:
Characters can be incremented since they’re internally numbers (`'Y' + 1 = 'Z'`).

⚙️ **Practical Uses of ASCII in Java**

1. **Character arithmetic**

   ```java
   char next = (char) ('A' + 1); // 'B'
   ```
2. **Character comparison**

   ```java
   if ('A' < 'a') System.out.println("Uppercase comes first in ASCII");
   ```
3. **Validating input**

   ```java
   if (ch >= '0' && ch <= '9') System.out.println("Digit detected");
   ```
4. **Encoding/decoding** text in communication systems.

🧩 **Key Notes**

- ASCII uses **7 bits** to represent each character (values `0–127`).
- **Extended ASCII** (used in old systems) uses **8 bits (0–255)**.
- **Unicode** is a superset of ASCII — includes characters from all languages.
- Java’s `char` type is **2 bytes (16 bits)**, hence supports Unicode by default.

| Feature             | ASCII                                              |
| ------------------- | -------------------------------------------------- |
| Full Form           | American Standard Code for Information Interchange |
| Bit Length          | 7-bit (128 characters)                             |
| Character Range     | 0 – 127                                            |
| Type                | Character Encoding Standard                        |
| Used In             | English text representation                        |
| Relation to Unicode | Unicode’s first 128 values = ASCII                 |

📘 **Real-World Analogy**

Think of ASCII as a **translator** that tells computers what each character (like ‘A’ or ‘#’) means in numbers.
Without ASCII (or Unicode), your computer would not know how to display or interpret letters and symbols.

## 40. Inheritance
- Java supports only 3 types of Inheritance: `Single`, `Mutli-level`, `Hierarchical`.
- We can't inherit multiple classes because **Java doesn't support multiple inheritance**.

> Inheritance represents the "**is-a**" relationship, also known as **parent-child** relationship.

```java
class abc{ // parent class (Super Class)
    void display(){
        System.out.println("hello");
    }
}
class xyz extends abc{ // child class (Sub Class)
    void disp(){
        System.out.println("world");
    }
}
class mno {
    public static void main(String[] args) {
        xyz obj = new xyz();
        obj.display();
        obj.disp();
    }
}
```
### Types of Inheritance
**1. Single Inheritance**

In single inheritance, a sub-class is derived from only one super class. It inherits the properties and behavior of a single-parent class. Sometimes, it is also known as simple inheritance.

![single_inheritance](./resources/single_inheritance.png)

**2. Multilevel Inheritance**

In Multilevel Inheritance, a derived class will be inheriting a base class and as well as the derived class also acts as the base class for other classes.

![multilevel_inheritance](./resources/Multilevel_Inheritance.png)

**3. Hierarchical Inheritance**

In hierarchical inheritance, more than one subclass is inherited from a single base class. i.e. more than one derived class is created from a single base class. For example, cars and buses both are vehicle

![hierarchical_inheritance](./resources/Hierarchical_inheritance.png)

**4. Multiple Inheritance (Through Interfaces)**
In Multiple inheritances, one class can have more than one superclass and inherit features from all parent classes.

> 📝: that **Java does not support multiple inheritances** with classes. In Java, we can achieve multiple inheritances **only through Interfaces**. 

![multiple_inheritance](./resources/multiple_inheritance.png)

### Upcasting
    abc obj = new xyz();
- `obj` → reference of `abc`
- `xyz` → object of class `xyz`

        obj.display(); // accessing member function of class abc
        obj.disp(); // error // we can't access member of class xyz
  When reference variable of **Parent** class refers to the object of **Child** class, it it known as **upcasting**.

  ![upcasting](./resources/upcasting.png)      

### Why use Inheritance in Java
- For **Method Overriding**  (so that runtime polymorphism can be achieved.)
- For Code Reusability.

### What Can Be Done in a Subclass?
In sub-classes we can inherit members as is, replace them, hide them or supplement them with new members: 

- The inherited fields can be used directly, just like any other fields.
- We can declare new fields in the subclass that are not in the superclass.
- The inherited methods can be used directly as they are.
- We can write a new instance method in the subclass that has the same signature as the one in the superclass, thus **overriding** it (as in the example above, toString() method is overridden).
- We can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
- We can declare new methods in the subclass that are not in the superclass.
- We can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword `super`.

### Advantages of Inheritance in Java
- **Code Reusability**: Inheritance allows for code reuse and reduces the amount of code that needs to be written. The subclass can reuse the properties and methods of the superclass, reducing duplication of code.
- **Abstraction**: Inheritance allows for the creation of abstract classes that define a common interface for a group of related classes. This promotes abstraction and encapsulation, making the code easier to maintain and extend.
- **Class Hierarchy**: Inheritance allows for the creation of a class hierarchy, which can be used to model real-world objects and their relationships.
- **Polymorphism**: Inheritance allows for polymorphism, which is the ability of an object to take on multiple forms. Subclasses can override the methods of the superclass, which allows them to change their behavior in different ways.

### Disadvantages of Inheritance in Java
- **Complexity**: Inheritance can make the code more complex and harder to understand. This is especially true if the inheritance hierarchy is deep or if multiple inheritances is used.
- **Tight Coupling**: Inheritance creates a tight coupling between the superclass and subclass, making it difficult to make changes to the superclass without affecting the subclass.

> ❓: Why **multiple inheritance** is not supported in Java?

▶ To reduce the complexity and simplify the language, multiple inheritance is not supported in Java.

Consider a scenario where A, B and C are three classes. The C class inherits A and B classes. If A and B classes have same method and you call it from child class object, there will be ambiguity to call method of A or B class.
Since compile time errors are better than runtime errors, Java renders compile time error if you inherit 2 classes. so whether you have same method or different, there will be compile time error now.

## 41. Polymorphism  (Method Overriding - Runtime Polymorphism)
Polymorphism means "**many forms**", and it occurs when we have many classes that are related to each other by inheritance.

It works hand-in-hand with inheritance:
- Inheritance lets one class derive attributes & methods from another.
- Polymorphism lets those methods perform differently for different subclasses.

**Inheritance** lets us inherit attributes and methods from another class. **Polymorphism** uses those methods to perform different tasks. This allows us to perform a single action in different ways.

**Why And When To Use "Inheritance" and "Polymorphism"?**
✨ It is useful for code reusability: reuse attributes and methods of an existing class when you create a new class.

![polymorphism](./resources/polymorphism_in_java.png)

### Types of Polymorphism
Polymorphism in Java is mainly of 2 types as mentioned below: 
1. **Method Overloading**: Also, known as compile-time polymorphism, is the concept of Polymorphism where more than one method share the same name with different signature(Parameters) in a class. The return type of these methods can or cannot be same.

2. **Method Overriding**: Also, known as run-time polymorphism, is the concept of Polymorphism where method in the child class has the same name, return-type and parameters as in parent class. The child class provides the implementation in the method already written.

Below is the implementation of both the concepts:
```java
// Parent Class
class Parent {
    // Overloaded method (compile-time polymorphism)
    public void func() {
        System.out.println("Parent.func()");
    }

    // Overloaded method (same name, different parameter)
    public void func(int a) {
        System.out.println("Parent.func(int): " + a);
    }
}

// Child Class
class Child extends Parent {
    // Overrides Parent.func(int) — runtime polymorphism
    @Override
    public void func(int a) {
        System.out.println("Child.func(int): " + a);
    }
}

public class Main {
    public static void main(String[] args) {
        Parent parent = new Parent();
        Child child = new Child();
        Parent polymorphicObj = new Child();  // Upcasting

        // Method Overloading (compile-time)
        parent.func();        // Parent.func()
        parent.func(10);      // Parent.func(int): 10

        // Method Overriding (runtime)
        child.func(20);       // Child.func(int): 20

        // Polymorphism in action (runtime binding)
        polymorphicObj.func(30);  // Child.func(int): 30
    }
}
```
Output:
```
Parent.func()
Parent.func(int): 10
Child.func(int): 20
Child.func(int): 30
```

> Runtime Polymorphism (achieved by method overriding) or **'Dynamic Method Dispatch'** is a process in which a call to an overriden method is resolved at runtime rather than compile-time.
In this process, an overriden method is called through the reference variable of a superclass. The determination of the method to be called is based on the object being referred to by the reference variable.

| Type                          | Timing          | Achieved By        | Example                                    |
| ----------------------------- | --------------- | ------------------ | ------------------------------------------ |
| **Compile-time Polymorphism** | At compile time | Method Overloading | Same method name, different parameter list |
| **Runtime Polymorphism**      | At runtime      | Method Overriding  | Subclass redefines parent method           |

### Method Overriding - Runtime Polymorphism
If we have two methods both in parent & child class of same name, second method is overridden. This is called **Method Overriding**.

- Even if we use upcasting, same name functions will be overrided. (cz the display() of `abc` class doesn't exist now).
- Works during runtime via dynamic method dispatch.
- The object type, not the reference type, determines which method runs.
- Static methods cannot be overridden — only hidden.
- Data members can't be overriden.
```java
class abc{
    int a =10;
}
class xyz extends abc{
    int a =20;
}
class mno{
    public static void main(String[] args) {
        abc a1 = new xyz(); // upcasting
        System.out.println(a1.a); // prints 10
    }
}
```
✅ **Explanation**: Variables depend on reference type, not object type.

> ⚙️ **Static Methods Are Not Overridden**
They are bound at **compile time**.
Defining another static method in a subclass **hides** the parent method.

#### Rules for Java Method Overriding
1. Same method **name and parameter list**.
2. Must exist an **IS-A relationship** (inheritance).
3. Return type must be the **same or covariant** (a subclass of parent return type).
4. Static and private methods **cannot be overridden**.
5. Constructors are **not inherited**, hence cannot be overridden.

> 📝: In Java, we can't inherit multiple classes because **Java doesn't support multiple inheritance**.

-  picks which method to run at run time, based on the actual object type, not just the reference variable type.
- The `@Override` annotation catches mistakes like typos in method names.

#### Usage of Java Method Overriding
- Method overriding is used to provide a specific implementation of a method in a subclass that differs from the implementation in the superclass.
- Method overriding is used to achieve **runtime polymorphism**.

> 📝: Method overriding is not allowed in Java if the method in the child class has a different return type from the method in the parent class.

```java
class Animal {
    void move() {
        System.out.println("Animal is moving.");
    }
    void eat() {
        System.out.println("Animal is eating.");
    }
}

class Dog extends Animal {
    @Override
    void move() { // overridden method
        System.out.println("Dog is running.");
    }
    void bark() {
        System.out.println("Dog is barking.");
    }
}

public class Geeks {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.move();  // calls overridden move()
        d.eat();   // calls inherited method
        d.bark();  // own method
    }
}
```
Output:
```
Dog is running.
Animal is eating.
Dog is barking.
```
**Explanation**: 
- `move()` is overridden in `Dog`.
- `eat()` is inherited unchanged.
- `bark()` is Dog’s own method.

The Animal class defines base functionalities like move() and eat(). The Dog class inherits from Animal and overrides the move() method to provide a specific behavior Dog is running. Both classes can access their own methods. When creating a Dog object, calling move() executes the overridden method.

![method_overriding](./resources/Overriding-in-Java.png)

> 📝: Constructors are not member methods, and so are not inherited by subclasses. However, the constructor of the superclass is called when the subclass is instantiated.

They’re not methods; but a subclass must call a superclass constructor (implicitly or explicitly).
```java
class ABC{
    int a, b;
    ABC(int a, int b){
        this.a = a;
        this.b = b;
    }
    int sum(){
        return a + b;
    }
}
class XYZ extends ABC{
    XYZ(int a, int b){
        super(a, b); // calls parent constructor
    }
}
class mno{
    public static void main(){
        XYZ x1 = new XYZ(10, 20);
        System.out.println(x1.sum()); // Output: 30
    }
}
```

💡 **Accessing Parent Class Members**
We can also access member function or variables of parent class using `super` keyword.
```java
super.display(); // Calls parent class method
super();         // Calls parent class constructor
```

### Special Cases in Overriding
**1. Calling Parent Method Using super**

The `super` keyword can invoke the parent class method from the overriding method.

**2. Final Methods Cannot Be Overridden**

If we don't want a method to be overridden, we declare it as `final`.

**3. Static Methods**
- Static methods cannot be overridden; defining a static method in a subclass with the same signature as in the superclass hides the superclass method.
- Instance methods can be overridden, but a subclass cannot override a superclass static method.
- A static method in a subclass with the same signature as a superclass static method hides the original method.

**4. Private Methods**
- Private methods cannot be overridden because they are not visible to subclasses.
- A subclass method with the same name is treated as a new, independent method, unrelated to the parent class.

**5. Covariant Return Types**
- In method overriding, the return type of the overriding method can be a subclass of the return type of the overridden method.
- This feature is known as covariant return type and allows more specific return types in the subclass.

| Case                       | Description                                                           |
| -------------------------- | --------------------------------------------------------------------- |
| **`super` keyword**        | Used to call parent method or constructor.                            |
| **`final` methods**        | Cannot be overridden.                                                 |
| **Static methods**         | Cannot be overridden; only hidden.                                    |
| **Private methods**        | Not visible to child classes, hence not overridden.                   |
| **Covariant return types** | Overriding method can return a subclass type of parent’s return type. |


### Why Do We Use Method Overriding?
- To change or enhance the behavior of an existing method in a subclass.
- To achieve runtime polymorphism — method calls depend on the actual object type.
- To reuse method names logically, reducing redundancy.

📋 **Summary : Overloading vs Overriding in Java**

| Concept                | Compile-time / Runtime            | Description                                                                                                                 | Example                                                           |
| ---------------------- | --------------------------------- | --------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Method Overloading** | **Compile-time**                  | Same method name but **different parameter lists** (type, number, or order). Determined at compile time.                    | `void show(int a)` and `void show(String b)`                      |
| **Method Overriding**  | **Runtime**                       | Subclass redefines a **method with the same signature** as in parent class. Decided by **object type**, not reference type. | `class A { void display() } class B extends A { void display() }` |
| **Data Members**       | **Compile-time (not overridden)** | Variables are **not polymorphic**. Access depends on **reference type**, not object type.                                   | `A obj = new B(); System.out.println(obj.x);` — uses `A`’s `x`    |
| **Static Methods**     | **Compile-time (hidden)**         | Can’t be overridden; they are **method-hidden**, chosen based on reference type.                                            | `A.show()` vs `B.show()`                                          |
| **Private Methods**    | **Compile-time (inaccessible)**   | Not inherited, hence can’t be overridden. Subclass may define a method with same name, but it’s **completely separate**.    | `private void display()` in both parent and child are unrelated   |

- **Overloading** = compile-time polymorphism (method signature differs).
- **Overriding** = runtime polymorphism (method signature same, object differs).

> If you overload static method in Java, it is the example of **compile-time polymorphism**.

> Java doesn't support **multiple inheritance** due to the ambiguity (data loss).
To reduce the complexity and simplify the language, multiple inheritance is not supported in Java.

## 42. `super` keyword
The `super` keyword in java is a reference variable which is used to refer immediate parent class object. Whenever you create the instance of subclass, an instance of parent class is created implicitly which is referred by `super` reference variable.

It helps access **parent class members** (variables, methods, constructors) that are **hidden or overridden** by the child class.

### Usage of `super` keyword
1. `super` can be used to refer immediate parent class instance variable.
2. `super` can be used to invoke immediate parent class method. (it is used if function is overriden.)
3. `super()` can be used to invoke immediate parent class constructor.

| Purpose                                 | Description                                                                   | Example                                            |
| --------------------------------------- | ----------------------------------------------------------------------------- | -------------------------------------------------- |
| 1️⃣ Access parent class **variables**   | When a subclass has a variable with the same name as the parent class         | `super.variableName`                               |
| 2️⃣ Call parent class **methods**       | When the subclass overrides a method but still wants to call parent’s version | `super.methodName()`                               |
| 3️⃣ Invoke parent class **constructor** | To initialize parent class fields before executing subclass constructor       | `super()` (must be first statement in constructor) |

> `super()` is added in each class constructor automatically by compiler if there is no `super()` or `this()`.

![super](./resources/super.png)

> 📝: The call to super() must be the **first statement** in the subclass constructor.

As we know well that default constructor is provided by compiler automatically if there is no constructor. But, it also adds `super()` as the first statement.

### **Rules of `super`**

1. `super()` must be **the first statement** in a constructor.
2. You **cannot** use both `this()` and `super()` in the same constructor.
3. `super` is **used only within a subclass constructor or method**.
4. If you don’t call `super()` explicitly, Java automatically calls the **no-argument constructor** of the parent class.

⚙️ Difference Between `this` and `super`
| Feature          | `this`                                  | `super`                           |
| ---------------- | --------------------------------------- | --------------------------------- |
| Refers to        | Current class instance                  | Immediate parent class instance   |
| Access           | Current class members                   | Parent class members              |
| Constructor call | Calls another constructor of same class | Calls constructor of parent class |
| Usage location   | Within the same class                   | Inside subclass only              |

> 📝: `super` improves clarity in inheritance, avoids ambiguity, and supports **constructor chaining** — a core part of OOP design.

## 43. Abstraction
Abstraction in Java is the process of hiding internal implementation details and showing only essential functionality to the user. It focuses on what an object does rather than how it does it.

- Abstraction hides the complex details and shows only essential features.
- Abstract classes may have methods without implementation and must be implemented by subclasses.
- By abstracting functionality, changes in the implementation do not affect the code that depends on the abstraction.

The `abstract` keyword is a non-access modifier, used for classes and methods:
1. **Abstract class**: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- A class that is declared with `abstract` keyword, is known as **abstract class** in Java. It can have abstract and non-abstract methods (methods with body).
- It needs to be extended and its method implemented. It cannot be instantiated.

2. **Abstract method**: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).
- A method that is declared as `abstract` and does not have implementation is known as abstract method.
- Syntax:
    ```java
    abstract void methodName(); // no body in abstract method
    ```

### How to Achieve Abstraction in Java?
Java provides two ways to implement abstraction, which are listed below:
- Abstract Classes (Partial Abstraction)
- Interface (100% Abstraction)

```java
abstract class XYZ{
    abstract void display();
    void disp(){
        System.out.println("Hello");
    }
}
class mno exteds XYZ{
    void display(){ // here abstract method of XYZ is extended so that mno class won't become abstract
        System.out.println("Hi");
    }
    public static void main(String... args){
        XYZ x1 = new mno(); // object of child class mno as we can't initialize object of abstract class
        x1.display(); // x1 is reference of class XYZ
        x1.disp();
    }
}
```
- **Rule 1:** If there is any abstract method in a class, the class must be declared as abstract.
- **Rule 2:** If you are extending any abstract class that have abstract method, you must either provide the implementation of the method or make the class abstract.

### Key Features of Abstraction
1. An abstract class has no use until unless it is extended by some other class.
2. If you declare an abstract method in a class then you must declare the class abstract as well. You can't have abstract method in a concrete class. Its vice versa is not always true: If a class is not having any abstract method then also it can be marked as abstract.
3. Abstract method has no body.
4. It must be overidden. An abstract class must be extended and in a same way abstract method must be overriden.
5. The class which is extending abstract class must override all the abstract methods.

> **Defining `main()` in an abstract class :**
```java
abstract class abc{
    public static void main(String... args){
        System.out.println("Hello");
    }
}
```
`main()` isn't called by an object nor we can define its object. Therefore, adhering the property of abstract class. As abstract class cannot be instantiated.

### Advantages of Abstraction
- Abstraction makes complex systems easier to understand by hiding the implementation details.
- Abstraction keeps different part of the system separated.
- Abstraction maintains code more efficiently.
- Abstraction increases the security by only showing the necessary details to the user.

### Disadvantages of Abstraction
- It can add unnecessary complexity if overused.
- May reduce flexibility in implementation.
- Makes debugging and understanding the system harder for unfamiliar users.
- Overhead from abstraction layers can affect performance.

### Common Mistakes to Avoid
The common mistakes that can occur and we should avoid when working with Abstraction in Java are listed below:

- **Not Implementing Abstract Methods**: Always make sure that the abstract methods are implemented in the concrete subclass.
- **Overusing Abstraction**: Avoid making everything abstract when it’s not required. Use abstraction only when it enhances the design.
- **Inconsistent Method Signatures in Subclasses**: When you override abstract methods, please make sure the method signature matches exactly, any mistake can cause errors.

❓ **Why And When To Use Abstract Classes and Methods?**
▶ To achieve security - hide certain details and only show the important details of an object.

❓ **Why can't we create the object of abstract class?**
▶ Because these classes are incomplete, they have abstract methods that have no body so if Java allows you to create object of this class then if someone calls the abstract method using that object then *what* would happen? There would be no actual implementation of the method to invoke. Also, becuase an object is concrete. An abstract class is like a template, so you have to extend it and build on it before you can use it.

🧩 **Analogy**: Think of an abstract class as an **architectural plan** - you can’t live in a plan; you can only live in a **house built from that plan**.
Similarly, you can only create an object from a **concrete subclass**, not from the abstract class itself.

⚠️ **Common Misconceptions about Abstract Classes**
| ❓ **Misconception**                                                | ✅ **Clarification / Truth**                                                                                                                                                                                                         |
| ------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1. Abstract classes cannot have constructors.**                  | ❌ False. Abstract classes **can have constructors**, and they are often used to **initialize common fields** when a subclass object is created. The constructor of an abstract class is called **when a subclass is instantiated**. |
| **2. All methods in an abstract class must be abstract.**          | ❌ False. An abstract class can have **both abstract and non-abstract (concrete)** methods. This allows defining **shared functionality** along with **enforced structure**.                                                         |
| **3. Abstract classes cannot have variables or data members.**     | ❌ False. They can have **instance variables**, **static variables**, and **final variables** — just like any other class.                                                                                                           |
| **4. Abstract classes cannot extend other classes.**               | ❌ False. An abstract class **can extend** another **abstract or concrete** class and **can also implement interfaces**.                                                                                                             |
| **5. You cannot create references of an abstract class.**          | ❌ False. You **can declare a reference variable** of an abstract class type — you just **cannot instantiate** it directly. This is essential for **polymorphism**.                                                                  |
| **6. Abstract classes must contain at least one abstract method.** | ❌ False. A class can be declared abstract **even without any abstract methods**, often used to **prevent direct instantiation**.                                                                                                    |
| **7. Abstract classes are the same as interfaces.**                | ❌ False. Abstract classes can have **state (fields)** and **implemented methods**, while interfaces define **pure contracts** (methods without state).                                                                              |

> Abstract classes act as **partially implemented blueprints**, combining both concrete behavior and abstract structure - bridging the gap between a simple class and a pure interface.



## 44. Anonymous Class
It is an inner class without a name and for which only a single object is created.

It should be used if you have to override method of class or interface.
Java Anonymous inner class can be created by two ways:
- Class (may be abstract or concrete)
- Interface

An **anonymous class** in Java is a **local inner class without a name**, used to create a **one-time object** with a custom implementation.
It is typically used when you need to **override a method** of a class or interface without formally declaring a subclass.

### Internal working of Anonymous Class
✅ **Key Features**

- Declared and instantiated **at the same time**.
- Has **no name** (defined within an expression).
- Used when a **single instance** of a class is required.
- Commonly used in **GUI applications**, **event handling**, and **thread creation**.

### **Syntax**
The syntax of an anonymous class expression is like the invocation of a constructor, except that there is a class definition contained in a block of code. 
```java
ParentType ref = new ParentType() {
    // body of anonymous class
    @Override
    public void someMethod() {
        // overridden method logic
    }
};
```

### Difference between regular class(normal classes) and Anonymous Inner class

- A normal class can implement any number of interfaces but the anonymous inner class can implement only one interface at a time.
- A regular class can extend a class and implement any number of interfaces simultaneously. But anonymous Inner class can extend a class or can implement an interface but not both at a time.
- For regular/normal class, we can write any number of constructors but we can't write any constructor for anonymous Inner class because the anonymous class does not have any name and while defining constructor class name and constructor name must be same.

### **Internal Working of Anonymous Class**

1. The compiler **creates a separate class file** (e.g., `Main$1.class`) for the anonymous class.
2. This class **extends** the given superclass (or **implements** the given interface).
3. The object of this compiler-generated class is **assigned** to the reference variable.

```java
abstract class pqr{
    abstract void di();
}
abstract class XYZ {
    abstract void display();
    void disp(){
        System.out.println("Hello");
    }
}
class mno {
    public static void main(String... args){
        XYZ x1 = new XYZ() { // anonymous class
            void display(){
                System.out.println("Hi");
            }
        }
        x1.display();

        pqr p1 = new pqr(){
            void di(){
                System.out.println("Hey");
            }
        };
        p1.di();
    }
}
```
- A class is created but its name is decided by the compiler which extends the `XYZ` class and provides the implementation of the `display()` method.
- An object of **Anonymous class** is created that is referred by `x1` reference variable of `XYZ` type.

### When to Use Anonymous Classes?
Use anonymous classes when:
- You need a **one-time** subclass or interface implementation.
- You want to **override methods quickly** without defining a new named class.
- You’re writing **short, localized behavior**, especially:

  - Event listeners (`ActionListener`, `MouseListener`)
  - Runnable threads
  - Callback implementations

**Example 1 – Anonymous Class Extending an Abstract Class**
```java
abstract class XYZ {
    abstract void display();
    void disp() {
        System.out.println("Hello from XYZ");
    }
}

public class Demo {
    public static void main(String[] args) {
        XYZ obj = new XYZ() { // Anonymous inner class
            void display() {
                System.out.println("Hi from Anonymous Class");
            }
        };
        obj.display();  // calls overridden method
        obj.disp();     // inherited method
    }
}
```

**Output:**
```
Hi from Anonymous Class
Hello from XYZ
```

---
**Example 2 – Anonymous Class Implementing an Interface**
```java
interface Greet {
    void sayHello();
}

public class Main {
    public static void main(String[] args) {
        Greet g = new Greet() {
            public void sayHello() {
                System.out.println("Hello, World!");
            }
        };
        g.sayHello();
    }
}
```

**Output:**
```
Hello, World!
```

---
**Example 3 – Anonymous Class with a Concrete Class**
```java
class Parent {
    void show() {
        System.out.println("Parent show()");
    }
}

public class Test {
    public static void main(String[] args) {
        Parent p = new Parent() {
            void show() {
                System.out.println("Overridden show() in Anonymous class");
            }
        };
        p.show();
    }
}
```

**Output:**
```
Overridden show() in Anonymous class
```
Use anonymous classes when you need to create a short class for one-time use. For example:
- Overriding a method without creating a new subclass
- Implementing an interface quickly
- Passing small pieces of behavior as objects

### **Rules and Limitations**

1. Anonymous classes **cannot have constructors** (since they don’t have a name).
2. They can **access final or effectively final variables** from the enclosing scope.
3. They **cannot define static members** (except static final constants).
4. **Only one anonymous class** can be created per expression.

---

### Advantages
- Concise and clean syntax for one-time subclasses.
- Reduces boilerplate code.
- Improves readability for short-lived logic.

### Disadvantages
- Cannot be reused elsewhere.
- Harder to debug due to lack of name.
- Makes the code less readable if overused.

---

### Real-World Example: Runnable Thread

```java
public class ThreadDemo {
    public static void main(String[] args) {
        Thread t = new Thread(new Runnable() {
            public void run() {
                System.out.println("Thread running via anonymous class");
            }
        });
        t.start();
    }
}
```

**Output:**

```
Thread running via anonymous class
```

| Use Case                  | Extends / Implements | Purpose                         | Can Have Constructor? | Example Use Case               |
| ------------------------- | -------------------- | ------------------------------- | --------------------- | ------------------------------ |
| Abstract / Concrete Class | `extends`            | To override a method            | ❌ No                  | Custom subclass for 1-time use |
| Interface                 | `implements`         | To provide quick implementation | ❌ No                  | Runnable, ActionListener etc.  |

---

**In short:**
> An *anonymous class* is perfect when you need a **one-off** subclass or interface implementation that won’t be reused — clean, quick, and concise. 

## 45. Encapsulation
Encapsulation is defined as the **process of wrapping data (variables) and the methods into a single unit**, typically a **class**. It is the mechanism that binds together the code and the data. It manipulates. Another way to think about encapsulation is that it is a protective shield that prevents the data from being accessed by the code outside this shield. 

- Technically, in encapsulation, the variables or the data in a class is hidden from any other class and can be accessed only through any member function of the class in which they are declared.
- In encapsulation, the data in a class is hidden from other classes, which is similar to what data-hiding does. So, the terms "encapsulation" and "data-hiding" are used interchangeably.
- Encapsulation can be achieved by declaring all the variables in a class as private and writing public methods in the class to set and get the values of the variables.

![Encapsulation](/resources/Encapsulation.png)

### Implementation of Encapsulation in Java
- **Declare data as private**: Hide the class data so it cannot be accessed directly from outside the class.
- **Use getters and setters**: Keep variables private and provide public getter and setter methods for controlled access and safe modification, often with validation.
- **Apply proper access modifiers**: Use private for data hiding and public for methods that provide access.

### Best Practices for Encapsulation
- Always give the most restrictive access level that still allows the code to work. This helps hide implementation details and reduces coupling.
- Expose data through methods (getters/setters) rather than making fields public. This gives more control (validation, lazy initialization, invariants, etc.).
- Use validation logic inside setters to ensure correct data.
- Avoid unnecessary setters if data should not be modified externally (e.g., IDs).

### Advantages of Encapsulation
- **Data Hiding**: Encapsulation restricts direct access to class variables, protecting sensitive data from unauthorized access.
- **Improved Maintainability**: Changes to internal implementation can be made without affecting external code that uses the class.
- **Enhanced Security**: Encapsulation allows validation and control over data, preventing invalid or harmful values from being set.
- **Code Reusability**: Encapsulated classes can be reused in different programs without exposing internal logic.
- **Better Modularity**: Encapsulation promotes organized, modular code by keeping data and methods together within a class.

### Disadvantages of Encapsulation
- **Increased Code Complexity**: Writing getter and setter methods for every variable can make the code longer and slightly more complex.
- **Performance Overhead**: Accessing data through methods instead of directly can introduce a minor performance cost, especially in performance-critical applications.
- **Less Flexibility in Some Cases**: Over-restricting access to class members may limit the ability of other classes to extend or use the class efficiently.

### Why Encapsulation?
- Better control of class attributes and methods
- Class attributes can be made **read-only** (if you only use the `get` method), or **write-only** (if you only use the `set` method)
- Flexible: the programmer can change one part of the code without affecting other parts
- Increased security of data

## 46. Interface
- Like a class, an interface can have methods and variables, but the methods declared in interface are by default abstract (only method signature, no today).
- The members of an interface are `public`, `static` and `final` by nature.
- Java Interface also represents **IS-A** relationship.

```java
// Declaring an interface using the 'interface' keyword
interface abc{ 
    int a = 10; // 'a' is public, static, and final by default (constant)

    void display(); // Abstract method (no body) – implicitly public and abstract
}

// Class 'xyz' implements interface 'abc'
class xyz implements abc{

    // Must provide implementation for all abstract methods in the interface
    public void display(){
        System.out.println("hello");
    }

    public static void main(String... args){
        // Reference of interface type, object of implementing class
        abc a1 = new xyz();

        a1.display(); // Calls overridden display() method

        // a1.a = 20; // ❌ Error: Cannot modify 'a' because it’s final (constant)
        
        // Accessing interface variable using interface name (recommended way)
        System.out.println(abc.a); // ✅ Output: 10
    }
}
```
- A class that implements interface must implement all the methods declared in the interface. To implement interface use `implements` keyword.
- Since Java doesn't support multiple inheritance in case of class, but by using interface it can achieve multiple inheritance.
- Interface are used to implement **abstraction**.

❓ **Why use interfaces when we have abstract class?**
▶ The reason is, abstract classes may contain non-final variables, whereas variables in interface are `final`, `public` and `static`.

### Important points about Interface
- We can't create instance (interface can't be instantiated) of interface but we can make reference of it that refers to the object of its implementing class.
- A class can **implement** more than one interface.
    ![class_implement](/resources/class_interface.png)

- An interface can **extend** another interface or interfaces (more than one interface).
    ![interface_extends](/resources/interface_extend.png)

- A class that implements interface must implement all the methods in interface.
- All the methods are `public` and `abstract`. And all the fields are `public`, `static` and `final`.
- It is used to achieve **multiple inheritance**.

```java
// Declaring an interface 'Bank'
interface Bank{
    int a = 10; // Interface variable — public, static, and final by default

    int getInterest(); // Abstract method — must be implemented by any class that implements this interface
}

// SBI class implements Bank interface and provides its own implementation
class SBI implements Bank{
    public int getInterest(){
        return 9;  // SBI offers 9% interest
    }
}

// PNB class implements Bank interface and provides its own implementation
class PNB implements Bank{
    public int getInterest(){
        return 7; // PNB offers 7% interest
    }
}
class xyz {
    public static void main(String... args){
         // Creating a reference variable of type Bank (interface)
        Bank b = new PNB();  // Object of PNB assigned to Bank reference

        // Calls PNB's implementation of getInterest()
        System.out.println(b.getInterest());  // Output: 7

        // Reassigning same reference variable to SBI object
        b = new SBI();

        // Calls SBI's implementation of getInterest()
        System.out.println(b.getInterest());  // Output: 9
    }
}
```
**How It Works :**
- `interface Bank` defines a **contract** — any class implementing it **must** define `getInterest()`.
- Both `SBI` and `PNB` **implement** the same interface, providing their own method logic.
- The reference `Bank b` can hold an object of any class that implements `Bank` → demonstrating **runtime polymorphism**.
- The method executed depends on the **actual object type** (`SBI` or `PNB`), not the reference type (`Bank`).
---

- Interfaces specify what a class must do and not how. It is the **blueprint of the class**.
- An Interface is about capabilities like a `Bank` may be an interface and any class implementing `Bank` must be able to (or must implement) `getInterest()`. So it specifies a set of methods that the class has to implement.
- If a class implements an interface and does not provide method bodies for all functions specified in the interface, then class must be declared `abstract`.
- We have to override all the members of an Interface.

### Why And When To Use Interfaces?
1) To achieve security - hide certain details and only show the important details of an object (interface).

2) Java does not support "multiple inheritance" (a class can only inherit from one superclass). However, it can be achieved with interfaces, because the class can implement multiple interfaces. Note: To implement multiple interfaces, separate them with a comma (see example below).
---
**Notes**:
- Private methods can only be called inside default or static methods.
- Static methods are accessed using the interface name, not via objects.
- To implement an interface, use the implements keyword.
- Interfaces define **what** a class should do, not **how** it should do it.
- All variables in interfaces are constants (`public static final`).
- All methods are **public and abstract** by default (till Java 7).
- A class **implements** an interface, not extends it.
- You can **implement multiple interfaces**, achieving multiple inheritance in Java.

### Relationship Between Class and Interface
A class can extend another class and similarly, an interface can extend another interface. However, only a class can implement an interface and the reverse (an interface implementing a class) is not allowed.

![class-interface](./resources/Interfaces.png)

### When to Use Class and Interface?
**Use a Class when:**
- Use a class when you need to represent a real-world entity with attributes (fields) and behaviors (methods).
- Use a class when you need to create objects that hold state and perform actions
- Classes are used for defining templates for objects with specific functionality and properties.

**Use a Interface when:**
- Use an interface when you need to define a contract for behavior that multiple classes can implement.
- Interface is ideal for achieving abstraction and multiple inheritance.

> **Implementation**: To implement an interface, we use the keyword `implements`

### Multiple Inheritance in Java Using Interface
Java does not support multiple inheritance with classes to avoid ambiguity, but it supports multiple inheritance using interfaces.

![multiple_inheritance](./resources/MutlipleInheritance_Interface.png)

```java
import java.io.*;

// Add interface
interface Add{
    int add(int a,int b);
}

// Sub interface
interface Sub{
  	int sub(int a,int b);
}

// Calculator class implementing Add and Sub 
class Cal implements Add , Sub
{
  	// Method to add two numbers
  	public int add(int a,int b){
      	return a+b;
    }
  
  	// Method to sub two numbers
  	public int sub(int a,int b){
    	return a-b;
    }
}
class GFG{
    // Main Method
    public static void main (String[] args){
        
      	// instance of Cal class
      	Cal x = new Cal();
      	System.out.println("Addition : " + x.add(2,1));
      	System.out.println("Substraction : " + x.sub(2,1));
    }
}
```
Output:
```
Addition : 3
Substraction : 1
```

---
- Like **abstract classes**, interfaces **cannot** be used to create objects.
- Interface methods do not have a body - the body is provided by the "implement" class
- On implementation of an interface, you must override all of its methods
- Interface methods are by default `abstract` and `public`
- Interface attributes are by default `public`, `static` and `final`
- An interface cannot contain a constructor (as it cannot be used to create objects)

### JDK 8 New Features Added in Interfaces 
There are certain features added to Interfaces in JDK 8 update mentioned below:

1. **Default Methods**
- Interfaces can define methods with default implementations.
- Useful for adding new methods to interfaces without breaking existing implementations.

Prior to JDK 8, interface could not define implementation. We can now add default implementation for interface methods.
This default implementation has special use and does not affect the intention behind interfaces.

Suppose we need to add a new method in an existing interface. Obviously the old code will not work as the classes have not implemented those new functions. So with the help of default implementation, we will give a deafult body for the newly added functions. Then the old codes will still work.
```java
interface in1{
    final int a = 10;
    default void display() {
        System.out.println("hello");
    }
}
class testClass implements in1{
    public static vod main(String... args) {
        testClass t = new testClass();
        t.display();
    }
}
```

2. **Static Methods**
- Interfaces can now include static methods.
- These methods are called directly using the interface name and are not inherited by implementing classes.

Another feature that was added in JDK 8 is that we can now define static methods in interfaces that can be called independently without an object. 
> These methods are not inherited.
```java
interface in1{
    static void display(){
        System.out.println("Hello");
    }
}
class testClass implements in1 {
    public static void main(String... args){
        in1.display();
    }
}
```

> Due to a new upgrade in JDK 8, now we can declare a non-abstract method in an interface, using `default` keyword.

```java
// Define interface ABC with one abstract method
interface ABC {
    void display(); // implicitly public and abstract
}

// Another interface A with same method signature
interface A {
    void display(); // implicitly public and abstract
}

// Another interface B with same method signature
interface B {
    void display(); // implicitly public and abstract
}

// Interface C extends multiple interfaces (ABC, A, and B)
// Demonstrates multiple inheritance using interfaces
interface C extends ABC, A, B {
    void display(); // still abstract; all parent display() methods merge into one
}

class XYZ {
    public static void main(String... args) {

        // Anonymous class implementing interface C
        // Since C is an interface, we must provide implementation for display()
        C c1 = new C() {
            public void display() {
                System.out.println("Hello");
            }
        };

        // Call display() method from anonymous class
        c1.display(); // Output: Hello
    }
}
```
- Interfaces in Java can **extend multiple interfaces**, achieving multiple inheritance of type.
- When multiple parent interfaces define the **same method signature**, they are merged into one — no conflict occurs.
- You can’t instantiate an interface directly, but you can use an **anonymous class** to provide implementation on the spot.

> A class implements interface but one interface extends another interface.

3. **Functional Interface**
- Functional interfaces can be used with **lambda expressions** or **method references**.
- The @FunctionalInterface annotation can be used to indicate that an interface is a functional interface, although it’s optional.

```java
@FunctionalInterface
public interface Calculator {
    int compute(int x, int y); // single abstract method
}
```

###  JDK 9 New Features Added in Interfaces
From Java 9 onwards, interfaces can contain the following also:

**Private Methods**
- Interface can now include private methods.
- Private methods are defined within the interface but it cannot be accessed by the implementing classes.
- Private methods cannot be overridden by implementing classes as they are not inherited.

```java
interface Vehicle {
    // Private method for internal use
    private void startEngine() {
        System.out.println("Engine started.");
    }
    
    // Default method that uses the private method
    default void drive() {
         // Calls the private method
        startEngine(); 
        System.out.println("Vehicle is now driving.");
    }
}

class Car implements Vehicle {
    // Car class implements Vehicle interface and inherits the default method 'drive'
}

public class Main {
    public static void main(String[] args) {
        Car car = new Car();
        // This will call the default method, which in turn calls the private method
        car.drive();  
    }
}
```
Output
```
Engine started.
Vehicle is now driving.
```

### Extending Interfaces
One interface can inherit another by the use of keyword extends. When a class implements an interface that inherits another interface, it must provide an implementation for all methods required by the interface inheritance chain.

❓: **Multiple inheritance is not supported through class in Java but it is possible by interface, why?**
▶ Multiple inheritance is not supported in case of class because of ambiguity. But it is supported in case of interface because there is no ambiguity as implementation is provided by the implementation class.

```java
interface Printable{
    void print();
}
interface Showable{
    void print();
}

class TestInterface implements Printable, Showable{
    public void print(){
        System.out.println("hello");
    }
    public static void main(String... args){
        TestInterface obj = new TestInterface();
        obj.print();
    }
}
```
In the above example,`Printable` and `Showable` interface have same methods but its impleentation is provided by class `TestInterface`, so there is no ambiguity.

### Internal addition by Compiler
The Java compiler adds `public` and `abstract` keywords before the interface method.
More, it adds `public`, `static` and `final` keywords before data members.

In other words, Interface fields are `public`, `static` and `final` by default, and methods are **public** and **abstract**.

![interface](./resources/interface_compiler.png)

Although Class and Interface seem the same there are certain differences between Classes and Interface. The major differences between a class and an interface are mentioned below:

| **Feature**          | **Class**                                                            | **Interface**                                                                                                     |
| -------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Instantiation**    | You **can create objects** of a class (unless it’s abstract).        | You **cannot create objects** of an interface directly.                                                           |
| **Variables**        | Can have **instance, static, and final** variables.                  | All variables are **`public static final`** (constants only).                                                     |
| **Methods**          | Can have **concrete (defined)** and **abstract** methods.            | All methods are **abstract by default** (till Java 7). From Java 8+, can have **default** and **static** methods. |
| **Inheritance**      | Supports **single inheritance** (a class can extend only one class). | Supports **multiple inheritance** (a class can implement multiple interfaces).                                    |
| **Constructors**     | Can have **constructors** (for object initialization).               | **No constructors** allowed in interfaces.                                                                        |
| **Access Modifiers** | Can use **private, protected, public, or default** modifiers.        | All members are **`public` by default**.                                                                          |
| **Keyword**          | Declared using the `class` keyword.                                  | Declared using the `interface` keyword.                                                                           |
| **Default Methods**  | ❌ Does **not support** default methods.                              | ✅ Supports **default methods** (introduced in **JDK 8**).                                                         |
| **Static Methods**   | ✅ Can have **static methods**.                                       | ✅ Supports **static methods** (introduced in **JDK 8**).                                                          |
| **Private Methods**  | ✅ Can have **private methods**.                                      | ✅ Supports **private methods** (introduced in **JDK 9**).                                                         |
| **Main Method**      | ✅ Can have `main()` for execution.                                   | ✅ Can have `main()` (since **JDK 8**, via static methods).                                                        |

- A class defines both data and behavior - it’s a blueprint to create objects.
- An interface defines only behavior (method signatures) - it’s a contract that classes must follow.

## 47. Difference Between Abstract Class and Interface
| Feature              | Abstract Class                                                      | Interface                                                                                  |
| -------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
| **Keyword**          | `abstract`                                                          | `interface`                                                                                |
| **Method Type**      | Can have abstract **and** concrete methods                          | All methods are **abstract** (Java 7); can have **default** & **static** methods (Java 8+) |
| **Variables**        | Can have instance & static variables                                | All variables are `public static final` (constants)                                        |
| **Access Modifiers** | Methods can be `public`, `protected`, or `default`                  | All methods are implicitly `public`                                                        |
| **Inheritance Type** | Supports **single inheritance**                                     | Supports **multiple inheritance**                                                          |
| **When to Use**      | When you need to share **partial implementation** across subclasses | When you only need to define a **contract or capability**                                  |
| **Object Creation**  | Cannot be instantiated directly                                     | Cannot be instantiated directly                                                            |
| **Constructors**     | Can have constructors                                               | Cannot have constructors                                                                   |

- Use **abstract classes** when classes share common behavior.
- Use **interfaces** when unrelated classes must adhere to a common set of methods (e.g., `Comparable`, `Runnable`, `Cloneable`).

**Abstraction**: Hiding the internal implementation of the feature and only showing the functionality to the users, i.e., what it works(showing), how it works (hiding). Both abstract class and interface are used for abstraction.

###  When to use what?
🔸 **Abstract Class**
- In Java application, there are some related classes that need to share some lines of code then you can put these lines of code within abstract class and this abstract class should be extended by all these related classes.
- You can define non-static or non-final field(s) in abstract class, so that via a method you can access and modify the state of Object to which they belong.
- You can except that the classes that extend an abstract class have many common methods or fields, or require access modifiers other than **public** (such as protected and private).

🔸 **Interface**
- It is **total abstraction**, all methods declared within an interface must be implemented by the class(es) that implements this interface.
- A class can implement more than one interface. It is called **multiple inheritance**.
- You want to **specify the behaviour** of particular data type, but not concerned about who implements its behaviour.

---
🧩 Additional Points to Add

**1. Real-world Analogy**

> An **abstract class** is like a *partially built house*—some rooms (methods) are complete, some are just blueprints.
> An **interface** is like a *design contract*—it just specifies what rooms must exist, but not how they’re built.

**2. Java 8+ Enhancements in Interfaces**
Add a line under the table or in a note:

> Since **Java 8**, interfaces can have `default` and `static` methods; since **Java 9**, they can also include `private` methods — bringing them conceptually closer to abstract classes, though still without state or constructors.

**3. Implementation Relationship Summary**
```
Class → extends → Abstract Class
Class → implements → Interface
Interface → extends → Interface
```

**4. Key Differences Summary (Quick Glance)**

| Criteria             | Abstract Class                         | Interface                                   |
| -------------------- | -------------------------------------- | ------------------------------------------- |
| Nature               | Partial abstraction                    | Full abstraction                            |
| Code Reuse           | Allows code reuse via concrete methods | No code reuse (till Java 8 default methods) |
| Multiple Inheritance | Not allowed                            | Allowed                                     |
| Performance          | Slightly faster (less indirection)     | Slight overhead due to abstraction layer    |
| Usage                | Common behavior across related classes | Common capability across unrelated classes  |

## 48. Exception Handling
Exception is an event that disrupts the normal flow of the program.

It is one of the powerful **mechanism to handle the runtime errors** so that normal flow of the application can be maintained.

The core advantage of exception handling is **to amintain the normal flow of the application**. Exception normally disrupts the normal flow of the application that is why we use exception handling.

### Hierarchy of Java Exception Classes

![exception_hierarchy](/resources/exceptionHierarchy.png)

### Types of Exceptions
There are mainly two types of exceptions: **Checked** and **Unchecked**; where `error` is considered unchecked exception.
The SunMicrosystem says there are three types of exceptions:

1. Checked Exception ➡ **Compile Time**
The classes that extend `Throwable` class except `RuntimeException` and `Error` are known as **checked exception**. eg, `IOException`, `SQLException`, `ClassNotFoundException`.

2. Unchecked Exception ➡ **Run Time**
The classes that extend `RuntimeException` are known as **unchecked exceptions**. eg, `ArithemeticException`, `NullPointerException`, `ArrayIndexOutOfBoundsException`, etc.
Unchecked exceptions are not checked at compile-time rather they are checked at runtime.

3. `error`
Error is irrecoverable. eg, `OutOfMemoryError`, `VirtualMachineError`, `AssertionError`, etc.

**Runtime Exceptions**:
- `ArithmeticException`
- `ArrayIndexOutOfBoundsException`
- `StringIndexOutOfBoundsException`
- `ClassCastException`
- `NullPointerException`
- `NumberFormatException`

**Checked Exception**:
- `IOException`
- `FileNotFoundException`
- `ClassNotFoundException`
- `InterruptedException`

![exception_types](/resources/Exceptions-in-Java.png)

---
### Exception Handling Keywords
1. `try`
2. `catch`
3. `finally`
4. `throw`
5. `throws`

![exception_handling](/resources/exceptionHandling1.png)

![exception_handling](/resources/exceptionHandling2.png)

### `try-catch`
- `try` block is used to enclose code that might throw an exception. It must be used within the method.
- The `try` block must be followed by either `catch` or `finally` block.

```java
try {
    // code that might throw an exception
} catch (Exception e) {
    // handle the exception
} finally {
    // code that will be executed regardless of whether an exception occurred or not
}
```
If an error occurs, we can use `try...catch` to catch the error and execute some code to handle it:

```java
class A{
    public static void main(String... args){
        int a = 10;
        int b = 0;
        try{
            int c = a/b;
            System.out.println(c);
        } catch(ArithmeticException e){
            System.out.println(" Error: " + e.getMessage());
        }
    }
}
```
- The try block contains code that might throw an exception,
- The catch block handles the exception if it occurs.

#### Internal Working of try-catch Block:

- JVM executes code inside the try block.
- If an exception occurs, remaining try code is skipped and JVM searches for a matching catch block.
- If found, the catch block executes.
- Control then moves to the finally block (if present).
- If no matching catch is found, the exception is handled by JVM’s default handler.
- The finally block always executes, whether an exception occurs or not.

> 📝: When an exception occurs and is not handled, the program terminates abruptly and the code after it, will never execute.

![try-catch working](/resources/try-catch_working.png) 

The JVM firstly checks whether the exception is handled or not. If exception is not handled, JVM provides a default exception handler that performs the following tasks:
- Prints out exception description.
- Prints the stack trace (hierarchy of methods where the exception occurred).
- Causes the profram to terminate.

But if exception is handled by the application programmer, normal flow of the application is maintained, i.e., rest of the code is executed.

#### How to use command line arguments
```java
class A{
    public static void main(String... args){
        try{
            System.out.println(args[0]);
            System.out.println(args[1]);
            System.out.println(args[2]);
        } catch(ArrayIndexOutOfBoundsException e){
            System.out.println(" Error: " + e.getMessage());
        }
    }
}
```

> From JDK 7, we can use multiple exceptions in a `catch` block separated by `|` **OR** operator.
```java
catch(ArrayIndexOfBoundsException | ArithemeticException e){
    System.err.print("Exception occurred");
    // System.err.print("Exception occur " + e.toString());
}
```
- `catch` block is used to handle the exception. It must be used after the `try` block only.
- You can use multiple `catch` blocks with a single `try`.

```java
catch(Exception e) {
    e.printStackTrace();
}
```

```java
catch(Exception e){
    System.err.println("Exception occurred " + e);
}
```
`Exception` class consists of all the exceptions. So, instead of mentioning exceptions individually, just use class name.

#### Nested try-block
We can use method nested try-block. Sometimes a situation may arise where a part of a block may causeone error and the entire block itself may cause another error. In such cases, exception handlers have to be nested.

```java
try {
    try{
        int len = atgs.length;
        int b = 10/len;
    } catch (ArithmeticException e) {
        System.out.println(args[0]);
        System.out.println(args[1]);
        System.out.println(args[2]);
    }
} catch (Exception e){
    e.printStackTrace();
}
catch(Exception ee){

}
```
📝: At a time only one Exception is occurred and at a time only one catch block is executed.
📝: All `catch` blocks must be ordered from most specific to most general, i.e., `catch` for `ArithemeticException` must come before `catch` for Exception.

> 📝: We can't use child class exception below a top class ('Exception') exception.
```java
catch (Exception e){}
catch (ArithemeticException e){} // error
```

### `finally`
`finally` block is a block that is used to **exceute importent code** such as closing connection, stream.

- `finally` block is always executed, whether an exception occurs or not.
- `finally` block is used to release resources, such as closing a file or a database connection.
- `finally` block follows `try-catch` block.
```java
try{
    int len = 10;
    b = 40/len;
} catch(ArithmeticException e){
    System.err.println("Exception occur " + e);
}
finally{
    System.out.println("Exception occurred!!");
}
```

❓: **Why use `finally` block?**
▶ `finally` block in Java can be used to put 'cleanup' code such as closing a file, a database connection, etc. Finally block is always executed, whether an exception occurs or not.

> If you have to perform different tasks at the occurences of different Exceptions, use java mutli-catch blocks.

#### Internal working of finally block

![finally](/resources/finally_block.png)

> If you don'thandle exception, before terminating the program, JVM excutes finally block (if any).

📝: For each `try` block there can be zero or more `catch` blocks, but only one `finally` block.

> The `finally` block will not be executed if program exists (either by calling `System.exit()` or by causing a fatal error that causes the process to `abort()`). 

![final vs finally vs finalize](/resources/finalfinallyfinalize.png) 

### `throw`
`throw` is used to explicitly throw an exception. We can throw either checked or unchecked exception in java by throw keyword. The `throw` keyword is mainly used to throw custo exception.

**Syntax:** 

    throw exception;
**Example:**
```java 
throw new IOException("Sorry, device error!");
```    

```java
class A{
    public static void main(String... args){
        int a = 10;
        if(a > 0){
            throw new ArithmeticException("Invalid Number.");
        }
    }
}
```

### `throws`
`throws` used to declare an exception. It gives an **information to the programmer that there may occur an exception** so it is better for the programmer to provide the exception handling code so that normal flow can be maintained. 

Declares exceptions that a method might throw, informing the caller to handle them. It is mainly used with checked exceptions (explained below). If a method calls another method that throws a checked exception, and it doesn’t catch it, it must declare that exception in its `throws` clause

```java
import java.io.*;

class Demo {
    static void readFile(String fileName) throws IOException {   
        FileReader file = new FileReader(fileName);
    }

    public static void main(String[] args){
        try {
            readFile("test.txt");
        } catch (IOException e){
            
            System.out.println("File not found: " + e.getMessage());
        }
    }
}
```

❓: **Which exception should be declared?**
▶ Checked exception only, becuase:
- Unchecked Exception: under you control so correct your code.
- error: beyond your control. eg, you are unable to do anything if there occurs `VirtualMachineError` or `StackOverflowError`.

> 📝: If you're calling a method that declares an exception, you must either **caught**(handle exception using try-catch) or **declare**(specifying throws with method) the exception.

```java 
import java.io.*;

class A{
    // Checked Exception0
    public static void main(String... args) throws IOException{ 
        int a = 10;
        if(a > 0){
            throw new IOException("Invalid Number.");
        }
    }
}
```

### Custom Exceptions (User defined exceptions) : Checked
```java
class CustomException extends Exception{
    CustomException(String message){
        super(message);
    }
    class pqr{
        int getData(int a) throws Exception {
            int (a > 0) {
                throw new CustomException("Error!");
            }
            return a;
        }
    }
    class A{
        public static void main(String... args) throws Exception{
            pqr p = new pqr();
            System.out.println(p.getData(10));
        }
    }
}
```

### How Does JVM Handle an Exception?
When an Exception occurs, the JVM creates an exception object containing the error name, description and program state. Creating the exception object and handling it in the run-time system is called throwing an exception. There might be a list of the methods that had been called to get to the method where an exception occurred. This ordered list of methods is called call stack. Now the following procedure will happen:

- The run-time system searches the call stack for an exception handler
- It starts searching from the method where the exception occurred and proceeds backward through the call stack.
- If a handler is found, the exception is passed to it.
- If no handler is found, the default exception handler terminates the program and prints the stack trace.

        Exception in thread "abc" Name of Exception : Description
        // Call Stack

```java 
class abc{
    public static void main(String args[])
    {
        // Taking an empty string
        String s = null;
      
        // Getting length of a string
        System.out.println(s.length());
    }
}
```

## 49. Inner Classes (Nested Classes)

An **inner class** is a class **defined inside another class**.
It helps logically group classes that are only used in one place, improving **encapsulation and readability**.

**Syntax:**

```java
class Outer {
    class Inner {
        // Inner class body
    }
}
```
- Java inner class or nested class is a class which is declared inside the class or interface. 
- We use inner classes to logically group classes and interfaces in one place so that it can be more readable and maintainable.

```java
// Outer class A
class A {
    // Static nested class B (inner class inside class A)
    // Because it's static, it can be accessed without creating an object of A
    static class B {

        // Static variable inside nested class
        static int a = 10;
    }
}

// Separate class with main() method
class xyz {
    public static void main(String... args) {
        // Accessing static variable 'a' of static nested class B
        // Syntax: OuterClass.InnerClass.variable
        System.out.println(A.B.a);
    }
}
```
- Additionally, it can **access all the members of the outer class** including private data members and methods.
```java
// Outer class A
class A {

    // Non-static inner class B
    // This inner class can access ALL members of class A (including private)
    class B {
        int a;   // Instance variable inside inner class
    }
}

class xyz {
    public static void main(String... args) {
        // Creating object of outer class A
        A a1 = new A();

        // Creating object of inner class B using outer class instance
        // Syntax: outerObject.new InnerClass()
        A.B b1 = a1.new B();

        // Alternatively:
        // A.B b1 = new A().new B();

        // Assigning value to inner class variable
        b1.a = 10;

        // Printing value
        System.out.println(b1.a);
    }
}
```

> A ➡ B ➡ C
```java
A a1 = new A();
A.B b1 = a1.new B();
A.B.C c1 = b1.new C();
```

### **Types of Inner Classes in Java**

| Type                          | Defined As            | Can Access Outer Members?               | Static/Non-static | Typical Use Case                                            |
| ----------------------------- | --------------------- | --------------------------------------- | ----------------- | ----------------------------------------------------------- |
| **1. Non-static Inner Class** | Inside another class  | ✅ Yes (even private)                    | Non-static        | Helper classes tightly coupled to outer class               |
| **2. Static Nested Class**    | With `static` keyword | ❌ Only static members of outer class    | Static            | When inner class doesn’t need outer instance                |
| **3. Local Inner Class**      | Inside a method       | ✅ Yes (final or effectively final vars) | Non-static        | Used within a specific method only                          |
| **4. Anonymous Inner Class**  | No name               | ✅ Depends                               | Non-static        | For quick implementation (e.g., interfaces, event handlers) |

---

**1. Non-static Inner Class**
```java
class Outer {
    private String message = "Hello from Outer";

    class Inner {
        void display() {
            System.out.println(message); // can access private members
        }
    }
}
public class Test {
    public static void main(String[] args) {
        Outer outer = new Outer();
        Outer.Inner inner = outer.new Inner(); // creating inner class object
        inner.display();
    }
}
```
**Output:**
```
Hello from Outer
```
---
**2. Static Nested Class**
```java
class Outer {
    static int data = 50;
    static class Inner {
        void msg() {
            System.out.println("Data: " + data);
        }
    }
}
public class Test {
    public static void main(String[] args) {
        Outer.Inner obj = new Outer.Inner(); // no Outer object needed
        obj.msg();
    }
}
```
**Output:**
```
Data: 50
```
---

**3. Local Inner Class**
```java
class Outer {
    void outerMethod() {
        System.out.println("Inside outerMethod()");
        class LocalInner {
            void innerMethod() {
                System.out.println("Inside local inner class");
            }
        }
        LocalInner obj = new LocalInner();
        obj.innerMethod();
    }
}
public class Test {
    public static void main(String[] args) {
        new Outer().outerMethod();
    }
}
```
**Output:**
```
Inside outerMethod()
Inside local inner class
```
---
**4. Anonymous Inner Class**
Used when you need to override a method or implement an interface **once**.

```java
abstract class Animal {
    abstract void sound();
}
public class Test {
    public static void main(String[] args) {
        Animal dog = new Animal() {
            void sound() {
                System.out.println("Dog barks");
            }
        };
        dog.sound();
    }
}
```
**Output:**
```
Dog barks
```
---

| Concept                 | Description                                                          |
| ----------------------- | -------------------------------------------------------------------- |
| **Inner Class**         | A class defined within another class.                                |
| **Static Nested Class** | Does not require outer instance.                                     |
| **Local Inner Class**   | Defined within a method or block.                                    |
| **Anonymous Class**     | Declared and instantiated together.                                  |
| **Encapsulation**       | Inner classes can access outer private data, supporting data hiding. |

---
### **Advantage of Inner Class**

1. Nested classes represent a special type of relationship that is **it can access all the members (data members and methods) of outer class** including private.
2. Nested classes are used to develop more readable and maintainable code because it logically group classes and interfaces in one place only.
3. **Code Optimization**: It requires less code to write.

### **Real-World Example**

Inner classes are heavily used in:

- GUI event handling (`ActionListener`, `MouseAdapter`)
- Multithreading callbacks
- Encapsulating helper logic (e.g., `Map.Entry` inside `HashMap`)

---

### **Output Comparison**

| Inner Class Type | Needs Outer Object? | Has Name? | Common Use              |
| ---------------- | ------------------- | --------- | ----------------------- |
| Non-static       | ✅ Yes               | ✅ Yes     | Access outer members    |
| Static           | ❌ No                | ✅ Yes     | Independent logic       |
| Local            | ✅ Within method     | ✅ Yes     | Method-scoped logic     |
| Anonymous        | ✅ Yes               | ❌ No      | One-time implementation |

> Inner classes → connect one class logically inside another
  Together, they strengthen **encapsulation, hierarchy, and modularity** in OOP design.

## 50. File Handling
- File handling is an important part of any application.
- Java has several methods for creating, reading, updating, and deleting files.
- The `File` class from the `java.io` package, allows us to work with files.
- To use the File class, create an object of the class, and specify the filename or directory name:
```java
import java.io.File;  // Import the File class
File myObj = new File("filename.txt"); // Specify the filename
```

![file_handling](/resources/file_handling_in_java.png) 

- A stream is a sequence of data. In Java, a stream is composed of bytes.
- stream (bytecode) 
    - InputStream : **System.in**
    - Outputstream : **System.out** , **System.err**

![input_output_stream](/resources/input_output_stream.png)

![stream_hierarchy](/resources/stream_hierarchy.png) 

### Why File Handling is Required?
- To store data permanently instead of keeping it only in memory.
- To read and write data from/to files for later use.
- To share data between different programs or systems.
- To organize and manage large data efficiently.
- To support file handling, Java provides the `File` class in the `java.io` package.

### File Class
File class in Java (from the `java.io` package) is used to represent the name and path of a file or directory. It provides methods to create, delete, and get information about files and directories.
```java
// Importing File Class
import java.io.File;
class abc{
    public static void main(String[] args){      
        // File name specified
        File obj = new File("myfile.txt");
        System.out.println("File Created!");
    }
}
```
Output:
```
File Created!
```
In Java, I/O streams are used to perform input and output operations on files.

### I/O Streams in Java
In Java, I/O streams are the fundamental mechanism for handling input and output operations. They provide a uniform way to read data from various sources (files, network, memory) and write data to different destinations.

Java I/O streams are categorized into two main types based on the type of data they handle:

1. **Byte Streams**
In Java, Byte Streams are used to handle raw binary data such as images, audio files, videos or any non-text file. They work with data in the form of 8-bit bytes.

![Byte Stream](/resources/byte_streams.png) 

The two main abstract classes for byte streams are:

- InputStream: for reading data (input)
- OutputStream: for writing data (output)
Since abstract classes cannot be used directly, we use their implementation classes to perform actual I/O operations.

- FileInputStream: reads raw bytes from a file.
- FileOutputStream: writes raw bytes to a file.
- BufferedInputStream / BufferedOutputStream: use buffering for faster performance.
- ByteArrayInputStream: reads data from a byte array as if it were an input stream.
- ByteArrayOutputStream: writes data into a byte array, which grows automatically.

2. **Character Streams**

In Java, Character Streams are used to handle text data. They work with 16-bit Unicode characters, making them suitable for international text and language support.

![Character Stream](/resources/character_streams.png)

The two main abstract classes for character streams are:

- Reader: Base class for all character-based input streams (reading).
- Writer: Base class for all character-based output streams (writing).
Since abstract classes cannot be used directly, we use their implementation classes to perform actual I/O operations.

- FileReader: reads characters from a file.
- FileWriter: writes characters to a file.
- BufferedReader: reads text efficiently using buffering; also provides readLine() for reading lines.
- BufferedWriter: writes text efficiently using buffering.
- StringReader: reads characters from a string.
- StringWriter: writes characters into a string buffer.

> Use Byte Streams when working with binary data (images, audio, video, executable files) and use Character Streams when working with text data (characters, strings, text files).

- `File` class doesn't works on data, it only works on files.

```java
import java.io.File;
class A{
    public static void main(String... args){
        // File name specified
        File obj = new File("f://mm.txt");
        boolean b = obj.delete(); // returns true if the file is deleted
        System.out.println(b);
    }
}
```
- To make a directory `mkdir()` method is used.

```java
import java.io.*;
class A extends File{
    A(String path){
        super(path);
    }
    public static void main(String... args){
        for (int i = 0; i < 10; i++){
            A f = new A("f://mm/dir" + i); // code to create multiple directories in a directory named 'mm'
            f.delete();
        }
    }
}
```

```java
import java.io.*;
class A extends File{
    A(String path){
        super(path);
    }
    public static void main(String... args) throws Exception{
        A a1 = new A("f://mm/myfile.pdf");
        a1.createNewFile();
    }
}
```
- If a directory contains contents, it won't be deleted, first its contents (files/directories) must be deleted.

**Code to find all the files in a drive:**
```java
import java.io.*;
class A extends File{
    A(String path){
        super(path)
    }
    public static void main(String... args){
        A a1 = new A("f://");
        String arr[] = a1.list();
        for(String p: arr){
            System.out.println(p);
        }
    }
}
```

**Code to calculate free space in a drive:**
```java
A a1 = new A("C://");
double d = ((a1.getFreeSpace()/1024)/1024)/1024;
System.out.println(d);
```
> Function to get/calculate total space of a drive: `getTotalSpace()`.

## 51. File Class
The `File` Class is an abstract representation of file and directory pathname.
The **File** class have several methods for working with directories and files such as creating new directories or files, deleting and renaming directories or files etc.

A directory is a collection of files and subdirectories. A directory inside a directory is known as subdirectory.

```java
import java.io.File;  // Import the File class
File f = new File("E://abc.txt");
f.setWritable(false); // file can't be modified
```

> 📝: In Java, creating a file object does not mean creating a file. Instead, a file object is an abstract representation of the file or directory pathname (specified in the parenthesis).

### Java File Handling

#### **A) File Operations Overview**

These are the general *tasks* we perform with files.

| Operation               | Method            | Class        | Description                                         |
| ----------------------- | ----------------- | ------------ | --------------------------------------------------- |
| Create file             | `createNewFile()` | `File`       | Creates a new empty file if it doesn’t exist.       |
| Read file               | `read()`          | `FileReader` | Reads file data character-by-character.             |
| Write file              | `write()`         | `FileWriter` | Writes data into a file.                            |
| Delete file             | `delete()`        | `File`       | Deletes a file or empty directory.                  |
| Create directory        | `mkdir()`         | `File`       | Creates a single directory.                         |
| List directory contents | `list()`          | `File`       | Returns all files/subdirectories as a string array. |

---

#### **B) Java `File` Class Methods**

Below is a complete table of commonly used methods **inside `java.io.File`**.

| Method              | Description                                   |
| ------------------- | --------------------------------------------- |
| `getName()`         | Returns the name of file/directory.           |
| `getAbsolutePath()` | Returns the full absolute path.               |
| `canRead()`         | Checks if file is readable.                   |
| `canWrite()`        | Checks if file is writable.                   |
| `exists()`          | Returns true if file/directory exists.        |
| `isDirectory()`     | Checks if path refers to a directory.         |
| `isFile()`          | Checks if path refers to a regular file.      |
| `length()`          | Returns file size in bytes.                   |
| `createNewFile()`   | Creates a new empty file.                     |
| `delete()`          | Deletes file/directory (must be empty).       |
| `list()`            | Returns names of files/directories in folder. |
| `mkdir()`           | Creates a directory.                          |
| `mkdirs()`          | Creates directory including parent folders.   |
| `getFreeSpace()`    | Returns available disk space (bytes).         |
| `getTotalSpace()`   | Returns total disk space.                     |
| `getUsableSpace()`  | Space available to JVM.                       |

---

#### **C) FileReader & FileWriter Methods**

**FileReader (for reading characters)**

| Method         | Description                   |
| -------------- | ----------------------------- |
| `read()`       | Reads one character.          |
| `read(char[])` | Reads into a character array. |
| `close()`      | Closes the reader.            |

**FileWriter (for writing characters)**

| Method            | Description                |
| ----------------- | -------------------------- |
| `write(int c)`    | Writes a single character. |
| `write(String s)` | Writes a string.           |
| `write(char[])`   | Writes char array.         |
| `close()`         | Closes the writer.         |
| `flush()`         | Forces write to disk.      |


Full list of methods available only in `java.io.File` class.
| **Sr. No.** | **Method**          | **Description**                                                                     |
| ----------- | ------------------- | ----------------------------------------------------------------------------------- |
| **1**       | `getName()`         | Returns the name of the file or directory.                                          |
| **2**       | `getAbsolutePath()` | Returns the absolute (full) path of the file or directory.                          |
| **3**       | `canRead()`         | Returns **true** if the file exists and can be read by the application.             |
| **4**       | `canWrite()`        | Returns **true** if the file exists and can be modified (written).                  |
| **5**       | `exists()`          | Returns **true** if the file or directory actually exists.                          |
| **6**       | `isDirectory()`     | Returns **true** if the path exists and is a directory.                             |
| **7**       | `isFile()`          | Returns **true** if the path exists and is a regular file (not a directory).        |
| **8**       | `length()`          | Returns file size in **bytes**. Returns 0 for directories.                          |
| **9**       | `createNewFile()`   | Creates a new empty file **if it does not already exist**. Returns true on success. |
| **10**      | `delete()`          | Deletes the file or empty directory. Returns true on success.                       |
| **11**      | `list()`            | Returns a **String[]** of names inside a directory (files + directories).           |
| **12**      | `mkdir()`           | Creates a single directory. Returns true if created successfully.                   |
| **13**      | `mkdirs()`          | Creates multiple directories. Returns true if created successfully.                 |
| **14**      | `renameTo()`        | Renames the file or directory. Returns true if renamed successfully.              |

---

### Java File I/O (Input/Output Streams)

#### ➡ Counting Hidden & Visible Files in a Directory
```java
// Listing Files & Checking Attributes (isHidden, isDirectory, etc.)
import java.io.*;
class A extends File { // ❌ NOTE: You should NOT extend File class.
// File is a final representation; we don’t need inheritance here.
    public static void main(String... args){
        File f = new File("f://"); // Create File object for the target directory

        int hidden = 0;
        int visible = 0;

        String path[] = f.list(); // List the names of all files/folders inside the directory

        // Null check (in case path is empty or drive not found)
        if(path == null){
            System.out.println("Directory not found or empty.");
            return;
        }

        // Loop through each file/folder
        for(String p:path) {
            File ff = new File(p); // Create File object for every item

            if(ff.isHidden()){
                hidden++;
            } else {
                visible++;
            }
        }
        System.out.println("HIDDEN" + hidden);
        System.out.println("VISIBLE" + visible);
    }
}
```
**Explanation:**
- `File.list()` returns all file/folder names inside a directory.
- `isHidden()` checks whether the file is hidden.
- Counts visible and hidden items.

#### ➡ FileInputStream – Skipping Bytes While Reading a File
```java
// FileInputStream: Reading Bytes & Using skip()
class A{
    public static void main(String... args) throws IOException{
        File f = new File("f://tt.txt");
        FileInputStream fin = new FileInputStream(f);
        int i;
        // Read until end of file (-1)
        while((i = fin.read()) != -1){
            fin.skip(2); // ❗ Skips 2 bytes after each read
            System.out.print((char)i); // print current character
        }
    }
}
```
**Explanation:**
- Reads the file one byte at a time.
- After reading each byte, `skip(2)` jumps forward by 2 bytes.
- So effectively reads every **3rd character**.

#### ➡ Merge two files (SequenceInputStream) 
Read the data from two files and writes into another file.
```java 
// SequenceInputStream: Merging Multiple Input Streams
class A{
    public static void main(String... args) throws IOException{
        File f = new File("f://mp.mp3");
        FileInputStream fin = new FileInputStream(f); // Input file 1
        FileInputStream fin1 = new FileInputStream("f://mp1.mp3"); // Input file 2
        SequenceInputStream ss = new SequenceInputStream(fin, fin1); // Combines two streams into one
        FileOutputStream fout = new FileOutputStream("f://Nfile.mp3"); // Output file

        int i;
        // Reads from merged stream
        while((i = ss.read()) != -1){
            fout.write(i); // write into new file
            System.out.print((char)i);
        }
        // Close streams
        ss.close();
        fin.close();
        fin1.close();
        fout.close();

        System.out.println("Files merged successfully.");
    }
}
```
**Explanation:**
- `SequenceInputStream` merges **multiple input streams** into one continuous stream.
- Reads from `fin` first → then automatically switches to `fin1`.
- Useful for merging text files, audio, etc.

#### ➡ Taking Keyboard Input (BufferedInputStream) & Writing Into a File
```java
import java.io.*;
class A {
    public static void main(String... args) throws IOException {
        FileOutputStream fout = new FileOutputStream("f://tt.txt");
        // Read input from keyboard via System.in
        BufferedInputStream bb = new BufferedInputStream(System.in);
        System.out.println("Enter data (Press 'N' to stop):");

        int i;
        // Reads until 'N' is typed
        while((i = bb.read()) != 'N'){
            fout.write(i);
        }
        fout.close();
    }
}

```
Takes the data from the keyboard (console) and stores it in the file.

**Explanation:**
- Takes input from keyboard byte-by-byte.
- Stops writing when character `'N'` is entered.
- Stores typed content into `tt.txt`.

#### ➡ Append Mode in FileOutputStream
```java
// Appending Data to a File (FileOutputStream append = true)
FileOutputStream fout = new FileOutputStream("f://tt.txt", true); // set true for the appendable mode
String s = "Hello";
fout.write(s.getBytes()); // convert string → byte[]
fout.close();
```
**Explanation:**
- Setting `true` enables *append mode* (does not overwrite file).
- `getBytes()` converts String into byte array.

#### ➡ ByteArrayInputStream – Read Data from Byte Array
As the name suggests, it can be used to read byte array as input stream.

Java ByteArrayInputStream class contains an internal buffer which is used to read byte array as stream. In this stream, the data is read from a byte array.

The buffer of ByteArrayInputStream automatically grows according to data.

```java
// ByteArrayInputStream: Reading Bytes from Memory Buffer
FileOutputStream fout = new FileOutputStream("f://output.txt");
byte arr[] = "welcome".getBytes();
ByteArrayInputStream bb = new ByteArrayInputStream(arr);
int i;
while((i = bb.read()) != -1){
    fout.write(i); // write to the file
    System.out.print((char)i); // print to the console
}

fout.close();
bb.close();
```
**Explanation:**
- `ByteArrayInputStream` lets you treat a byte array as a file.
- Useful for:
    - Testing I/O
    - Processing data in memory
    - Object serialization/deserialization

➡ **Partial Read Using ByteArrayInputStream**
```java
// ByteArrayInputStream with Offset & Length
ByteArrayInputStream by = new ByteArrayInputStream(arr, 0, 3); // reads arr from index 0 to 3
```
**Explanation:**
- Reads only part of the array: from index `0` to `3` (3 bytes).
- Useful when you want only a portion of data to be processed.


#### ➡ PrintStream – Writing Formatted Data to Streams
PrintStream class provides methods to write data to another stream. The PrintStream class automatically flushes the data so there is no need to call `flush()` method. Moreover, its methods don't throw `IOException`.

PrintStream provides convenient `print()` and `println()` methods to write data to:
- `console (System.out)`
- files

It **auto-flushes and never throws `IOException`**.

**Example 1: Printing to Console**
```java
PrintStream out = new PrintStream(System.out); // prints data on the screen
out.print("hi");
```
**Example 2: Printing to a File**
```java
FileOutputStream f = new FileOutputStream("f://tt.txt");
PrintStream out = new PrintStream(f); // prints data in file
out.print("hello");
```
#### ➡ FileOutputStream – Writing Raw Bytes to a File
It is an output stream used for writing data to a file.

`FileOutputStream` is used to write byte data such as:
- text
- images
- audio
- binary files

▶ **Writing a Single Byte**
```java
FileOutputStream fout = new FileOutStream ("D://t.txt");
fout.write(65); // writes ASCII 65 → 'A'
// The content of a text file t.txt is set with the data 'A'
```
**Result:** File contains the character `A`.

▶ **Writing a String**
```java 
FileOutputStream fout = new FileOutputStream("D:\\t.txt");
String s = "Welcome";
byte b[] = s.getBytes(); // converting String into byte array 
fout.write(b); // content of text file tt.txt is set with the data 'Welcome'
```
#### ➡ FileInputStream – Reading Raw Bytes from a File
`FileInputStream` reads byte-oriented data, typically:
- images, videos, audio
- binary files

It can read text, but for character data `FileReader` is preferred.

This class obtains input bytes from a file. 

It is used for reading byte-oriented data (streams of raw bytes) such as image data, audio, video, etc.

You can also read character-stream data. But, for reading streams of chracters, it is recommended to use `FileReader` class.

▶ **Read a Single Character**
```java 
FileInputStream file = new FileInputStream("D://tt.txt");
int i = file.read(); // reads a single character  // reads 1 byte
System.out.println((char)i); // prints the character // convert byte → character
```
`tt.txt` File Content: `Welcome`
After executing the above code, you will get a single character from the file which is `87` (in byte form). To see the text, you need to convert it into character.
Output: `W`

▶ **Read All Characters**
```java
FileInputStream fin = new FileInputStream("D://tt.txt");
int i = 0;
while((i = fin.read()) != -1){
    System.out.print((char)i);
}
```
Output: `Welcome`

#### ➡ SequenceInputStream – Reading Multiple Streams Sequentially
`SequenceInputStream` combines **two input streams** into one stream.
It reads the first completely, then the second.

This class is used to read data from multiple streams. It reads data sequentially (one by one).

**Reading t1.txt + t2.txt**
```java
import java.io.*;
class A{
    public static void main(String... args) throws Exception{
        FileInputStream input1 = new FileInputStream("f://t1.txt");
        FileInputStream input2 = new FileInputStream("f://t2.txt");
        SequenceInputStream inst = new SequenceInputStream(input1, input2);
        int i;
        while((i = inst.read()) != -1){
            System.out.print((char)i);
        }
        input.close();
        input1.close();
        input2.close();
    }
}
```

let, `t1.txt`: Java IO Programming.
     `t2.txt`: SequenceInputStream class.

Output:
```
Java IO Programming. SequenceInputStream class.
```

#### ➡ BufferedInputStream – Fast Reading with Internal Buffer
`BufferedInputStream` improves performance using an internal buffer.

Instead of reading byte-by-byte from disk, it loads data in **chunks**.

This class is used to read information from stream. It internally uses buffer mechanism to make the performance fast.

The important points about BufferedInputStream:
- When the bytes from the stream are skipped or read, the internal buffer automatically refilled from the contained input stream, many bytes at a time.
- When a BufferedInputStream is created, an internal buffer array is created.

**Key Points:**
- Uses internal buffer array.
- When reading → first checks buffer.
- If buffer empty → fetches a **bulk batch** of bytes from disk.
- More efficient than `FileInputStream`.

### BufferInputStream vs FileInputStream

| No.                    | **BufferedInputStream**                                                                                                                                                                                                                    | **FileInputStream**                                                                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| **1**                  | It is **buffered**.                                                                                                                                                                                                                        | It is **not buffered**.                                                                                                 |
| **2**                  | Reads bytes from another InputStream (e.g., FileInputStream).<br>It **wraps** another stream. <br><br>`java<br>FileInputStream fis = new FileInputStream("c:/myFile.txt");<br>BufferedInputStream bis = new BufferedInputStream(fis);<br>` | Reads bytes **directly from a file**. <br><br>`java<br>FileInputStream fis = new FileInputStream("c:/myFile.txt");<br>` |
| **3**                  | `read()` mostly reads data from the **buffer**.<br>If buffer is empty → it fetches a *chunk* of bytes from disk and fills the buffer.                                                                                                      | Each `read()` call directly accesses the **file system**, reading **1 byte at a time** → very slow.                     |
| **4**                  | Supports **mark()** and **reset()**. <br>An internal buffer array is created and refilled as needed, reading many bytes at once.                                                                                                           | Does **NOT** support mark/reset. <br>Reads bytes one-by-one from disk.                                                  |
| **5**                  | Much **faster** due to buffering.                                                                                                                                                                                                          | **Slower** because of frequent disk I/O calls.                                                                          |
| **6**                  | Example: If reading 256 bytes, it may read 128 bytes at a time → only **2 system calls**.                                                                                                                                                  | If reading 256 bytes, it makes **256 system calls** (1 per byte).<br>Very slow.                                         |
| **Real-World Analogy** | Like YouTube **buffering** the video → smooth playback.                                                                                                                                                                                    | No buffering → video would hang every second.                                                                           |

---

❓ **Why do we use the `File` class in Java?**
➡ Because `File` class represents **file or directory paths** and allows us to check properties like *hidden, readable, writable, exists*, etc.

❓ **Can the `File` class read or write data?**
➡ No. `File` class **cannot** read/write data. It only represents **metadata/path**.
To read/write, we use streams like **FileInputStream, FileOutputStream**.

 ❓ **How do we count hidden and visible files in a directory?**
➡ By calling `f.list()` to get all file names and then checking each file with
`isHidden()` → hidden
otherwise → visible.

 ❓ **What does `skip()` do in FileInputStream?**
➡ `skip(n)` moves the cursor forward by **n bytes** without reading them.

 ❓ **How do we merge two files in Java?**
➡ Use `SequenceInputStream` to combine two input streams and write the result using `FileOutputStream`.

❓ **How do we take input from keyboard and save it to a file?**
➡ Wrap `System.in` in `BufferedInputStream`, read byte-by-byte, and write into `FileOutputStream`.

❓ **How to append data to an existing file?**
➡ Create FileOutputStream with **append mode ON**:
`new FileOutputStream("file.txt", true)`

❓ **What is ByteArrayInputStream?**
➡ A stream that reads data from a **byte array**, not from a file.
Useful for testing, converting strings to streams, in-memory data processing.

❓ **Why use ByteArrayInputStream?**
➡ Because it allows:
* reading data without actual file
* fast in-memory operations
* treating strings/bytes like an InputStream


❓ **What does `ByteArrayInputStream(arr, 0, 3)` mean?**
➡ It creates a stream that reads only a **portion** of array → from index `0` up to `3`.

## 52. Multithreading
Process of executing multiple threads simultaneously.

Thread is basically a lightweight sub-process, a smallest unit of processing. Multiprocessing and Multithreading, both are used to achieve **multitasking**.

But we use Multithreading than multiprocessing because threads share a common memmory area. They don't allocate separate memory area so saves memory, and context-switching between the threads takes less time than process.

Multithreading in Java is a feature that enables a program to run multiple threads simultaneously, allowing tasks to execute in parallel and utilize the CPU more efficiently. A thread is a lightweight, independent unit of execution inside a program (process).

- A process can have multiple threads.
- Each thread runs independently but shares the same memory.

![java_multithreading](/resources/Java-Multithreading1.png)

### Key Features of Multithreading
- A thread is the smallest unit of execution in Java.
- Threads share the same memory space but run independently.
- Java provides the Thread class and Runnable interface to create threads.
- Multithreading ensures better CPU utilization by executing tasks simultaneously.
- Synchronization is needed to prevent data inconsistency when threads share resources.

**Example:** Imagine a restaurant kitchen. Multiple chefs (threads) are preparing different dishes at the same time. This speeds up service and utilizes all available resources (CPU).

![multithreading](/resources/multithreading_example.png)

### Java Threads
A thread is a lightweight sub-process, a smallest unit of processing. It is a separate path of execution.

Threads are independent, if there occurs exception in one thread, it doesn't affect other threads. It shares a common memory area.

![thread](/resources/thread.png) 

As shown in the fig, thread is executed inside the process. There is context-switching between the threads. There can be multiple processes inside the OS and one process can have multiple threads.

> 📝: At a time one thread is executed only.

Threads allows a program to operate more efficiently by doing multiple things at the same time.

Threads can be used to perform complicated tasks in the background without interrupting the main program.
> 📝: In Multithreading, more than one tasks work simultaneously.

![threads](/resources/threads.png)

1. Process-based Thread – **Multitasking**
- This refers to running multiple processes at the same time.
- Example: Running Chrome, VS Code, and Spotify simultaneously.
- Each process has its own memory, and switching between them is multitasking.

2. Thread-based Thread – **Multithreading**
- This refers to running multiple threads inside the same process.
- Example: A single program where one thread handles UI, another handles I/O, another handles computation.
- Threads share the same memory of the process.

> 📝: **Java doesn't support multitasking**. Multitasking is handled by the OS.

🔸 **In Short :**
- **Multitasking** = multiple processes running together.
- **Multithreading** = multiple threads within one process running together.

### Thread vs Process
| **Point**               | **Process**                                          | **Thread**                                                     |
| ----------------------- | ---------------------------------------------------- | -------------------------------------------------------------- |
| **Definition**          | A program in execution.                              | A lightweight segment of a process.                            |
| **Creation Time**       | Takes more time to create.                           | Takes less time to create.                                     |
| **Termination Time**    | Takes more time to terminate.                        | Takes less time to terminate.                                  |
| **Context Switching**   | Slow, heavyweight switch.                            | Fast, lightweight switch.                                      |
| **Memory Usage**        | Has its own memory, PCB, stack, address space.       | Shares parent’s memory, has its own TCB & stack.               |
| **Communication**       | Less efficient, requires IPC (pipes, sockets, etc.). | Efficient — threads communicate via shared memory.             |
| **Independence**        | Processes run independently.                         | Threads depend on each other.                                  |
| **Blocking Behavior**   | One blocked process does not affect others.          | If one user-level thread blocks, all may block.                |
| **Changes Propagation** | Parent process changes don’t affect child processes. | Changes in main thread may affect all threads (shared memory). |
| **Weight**              | Heavyweight.                                         | Lightweight.                                                   |
| **Data Sharing**        | Processes do *not* share data.                       | Threads *share* data.                                          |
| **Use of System Calls** | Requires system calls for creation.                  | No system call (created via APIs).                             |
| **Execution Model**     | Used in multiprogramming (multiple processes).       | Used in multithreading (multiple threads in one process).      |
| **OS Involvement**      | OS must handle process switching.                    | Thread switching may occur without OS involvement.             |

#### ➕ Advantages of Process
- Processes work independently in their own memory, ensuring no interference and better security.
- Resources like CPU and memory are allocated effectively to optimize performance.
- Processes can be prioritized to ensure important tasks get the resources they need.

#### ➖ Disadvantages of Process
- Frequent switching between processes can slow down the system and reduce speed.
- Improper resource management can cause deadlocks where processes block each other.
- Too many processes increase the size of the process table, consuming memory and slowing operations like searching and updating.

#### ➕ Advantages of Thread
- When there is heavy computation + I/O work, threads enable parallelism and speed up execution.
- Threads are lightweight, so they are much faster to create and destroy than processes.
- Threads allow applications to handle multiple tasks at the same time (e.g., browser loading page + playing video + scrolling).

#### ➖ Disadvantages of Thread
- Threads share memory, so one thread can accidentally overwrite or corrupt data used by another thread.
- Threads share resources like file handles — one closing a file can break another thread that is using it.
- Creating too many threads can degrade performance or exhaust system memory.

### Creating a Thread
![create_thread](/resources/Java-Multithreading2.png)

There are two ways to create a thread, both are defined in `java.lang` package:

1.**Extending the Thread class**

 It can be created by extending the Thread class and overriding its run() method:

```java
public class Main extends Thread {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```
2. **Implementing the Runnable Interface**

Another way to create a thread is to implement the `Runnable` interface:

```java
public class Main implements Runnable {
  public void run() {
    System.out.println("This code is running in a thread");
  }
}
```
> `run()` method of `Runnable` interface is an **abstract method**, so we have to override it, whenever we use it.

> **Differences between "extending" and "implementing" Threads :**
 The major difference is that when a class extends the Thread class, you cannot extend any other class, but by implementing the Runnable interface, it is possible to extend from another class as well, like: class `MyClass extends OtherClass implements Runnable`.

**Which method is better?**

✔ Use Runnable when:
- You want to extend another class
- You want to share the same job among multiple threads
- Code is cleaner and more flexible

✔ Use Thread when:
- You want full control by overriding Thread class itself
- Rarely preferred

> 📝: Java does not support multiple inheritance → so Runnable is usually used.

> A thread can be started **only once**. 
Calling `start()` again → `IllegalThreadStateException`.

### Thread Class
Thread is a line of execution within a program. Each program can have multiple associated threads. Each thread has a priority which is used by the thread scheduler to determine which thread must run first. Java provides a thread class that has various method calls to manage the behavior of threads by providing constructors and methods to perform operations on threads. 

A Thread is a program that starts with a method() frequently used in this class only known as the `start()` method. This method looks out for the `run()` method which is also a method of this class and begins executing the body of the `run()` method. Here, keep an eye on the `sleep()` method which will be discussed later below.

> 📝: Every class that is used as a thread must implement `Runnable` interface and override its run method.

**Syntax:**
```java
public class Thread extends Object implements Runnable
```

**Thread Class - Common Methods**
| Method                                | Description                                                                                       |
| ------------------------------------- | ------------------------------------------------------------------------------------------------- |
| `run()`                               | Entry point of a thread. Contains the code that executes when the thread starts.                  |
| `start()`                             | Calls the `run()` method internally and starts a new thread of execution.                         |
| `static sleep(long millis)`           | Makes the **current thread** sleep for the specified milliseconds. Throws `InterruptedException`. |
| `isAlive()`                           | Returns `true` if the thread is still running; otherwise `false`.                                 |
| `join()`                              | Causes the current thread to wait until the specified thread finishes execution.                  |
| `setPriority(int pr)`                 | Changes the priority of the thread.                                                               |
| `int getPriority()`                   | Returns the priority of the thread.                                                               |
| `setName(String n)`                   | Sets/changes the name of the thread.                                                              |
| `String getName()`                    | Returns the name of the thread.                                                                   |
| `wait()` / `notify()` / `notifyAll()` | Methods of the **Object** class; used for inter-thread communication.                             |

#### Running Threads in Java
There are two methods used for running Threads in Java:
- `run()` Method: Contains the code for the thread. Calling it directly behaves like a normal method call.
- `start()` Method: Launches a new thread and internally calls `run()` concurrently.

#### Thread by extending Thread Class
```java
class A extends Thread {
    public void run() {
        for(int i = 0; i <= 10; i++) {
            try {
                Thread.sleep(1000);  // make child thread sleep for 1 second
            } catch(InterruptedException e) { }
            
            System.out.println("Child Thread " + i);
        }
    }

    public static void main(String... args) {
        A a1 = new A();
        a1.start();  // start child thread

        for(int i = 0; i <= 10; i++) {
            try {
                Thread.sleep(1000);  // main thread sleeps
            } catch(InterruptedException e) { }
            
            System.out.println("Main Thread " + i);
        }
    }
}
```
Explanation: 
- Creates a child thread by extending `Thread`
- Both **Main Thread** and **Child Thread** run loops simultaneously
- Each prints numbers 0–10
- Both sleep for 1 second in each iteration → outputs interleave

> 📝: As you know that at a time only one thread is executed. If you sleep a thread for the specified time, the thread schedular picks up another thread and so on.

> 📝: `Thread` Class extends `Object` class and implements `Runnable` Interface.

```java
class A extends Thread{
    static volatile int count = 5;
    public void run() {
        while(count > 0) {}
        System.out.println("Loop terminate");
    }
    public static void main(String... args){
        A a1 = new A();
        a1.start();
        try{ Thread.sleep(5000); } // wait for 5 sec
        catch(Exception e) {}
        count = -1; // update shared variable
        System.out.println("Main terminate");
    }
}
```

> 📝: **volatile keyword**: Declaring a volatile variable means: The value of this variable will never be cached thread-locally: all reads and writes will go straight to 'main memory'.

`volatile` is used in multithreading to ensure **visibility** of a variable across all threads.

✔ What it does
* Value is **never cached** by threads
* All reads/writes go **directly to main memory**
* All threads see the **latest** updated value immediately

✔ Good for
* Flags (`running`, `stop`)
* Status variables
* Simple read/write shared variables

❌ What it does NOT do
* Does **not** provide locking
* Does **not** make operations atomic
* Does **not** replace `synchronized`

> ✔ `volatile` = **visibility only**, not atomicity.

```java
class Worker extends Thread {
    volatile boolean running = true;

    public void run() {
        while(running) { }
    }
}
```

### Life Cycle of a Thread (controlled by JVM)
A thread passes through different states like New, Runnable, Running, Waiting and Terminated. The lifecycle is managed by the JVM and thread scheduler.

A thread passes through different states like New, Runnable, Running, Waiting and Terminated. The lifecycle is managed by the JVM and thread scheduler.

![thread_lifecycle](/resources/Java-Multithreading3.png)

During its thread life cycle, a Java thread transitions through several states from creation to termination.
- **New**: Thread object is created but not started.
- **Runnable**: Thread is ready to run and waiting for CPU allocation.
- **Running**: Thread is executing its run() method.
- **Waiting/Blocked**: Thread waits for a resource or another thread.
- **Terminated**: Thread completes execution or is stopped.

### Thread Priorities
Threads can be assigned priorities to influence scheduling decisions. Higher priority threads are given preference by the thread scheduler.

### Synchronization
Synchronization ensures that multiple threads do not interfere with each other while accessing shared resources. It helps prevent data inconsistency and race conditions.

### Inter-thread Communication
Threads can communicate using methods like wait(), notify() and notifyAll(). This enables coordination between multiple threads.

### Deadlock
Deadlock occurs when two or more threads wait indefinitely for resources locked by each other. Java provides techniques to avoid and resolve deadlocks.

### Thread Safety
Thread safety ensures correct program execution when multiple threads access shared data. Techniques include synchronized, volatile and ThreadLocal.

### Concurrency Utilities (java.util.concurrent)
The concurrency package provides tools like Executors, Callable, Future and Thread Pools. These simplify managing multithreaded applications.

### Advantages of Multithreading in Java
1. It doesn't block the user because threads are independent and you can perform multiple operations at same time.
2. You can perform many operations together so it saves time.
3. Threads are independent so it doesn't affect other threads if exception occur in a single thread. 

![advantages_of_multithreading](/resources/Java-Multithreading4.png)

- **Improved Performance**: Multiple tasks can run simultaneously, reducing execution time.
- **Efficient CPU Utilization**: Threads keep the CPU busy by running tasks in parallel.
- **Responsiveness**: Applications (like GUIs) remain responsive while performing background tasks.
- **Resource Sharing**: Threads within the same process share memory and resources, avoiding duplication.
- **Better User Experience**: Smooth execution of tasks like file downloads, animations, and real-time updates.

### Real-World Applications

![multithreading_applications](/resources/Java-Multithreading5.png)

## 53. Runnable Interface
The `Runnable` interface is a functional interface that defines a single method, `run()`, which is used to execute a task in a separate thread.

The `Runnable` interface is a **functional interface** that contains **one abstract method**, run().
It represents a task that can be executed by a thread.

📝 **Key Idea:**
- **Runnable** = What to do (task)
- **Thread** = Who will do it (worker)

A `Thread` object is responsible for scheduling and running the `Runnable` task.

### Why Use Runnable?
- Java **does not support multiple inheritance**, so if your class extends something else, it cannot extend Thread.
- Runnable is preferred for **clean separation** of *task* and *execution mechanism*.
- Allows the **same Runnable task** to be executed by multiple threads.

### Thread by implementing Runnable interface:
The `Runnable` interface should be implemented by any class whose instances are intended to be executed by a thread.
Runnable interface have only one method named `run()`.

The class must implement `Runnable` and **override** the `run()` method.
```java
class A implements Runnable {
    A() {
        Thread t = new Thread(this); // Providing object of class that implements Runnable interface to the Thread class
        t.start(); // This calls run() in a new thread
    }
    public void run() {
        for(int i = 0; i <= 10; i++) {
            try {Thread.sleep(1000);}
            catch(Exception e) {}
            System.out.println("Child Thread");
        }
        public static void main(String... args) {
            A a1 = new A(); // Runnable object created → Thread starts

            for(int i = 0; i <= 10; i++) {
                try {Thread.sleep(1000);}
                catch(Exception e) {}
                System.out.println("Main Thread");
            }
        }
    }
}
```
- A class implementing `Runnable` **does NOT become a thread**.
- You must create a **Thread object** and pass the Runnable to it.
- `new Thread(this)` tells Java: "*Run my run() method inside a new thread.*"

> 📝: If you are not extending the `Thread` class, your class object would not be treated as a thread object. So you need to explicitly create `Thread` class object.
We are passing the object of your class that implements `Runnable` so that your class `run()` method may execute.

**Example with Thread names (Multiple Threads)**
```java
class A implements Runnable{
    String name;
    Thread t;
    A(String name){
        this.name = name;

        t = new Thread(this);  // associate Runnable with a Thread
        t.setName(name);       // give thread a name
        t.start();             // start execution in new thread
    }
    public void run(){
        for(int i=0;i<=10;i++){
            try { Thread.sleep(1000); }
            catch(Exception e) {}
            System.out.println(t.getName()); // prints thread name
        }
    }
    public static void main(String... args){
        A a1 = new A("One");
        A a2 = new A("Two");
        A a3 = new A("Three");
        A a4 = new A("Four");
        A a5 = new A("Five");
        for(int i = 0; i <= 10; i++){
            try{ Thread.sleep(1000); }
            catch(Exception e) {}
            System.out.println("Main Thread");
        }
    }
}
```

- Threads created using the same `Runnable` share the **same object**, but different threads.
- Each `Thread` object maintains **its own stack**, but all share the **same heap**.
- Calling `t.start()` → executes `run()` in **parallel** with the main thread.
- You must **never** call `run()` directly → it will run like a normal method, not a thread.

### When to Use Which?
✔ Use **extends Thread** when:
- Your class does not extend any other class
- You want to customize Thread class itself

✔ Use **implements Runnable** when (recommended) :
- Your class already extends another class (preferred because Java doesn’t support multiple inheritance)
- You want cleaner, modular code
- You want to share the same task among multiple threads
- You prefer composition over inheritance

> 📝: Runnable is the standard and preferred approach in enterprise applications.

## 54. `isAlive()` Method
The `isAlive()` method of the `Thread` class is used to check whether a thread is **still running** or **has finished its execution**. 
It returns **true** if the thread upon which it is invoked is **alive**; otherwise, it returns **false**.

```java
public final boolean isAlive()
```

✔ **What it returns**

* **true** → Thread is still running (Runnable/Running state)
* **false** → Thread has finished execution or has not started yet

### Why use `isAlive()`?

It helps to:
* Check if a thread is still active
* Confirm if a thread has completed execution
* Debug or monitor thread behavior
* Coordinate between threads

**Basic `isAlive()` Usage :**
```java
class A implements Runnable{
    String name;
    Thread t;
    int time;
    A(String name, int time){
        this.time = time;// sleep time for each thread
        this.name = name;     // thread name

        t = new Thread(this); // passing Runnable object to Thread
        t.setName(name);      // assigning thread name

        t.start();            // start the thread → calls run() internally
    }
    public void run(){
        for (int i = 0; i<=10; i++){
            try{ Thread.sleep(time); // each thread sleeps for its own time
            } catch(Exception e) {}
            System.out.println(t.getName()); // print thread name
        }
    }
    public static void main(String... args){
        // Create 5 threads with different names + sleep times
        A a1 = new A("One", 1000);
        A a2 = new A("Two", 200);
        A a3 = new A("Three", 500);
        A a4 = new A("Four", 800);
        A a5 = new A("Five", 900);

        // Main thread prints isAlive() status for each thread
        for(int i = 0; i <= 10; i++){
            try{ Thread.sleep(1000); }
            catch(Exception e) {}
            System.out.println(a1.t.getName() + "" + a1.t.isAlive());
            System.out.println(a2.t.getName() + "" + a2.t.isAlive());
            System.out.println(a3.t.getName() + "" + a3.t.isAlive());
            System.out.println(a4.t.getName() + "" + a4.t.isAlive());
            System.out.println(a5.t.getName() + "" + a5.t.isAlive());
        }
    }
}
```
**Explanation:**
- Each object of class `A` creates **its own thread** with custom sleep duration.
- `isAlive()` returns:
    - **true** → thread is still running (hasn't completed `run()`)
    - **false** → thread finished executing
- Threads with **shorter sleep times** will finish earlier.
- Main thread continues running independently and monitors thread status.
---
`isAlive()` tests if this thread is alive. A thread is alive if it has been started and has not yet died. There is a transitional period from when a thread is running to when a thread is not running. After the `run()` method returns, there is a short period of time before the thread stops. If we want to know if the `start` method of the thread has been called or if thread has been terminated, we must use `isAlive()` method.
This method is used to find out if a thread has actually been started and has yet not terminated.

`isAlive()` checks whether a thread is **still active**.
A thread is considered **alive** if:

* It has been **started** using `start()`
* Its `run()` method **has not finished yet**

There is a brief transitional moment after the `run()` method completes but before the thread fully stops. During this time, the thread may still be considered alive.

`isAlive()` is useful when you want to confirm:

* Whether the thread’s `start()` method has been called
* Whether the thread has **not yet terminated**
* Whether the thread has completed its execution or is still running

In short:

> **`isAlive()` helps determine if a thread has actually started and has not yet finished running.**

* A thread becomes "alive" **only after** calling `start()`.
* Calling `run()` directly does **NOT** make a thread alive.
* A thread remains alive until the `run()` method completes.
* After completion, `isAlive()` always returns `false`.

## 53. Life Cycle of a Thread - Thread States (controlled by JVM)
The lifecycle of the thread in Java is controlled by JVM.

![thread_lifecycle](/resources/thread_lifecycle.png)

1. **New**: The thread is in new state if you create an instance of `Thread` class but before the invocation of `start()` method.
2. **Runnable**: The thread is in `Runnable` state after the invocation of `start()` method, but the thread schedular has not selected it to be the running thread.
3. **Running**: The thread is in running state if the thread schedular has selected it.
4. **Non-Runnable (Blocked)**: This is the state when the thread is still alive, but is currently not eligible to run.
5. **Terminated**: A thread is in terminated or dead state when its `run()` method exists.

### Thread Schedular in Java
- It is the part of the JVM that decides which thread should run.
- There is no guarantee that which runnable thread will be chosen to run by the thread schedular.
- Only one thread at a time can run in a single process.
- The thread schedular mainly uses preemptive or time-slicing scheduling to schedule the threads.

### Starting a thread
`start()` method of `Thread` class is used to start a newly created thread. It performs following tasks:
- A new thread starts (with new callstack).
- The thread moves from **New** state to **Runnable** state.
- When the thread gets a  chance to execute, its target `run()` method will run.

> 📝: `start()` methods only schedules the thread for execution and not actually begins the execution of the thread. The execution of the thread is started when the JVM calls the `run()` method of the thread once the CPU Schedular picks this scheduled thread for execution.

## 54. Synchronization
Synchronization in Java is a mechanism that ensures that **only one thread** can access a shared resource (like a variable, object, or method) at a time. It prevents concurrent threads from interfering with each other while modifying shared data.

The capibility to control the access of multiple threads to nay shared resource.

Java Synchronization is better option where we want to allow only one thread to access the shared resource.

**Syntax :**
```java
synchronized (object reference expression){
    // code block
}
```
✔ **What Synchronization Does**

Synchronization works by **locking** the object on which the synchronized method or block is executed.

Only one thread can hold the lock at a time.
```java
synchronized void output(String s, int time)  // synchronized method
```
Synchronization ensures that only one thread at a time can access a shared resource by locking the object on which the synchronized method is called.

It prevents inconsistent results when multiple threads modify shared data simultaneously.

✔ **Capability**: Control access of multiple threads to any shared resource.

✔ **Goal**: Prevent thread interference and data inconsistency.
```java
class A{
    synchronized void output(String s, int time) // synchronized method
    {
        System.out.println("[");
        try{ Thread.sleep(time);}
        catch(InterruptedException e) {}

        System.out.println(s);
        
        try{ Thread.sleep(time);}
        catch(InterruptedException e) {}
        System.out.println("]");
    }
}
class B implements Runnable{
    A a1;
    Thread t1;
    int time;
    String s;
    B(String s, int time, A a1){
        this.time = time;
        this.s = s;
        this.a1 = a1;

        t = new Thread(this);
        t.start();
    }
    public void run(){
        a1.output(s.time); // calling synchronized method
    }
}
class C{
    public static void main(String... args){
        A a1 = new A(); // ONE shared object

        B b1 = new B("hi hello", 700, a1);
        B b2 = new B("hi welcome", 300, a1);
        B b3 = new B("hi ABC", 500, a1);
    }
}
```
- When multiple threads call the same **synchronized method**, only **one** thread can execute it at a time.
- All other threads **wait** until the lock is released.
- The lock belongs to the **object**, not the method.

> 📝: When a thread invokes a synchronized method, it automatically acquires the lock for that object and releases it when the thread completes its task.

**Synchronization block**
Use when only a **small portion** of code needs synchronization.
```java
public void run(){
    synchronized(a1) // locking a1 object
    { a1.output(s.time); }
}
```
Synchronized blocks in Java are marked with the `synchronized` keyword.
A synchronized block in Java is synchronized on some object. All synchronized blocks synchronized on the same object can only have one thread executing inside them at the same time.
All other threads attempting to enter the synchronized block are blocked until the thread inside the synchronized block exists the block.

### Why use Synchronization
The synchronization is mainly used to:
- To prevent thread interference.
- To prevent consistency problem.

### Concept of Lock (Monitor)
Every Java object has one **monitor lock**.

A thread must:
1. **Acquire the lock**
2. Execute synchronized code
3. **Release the lock**

Other threads wait until the lock is free.

Synchronization is built around an internal entity known as the lock or monitor. Every object has an lock associated with it.

By convention, a thread that needs consistent access to an object's fields has to acquire the object's lock before accessing them, and then release the lock when it's done with them.

### Synchronized block
Synchrnoized block can be used to perform synchronization on any specific resource  of the method.

Suppose you have 50 lines of code in your method, but you want to synchronize only 5 lines, you can use **synchronized block**.

If you put all the codes of the method in the synchronized block, it will work same as the synchronized method.

#### Why use synchronized blocks
- Prevents locking the entire method
- Increases performance
- Allows fine-grained control over critical sections

> ✔ **Only the code inside the synchronized block is locked.**

#### Points to remember for Synchronization block
* Used to lock **only specific code**, not the entire method.
* Useful when only a few lines need synchronization.
* All synchronized blocks synchronized on the **same object** allow only **one thread** at a time.
- Synchronized block is used to lock an object for any shared resource.
- Scope of synchronized block is smaller than the method.

| Concept             | Meaning                                     |
|---------------------|----------------------------------------------|
| Synchronized Method | Locks the entire method                      |
| Synchronized Block  | Locks only a specific part of the code       |
| Lock / Monitor      | Every object has one intrinsic lock (monitor)|
| Purpose             | Prevent thread interference & inconsistency  |
| Limitation          | Can reduce performance due to locking        |
