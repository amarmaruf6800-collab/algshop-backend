# 🛒 AlgShop Backend

> Laravel REST API backend for the AlgShop e-commerce marketplace.

AlgShop Backend provides the server-side API for AlgShop, handling authentication, shops, products, shopping carts, checkout, orders, addresses, reviews, and seller workflows.

The backend is built with **Laravel 12**, **PHP**, and a **MySQL-compatible database**.

---

## 🔗 Related Project

### Frontend

https://github.com/amarmaruf6800-collab/algshop-frontend

### Live Demo

https://algshop.vercel.app

> The current demo uses simulated payment processing for development and demonstration purposes.

---

## ✨ Features

### 🔐 Authentication

- User registration
- User login
- Laravel Sanctum authentication
- Protected API endpoints
- Authenticated user profile access

### 🏪 Shop Management

- Create a seller shop
- Manage seller shop data
- Associate products with individual shops
- Buyer and seller workflows

### 📦 Product Management

- Create products
- Update products
- Delete products
- Product pricing
- Discount management
- Stock management
- Multiple product images
- Product catalog API

### 🛒 Shopping Cart

- Add products to cart
- View cart
- Update cart data
- Remove cart items
- User-specific cart
- Prevent users from purchasing products from their own shop

### 📍 Address Management

- Add shipping addresses
- Edit addresses
- Delete addresses
- Set default address
- Manage user-specific addresses

### 🧾 Checkout & Orders

- Checkout cart
- Select shipping address
- Group orders by seller/shop
- Generate invoice numbers
- Create order items
- Deduct product stock during checkout
- Buyer order history
- Seller incoming orders
- Seller order status management

### 💳 Payment Flow

- Invoice-based payment flow
- Simulated payment endpoint
- Payment status handling

> **Note:** The current implementation uses a simulated payment endpoint and does not represent a live payment gateway integration.

### ⭐ Reviews

- Product ratings from 1–5 stars
- Review comments
- Verified-purchase review validation
- Prevent duplicate reviews from the same user

---

## 🧱 Architecture

```text
                     ALGSHOP

┌──────────────────────────────────┐
│        React + Vite Frontend     │
│                                  │
│ Catalog • Cart • Checkout        │
│ Orders • Seller Dashboard        │
└───────────────┬──────────────────┘
                │
                │ HTTP / REST API
                ▼
┌──────────────────────────────────┐
│          Laravel 12 API          │
│                                  │
│ Sanctum Authentication           │
│ Product • Shop • Cart APIs       │
│ Order • Address • Review APIs    │
└───────────────┬──────────────────┘
                │
                ▼
┌──────────────────────────────────┐
│       MySQL-compatible DB         │
│                                  │
│ Users • Shops • Products         │
│ Orders • Cart • Reviews          │
└──────────────────────────────────┘
```

The frontend is deployed separately from the Laravel backend.

---

## 🛠️ Tech Stack

### Backend

- PHP
- Laravel 12
- Laravel Sanctum
- Laravel Breeze
- Eloquent ORM

### Database

- MySQL / MariaDB-compatible database

### Frontend Integration

- REST API
- JSON
- HTTP authentication

### Deployment

- VPS backend deployment
- Vercel frontend deployment

---

## 📁 Project Structure

```text
algshop-backend/
│
├── app/
│   ├── Http/
│   ├── Models/
│   └── ...
│
├── bootstrap/
├── config/
├── database/
│   ├── migrations/
│   └── seeders/
│
├── public/
├── resources/
├── routes/
│   └── api.php
│
├── storage/
├── artisan
├── composer.json
├── composer.lock
└── README.md
```

---

## 🔑 API Overview

The API is organized around the main marketplace workflows.

### Authentication

```text
POST /api/login
POST /api/register
```

### Catalog

```text
GET /api/katalog
GET /api/produk/{id}
```

### Buyer

```text
GET    /api/keranjang
POST   /api/keranjang/{product_id}
POST   /api/checkout-keranjang

GET    /api/alamat
POST   /api/alamat
PUT    /api/alamat/{id}
DELETE /api/alamat/{id}
PUT    /api/alamat/{id}/default

POST   /api/bayar-simulasi
GET    /api/riwayat-belanja
POST   /api/produk/{id}/ulasan
```

### Seller

```text
POST   /api/buka-toko

GET    /api/toko-saya/produk
POST   /api/toko-saya/produk
POST   /api/toko-saya/produk/{id}
DELETE /api/toko-saya/produk/{id}

GET    /api/pesanan-masuk
PUT    /api/pesanan/{id}/status
```

---

## 🚀 Run Locally

### Requirements

- PHP 8.2+
- Composer
- MySQL / MariaDB-compatible database
- Node.js and npm for the frontend

### 1. Clone the repository

```bash
git clone https://github.com/amarmaruf6800-collab/algshop-backend.git

cd algshop-backend
```

### 2. Install PHP dependencies

```bash
composer install
```

### 3. Configure environment

Create the environment file:

```bash
cp .env.example .env
```

Configure the database and application settings in `.env`.

### 4. Generate application key

```bash
php artisan key:generate
```

### 5. Run migrations

```bash
php artisan migrate
```

### 6. Create storage link

```bash
php artisan storage:link
```

### 7. Start the development server

```bash
php artisan serve
```

---

## 🔐 Environment Variables

Do not commit production credentials or secrets to GitHub.

Configure environment-specific values in `.env`.

Example:

```env
APP_NAME=AlgShop
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=algshop
DB_USERNAME=your-user
DB_PASSWORD=your-password
```

---

## 📌 Project Highlights

AlgShop Backend demonstrates practical backend development through:

- REST API development with Laravel
- Authentication with Laravel Sanctum
- Role-based buyer and seller workflows
- Product and shop management
- Shopping cart implementation
- Checkout and order processing
- Stock deduction during checkout
- Shipping address management
- Product review validation
- Relational database integration
- Frontend/backend API integration

---

## 🎯 Marketplace Workflow

```text
User
 ↓
Authentication
 ↓
Browse Catalog
 ↓
Product Detail
 ↓
Shopping Cart
 ↓
Checkout
 ↓
Payment Simulation
 ↓
Order Creation
 ↓
Stock Deduction
 ↓
Seller Order Management
```

---

## 👨‍💻 Author

**Amar**

Junior Web Developer | Full-Stack Enthusiast

Information Technology / Web Development
