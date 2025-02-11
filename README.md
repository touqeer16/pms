# 🛒 Laravel Product Management API

A simple **Product Management System** built with **Laravel 11**, supporting **CRUD operations**, **variant management**, **category assignment**, **filtering**, **authentication**, and **caching**.

---

## 🚀 Setup Instructions

### **1️⃣ Clone the Repository**

```sh
git clone https://github.com/yourusername/laravel-product-management.git
cd laravel-product-management
```

## Install Dependencies

```sh
composer install
```

## Configure .env File

Copy .env.example to .env and update database credentials:

```sh
cp .env.example .env
```

Set up database connection in .env:

```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=your_db_name
DB_USERNAME=your_db_user
DB_PASSWORD=your_db_password
```

## Generate App Key

```sh
php artisan key:generate
```

## Run Database Migrations & Seeders

```sh
php artisan migrate --seed
```

## Start the Server

```sh
php artisan serve
```

API is now available at:
📌 http://127.0.0.1:8000/api/

# 📖 API Documentation

## 🔹 Authentication

| Method | Endpoint      | Description          |
| ------ | ------------- | -------------------- |
| `POST` | `/api/login`  | User login (Sanctum) |
| `POST` | `/api/logout` | User logout          |

---

## 🔹 Product Management

| Method   | Endpoint             | Description                        |
| -------- | -------------------- | ---------------------------------- |
| `GET`    | `/api/products`      | List products (supports filtering) |
| `GET`    | `/api/products/{id}` | Get a specific product             |
| `POST`   | `/api/products`      | Create a product with variants     |
| `PUT`    | `/api/products/{id}` | Update a product & variants        |
| `DELETE` | `/api/products/{id}` | Delete a product & variants        |

---

## 🔹 Filtering Products

| Query Parameter | Example                       |
| --------------- | ----------------------------- |
| `min_price`     | `/api/products?min_price=50`  |
| `max_price`     | `/api/products?max_price=500` |
| `category_id`   | `/api/products?category_id=3` |
| `in_stock`      | `/api/products?in_stock=1`    |

## 🔹 Example Requests

### Create a Product

```http
POST /api/products
```

```json
{
    "name": "Smartphone X",
    "description": "Latest flagship model",
    "price": 999.99,
    "variants": [
        {
            "sku": "SMX-001",
            "color": "Black",
            "size": "128GB",
            "price": 1099.99,
            "stock": 50
        }
    ]
}
```

### Update a Product

```http
PUT /api/products/1
```

```json
{
    "name": "Smartphone X Pro",
    "price": 1099.99,
    "variants": [
        {
            "id": 1,
            "sku": "SMX-001",
            "color": "Black",
            "size": "128GB",
            "price": 1199.99,
            "stock": 40
        }
    ]
}
```

### Delete a Product

```http
DELETE /api/products/1
```

## 🤔 Assumptions Made

-   Variants are optional when creating a product.
-   Price is stored in decimal format (10,2) for accuracy.
-   Authentication is handled using Laravel Sanctum.
-   Filtering is supported by price range, category, and stock availability.
-   Soft deletes are not implemented, meaning deletion is permanent.

## ⏳ Time Spent on the Task

-   Project Setup & Migrations: ⏱️ 2 hours
-   Model & Relationship Setup: ⏱️ 2 hours
-   API Development: ⏱️ 4 hours
-   Filtering & Caching Implementation: ⏱️ 2 hours
-   Authentication Setup (Sanctum): ⏱️ 1 hour
-   Testing & Debugging: ⏱️ 3 hours
-   Documentation & Refinement: ⏱️ 1 hour
-   Total Time Spent: ⏳ 15 hours
