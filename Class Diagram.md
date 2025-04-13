classDiagram
    class Product {
        -productId: String
        -name: String
        -quantity: int
        -reorderLevel: int
        +updateStock(): void
        +checkReorder(): bool
    }

    class Category {
        -categoryId: String
        -name: String
        +addProduct(): void
        +removeProduct(): void
    }

    class Supplier {
        -supplierId: String
        -name: String
        -contactInfo: String
        +supplyProduct(): void
    }

    class Order {
        -orderId: String
        -date: Date
        -status: String
        -totalAmount: float
        +placeOrder(): void
        +cancelOrder(): void
    }

    class User {
        -userId: String
        -name: String
        -role: String
        +login(): bool
        +placeOrder(): void
    }

    class InventoryLog {
        -logId: String
        -timestamp: DateTime
        -action: String
        -productId: String
        +recordAction(): void
    }

    Category "1" -- "0..*" Product : categorizes
    Supplier "1" -- "0..*" Product : supplies
    Order "1" -- "1..*" Product : contains
    User "1" -- "0..*" Order : places
    Product "1" -- "0..*" InventoryLog : trackedBy


## Design Notes

The relationships reflect real-world use cases (e.g., users placing orders, inventory tracking per product).

Chose association over inheritance to reduce unnecessary complexity.

InventoryLog adds traceability without bloating the Product class.
