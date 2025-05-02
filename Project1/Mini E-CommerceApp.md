**📦 Sample Project 1: Mini E-Commerce App – Visual Documentation**

---

### 🔹 Project Overview

**Title:** Mini E-Commerce App
**Stack:** React (Frontend) + Spring Boot (Backend) + MySQL (Database)
**Auth:** JWT-based login system
**Users:** Admin and Customers

---

### 🔸 1. System Architecture Diagram

```
Client (Browser)
   ↓
React App (Frontend)
   ↓
Axios HTTP Requests
   ↓
Spring Boot REST API (Backend)
   ↓
Service Layer
   ↓
JPA Repository
   ↓
MySQL Database
```

---

### 🔸 2. Component Tree (React)

```
<App>
 ├── <Navbar />
 ├── <ProductList />
 │     └── <ProductCard />
 ├── <Cart />
 ├── <Checkout />
 ├── <Login /> / <Register />
 └── <AdminPanel />
        ├── <ProductForm />
        └── <OrderManager />
```

---

### 🔸 3. API Flow Map

| Endpoint            | Method | Purpose           | Access     |
| ------------------- | ------ | ----------------- | ---------- |
| `/api/products`     | GET    | List all products | Public     |
| `/api/products`     | POST   | Add new product   | Admin Only |
| `/api/cart`         | POST   | Add item to cart  | Customer   |
| `/api/checkout`     | POST   | Create order      | Customer   |
| `/api/orders`       | GET    | List user orders  | Customer   |
| `/api/admin/orders` | GET    | Admin order list  | Admin Only |

---

### 🔸 4. Database Design (ERD)

```
Users
- id (PK)
- username
- email
- password
- role [ADMIN, CUSTOMER]

Products
- id (PK)
- name
- description
- price
- stock

Orders
- id (PK)
- user_id (FK → Users)
- total_amount
- created_at

OrderItems
- id (PK)
- order_id (FK → Orders)
- product_id (FK → Products)
- quantity
- unit_price
```

---

### 🔸 5. JWT Auth Flow

1. User logs in with credentials → `/api/auth/login`
2. Backend validates → returns JWT
3. Frontend stores token (e.g., localStorage)
4. All secure API calls include `Authorization: Bearer <token>`
5. Backend verifies JWT and authorizes access

---

### 🔸 6. Error Handling Path

```
Frontend Input → Form Validation
↓
Spring Controller → @Valid + ExceptionHandler
↓
Service Layer → Custom Business Exceptions
↓
Global Error Handler → Consistent Response
```

---

### 🔸 7. CI/CD (Optional Advanced)

* GitHub Actions triggers on push
* Build React + Spring Boot artifacts
* Docker image creation
* Deploy to EC2 with Docker Compose

---

### 🔸 8. Interview Storyboard

"I built an E-Commerce app using Spring Boot and React. I implemented role-based authentication using JWT, used JPA for order-product-user relationships, and designed a secure checkout system. I used Docker to containerize the services and deployed it using Docker Compose."

---

Would you like visual diagrams (PDF or Draw\.io) for any of the above sections?
