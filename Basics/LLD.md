When you're in an LLD interview, don't start by thinking:

"Which design pattern should I use?"
Start with:

1. What are my objects?
        ↓
2. What responsibility does each object have?
        ↓
3. What does each object own?
        ↓
4. What relationships exist?
        ↓
5. What behavior is likely to vary?
        ↓
6. Can I isolate that variation?
        ↓
7. Where are my abstractions?
        ↓
8. Is coupling low?
        ↓
9. Is cohesion high?
        ↓
10. Can I extend the system without breaking existing code?

A very useful LLD checklist
When you're given an LLD problem, walk through it in this order:

Step 1 — Identify entities
Ask:

What are the important nouns?
For an online shopping system:

User
Product
Cart
Order
Payment
Address
Step 2 — Identify responsibilities
Ask:

What does each object actually do?
Cart → add/remove items
Order → represent purchase
Payment → process payment
Step 3 — Identify relationships
Look for:

IS-A       → inheritance
HAS-A      → composition
USES-A     → dependency
IMPLEMENTS → interface
Step 4 — Identify what varies
Ask:

What will likely have multiple implementations?
Examples:

Payment method
Notification method
Pricing strategy
Parking spot allocation
Vehicle type
Discount strategy
Those are candidates for:

interface + polymorphism
Step 5 — Apply SOLID
Ask:

Does each class have one responsibility?

Can I add new behavior without modifying existing code?

Are subclasses actually substitutable?

Are my interfaces too large?

Am I depending on abstractions?
Step 6 — Look for coupling
Ask:

If I change X, how many classes need modification?
If changing:

UPI → something else
requires modifying 15 classes, your design is probably too coupled.

Step 7 — Look for unnecessary complexity
Ask:

Can I make this simpler?
This is where:

KISS
YAGNI
DRY
help.

-------

# SOLID 

* Single Reponsibility - A class should have 1 responsibility
* Open/Close
* Liskov Substitution
* Interface Seggregation
* Dependency Inversion

## Single Responsibility:
It doesnt mean a single method per class. It means a class should be responsible for 1 functionality. For example OrderService class should not contain logic for sending email after order.


-------
# Design patterns

## Singleton: one shared instance, centrally controlled
Intution: For the whole application when you need a service that only one instance is available. The core intuition (one shared instance, centrally controlled) is right

When to use this: When you modify something it has to be applicable for the whole application. If each class or service creates its own instance it is difficult to change a config for whole application. For example consider logger service if each class using logger creates its own instance then to make app to log DEBUG level needs update in all the instance if its not singleton

- **Shared mutable state:** a cache, a connection pool, an in-memory counter — if two instances existed, they’d diverge and you’d get inconsistent behavior.
- **Shared access to a scarce resource:** a DB connection pool, a thread pool — creating multiple instances could exhaust resources or cause contention.


Other examples beyond logger:
* Configuration manager (app-wide settings loaded once)
* Database connection pool
* Cache manager
* Hardware interface access (e.g., a printer spooler, device driver)

the trade-offs:
Unit Testing is difficult, Hidden dependencies- classes that silently reach for Singleton.getInstance() instead of having it injected are harder to test and reason about.


## Factory: 


## Observer:
The Observer Pattern is a behavioral design pattern where an object (called the Subject) maintains a list of its dependents (called Observers) and notifies them automatically of any state changes, usually by calling one of their methods. It is commonly used for implementing distributed event-handling systems.


