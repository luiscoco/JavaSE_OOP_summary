# Java SE Object Oriented Programming summary

![image](https://github.com/luiscoco/JavaSE_OOP_summary/assets/32194879/128a1cc7-4a06-41b6-be29-907017774d1c)

## 1. Abstraction

Hiding internal details and showing functionality is known as abstraction

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

Binding (or wrapping) code and data together into a single unit are known as encapsulation

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

When one object acquires all the properties and behaviors of a parent object, it is known as inheritance. It provides code reusability. It is used to achieve runtime polymorphism

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

If one task is performed in different ways, it is known as polymorphism. In Java, we use method overloading and method overriding to achieve polymorphism

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
