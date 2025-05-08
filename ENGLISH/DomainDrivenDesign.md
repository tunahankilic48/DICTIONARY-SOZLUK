# 📘 What is Domain-Driven Design (DDD)?

**Domain-Driven Design (DDD)** is a software development approach that places real-world business problems at the center of software projects. This approach advocates that software should be designed to directly address business needs.

Here, the **domain** refers to the business problem that the software aims to solve.  
For example: "Calculating a vehicle’s average fuel consumption" could be a domain. However, this domain should be **clearer** and have **well-defined boundaries**.  
A more precise definition might be:  
➡️ "Calculating the average fuel consumption of trucks" or  
➡️ "Calculating the average fuel consumption of passenger aircraft".

Such clearly defined business problems are referred to as the **domain**.  
**DDD** aims to build a model aligned with this domain to bridge the gap between software and business requirements.

---

# 🧱 Core Concepts

## 1. Domain
The business problem that the software aims to solve.  
**Example:** In a banking system, the domain could be financial transactions.

## 2. Model
An abstract representation of the domain.  
It includes the classes, relationships, and rules that form the core of the system.

## 3. Ubiquitous Language
A shared language developed collaboratively by developers and domain experts, used consistently in code, documentation, and daily communication.

## 4. Bounded Context
Defines the boundaries within which a particular model is valid.  
In large systems, each bounded context can have its own model and language, independent from others.

## 5. Entity
An object with a unique identity that changes over time.  
**Example:** User, Order, Product.

## 6. Value Object
An object defined solely by its value and without identity.  
**Example:** Money, Address, Coordinates.

## 7. Aggregate
A cluster of associated entities and value objects treated as a unit.  
Access to the aggregate is only allowed through the **aggregate root**.

## 8. Repository
An abstraction layer that handles data access.  
Applications interact with data through repositories instead of directly accessing the database.

---

# 🧭 Strategic Design

Strategic design focuses on the big picture of the system. It involves dividing the domain into parts, defining boundaries, and managing relationships between these parts.

### 🔹 Key Concepts:

- **Bounded Context:**

- **Context Map:**  
  Maps out the relationships and communication between different bounded contexts.

- **Ubiquitous Language:**

---

# 🛠️ Tactical Design

Tactical design focuses on the internal structure of the domain model within a specific bounded context. It defines how the software is architected at a detailed level.

### 🔸 Key Concepts:

- **Entity**  
- **Value Object**  
- **Aggregate**  
- **Repository**  
- **Domain Service:** Business rules that do not naturally belong to an entity or value object.  
- **Factory:** Used for creating complex objects.

---

# 🎯 Summary Table

| Design Level           | Purpose                                               | Key Concepts                                                   |
|------------------------|-------------------------------------------------------|-----------------------------------------------------------------|
| **Strategic Design**   | Model the big picture and define contextual boundaries | Bounded Context, Context Map, Ubiquitous Language               |
| **Tactical Design**    | Design the internal structure of the domain model      | Entity, Value Object, Aggregate, Repository, Service, Factory   |
