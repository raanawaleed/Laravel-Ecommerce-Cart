# Laravel E-commerce Shopping Cart

A simple e-commerce shopping cart application built with **Laravel 11** and **PHP 8.2**, demonstrating clean architecture, Laravel best practices, and real-world features such as queues, scheduled jobs, and user-based cart persistence.

---

## 🚀 Tech Stack

- **Backend:** Laravel 11 (PHP 8.2)
- **Frontend:** Livewire
- **Styling:** Tailwind CSS
- **Authentication:** Laravel Breeze (Livewire)
- **Database:** MySQL / SQLite
- **Queues:** Laravel Queue (database driver)
- **Scheduler:** Laravel Task Scheduler
- **Version Control:** Git & GitHub

---

## ✨ Features

- User authentication (register / login)
- Browse products with name, price, and stock quantity
- User-based shopping cart (database-driven)
- Add products to cart
- Update cart item quantities
- Remove items from cart
- Checkout flow with order & order items creation
- Stock quantity updates on checkout
- Low stock email notification (queued job)
- Daily sales report email (scheduled job)
- Clean validation using Form Request classes
- Structured responses using API Resources

---

## 🛒 Shopping Cart Behavior

- Each cart is associated with the **authenticated user**
- Cart data is stored in the **database**
- No sessions or local storage are used
- Cart persists across page refreshes and logins

---

## 📦 Project Setup

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/raanawaleed/Laravel-Ecommerce-Cart
cd laravel-ecommerce-cart
