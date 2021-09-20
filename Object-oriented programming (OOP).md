# What  Is Object Oriented Programming?

**Object-Oriented Programming (OOP)**  is a programming paradigm based on the concept of "objects".

**A programming paradigm** : is a style of programming , a way of thinking about software construction.

Programming paradigm does not refer to a specific language but rather to a way to build program or a methodology to      apply.

Example on programming paradigm like Procedural (FORTRAN ,COBAL) , OOP(C++,JAVA) ,Declarative(Prolog),Functional(LISP),Event-driven(VISUAL BASIC , c#).

Example on object Student Housing Environment : Students , Room , Building , Furniture.

# What is object and class in programming?

**Object** : an object is an element (or instance) of a class,objects have the behaviors of their class.

The object is actual component of programs,

while **the class** : specifies how instances are created and how they behave(where the object come from).

**a class is a** **blueprint for creating** objects (a particular data structure), providing initial values for state (member variables or attributes), and implementations of behavior (member functions or methods). The class is a blueprint that defines a nature of a future object.

**Method** : an action which an object is able to perform.

Note when add or remove in class it will do same thing in all instance object. 

Address is stored in the variable

Ex the object's memory address is assigned to rand variable.

```java
Random rand = new Random();
```

# Object Is comprised of 

Object ==> Attribute & Functions()

Example Product ==> Attribute like Product_name , Price .

​			                 ==> Functions() like  Modify Price() , Get Product Price() .

Note Attribute == Property == Data stored == Data item == Data member (all this are same).

# Functions vs Attribute 

**Attribute** is a changeable property or characteristic of some component of a program that can be set to different values.

**Functions**  are "self contained" modules of code that accomplish a specific task. Functions usually "take in" data, process it, and "return" a result. Once a function is written, it can be used over and over and over again.(A set of instructions grouped together to achieve a specific result).

Ex of attribute in HTML an attribute is a characteristic of page element, such as a font,size,color.

```js
font-size:16px
```

Ex of Functions in java

```java
public int addNum(int x,int y){
    int sum = x + y;
    return sum;
}
```

# Encapsulation  Vs  Polymorphism

**Encapsulation** is a programming style where implementation details are hidden. It reduces software development complexity greatly. With Encapsulation, only methods are exposed. The programmer does not have to worry about implementation details but is only concerned with the operations.

Ex of Encapsulation in JAVA

```java
//A Java class which is a fully encapsulated class.  
//It has a private data member and getter and setter methods.  
package com.javatpoint;  
public class Student{  
//private data member  
private String name;  
//getter method for name  
public String getName(){  
return name;  
}  
//setter method for name  
public void setName(String name){  
this.name=name  
}  
}  
```

**Polymorphism** : Polymorphism is the capability of a method to do different things based on the object that it is acting upon. In other words, polymorphism allows you define one interface and have multiple implementations. 

existing in many forms. Variables, functions, and objects can exist in multiple forms in Java and Python. There are two types of polymorphism which are run time polymorphism and compile-time polymorphism. Run time can take a different form while the application is running and compile-time can take a different form during compilation.

Ex of Polymorphism in JAVA

Types of polymorphism and method overloading & overriding are covered in the separate:

## 1- Method Overloading

```java
add(int, int)
add(int, int, int)
```

## 2- Method Overriding in

Animal.java

```java
public class Animal{
   public void sound(){
      System.out.println("Animal is making a sound");   
   }
}
```

Horse.java

```java
class Horse extends Animal{
    @Override
    public void sound(){
        System.out.println("Neigh");
    }
    public static void main(String args[]){
    	Animal obj = new Horse();
    	obj.sound();
    }
}
```

Note : the type of object should be child inherit from his father(base class)

```java
 father obj = new child();
```

## 3-if it static in Runtime and compile time

Animal.java

```java
public class Animal{
   public static void sound(){
      System.out.println("Animal is making a sound");   
   }
}
```

Horse.java

```java
class Horse extends Animal{
    @Override
    public static void sound(){
        System.out.println("Neigh");
    }
    public static void main(String args[]){
    	Animal obj = new Horse();
    	obj.sound();
    }
}
```

Note : at compile time its convert name of obj to (class name type) Animal

not use the method override it use method base(in super class).

