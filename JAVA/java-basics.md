# Core Java Basics – Quick Interview Revision Sheet

> Purpose: One-page-style reference of core Java basics for quick revision during interviews. Focus is on names, definitions, and key points – with short examples where useful.[web:1][web:4][web:10][web:13]

---

## Index

- [1. Java Overview](#1-java-overview)
- [2. Java Program Structure](#2-java-program-structure)
- [3. JVM, JRE, JDK](#3-jvm-jre-jdk-just-the-crux)
- [4. Identifiers, Literals, Comments](#4-identifiers-literals-comments)
- [5. Data Types](#5-data-types)
- [6. Variables and Scope](#6-variables-and-scope)
- [7. Type Conversion & Casting](#7-type-conversion--casting)
- [8. Operators](#8-operators-high-level-list)
- [9. Decisions (`if`, `switch`)](#9-control-flow--decisions)
- [10. Loops & Branching](#10-control-flow--loops--branching)
- [11. Arrays](#11-arrays-basics-only)
- [12. Core OOP Concepts](#12-core-oop-concepts-names--one-line)
- [13. Classes, Objects, Constructors](#13-classes-objects-constructors)
- [14. Methods – Basics](#14-methods--basics)
- [15. Access Modifiers, `static`, `final`](#15-access-modifiers--staticfinal)
- [16. Important Core Keywords](#16-important-core-keywords-basic-usage)
- [17. Packages & Imports](#17-packages--imports)
- [18. String Basics](#18-string-basics-non-advanced)
- [19. Wrapper Classes & Autoboxing](#19-wrapper-classes--autoboxing-names-only)
- [20. Basic Exception Concepts](#20-basic-exception-concepts-just-to-not-blank-out)
- [21. Collections – Names Only](#21-collections--only-names-you-must-recognize-no-internals-here)
- [22. Very High-Level Memory Model](#22-very-high-level-memory-model-interview-one-liners)
- [23. `main` Method Essentials](#23-main-method-essentials)
- [24. Java Version Basics](#24-java-version-basics-for-context-only)
- [25. Quick Self-Check Questions](#25-quick-self-check-questions-basics)

---

## 1. Java Overview

- Java is a high-level, class-based, object-oriented, platform-independent language that runs on the Java Virtual Machine (JVM).[web:7][web:13]
- “Write Once, Run Anywhere” comes from compiling to bytecode that runs on any compatible JVM instead of OS-specific binaries.[web:15]
- Main components: JDK (development kit with tools), JRE (runtime environment), JVM (virtual machine executing bytecode).[web:1][web:15]

---

## 2. Java Program Structure

- Order (typical): optional `package`, optional `import` statements, then `class` definition, fields, methods, and `main`.[web:10][web:13]
- Filename must match the public class name, including case, and end with `.java`.[web:15]
- Flow: source `.java` → `javac` compiles to `.class` bytecode → `java` command runs bytecode on the JVM.[web:15]

**Tiny example:**

```java
package com.example;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

---

## 3. JVM, JRE, JDK (Just the Crux)

- JDK = JRE + tools like `javac`, `javadoc`, debuggers; used by developers.[web:1][web:15]
- JRE = JVM + core libraries; used to run Java applications.[web:15]
- JVM loads classes, verifies bytecode, manages memory (heap, stack), and executes instructions.[web:1][web:15]

---

## 4. Identifiers, Literals, Comments

- Identifiers name classes, methods, variables; must not start with a digit and cannot be reserved keywords.[web:10][web:13]
- Literals: numeric (`42`, `3.14`), char (`'A'`), string (`"hello"`), boolean (`true`/`false`).[web:7][web:13]
- Comments: `//` single-line, `/* ... */` multi-line, `/** ... */` Javadoc for API documentation.[web:15]

**Tiny example:**

```java
int count = 10;      // identifier: count, literal: 10
String name = "Max"; // literal: "Max"
/**
 * This is a Javadoc comment.
 */
```

---

## 5. Data Types

### Primitive Types

- Integral: `byte` (8-bit), `short` (16-bit), `int` (32-bit), `long` (64-bit).[web:7][web:9]
- Floating point: `float` (32-bit, single precision), `double` (64-bit, double precision).[web:7][web:9]
- Other: `char` (16-bit Unicode code unit), `boolean` (`true` or `false`).[web:7][web:9]

### Non-Primitive Types

- Classes, interfaces, arrays, enums, and `String` are reference types.[web:1][web:7]
- Variables of non-primitive type store a reference (pointer-like) to objects on the heap.[web:7][web:15]

**Tiny example:**

```java
int age = 25;
double price = 199.99;
char grade = 'A';
boolean active = true;
String city = "Mumbai";
```

---

## 6. Variables and Scope

- Local variables: declared inside methods/blocks; must be initialized before use.[web:1][web:15]
- Instance variables: non-static fields; each object has its own copy.[web:1][web:15]
- Static variables: class-level fields shared by all instances.[web:1][web:15]

**Tiny example (scope):**

```java
public class ScopeDemo {
    int instanceVar = 10;      // instance

    static int staticVar = 20; // static

    void method() {
        int local = 5;         // local
        System.out.println(local);
    }
}
```

---

## 7. Type Conversion & Casting

- Widening: safe, automatic promotion `byte → short → int → long → float → double`.[web:1][web:7]
- Narrowing: explicit cast required, may lose data (e.g., `double` to `int`).[web:1][web:7]
- `String` ↔ primitive: `Integer.parseInt("10")`, `String.valueOf(10)`.[web:1][web:15]

**Tiny example:**

```java
int n = 10;
double d = n;        // widening

double x = 9.7;
int y = (int) x;     // narrowing (y becomes 9)
```

---

## 8. Operators (High-Level List)

- Arithmetic: `+`, `-`, `*`, `/`, `%`.[web:10]
- Relational: `==`, `!=`, `>`, `<`, `>=`, `<=`.[web:9][web:10]
- Logical: `&&`, `||`, `!` (short-circuit for `&&` and `||`).[web:9][web:10]
- Bitwise: `&`, `|`, `^`, `~`, `<<`, `>>`, `>>>`.[web:10]
- Assignment and compound assignment: `=`, `+=`, `-=`, `*=`, `/=`, `%=` etc.[web:9][web:10]
- Ternary: `condition ? a : b` as compact `if-else`.[web:9][web:10]

**Tiny example:**

```java
int a = 5, b = 3;
int max = (a > b) ? a : b; // ternary
```

---

## 9. Control Flow – Decisions

- `if`, `if-else`, `if-else-if` choose blocks based on boolean conditions.[web:7][web:67]
- `switch` is used for multi-branch selection on values like `int`, `String`, `enum` etc.[web:10][web:67]
- Use braces `{}` to clearly define the block associated with `if` or `else` to avoid bugs.[web:64][web:67]

**Tiny example (`if-else`):**

```java
int score = 72;

if (score >= 60) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}
```

**Tiny example (`switch`):**

```java
String day = "MON";
switch (day) {
    case "MON":
        System.out.println("Start of week");
        break;
    case "SUN":
        System.out.println("Weekend");
        break;
    default:
        System.out.println("Midweek");
}
```

---

## 10. Control Flow – Loops & Branching

- Loops: `for`, enhanced `for-each`, `while`, `do-while`.[web:7][web:10][web:55]
- Branching statements: `break` (leave loop/switch), `continue` (skip to next iteration), `return` (exit method).[web:1][web:10]
- Use `for-each` when you just need each element; normal `for` when you also need the index.[web:55]

**Tiny examples:**

```java
// for loop
for (int i = 0; i < 3; i++) {
    System.out.println("i = " + i);
}

// while loop
int n = 3;
while (n > 0) {
    System.out.println(n);
    n--;
}
```

---

## 11. Arrays (Basics Only)

- Fixed-length container of elements of the same type, indexed from `0` to `length - 1`.[web:10][web:13]
- Declaration/creation: `int[] a = new int[3];`, initialization: `int[] b = {1, 2, 3};`.[web:10][web:13]
- Multi-dimensional arrays are arrays of arrays (e.g., `int[][] matrix = new int[2][3];`).[web:1][web:10]

**Tiny example:**

```java
int[] nums = {10, 20, 30};
for (int i = 0; i < nums.length; i++) {
    System.out.println(nums[i]);
}
```

---

## 12. Core OOP Concepts (Names + One-Line)

- Class: blueprint for objects; defines state (fields) and behavior (methods).[web:6][web:12]
- Object: instance of a class; has its own state and can call methods.[web:6][web:12]
- Encapsulation: hide internal state; expose operations via methods and use access modifiers.[web:6][web:12]
- Inheritance: one class extends another to reuse fields/methods (IS-A relationship).[web:6][web:12]
- Polymorphism: one interface, many implementations; overloading (same name, different params) and overriding (subclass changes behavior).[web:1][web:12]
- Abstraction: show essential features; hide implementation using abstract classes or interfaces.[web:1][web:12]

**Tiny example:**

```java
class Animal {
    void speak() { System.out.println("Some sound"); }
}

class Dog extends Animal {
    @Override
    void speak() { System.out.println("Bark"); }
}
```

---

## 13. Classes, Objects, Constructors

- Class members include fields, methods, constructors, initializer blocks, and nested types.[web:15]
- Constructor: same name as class, no return type; used to initialize new objects.[web:1][web:15]
- `this` refers to the current object; used to access fields or call other constructors.[web:1][web:15]

**Tiny example:**

```java
public class User {
    private String name;

    public User(String name) { // constructor
        this.name = name;
    }
}
```

---

## 14. Methods – Basics

- Method signature: modifiers + return type + name + parameter list.[web:15]
- Overloading: same method name, different parameter list; resolved at compile time.[web:1][web:4]
- `static` methods belong to the class; can be called without an instance.[web:1][web:15]

**Tiny example:**

```java
class MathUtil {
    static int square(int x) {
        return x * x;
    }

    // overloaded
    static int square(int x, int y) {
        return x * x + y * y;
    }
}
```

---

## 15. Access Modifiers & `static`/`final`

- `public` (everywhere), `protected` (package + subclasses), default/package-private (package), `private` (within class).[web:1][web:15]
- `static`: class-level – shared fields, utility methods, static blocks.[web:1][web:15]
- `final`: variable cannot be reassigned; method cannot be overridden; class cannot be extended.[web:1][web:3]

**Tiny example:**

```java
public final class Constants {
    public static final double PI = 3.14159;
}
```

---

## 16. Important Core Keywords (Basic Usage)

- `this` (current object), `super` (parent class reference).[web:1][web:3]
- `static`, `final`, `abstract` (no instances of abstract class; may have abstract methods).[web:1][web:3]
- `package`, `import`, `new`, `return`.[web:3][web:10]
- Control keywords: `if`, `else`, `switch`, `case`, `default`, `for`, `while`, `do`, `break`, `continue`.[web:3][web:10]

---

## 17. Packages & Imports

- Package groups related classes; declared once at top: `package com.example.app;`.[web:1][web:10]
- `import` brings types into scope: `import java.util.List;`.[web:3][web:10]
- Default package (no package statement) is allowed but discouraged for real projects.[web:15]

---

## 18. String Basics (Non-Advanced)

- `String` is an immutable sequence of characters in `java.lang`.[web:1][web:13]
- Use `equals` to compare content, not `==` (which compares references).[web:4][web:13]
- Common methods: `length()`, `substring`, `charAt`, `toUpperCase`, `toLowerCase`.[web:4][web:13]

**Tiny example:**

```java
String s1 = "Java";
String s2 = "Java";

System.out.println(s1.equals(s2)); // true
System.out.println(s1 == s2);      // may be true due to string pool, but don't rely on it
```

---

## 19. Wrapper Classes & Autoboxing (Names Only)

- Wrapper classes: `Integer`, `Long`, `Double`, `Float`, `Character`, `Boolean`, `Byte`, `Short`.[web:1][web:13]
- Autoboxing: primitive to wrapper automatically; unboxing: wrapper to primitive.[web:4][web:15]
- Necessary for generic collections which work with reference types.[web:1][web:11]

**Tiny example:**

```java
List<Integer> list = new ArrayList<>();
list.add(10);   // int autoboxed to Integer
int x = list.get(0); // unboxed to int
```

---

## 20. Basic Exception Concepts (Just to Not Blank Out)

- Exceptions are objects representing error conditions that interrupt normal flow.[web:11][web:15]
- Checked exceptions extend `Exception` (excluding `RuntimeException`) and must be declared or handled; unchecked extend `RuntimeException`.[web:11]
- Keywords: `try`, `catch`, `finally`, `throw`, `throws`.[web:3][web:11]

**Tiny example:**

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException ex) {
    System.out.println("Cannot divide by zero");
}
```

---

## 21. Collections – Only Names You Must Recognize (No Internals Here)

- Core interfaces: `List`, `Set`, `Queue`, `Map`.[web:5][web:11]
- Common implementations: `ArrayList`, `LinkedList`, `HashSet`, `TreeSet`, `HashMap`, `LinkedHashMap`, `TreeMap`.[web:5][web:11]
- Located primarily in `java.util` package.[web:5][web:11]

---

## 22. Very High-Level Memory Model (Interview One-Liners)

- Stack: stores method call frames and local variables; grows/shrinks with calls.[web:1][web:15]
- Heap: stores objects and arrays; shared across threads; cleaned by GC.[web:1][web:15]
- Method area / metaspace: stores class metadata, static fields, and constant pool depending on JVM implementation.[web:1][web:15]

---

## 23. `main` Method Essentials

- Standard signature: `public static void main(String[] args)`.[web:15]
- `String[] args` holds command-line arguments; length may be zero.[web:15]
- The class containing `main` is the entry point for standalone Java apps.[web:15]

---

## 24. Java Version Basics (For Context Only)

- Newer Java versions add features like `var` (local type inference), enhanced `switch`, and more APIs.[web:10][web:4]
- LTS versions (e.g., 8, 11, 17, 21) are most common in production.[web:8]
- For “basics”, focus on fundamentals available across versions (types, control flow, OOP, exceptions, core collections).[web:4][web:8]

---

## 25. Quick Self-Check Questions (Basics)

Use these to mentally verify understanding (no answers here, just triggers).

- What are the eight primitive data types and their typical sizes?[web:7][web:9]
- Difference between `==` and `equals` for `String`?[web:4][web:13]
- Explain `public static void main(String[] args)` in one line.[web:15]
- What is the difference between an array and an `ArrayList` at a high level?[web:5][web:11]
- Describe encapsulation and one way to implement it in Java.[web:6][web:12]
- What is the purpose of the `final` keyword on a variable, method, and class?[web:1][web:3]
- What is the difference between checked and unchecked exceptions (one sentence)?[web:11]

---

> Tip: During revision, pick a section from the index, jump via the link, and try explaining that topic plus example out loud in 30–60 seconds.