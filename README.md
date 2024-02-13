# JavaSE-Abstraction

See the Udemy course: https://www.udemy.com/course/curso-certificacion-profesional-desarrollador-java-se-11

In Java, abstraction is one of the four fundamental Object-Oriented Programming (OOP) principles, alongside encapsulation, inheritance, and polymorphism. 

Abstraction involves simplifying complex systems by modeling classes based on the essential properties and behaviors they share, while hiding the unnecessary details.

Here's a simple example to illustrate abstraction in Java:

```java
// Abstract class
abstract class Shape {
    // Abstract method (no implementation)
    abstract void draw();

    // Concrete method
    void displayArea() {
        System.out.println("Area: " + calculateArea());
    }

    // Abstract method to calculate area (to be implemented by subclasses)
    abstract double calculateArea();
}

// Concrete subclass
class Circle extends Shape {
    double radius;

    Circle(double radius) {
        this.radius = radius;
    }

    // Implementation of the abstract method
    void draw() {
        System.out.println("Drawing Circle");
    }

    // Implementation of the abstract method
    double calculateArea() {
        return Math.PI * radius * radius;
    }
}

// Concrete subclass
class Square extends Shape {
    double side;

    Square(double side) {
        this.side = side;
    }

    // Implementation of the abstract method
    void draw() {
        System.out.println("Drawing Square");
    }

    // Implementation of the abstract method
    double calculateArea() {
        return side * side;
    }
}

// Main class
public class Main {
    public static void main(String[] args) {
        // Using abstraction
        Shape circle = new Circle(5);
        Shape square = new Square(4);

        circle.draw();
        circle.displayArea();

        square.draw();
        square.displayArea();
    }
}
```

In this example, Shape is an abstract class that declares two abstract methods: draw() and calculateArea(). 

The draw() method is common to all shapes, but its implementation varies for each shape. The calculateArea() method is left abstract, as the formula for calculating the area differs for different shapes.

The concrete subclasses, Circle and Square, extend the abstract class Shape and provide their specific implementations for the abstract methods.

In the Main class, we create instances of Circle and Square using the abstract type Shape. This allows us to use abstraction to treat different shapes uniformly while taking advantage of their specific implementations when needed.

In essence, abstraction in Java helps in creating a simplified view of a complex system by focusing on the essential features and hiding the unnecessary details.
