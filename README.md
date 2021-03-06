# Learning-Python-Design-Patterns

《学习Python设计模式－第二版》本书16年2月上市  

`第二版，第一章预览`

# Chapter 1. Introduction to Design Patterns

In this chapter, we will go through the basics of object-oriented programming and discuss the object-oriented design principles in detail. This will get us prepared for the advanced topics covered later in the book. This chapter will also give a brief introduction to the concept of design patterns so that you will be able to appreciate the context and application of design patterns in software development. Here we also classify the design patterns under three main aspects—creational, structural, and Behavioral patterns. So, essentially, we will cover the following topics in this chapter:  

本章，我们会了解面向对象编程的基础，然后讨论面向对象设计原则的细节。这会给我们在本书稍后覆盖的搞基话题做好准备。本章对设计模式概念做了一个简要说明，这样你就能够理解上下文，以及软件开发中的应用设计模式。这里我们也对设计模式分为三个主要方面：创建模式，结构模式、以及行为模式。所以，基本上，在本章我们涵盖一下话题：  

- Understanding object-oriented programming
- Discussing object-oriented design principles
- Understanding the concept of design patterns and their taxonomy and context
- Discussing patterns for dynamic languages
- Classifying patterns—creational pattern, structural pattern, and behavioral pattern

- 理解面向对象编程
- 讨论面向对象的设计原则
- 理解设计模式的概念及其分类方法和上下文
- 讨论动态语言
- 划分设计——创建模式、结构模式和行为模式

## Understanding object-oriented programming 理解面向对象编程

Before you start learning about design patterns, it's always good to cover the basics and go through object-oriented paradigms in Python. The object-oriented world presents the concept of objects that have attributes (data members) and procedures (member functions). These functions are responsible for manipulating the attributes. For instance, take an example of the Car object. The Car object will have attributes such as fuel level, isSedan, speed, and steering wheel and coordinates, and the methods would be accelerate() to increase the speed and takeLeft() to make the car turn left. Python has been an object-oriented language since it was first released. As they say, everything in Python is an object. Each class instance or variable has its own memory address or identity. Objects, which are instances of classes, interact among each other to serve the purpose of an application under development. Understanding the core concepts of object-oriented programming involves understanding the concepts of objects, classes, and methods.  

再开始学习设计模式之前，概括基础内容的好办法是了解Python中的面向对象范式。  

## Objects 对象

The following points describe objects:  

- They represent entities in your application under development.
- Entities interact among themselves to solve real-world problems.
- For example, Person is an entity and Car is an entity. Person drives Car to move from one location to the other.

它们表示开发时位于应用中的实体。
实体之前互相交互以解决真实世界中的问题。
例如，人是一个实体，汽车是一个实体。人驾驶汽车从另一个地方去向另外一个地方

## Classes 类

Classes help developers to represent real-world entities:  

类帮助开发者表现物理世界的实体：  

- Classes define objects in attributes and behaviors. Attributes are data members and behaviors are manifested by the member functions
- Classes consist of constructors that provide the initial state for these objects
- Classes are like templates and hence can be easily reused

- 类使用属性和行为定义对象。属性来自于成员数据，行为由成员函数表示。
- 类由提供了对象初始状态的构造起组成。
- 类类似于模板，因此也是可以被重复使用的。 

For example, class Person will have attributes name and age and member function gotoOffice() that defines his behavior for travelling to office for work.  

例如，类Person拥有属性name和age以及定义个人的度假归来上班行为的函数gotoOffice()。  

## Methods 方法

The following points talk about what methods do in the object-oriented world:  

以下几点谈论了在面向对象的世界中方法可以用来做什么事情：  

- They represent the behavior of the object
- Methods work on attributes and also implement the desired functionality

- 表现对象的行为。
- 方法作用于属性而且还实现了所需的功能。

A good example of a class and object created in Python v3.5 is given here:  

这里给出的是在Python 3.5中一个创建类和对象的例子：  

```python
class Person(object):

    def __init__(self, name, age):  #constructor

        self.name = name    #data members/ attributes

        self.age = age

    def get_person(self,):   # member function

         return "<Person (%s, %s)>" % (self.name, self.age)


p = Person("John", 32)    # p is an object of type Person

print("Type of Object:", type(p), "Memory Address:", id(p))
```

The output of the preceding code should look as follows:

上面代码的输出大概如此：  

img:omit  

## Major aspects of object-oriented programming 面向对象编程的主要方向

Now that we have understood the basics of object-oriented programming, let's dive into the major aspects of OOP.  

现在我们已经理解了面向对象编程的基础，我们来更深入的学习OOP的主要方向

 
### Encapsulation 封装

The key features of encapsulation are as follows:  

封装的关键特性如下：  

- An object's behavior is kept hidden from the outside world or objects keep their state information private.
- Clients can't change the object's internal state by directly acting on them; rather, clients request the object by sending messages. Based on the type of requests, objects may respond by changing their internal state using special member functions such as get and set.
- In Python, the concept of encapsulation (data and method hiding) is not implicit, as it doesn't have keywords such as public, private, and protected (in languages such as C++ or Java) that are required to support encapsulation. Of course, accessibility can be made private by prefixing __ in the variable or function name.

- 对象的行为对外部世界进行了隐藏，或者对象保证自身状态信息的私有。
- 用户不能够改变直接地影响对象从而改变对象的内部状体，更确切地是用户透过发送消息来请求对象。是请求而定，对象使用特殊成员函数比如get和set来改变自身内部的状态以回应用户的请求。
- 在Python中，封装的概念（数据和方法的隐藏）不是隐式的，因为它不会有诸如public，private和protected（在C＋＋和Java语言中即是如此）这类关键字。当然，访问也可以是私有的，通过对变量或者函数名称的设置`_`前缀即可。  
 
### Polymorphism 多态

The major features of polymorphism are as follows:  

多态的主要特性如下

- Polymorphism can be of two types:
    - An object provides different implementations of the method based on input parameters
    - The same interface can be used by objects of different types
- In Python, polymorphism is a feature built-in for the language. For example, the + operator can act on two integers to add them or can work with strings to concatenate them

- 多态拥有两种类型：
    - 对象基于输入参数提供了不同的方法实现
    - 相同的接口能够被做对象的不同类型
- 在Python中，多态是一种语言内建的特性。例如，＋预算符可以作用于两个整数，并将它们相加，或者把字符串连接起来

In the following example, strings, tuples, or lists can all be accessed with an integer index. This shows how Python demonstrates polymorphism in built-in types:  

下面的例子中，字符串、元组、

```python
a = "John"

b = (1,2,3)

c = [3,4,6,8,9]

print(a[1], b[0], c[2])
```

### Inheritance 继承

The following points help us understand the inheritance process better:  

以下要点能够帮助我们更好地理解继承过程：  

- Inheritance indicates that one class derives (most of its) functionality from the parent class.
- Inheritance is described as an option to reuse functionality defined in the base class and allow independent extensions of the original software implementation.
- Inheritance creates hierarchy via the relationships among objects of different classes. Python, unlike Java, supports multiple inheritance (inheriting from multiple base classes).

In the following code example, class A is the base class and class B derives its features from class A. So, the methods of class A can be accessed by the object of class B:  

```python
class A:

    def a1(self):

        print("a1")



class B(A):

    def b(self):

        print("b")





b = B()

b.a1()
```

### Abstraction

The key features of abstraction are as follows:  

- It provides you with a simple interface to the clients, where the clients can interact with class objects and call methods defined in the interface
- It abstracts the complexity of internal classes with an interface so that the client need not be aware of internal implementations

In the following example, internal details of the Adder class are abstracted with the add() method:  

```python
class Adder:

    def __init__(self):

        self.sum = 0

    def add(self, value):

        self.sum += value


acc = Adder()

for i in range(99):

    acc.add(i)

print(acc.sum)
```

 
### Composition 合成

Composition refers to the following points:  

合成涵盖以下要点：  

- It is a way to combine objects or classes into more complex data structures or software implementations
- In composition, an object is used to call member functions in other modules thereby making base functionality available across modules without inheritance

In the following example, the object of class A is composited under class B:  

在下面的例子中，类A的对象是由下面类B合成的：  

```python
class A(object):

    def a1(self):

        print("a1")


class B(object):

    def b(self):

        print("b")

        A().a1()


objectB = B()

objectB.b()
```

## Object-oriented design principles 面向对象的设计原则

Now, let's talk about another set of concepts that are going to be crucial for us. These are nothing but the object-oriented design principles that will act as a toolbox for us while learning design patterns in detail.  

现在，我们来说一说另外一组对我们特别重要的概念。
 
### The open/close principle 开发／闭合原则

The open/close principle states that classes or objects and methods should be open for extension but closed for modifications.  

What this means in simple language is, when you develop your software application, make sure that you write your classes or modules in a generic way so that whenever you feel the need to extend the behavior of the class or object, then you shouldn't have to change the class itself. Rather, a simple extension of the class should help you build the new behavior.  

For example, the open/close principle is manifested in a case where a user has to create a class implementation by extending the abstract base class to implement the required behavior instead of changing the abstract class.  

Advantages of this design principle are as follows:  

- Existing classes are not changed and hence the chances of regression are less
- It also helps maintain backward compatibility for the previous code
 
### The inversion of control principle 倒向控制原则

The inversion of control principle states that high-level modules shouldn't be dependent on low-level modules; they should both be dependent on abstractions. Details should depend on abstractions and not the other way round.  

倒向控制原则规定高级模块不应该依赖于低级模块；它们两都应该依赖于抽象。

This principle suggests that any two modules shouldn't be dependent on each other in a tight way. In fact, the base module and dependent module should be decoupled with an abstraction layer in between.  

This principle also suggests that the details of your class should represent the abstractions. In some cases, the philosophy gets inverted and implementation details itself decide the abstraction, which should be avoided.  

Advantages of the inversion of control principle are as follows:  

- The tight coupling of modules is no more prevalent and hence no complexity/rigidity in the system
- As there is a clear abstraction layer between dependent modules (provided by a hook or parameter), it's easy to deal with dependencies across modules in a better way

### The interface segregation principle 接口隔离原则

As the interface segregation principle states, clients should not be forced to depend on interfaces they don't use.  

This principle talks about software developers writing their interfaces well. For instance, it reminds the developers/architects to develop methods that relate to the functionality. If there is any method that is not related to the interface, the class dependent on the interface has to implement it unnecessarily.  

For example, a Pizza interface shouldn't have a method called add_chicken(). The Veg Pizza class based on the Pizza interface shouldn't be forced to implement this method.  

Advantages of this design principle are as follows:  

- It forces developers to write thin interfaces and have methods that are specific to the interface
- It helps you not to populate interfaces by adding unintentional methods

### The single responsibility principle 单一负责原则

As the single responsibility principle states, a class should have only one reason to change.  

单一负责原则规定类只能有一个改变的理由：  

This principle says that when we develop classes, it should cater to the given functionality well. If a class is taking care of two functionalities, it is better to split them. It refers to functionality as a reason to change. For example, a class can undergo changes because of the difference in behavior expected from it, but if a class is getting changed for two reasons (basically, changes in two functionalities), then the class should be definitely split.  

Advantages of this design principle are as follows:  

- Whenever there is a change in one functionality, this particular class needs to change, and nothing else
- Additionally, if a class has multiple functionalities, the dependent classes will have to undergo changes for multiple reasons, which gets avoided
 
### The substitution principle 替换原则

The substitution principle states that derived classes must be able to completely substitute the base classes.  

This principle is pretty straightforward in the sense that it says when application developers write derived classes, they should extend the base classes. It also suggests that the derived class should be as close to the base class as possible so much so that the derived class itself should replace the base class without any code changes.  

## The concept of design patterns 设计模式的概念

Finally, now is the time that we start talking about design patterns! What are design patterns?  

到最后了，现在是时候讨论一下设计模式了！到底什么是设计模式呢？  

Design patterns were first introduced by GoF (Gang of Four), where they mentioned them as being solutions to given problems. If you would like to know more, GoF refers to the four authors of the book, Design Patterns: Elements of Reusable Object-Oriented Software. The book's authors are Erich Gamma, Richard Helm, Ralph Johnson, and John Vlissides, with a foreword by Grady Booch. This book covers software engineering solutions to the commonly occurring problems in software design. There were 23 design patterns first identified, and the first implementation was done with respect to the Java program language. Design patterns are discoveries and not an invention in themselves.  

The key features of design patterns are as follows:  

- They are language-neutral and can be implemented across multiple languages
- They are dynamic, as new patterns get introduced every now and then
- They are open for customization and hence useful for developers

Initially, when you hear about design patterns, you may feel the following:  

- It's a panacea to all the design problems that you've had so far
- It's an extraordinary, specially clever way of solving a problem
- Many experts in software development world agree to these solutions
- There's something repeatable about the design, hence the word pattern

You too must have attempted to solve the problems that a design patterns intends to, but maybe your solution was incomplete, and the completeness that we're looking for is inherent or implicit in the design pattern. When we say completeness, it can refer to many factors such as the design, scalability, reuse, memory utilization, and others. Essentially, a design pattern is about learning from others' successes rather than your own failures!  

Another interesting discussion that comes up on design patterns is—when do I use them? Is it in the analysis or design phase of Software Development Life Cycle (SDLC)?  

Interestingly, design patterns are solutions to known issues. So they can be very much used in analysis or design, and as expected, in the development phase because of the direct relation in the application code.  

### Advantages of design patterns 设计模式的优点

The advantages of design patterns are as follows:  

- They are reusable across multiple projects
- The architectural level of problems can be solved
- They are time-tested and well-proven, which is the experience of developers and architects
- They have reliability and dependence
 
### Taxonomy of design patterns 设计模式的分类

Not every piece of code or design can be termed as a design pattern. For example, a programming construct or data structure that solves one problem can't be termed as a pattern. Let's understand terms in a very simplistic way below:  

- Snippet: This is code in some language for a certain purpose, for example, DB connectivity in Python can be a code snippet
- Design: A better solution to solve this particular problem
- Standard: This is a way to solve some kind of problems, and can be very generic and applicable to a situation at hand
- Pattern: This is a time-tested, efficient, and scalable solution that will resolve the entire class of known issues
 
### Context – the applicability of design patterns 上下文——设计模式的适用性

To use design patterns efficiently, application developers must be aware of the context where design patterns apply. We can classify the context into the following main categories:  

- Participants: They are classes that are used in design patterns. Classes play different roles to accomplish multiple goals in the pattern.

- Non-functional requirements: Requirements such as memory optimization, usability, and performance fall under this category. These factors impact the complete software solution and are thus critical.

- Trade-offs: Not all design patterns fit in application development as it is, and trade-offs are necessary. These are decisions that you take while using a design pattern in an application.

- Results: Design patterns can have a negative impact on other parts of the code if the context is not appropriate. Developers should understand the consequences and use of design patterns.

## Patterns for dynamic languages 动态语言的模式

Python is a dynamic language like Lisp. The dynamic nature of Python can be represented as follows:  

- Types or classes are objects at runtime.
- Variables can have type as a value and can be modified at runtime. For example, a = 5 and a = "John", the a variable is assigned at runtime and type also gets changed.
- Dynamic languages have more flexibility in terms of class restrictions.
- For example, in Python, polymorphism is built into the language, there are no keywords such as private and protected and everything is public by default.
- Represents a case where design patterns can be easily implemented in dynamic languages.

## Classifying patterns 对模式进行分类

The book by GoF on design patterns spoke about 23 design patterns and classified them under three main categories:  

- Creational patterns
- Structural patterns
- Behavioral patterns

The classification of patterns is done based primarily on how the objects get created, how classes and objects are structured in a software application, and also covers the way objects interact among themselves. Let's talk about each of the categories in detail in this section.  

 
### Creational patterns 创造模式

The following are the properties of Creational patterns:  

- They work on the basis of how objects can be created
- They isolate the details of object creation
- Code is independent of the type of object to be created

An example of a creational pattern is the Singleton pattern.  

 
### Structural patterns 结构模式

The following are the properties of Structural patterns:  

- They design the structure of objects and classes so that they can compose to achieve larger results
- The focus is on simplifying the structure and identifying the relationship between classes and objects
- They focus on class inheritance and composition

An example of a behavior pattern is the Adapter pattern.  

### Behavioral patterns 行为模式

The following are the properties of Behavioral patterns:  

- They are concerned with the interaction among objects and responsibility of objects
- Objects should be able to interact and still be loosely coupled
- An example of a behavioral pattern is the Observer pattern.

## Summary 总结

In this chapter, you learned about the basic concepts of object-oriented programming, such as objects, classes, variables, and features such as polymorphism, inheritance, and abstraction with code examples.  

We are also now aware of object-oriented design principles that we, as developers/architects, should consider while designing an application.  

Finally, we went on to explore more about design patterns and their applications and context in which they can be applied and also discussed their classifications.  

At the end of this chapter, we're now ready to take the next step and study design patterns in detail.  
