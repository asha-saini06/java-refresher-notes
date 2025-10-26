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

#### 💬 Key Takeaways: 
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

This distinction avoids confusion between Strings and Arrays — both have “length,” but one uses a *method* and the other a *field*.

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
- Java is **pass-by-value**, even for objects — but the *value passed* is the **reference** to the object.
So both caller and callee refer to the *same* object in memory.

- This means that **modifying an object inside a method** will reflect in the calling method,
because both point to the same memory address.

- If you create a **new object** inside the method and reassign the parameter, it won’t affect the original reference outside the method.

- When an **object** is passed to a method, Java passes the **reference value** (address in memory).
This means:
    - The method can call the object’s methods.
    - The method can modify the object’s fields.

- **Objects are never passed by value** (*copy of the object*) —
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

* After a string literal, all the `+` will be treated as string concatenation operator.

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

### Key Features of the String Class:

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

### Important Methods:
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

### join
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