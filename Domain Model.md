## Domain Model: Smart Inventory Management System

| Entity        | Attributes                                     | Methods                          | Relationships                                         |
|---------------|------------------------------------------------|----------------------------------|------------------------------------------------------|
| **Product**   | productId, name, quantity, reorderLevel        | updateStock(), checkReorder()    | Belongs to Category, associated with Order, tracked by InventoryLog |
| **Category**  | categoryId, name                               | addProduct(), removeProduct()    | Has many Products                                    |
| **Supplier**  | supplierId, name, contactInfo                  | supplyProduct()                  | Supplies many Products                               |
| **Order**     | orderId, date, status, totalAmount             | placeOrder(), cancelOrder()      | Contains many Products, placed by User               |
| **User**      | userId, name, role                             | login(), placeOrder()            | Places many Orders                                   |
| **InventoryLog** | logId, timestamp, action, productId         | recordAction()                   | Tracks changes to Product                            |

### Business Rules

- A product’s quantity must trigger a reorder when it drops below the reorder level.
- A user must be authenticated to place an order.
- One supplier can supply many products.
- An order can contain multiple products, and a product can be in many orders.
- Inventory changes (like reorder, update, or removal) must be logged in `InventoryLog`.
