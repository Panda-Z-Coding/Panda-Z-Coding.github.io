# **Java中的子类与继承基础知识**

## 目录

- [子类与父类](#子类与父类)
- [子类继承性](#子类继承性)
- [子类与对象](#子类与对象)
- [成员变量的隐蔽和方法重写](#成员变量的隐蔽和方法重写)
- [super关键字](#super关键字)
- [final关键字](#final关键字)
- [对象的上转型对象](#对象的上转型对象)
- [继承与多态](#继承与多态)
- [abstract类与abstract方法](#abstract类与abstract方法)
- [面向抽象编程](#面向抽象编程)
- [开-闭原则](#开-闭原则)

## 子类与父类

在Java中，通过**继承**机制，子类（Subclass）可以继承父类（Superclass）的属性和方法。这样可以实现代码的复用和逻辑的扩展。

```java
class Parent {
    int x = 10;
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    void show() {
        System.out.println("Child show");
    }
}
```

## 子类继承性

子类不仅继承了父类的属性和方法，还可以新增自己的属性和方法，从而在保持父类基本功能的同时，增加新的功能。

```java
class Child extends Parent {
    int y = 20;
    void show() {
        System.out.println("Value of y: " + y);
    }
}
```

## 子类与对象

通过子类创建的对象，可以访问父类的所有公共属性和方法。

```java
Child child = new Child();
child.display(); // 调用父类的方法
child.show();    // 调用子类的方法
```

## 成员变量的隐蔽和方法重写

- **成员变量的隐蔽**：如果子类中定义了与父类同名的成员变量，子类对象将隐藏父类的变量。

- **方法重写**：子类可以重写父类的方法，以提供特定的实现。

```java
class Parent {
    int x = 10;
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    int x = 20; // 隐蔽父类的x
    @Override
    void display() {
        System.out.println("Child display");
    }
}
```

## super关键字

- **super**关键字用于访问父类的成员变量和方法，甚至是父类的构造方法。

```java
class Parent {
    int x = 10;
    void display() {
        System.out.println("Parent display");
    }
}

class Child extends Parent {
    int x = 20;
    void show() {
        System.out.println("Child x: " + x);
        System.out.println("Parent x: " + super.x);
        super.display();
    }
}
```

## final关键字

- **final**关键字可以用于类、方法和变量：
  - final类不能被继承。
  - final方法不能被重写。
  - final变量的值不能被修改。

```java
final class FinalClass {
    // 不能被继承
}

class Test {
    final void display() {
        // 不能被重写
    }
}
final int f = 0  //f 不能被修改
      f = 1; //Error 
```

## 对象的上转型对象

- **上转型**（Upcasting）是指将子类对象转换为父类类型。上转型后，子类对象只能调用父类中声明的方法，但实际运行时仍调用子类重写的方法。
- **语法** 父类 类名 = new 子类;
- **对象与上转型对象**
  
![对应关系](https://github.com/Leno0z/MyBolg/assets/157597971/b6651077-4915-4cb6-9fa7-593baa846787)

```java
Parent p = new Child();
p.display(); // 调用子类的display方法
```

## 继承与多态

- **多态**（Polymorphism）是指同一个方法在不同对象上有不同的表现形式。通过继承和方法重写实现多态。

```java
// 定义一个父类Animal
class Animal {
    void makeSound() {
        System.out.println("Some generic animal sound");
    }
}
​
// Dog类继承了Animal类，并重写了makeSound方法
class Dog extends Animal {
    @Override
    void makeSound() {
        System.out.println("Bark");
    }
}
​
// Cat类继承了Animal类，并重写了makeSound方法
class Cat extends Animal {
    @Override
    void makeSound() {
        System.out.println("Meow");
    }
}
​
// Zoo类展示多态应用
class Zoo {
    public void makeAnimalSound(Animal animal) {
        animal.makeSound();
    }
​
    public static void main(String[] args) {
        Zoo zoo = new Zoo();
​
        Animal dog = new Dog();
        Animal cat = new Cat();
​
        zoo.makeAnimalSound(dog); // 输出：Bark
        zoo.makeAnimalSound(cat); // 输出：Meow
    }
}
```

## abstract类与abstract方法

- **abstract类**不能实例化，只能被子类继承，并且可以包含抽象方法。
- **abstract方法**没有实现，需要在子类中重写。

```java
abstract class AbstractClass {
    abstract void abstractMethod();
    
    void normalMethod() {
        System.out.println("This is a normal method.");
    }
}

class ConcreteClass extends AbstractClass {
    @Override
    void abstractMethod() {
        System.out.println("Abstract method implementation.");
    }
}
```

## 面向抽象编程

- **面向抽象编程**的核心思想是通过接口或抽象类来定义规范，而具体实现由具体的子类负责，从而提高代码的灵活性和可扩展性。

```java
interface Animal {
    void makeSound();
}

class Dog implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Bark");
    }
}

class Cat implements Animal {
    @Override
    public void makeSound() {
        System.out.println("Meow");
    }
}
```

## 开-闭原则

- **开-闭原则**（Open-Closed Principle）指软件实体（类、模块、函数等）应该对扩展开放，对修改关闭。通过继承和接口实现，能够在不修改已有代码的基础上扩展新的功能。

```java
abstract class Shape {
    abstract void draw();
}

class Circle extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square extends Shape {
    @Override
    void draw() {
        System.out.println("Drawing Square");
    }
}
```
### 6/14 IN 2024
