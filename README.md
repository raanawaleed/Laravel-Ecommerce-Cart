# Laravel E-commerce Shopping Cart (Laravel 11 / PHP 8.2)

This project is a **simple e-commerce shopping cart system** built with **Laravel 11** and **PHP 8.2**.
It demonstrates clean Laravel architecture, authenticated user-based cart persistence, queued jobs, scheduled tasks, and a Livewire frontend.

---

## Step 1: Tech Stack

* Laravel 11
* PHP 8.2
* Laravel Breeze (Livewire)
* Tailwind CSS
* MySQL / SQLite
* Laravel Queue (Database driver)
* Laravel Scheduler
* Git & GitHub

---

## Step 2: Features Implemented

* User authentication (register / login)
* Product browsing (name, price, stock quantity)
* Add products to cart
* Update cart item quantities
* Remove items from cart
* Cart persistence per authenticated user (database-driven)
* Checkout process (orders & order items)
* Automatic stock reduction on checkout
* Low stock email notification (queued job)
* Daily sales report email (scheduled job)
* Form Request validation
* API Resources for structured responses

---

## Step 3: Clone & Install

```bash
git clone https://github.com/raanawaleed/Laravel-Ecommerce-Cart
cd laravel-ecommerce-cart
composer install
npm install && npm run build
cp .env.example .env
php artisan key:generate
```

---

## Step 4: Authentication Setup

Laravel Breeze with Livewire is used:

```bash
composer require laravel/breeze --dev
php artisan breeze:install livewire
php artisan migrate --seed
```

> Seeders create sample products so the application can be tested immediately.

---

## Step 5: Application Structure

* `products` table: name, price, stock_quantity
* `cart_items` table: user-based cart storage
* `orders` & `order_items` tables for checkout and reporting

> Each cart item is linked to the authenticated user — no session or local storage is used.

---

## Step 6: Product Browsing & Cart Management

Users can:

* Browse available products
* Add products to their cart
* Update quantities directly in the cart
* Remove items from the cart

> All cart operations are persisted in the database and scoped to the logged-in user.

---

## Step 7: Checkout Flow

On checkout:

* Cart items are converted into an order
* Order items are created
* Product stock quantities are reduced
* The cart is cleared
* The operation runs inside a database transaction

---

## Step 8: Low Stock Notification (Queue Job)

* When a product’s stock reaches a low threshold, a queued job is dispatched
* A notification email is sent to a dummy admin email
* Emails are queued to avoid blocking the request

Run the queue worker:

```bash
php artisan queue:work
```

---

## Step 9: Daily Sales Report (Scheduler)

* A scheduled job runs every evening
* Sends a summary of all products sold that day to a dummy admin email
* Implemented using Laravel 11’s scheduler

Run scheduler locally:

```bash
php artisan schedule:work
```

---

## Step 10: Mail Configuration (Demo Mode)

For local development, emails are logged instead of sent:

```env
MAIL_MAILER=log
MAIL_FROM_ADDRESS=admin@example.com
MAIL_FROM_NAME="Ecommerce App"
```

Email logs can be found in:

```
storage/logs/laravel.log
```

---

## Step 11: Frontend (Livewire)

* Product listing
* Add to cart buttons
* Cart view with quantity updates
* Remove cart items
* Tailwind CSS for styling

> Livewire provides a reactive frontend without requiring a separate SPA.

---

## Step 12: Running the Application

```bash
php artisan serve
```

Visit:

```
http://localhost:8000
```
