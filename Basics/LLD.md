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
