🛒 Ya Ya’s Pixel Pantry – Grocery Store API
<img width="809" height="758" alt="image" src="https://github.com/user-attachments/assets/fe8f1a1b-6619-49c7-8892-00d2b39c3bbe" />


A full-stack Java Spring Boot REST API for an online grocery store application.
This project supports user authentication, role-based authorization, product browsing, category management, and shopping cart functionality, backed by a MySQL database.

 Project Overview

Ya Ya’s Pixel Pantry is a grocery store backend that allows:

Users to browse products and categories

Admins to manage categories and products

Secure login & registration using JWT authentication

Product filtering by category, price range, and subcategory

Persistent data storage using MySQL and DAO pattern

This project follows RESTful API standards, separation of concerns, and secure coding practices.


 Tech Stack

Java 17

Spring Boot

Spring Security (JWT Authentication)

MySQL

JDBC / DAO Pattern

Apache DBCP2

Insonmnia



🔐 Authentication & Authorization

JWT-based authentication

Roles supported:

ROLE_USER

ROLE_ADMIN

Security rules enforced using @PreAuthorize

Authentication Endpoints
Method	Endpoint	Description
POST	/register	Register new user
POST	/login	Login and receive JWT token

✔ Passwords are encrypted using BCrypt
✔ JWT token is returned in the Authorization header

Problem Child !!
<img width="1120" height="379" alt="Screenshot 2025-12-18 231747" src="https://github.com/user-attachments/assets/79ff62d3-9cc1-4ab3-ab21-af6176fad663" />

Categories API
<img width="769" height="578" alt="image" src="https://github.com/user-attachments/assets/a2bd590d-e658-4378-8a88-e3db6148c067" />

Method	Endpoint	Access	Description
GET	/categories	Public	Get all categories
GET	/categories/{id}	Public	Get category by ID
GET	/categories/{id}/products	Public	Get products by category
POST	/categories	Admin	Create new category
PUT	/categories/{id}	Admin	Update category
DELETE	/categories/{id}	Admin	Delete category

✔ Returns proper HTTP status codes
✔ Prevents deletion of categories in use
✔ Admin-only access enforced

🛍 Products API
Method	Endpoint	Access	Description
GET	/products	Public	Search & filter products
GET	/products/{id}	Public	Get product by ID
POST	/products	Admin	Create product
PUT	/products/{id}	Admin	Update product
DELETE	/products/{id}	Admin	Delete product
Product Search Filters

Category ID

Minimum price

Maximum price

Subcategory

✔ SQL logic correctly handles optional filters
✔ Prevents incorrect min/max price logic

🛒 Shopping Cart (In Progress)

The ShoppingCartController is structured to support:

Viewing cart by logged-in user

Adding products to cart

Updating quantities

Clearing cart

Shopping cart logic is backed by:

ShoppingCart

ShoppingCartItem

ShoppingCartDao

🗃 Database Design
<img width="1173" height="866" alt="Screenshot 2025-12-18 232400" src="https://github.com/user-attachments/assets/071652c3-abb1-4202-aac4-314d1be17339" />


users

profiles

categories

products

shopping_cart

orders / order_line_items (future expansion) 
<img width="1741" height="919" alt="image" src="https://github.com/user-attachments/assets/5ff10245-80fe-4aba-8bbe-ba1505945f0f" />


✔ Uses auto-increment IDs
✔ Foreign key relationships enforced
✔ Clean DAO abstraction

🧠 Architecture Highlights

Controller → DAO → Database flow

DAO interfaces for testability

MySQL implementations separated from interfaces

Centralized DB connection handling

Clear model-to-table mapping

🧪 Testing & Validation
<img width="1703" height="994" alt="Screenshot 2025-12-18 180341" src="https://github.com/user-attachments/assets/feb09a32-2307-4d21-a3fa-592f552b0914" />

✔ All major endpoints tested using Insonmnia
✔ Admin vs User access verified
✔ Error handling returns correct HTTP codes
✔ Screenshot evidence included showing:

Successful authentication

Category creation restrictions

Product browsing UI

Passing API test collections
<img width="599" height="815" alt="Screenshot 2025-12-18 230811" src="https://github.com/user-attachments/assets/9e4c45ba-b06e-42f2-82de-69c21fb006f9" />

🖥 Sample UI Preview

<img width="1892" height="1055" alt="Screenshot 2025-12-18 231552" src="https://github.com/user-attachments/assets/bb8cbd23-af31-46a9-a4d4-b1dca98827f0" />

The front-end grocery UI displays:

Product cards with images

Prices & descriptions

Category filters

Add-to-cart buttons




🚀 How to Run the Project

Clone the repository

Create a MySQL database

Update application.properties:

datasource.url=jdbc:mysql://localhost:3306/groceryapp
datasource.username=YOUR_USERNAME
datasource.password=YOUR_PASSWORD


Run the Spring Boot application

Test endpoints via Insonmnia

🌟 Key Takeaways

Demonstrates real-world backend development

Implements secure authentication

Uses industry-standard REST practices

Shows strong understanding of Java, SQL, and Spring Boot

👩🏽‍💻 Author

Ayanna Smith
Software Developer| Year Up United
Capstone Project – Grocery Store API
