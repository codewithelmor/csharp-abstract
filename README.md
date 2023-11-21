# Abstract

In C#, the **`abstract`** keyword is used to define an abstract class or abstract members within a class. Here are the key points related to the use of **`abstract`**:

1. **`Abstract Class`**:
* An abstract class is a class that cannot be instantiated on its own. It serves as a base class for other classes.
* It may contain both abstract and non-abstract (concrete) members.
* Abstract classes can have constructors, fields, properties, methods (abstract or not), and events.

```csharp
public abstract class Shape
{
    // Abstract method - to be implemented by derived classes
    public abstract void Draw();

    // Concrete method
    public void Move()
    {
        Console.WriteLine("Moving the shape");
    }
}
```

2. **`Abstract Method`**:
* An abstract method is a method declared without an implementation in the abstract class.
* Any class that derives from the abstract class must provide an implementation for all the abstract methods.

```csharp
public abstract class Shape
{
    // Abstract method - no implementation
    public abstract void Draw();
}
```

3. **`Derived Class Implementation`**:
* When a class inherits from an abstract class, it must provide concrete implementations for all abstract members.

```csharp
public class Circle : Shape
{
    // Concrete implementation of the abstract method
    public override void Draw()
    {
        Console.WriteLine("Drawing a circle");
    }
}
```

Usage of abstract classes and methods allows you to create a hierarchy of classes with a common base class, ensuring that certain methods are implemented by derived classes while providing a common interface and shared functionality.
