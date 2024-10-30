# Use Cases Document for Garment ERP Software

## Project Overview
This document outlines the detailed use cases for the Garment ERP software. Use cases define interactions between users (actors) and the system to achieve specific business goals, providing a comprehensive understanding of system functionalities.

## Use Case Diagram
*(Include a diagram illustrating the main actors and their interactions with the system, using tools like Lucidchart, Draw.io, or any UML diagram tool.)*

## Use Cases

### 1. User Registration and Authentication

#### Use Case 1.1: User Registration
- **Use Case ID**: UC-01
- **Actor**: New User (e.g., Employee, Manager)
- **Description**: A new user registers for access to the ERP system.
- **Preconditions**:
  - User has valid registration information (name, email, password, role).
  - User is not already registered in the system.
- **Postconditions**:
  - User is registered and can log in to the system.
  - User account status is set to "Active."
- **Main Flow**:
  1. User navigates to the registration page.
  2. User enters required information in the registration form.
  3. User submits the registration form.
  4. System validates the information:
     - If the email is already in use, go to step 6.
  5. System creates a new user account and sends a confirmation email.
  6. **End Use Case**.
  
- **Alternative Flow**:
  - **A1**: Email already registered
    - **Description**: If the system detects that the email is already registered.
    - **Steps**:
      1. System displays an error message: "Email already in use. Please try a different email."
      2. User is prompted to return to the registration form.

- **Business Rules**:
  - All email addresses must be unique.
  - Password must meet security criteria (minimum length, complexity).

#### Use Case 1.2: User Authentication
- **Use Case ID**: UC-02
- **Actor**: Registered User
- **Description**: A registered user logs into the ERP system.
- **Preconditions**:
  - User has an active account with valid credentials.
- **Postconditions**:
  - User is logged into the system and redirected to the dashboard.
- **Main Flow**:
  1. User navigates to the login page.
  2. User enters username and password.
  3. User submits the login form.
  4. System validates the credentials:
     - If invalid, go to step 6.
  5. System logs the user in and redirects them to the dashboard.
  6. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Invalid credentials
    - **Description**: If the system detects invalid username or password.
    - **Steps**:
      1. System displays an error message: "Invalid username or password."
      2. User is prompted to try again.

- **Business Rules**:
  - User accounts must be active for login.
  - Lock account after 5 failed login attempts for security.

---

### 2. Product Management

#### Use Case 2.1: Add New Product
- **Use Case ID**: UC-03
- **Actor**: Product Manager
- **Description**: The product manager adds a new product to the ERP system.
- **Preconditions**:
  - User is logged in with sufficient permissions (Product Manager role).
- **Postconditions**:
  - The new product is added to the inventory.
- **Main Flow**:
  1. User navigates to the product management section.
  2. User selects the option to add a new product.
  3. User enters product details (name, category, price, specifications, stock level).
  4. User submits the form.
  5. System validates the product information:
     - If validation fails, go to step 7.
  6. System saves the product and displays a success message with product ID.
  7. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Validation error
    - **Description**: If the system finds invalid input (e.g., negative price).
    - **Steps**:
      1. System displays an error message detailing the validation issues.
      2. User is prompted to correct the errors.

- **Business Rules**:
  - All products must have a unique identifier (SKU).
  - Price must be a positive value.

#### Use Case 2.2: Update Product Information
- **Use Case ID**: UC-04
- **Actor**: Product Manager
- **Description**: The product manager updates existing product details.
- **Preconditions**:
  - User is logged in with sufficient permissions.
  - The product exists in the system.
- **Postconditions**:
  - The product information is updated in the system.
- **Main Flow**:
  1. User navigates to the product management section.
  2. User searches for the product by name or SKU.
  3. User selects the product to update.
  4. User modifies the product details.
  5. User submits the changes.
  6. System validates the updated information:
     - If validation fails, go to step 8.
  7. System updates the product information and displays a success message.
  8. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Product not found
    - **Description**: If the product search yields no results.
    - **Steps**:
      1. System displays an error message: "Product not found."
      2. User is prompted to refine the search criteria.

- **Business Rules**:
  - Updates must maintain historical data for auditing purposes.

---

### 3. Order Management

#### Use Case 3.1: Create New Order
- **Use Case ID**: UC-05
- **Actor**: Sales Representative
- **Description**: The sales representative creates a new customer order.
- **Preconditions**:
  - User is logged in with sufficient permissions.
  - Customer exists in the system.
- **Postconditions**:
  - The new order is created and stored in the system.
- **Main Flow**:
  1. User navigates to the order management section.
  2. User selects the option to create a new order.
  3. User enters customer details and order items.
  4. User submits the order form.
  5. System processes the order and assigns a unique order ID.
  6. System displays a confirmation message with order details.
  7. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Customer not found
    - **Description**: If the user attempts to create an order for a non-existent customer.
    - **Steps**:
      1. System displays an error message: "Customer not found. Please add the customer first."
      2. User is redirected to the customer management section.

- **Business Rules**:
  - All orders must have a valid customer associated.
  - Payment must be processed before order confirmation.

#### Use Case 3.2: Track Order Status
- **Use Case ID**: UC-06
- **Actor**: Sales Representative
- **Description**: The sales representative checks the status of a customer order.
- **Preconditions**:
  - User is logged in with sufficient permissions.
  - The order exists in the system.
- **Postconditions**:
  - The user views the current status of the order.
- **Main Flow**:
  1. User navigates to the order management section.
  2. User selects the option to view orders.
  3. User searches for the specific order by ID or customer name.
  4. System displays the order status and details.
  5. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Order not found
    - **Description**: If the order search yields no results.
    - **Steps**:
      1. System displays an error message: "Order not found."
      2. User is prompted to refine the search criteria.

- **Business Rules**:
  - Order statuses must follow predefined states (e.g., Pending, Completed, Shipped).

---

### 4. Inventory Management

#### Use Case 4.1: Update Inventory Levels
- **Use Case ID**: UC-07
- **Actor**: Inventory Manager
- **Description**: The inventory manager updates stock levels for products.
- **Preconditions**:
  - User is logged in with sufficient permissions.
  - The product exists in the system.
- **Postconditions**:
  - The inventory levels are updated in the system.
- **Main Flow**:
  1. User navigates to the inventory management section.
  2. User selects a product to update.
  3. User enters the new stock level.
  4. User submits the changes.
  5. System validates the input:
     - If validation fails, go to step 7.
  6. System updates the inventory levels and displays a success message.
  7. **End Use Case**.

- **Alternative Flow**:
  - **A1**: Invalid stock level
    - **Description**: If the user enters a negative stock level.
    - **Steps**:
      1. System displays an error message: "Stock level cannot be negative."
      2. User is prompted to enter a valid stock level.

- **Business Rules**:
  - Inventory levels must reflect real-time data for accuracy.
  - Alerts must be triggered when stock falls below reorder levels.

---

### Conclusion
This document serves as a comprehensive guide for the use cases of the Garment ERP software project, detailing various functionalities essential for effective management. Additional use cases can be added as the project progresses to encompass other critical features and requirements.

### Appendices
- **Glossary**: Define terms used within the document.
- **References**: Cite any documents or resources that influenced the project. 