# Summary of Practice PROG03 – Using Objects (Java)

This document collects **everything learned and applied** during Exercises 1 and 2 of Unit 3 on Object‑Oriented Programming (OOP) in Java. Its goal is to serve as a **quick reference** for future practices and exams.

---

## What Is a Class?

A **class** is a blueprint or template from which objects are created. It defines:

* **Attributes** (data the object stores)
* **Methods** (actions the object can perform)

Examples used:

* `Cafetera`
* `Invento`

---

## Attributes

Attributes are **variables inside a class** that describe an object's characteristics.

Examples:

```java
private int capacidadMaxima;
private int cantidadActual;
private String nombre;
private Date fechaCreacion;
```

They are normally declared as `private` to enforce encapsulation.

---

## Constructors

Constructors are special methods used to **create objects** and initialize their attributes.

Types used:

* **Empty constructor**: receives no parameters.
* **Parameterized constructor**: assigns initial values passed from outside.

Example:

```java
public Cafetera(int capacidadMaxima, int cantidadActual) {
    this.capacidadMaxima = capacidadMaxima;
    this.cantidadActual = cantidadActual;
}
```

---

## Methods

Methods define the behavior of a class. They can:

* Modify attributes
* Read attributes
* Perform operations

Examples:

* `llenar()`
* `servirTaza(int ml)`
* `isHistorico()`
* `toString()`

---

## Getters and Setters

They allow controlled access to private attributes.

Example:

```java
public int getCantidadActual() { return cantidadActual; }
public void setCantidadActual(int cantidadActual) { this.cantidadActual = cantidadActual; }
```

These methods are key for **encapsulation**, a central concept in OOP.

---

## The toString() Method

Returns a text representation of the object.

Example:

```java
@Override
public String toString() {
    return "Capacidad máxima: " + capacidadMaxima + ", Cantidad actual: " + cantidadActual;
}
```

It is extremely useful for debugging and printing object state.

---

## Enumerations (enum)

An `enum` defines a fixed set of constant values.

Example used:

```java
public enum enumTipoInvento {
    TECNOLOGICO, MEDICO, INDUSTRIAL, CIENTIFICO, DOMESTICO, TRANSPORTE, COMUNICACION
}
```

Enums prevent mistakes such as typos in category names.

---

## The Date Class

`java.util.Date` allows storing dates. Its old constructor works in a non‑intuitive way:

* Year is counted from **1900**
* Month starts at **0** (January)
* Day is the day of the month

Example:

```java
new Date(76, 2, 7); // March 7, 1976
```

---

## The isHistorico() Method

A boolean method used to determine whether an invention was created **before the year 2000**.

Example:

```java
public boolean isHistorico() {
    Date limit = new Date(100, 0, 1); // January 1, 2000
    return fechaCreacion != null && fechaCreacion.before(limit);
}
```

---

## The Principal Class and the main Method

The `main` method is the entry point of a Java application. It is where you:

* Create objects
* Call their methods
* Print results to the console

Example:

```java
Cafetera c = new Cafetera();
c.llenar();
System.out.println(c.toString());
```

---

## Package Structure

Packages help organize code into logical groups.
Examples used:

* `com.prog03.cafetera`
* `com.prog03.principal`
* `com.prog03.inventos`

Good package organization is essential in real projects.

---

## Exporting Projects in NetBeans

Projects must be exported using:
**File → Export Project → To ZIP**

This ZIP contains:

* `build.xml`
* `nbproject/`
* `src/`

This is the required submission format.

---

## Skills Practiced in This Assignment

* Creating classes
* Encapsulation (`private` + getters/setters)
* Using multiple constructors
* Working with `Date`
* Declaring and using enums
* Overriding methods (`toString()`)
* Writing and using a `main` method
* Boolean logic (`isHistorico`)
* Package organization
* Exporting NetBeans projects correctly

These represent the foundation of **Object‑Oriented Programming in Java**.

---

## Conclusion

With this practice, you strengthened your understanding of:

* The real structure of a Java program
* How to create and use classes and objects
* Core OOP principles (encapsulation, methods, constructors)
* Proper project structure in NetBeans
* Professional submission workflow

This will serve you well in the rest of the course and future Java work.
