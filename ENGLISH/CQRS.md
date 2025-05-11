# ⚙️ CQRS (Command Query Responsibility Segregation)

**CQRS** is a software architectural pattern that separates **data modification operations (Commands)** from **data retrieval operations (Queries)**.

---

## 📖 Definition

CQRS allows an application to handle **read** and **write** operations through **different models or layers**.

In traditional architectures, the same model or object is often used for both reading and writing data.  
With CQRS, these responsibilities are **segregated**, resulting in a structure that is:

- ✅ More flexible  
- ✅ Easier to scale  
- ✅ Easier to maintain

---

## 🔄 Core Structure of CQRS

### 🔧 Command (Write Operations)
- Used to **change system state** (e.g., insert, update, delete).
- **Does not return data** (usually returns `void` or a status/result).
- 🧪 Has side effects.
- 📌 Examples:
  - `CreateOrderCommand`
  - `UpdateProfileCommand`

### 🔍 Query (Read Operations)
- Retrieves data but **does not change** it.
- 🌱 Must be side-effect free (idempotent).
- 📌 Examples:
  - `GetOrderByIdQuery`
  - `GetCustomerListQuery`

---

## 🧠 Why Use CQRS?

### ✅ Separation of Concerns
- Code is more organized.
- Each component **does one thing well** (aligned with the **Single Responsibility Principle** from SOLID).

### ✅ Performance Optimization
- Different **data models or databases** can be used for reads and writes.
- Read-heavy operations can be scaled **independently**.

### ✅ Easier Testing
- Commands and queries are separated and can be **unit tested independently**.

### ✅ Maintainability & Scalability
- Systems can grow and evolve more easily.
- Complex business logic is **easier to manage**.

---

## 🚫 When Not to Use CQRS

- In **simple CRUD applications**, CQRS adds **unnecessary complexity**.
- In **small teams or projects**, the overhead might **slow down development**.

---

## 🧰 Common CQRS Use Cases & Tools

- 🔄 **MediatR** – A popular CQRS library in C#
- 🗃️ **Event Sourcing** – Tracks changes as events instead of directly updating the database
- 🧠 **Domain Driven Design (DDD)** – Often paired with CQRS
- ⚙️ **Microservices** – Ideal for decoupling services and responsibilities

---

## 🔚 Summary Table

| Feature      | Command                      | Query                        |
|--------------|-------------------------------|-------------------------------|
| Purpose      | Changes data (write)          | Retrieves data (read)         |
| Return Value | `void` / status               | Data                          |
| Data Model   | Write model                   | Read model                    |
| Behavior     | May have side effects         | Must be idempotent            |

---

> 🧩 **Note:** CQRS is powerful for systems with complex workflows or high scalability requirements.  
> It should be used **wisely and only when necessary** to avoid overengineering.
