# 🎨 Decorator Pattern

## 📌 Definition
The Decorator Pattern is a structural design pattern that allows you to dynamically add new responsibilities or behaviors to an object without altering its structure.

---

## 🎯 Intent
To extend the functionality of objects at runtime without using inheritance, and to allow flexible and reusable code enhancements.

---

## 🧱 Structure

- **Component**: An abstract interface or base class defining the operations.
- **ConcreteComponent**: The original object whose behavior needs to be extended.
- **Decorator**: An abstract class that implements the `Component` interface and contains a reference to a `Component` object.
- **ConcreteDecorator**: A class that adds new behavior by extending the `Decorator`.

---

## 🔧 When to Use

- When you want to add behavior to individual objects, not an entire class.
- When using inheritance leads to too many subclasses.
- When you need a flexible alternative to subclassing for extending functionality.

---

## ✅ Advantages

- Complies with the **Open/Closed Principle** — classes are open for extension but closed for modification.
- Promotes composition over inheritance.
- Responsibilities can be added or removed at runtime.

---

## ❌ Disadvantages

- Can result in a large number of small classes.
- Code can become complicated due to multiple layers of decorators.
- Debugging may become more difficult as behavior is distributed.

---

## 🔄 Related Principles

- **[Open/Closed Principle](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/ENGLISH/SOLIDPrinciples.md)**
- **[Single Responsibility Principle](https://github.com/tunahankilic48/DICTIONARY-SOZLUK/blob/main/ENGLISH/SOLIDPrinciples.md)**
- **Composition Over Inheritance**
