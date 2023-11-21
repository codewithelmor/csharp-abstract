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

## Static Class

In C#, a **`static class`** cannot be **`abstract`**. A **`static class`** is **`sealed`** and cannot be **`instantiated`** or used as a base class. On the other hand, an **`abstract class`** is meant to be **`subclassed`**, and it may contain abstract members that must be implemented by derived classes. Since a static class cannot be instantiated or inherited, it doesn't make sense for it to be abstract.

If you want to create an abstract class in C#, you would use the abstract keyword for a regular (non-static) class, allowing it to have abstract members that must be implemented by any derived classes.

## Virtual

In C#, both **`abstract`** and **`virtual`** are keywords used in the context of classes and methods, but they serve different purposes.

1. **`Abstract`**:
* Applied to methods, properties, events, and indexers in an abstract class.
* An abstract method has no implementation in the abstract class and must be implemented by any non-abstract derived class.
* An abstract class cannot be instantiated and may contain a mix of abstract and non-abstract members.

```csharp
public abstract class Shape
{
    public abstract void Draw();
}
```

2. **`Virtual`**:
* Applied to methods, properties, events, and indexers in a class.
* A virtual method provides a default implementation in the base class but can be overridden by derived classes using the **`override`** keyword.
* A class with a virtual method can be instantiated, and the virtual method can be used as is or overridden.

```csharp
public class Animal
{
    public virtual void MakeSound()
    {
        Console.WriteLine("Generic animal sound");
    }
}

public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Bark");
    }
}
```

In summary, **`abstract`** is used to define a blueprint for derived classes, requiring them to provide specific implementations. **`virtual`** allows a method in a base class to be overridden in derived classes, providing a default implementation but allowing customization.
