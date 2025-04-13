Challenges in Designing the Domain Model and Class Diagram
Designing the domain model and class diagram for the Smart Inventory Management System was both an insightful and challenging experience. One of the main challenges was identifying the correct level of abstraction. Initially, it was tempting to include many attributes and methods per class, which risked over-complicating the model. I had to refine and focus on what each entity’s core responsibility was and eliminate non-essential details to keep the design clean and functional.

Another challenge was understanding the relationships between the classes. For instance, the decision of whether to use aggregation or composition for linking Product with Order required careful thought. Since products can exist independently of orders, I opted for aggregation. Similarly, defining multiplicities (like one-to-many or many-to-many) needed consistency with the business logic. Ensuring each class had clearly defined attributes and responsibilities helped in assigning the correct relationships.

Alignment with Previous Assignments
The class diagram and domain model strongly align with previous assignments. In Assignment 4, we defined the system's core requirement: to manage stock levels, track inventory movement, and streamline reordering. The Product, Order, and InventoryLog classes directly address these functions. In Assignment 5, the use cases of “Place Order”, “Update Stock”, and “Reorder Product” mapped well onto methods like placeOrder() and updateStock().

Assignment 8’s behavioral models, particularly the activity diagram for ordering and the state diagram for product status, helped define transitions and methods in the class diagram. For example, the checkReorder() method corresponds to the decision point where low inventory triggers reordering, and InventoryLog was introduced to model the state transition logging.

Trade-offs Made
A key trade-off was the decision not to implement inheritance between User types (e.g., admin vs. regular user). While inheritance would have allowed specialized methods, it would also introduce complexity not justified by our current scope. Instead, I added a role attribute to the User class and plan to handle permissions via conditional logic. Also, I chose to avoid composition between Order and Product since products exist independently and can be part of multiple orders—aggregation better suited the relationship.

Another simplification was not modeling the full supplier delivery lifecycle. Although potentially useful, it wasn’t critical for the MVP and would bloat the model. We focused on the supplyProduct() method and supplier-product relationship for clarity.

Lessons Learned
Through this assignment, I’ve gained a deeper understanding of object-oriented design principles, especially the importance of cohesion, responsibility assignment, and relationship clarity. I also realized how iterative design improves quality—my first version was cluttered, but after peer review and self-assessment, it evolved into something more robust and clean. Creating class diagrams with Mermaid.js helped reinforce correct UML syntax and structure.

Finally, I learned that a well-designed domain model simplifies future development and maintenance. By breaking down complex interactions into modular, testable classes, we reduce bugs and make the system easier to scale. This exercise highlighted how domain modeling acts as a bridge between requirements analysis and software implementation.
