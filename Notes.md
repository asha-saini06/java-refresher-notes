# ☕ Java - James Gosling

> Started in 1991 -> Oak -> 1995 -> Java (breed of Coffee)

- Java is _statically typed_, so variable type must be declared before use.
- Use `var` (Java 10+) for type inference.
- Java is a compiled language, so you must compile your code before you can run it.

## Features:

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

* Java is everywhere
* Write Once, Run Anywhere **(WORA)**

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

## 2. Data Types

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

## 3. `public static void main(String[] args)` explained

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

### Parameters used:

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

OOP stands for Object-Oriented Programming.

Procedural programming is about writing procedures or methods that perform operations on the data, while object-oriented programming is about creating objects that contain both data and methods.

Object-oriented programming has several advantages over procedural programming:

- OOP is faster and easier to execute

* OOP provides a clear structure for the programs

- OOP helps to keep the Java code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug

* OOP makes it possible to create full reusable applications with less code and shorter development time

> 📝: The "**Don't Repeat Yourself**" (DRY) principle is about reducing the repetition of code. You should extract out the codes that are common for the application, and place them at a single place and reuse them instead of repeating it.

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

## 6. Variables in Java:

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

>  Arrays in Java are objects stored in heap memory.

**❓ Difference between Array and ArrayList**

- Array → Fixed size, can hold primitives and objects.
- ArrayList → Dynamic size, only holds objects (wrapper classes needed for primitives).

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

## 9. Functions (methods)

A function (in Java, commonly called a **method**) is a block of code that performs a specific task. Methods help in *code reusability* and *modularity*.

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
First `display()` is called by  using `a1` object of class `abc`, it will set the values of `a` and `b` as 10, 20 respectively.
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

    * With return value (e.g., `int add()` returns a number).

    * Without return value (`void greet()` just performs an action).

> 📝 Method Signature → Consists of method name and parameter list.

Example: `add(int a, int b)` is the method signature.

📝 **Difference between Function and Method:**

- In general programming → "Function" = **block of reusable code.**
- In Java → **functions are always inside a class, so they’re called methods.**


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

