# Java SE Object Oriented Programming summary

https://www.youtube.com/playlist?list=PLqleLpAMfxGCbdaJ6SoExDfHrTfRDeWeG

https://www.mygreatlearning.com/blog/oops-concepts-in-java/

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/be4614c8-3307-4e41-88c1-0514090a123d)

**Object-Oriented Programming (OOP)**  is a paradigm that revolves around the concept of "objects"

These **objects** are **instances of classes**, which serve as blueprints for creating tangible, real-world entities in your code

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/7e2f0237-afcc-4ebe-b1a7-3d109fa3b03d)

Let's study the main principles in OOP: 

- Abstraction

- Encapsulation

- Inheritance

- Polymorphism

- Association

- Aggregation

- Composition

- Coupling

- Cohesion

## 1. Class

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/93ae42e4-caac-4d0c-aa83-07dfb3030e13)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/cec8cc62-0d19-4c8b-a375-6b72dbf8531f)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/5ed30874-e289-47a1-ba0f-fec8f328122a)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/6547fcc5-1299-4849-9064-72246f4dfc76)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/6bef4e1e-7efa-43d0-85df-9c4f0516fda9)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/96b066fb-2df2-4dbf-8cb4-14dece165f7d)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/92586afc-6f1a-437b-898b-4a1c61c9694f)


## 1. Abstraction

https://www.softwaretestinghelp.com/what-is-abstraction-in-java/

Youtube video: https://youtu.be/9R42iyJsgBw

Hiding internal details and showing functionality is known as abstraction

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/17267f5f-0250-4c32-a16a-c256bc75a796)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/29085ed1-e362-47fe-8a64-dc0734af433d)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/e41d776a-7200-42b7-b967-029a15ea357e)

For example phone call, we don't know the internal processing. In Java, we use abstract class and interface to achieve abstraction

**Abstraction sample**

```java
abstract class PhoneCall {
    abstract void makeCall();
}

class Smartphone extends PhoneCall {
    @Override
    void makeCall() {
        System.out.println("Dialing the number on a touchscreen interface.");
    }
}

public class TestAbstraction {
    public static void main(String[] args) {
        PhoneCall myPhone = new Smartphone();
        myPhone.makeCall();  // Outputs: Dialing the number on a touchscreen interface.
    }
}
```

## 2. Encapsulation

https://www.enjoyalgorithms.com/blog/encapsulation-in-oops

Binding (or wrapping) code and data together into a single unit are known as encapsulation

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/330fb0fc-6b51-4837-9ec5-ceacae17c500)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/5924bfe9-2100-442b-ac67-f44b81ae304a)

For example, a capsule, it is wrapped with different medicines.A java class is the example of encapsulation

**Encapsulation sample**

```java
public class MedicineCapsule {
    private String medicineName;
    private double dosage;

    public MedicineCapsule(String medicineName, double dosage) {
        this.medicineName = medicineName;
        this.dosage = dosage;
    }

    public String getMedicineName() {
        return medicineName;
    }

    public void setMedicineName(String medicineName) {
        this.medicineName = medicineName;
    }

    public double getDosage() {
        return dosage;
    }

    public void setDosage(double dosage) {
        this.dosage = dosage;
    }
}
```

## 3. Inheritance

https://www.enjoyalgorithms.com/blog/inheritance-in-java

When one object acquires all the properties and behaviors of a parent object, it is known as inheritance. 

It provides **code reusability**. It is used to achieve runtime polymorphism

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/b1f71391-561c-485e-b4c7-ee26ac0589f1)

**Inheritance sample**

```java
class Animal {
    public void eat() {
        System.out.println("This animal eats food.");
    }
}

class Dog extends Animal {
    @Override
    public void eat() {
        System.out.println("Dog eats dog food.");
    }
}

public class TestInheritance {
    public static void main(String[] args) {
        Dog myDog = new Dog();
        myDog.eat();  // Outputs: Dog eats dog food.
    }
}
```

## 4. Polymorphism

https://panditaarchit98.medium.com/know-everything-about-polymorphism-in-java-67ba0dd2804b

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/3693135f-ead1-4893-bc53-a94fe29b8b16)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/aae4f429-bf43-4aef-ad1a-55ccdc276218)

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/283f8b2a-a577-45e9-a405-1814e02cf56b)

Polymorphism in Java is a concept that allows objects of different classes to be treated as objects of a common class

It enables objects to behave differently based on their specific class type

In Java, we use method **overloading** and method **overriding** to achieve polymorphism

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/8c78e14b-c3dd-490c-9fe4-087eff4ac856)

**Polymorphism sample**

```java
class Calculator {
    // Method overloading
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }
    
    // Method overriding (would normally be in a subclass, shown here for simplicity)
    @Override
    public String toString() {
        return "Calculator class";
    }
}

public class TestPolymorphism {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println(calc.add(5, 3));     // Outputs: 8
        System.out.println(calc.add(5.0, 3.0)); // Outputs: 8.0
    }
}
```

Apart from these concepts, there are some other terms which are used in **Object-Oriented design**:

## 5. Association

Association represents the relationship between the objects. Here, one object can be associated with one object or many objects

There can be four types of association between the objects: One to One One to Many Many to One, and Many to Many

```java
class Student {
    String name;
    // Association between Student and LibraryCard
    LibraryCard card; 

    Student(String name, LibraryCard card) {
        this.name = name;
        this.card = card;
    }
}

class LibraryCard {
    String cardNumber;

    LibraryCard(String cardNumber) {
        this.cardNumber = cardNumber;
    }
}

public class TestAssociation {
    public static void main(String[] args) {
        LibraryCard card = new LibraryCard("123456789");
        Student student = new Student("John Doe", card);
        
        System.out.println(student.name + " has a library card number " + student.card.cardNumber); // Outputs: John Doe has a library card number 123456789
    }
}
```

## 6. Aggregation

This OOPs concept in Java is symbolic of the relationship where one object contains other objects as a part of the state

Aggregation represents a "has-a" relationship but with objects that can exist independently of the containing object

It implies a relationship where the child can exist independently of the parent

```java
class Engine {
    void start() {
        System.out.println("Engine has started.");
    }

    void stop() {
        System.out.println("Engine has stopped.");
    }
}

class Car {
    private final Engine engine; // Car HAS-A Engine

    Car(Engine engine) {
        this.engine = engine;
    }

    void startCar() {
        engine.start();
        System.out.println("Car is running.");
    }

    void stopCar() {
        engine.stop();
        System.out.println("Car has stopped.");
    }
}

public class TestAggregation {
    public static void main(String[] args) {
        Engine myEngine = new Engine();
        Car myCar = new Car(myEngine);
        myCar.startCar();  // Engine has started. Car is running.
        myCar.stopCar();   // Engine has stopped. Car has stopped.
    }
}
```

## 7. Composition

It is one of the **Java OOPs** concepts that represent the strong **relationship between the dependent object and the containing object**

Composition implies a stronger relationship where the **contained objects cannot exist without the container**

It involves a "part-of" relationship where the lifecycle of the contained objects depends on the lifecycle of the container

```java
class Processor {
    void process() {
        System.out.println("Processor is processing data.");
    }
}

class Computer {
    private Processor processor; // Computer HAS-A Processor

    Computer() {
        // Processor is instantiated as part of the Computer's instantiation
        this.processor = new Processor();
    }

    void startComputer() {
        processor.process();
        System.out.println("Computer is ready to be used.");
    }

    // Once Computer is destroyed, Processor will also be destroyed
}

public class TestComposition {
    public static void main(String[] args) {
        Computer myComputer = new Computer();
        myComputer.startComputer();  // Processor is processing data. Computer is ready to be used.
    }
}
```

## 8. Coupling

Coupling refers to the knowledge or information or dependency of another class. It arises when **classes are aware of each other**

If a class has the details information of another class, there is strong coupling

In Java, we use **private**, **protected**, and **public** access modifiers to display the visibility level of a class, method, and field

```java
class Display {
    void displayInfo(String info) {
        System.out.println(info);
    }
}

class Processor {
    Display display = new Display();

    void processInfo(String info) {
        // Moderate coupling - using Display class directly within Processor class
        display.displayInfo(info);
    }
}

public class TestCoupling {
    public static void main(String[] args) {
        Processor proc = new Processor();
        proc.processInfo("Hello, world!");  // Outputs: Hello, world!
    }
}
```

## 9. Cohesion

Cohesion refers to the level of a component which performs a single well-defined task

A single well-defined task is done by a highly cohesive method. The weakly cohesive method will split the task into separate parts

The **java.io package** is a highly cohesive package because it has I/O **related classes and interface**

However, the **java.util** package is a weakly cohesive package because it has **unrelated classes and interfaces**

```java
public class FileManager {
    // Highly cohesive method to read file content
    String readFile(String path) {
        // Implementation to read and return file content
        return "File content";
    }
}

public class TestCohesion {
    public static void main(String[] args) {
        FileManager fileManager = new FileManager();
        System.out.println(fileManager.readFile("example.txt")); // Outputs: File content
    }
}
```
