# Laravel API with Sanctum Authentication
This project is a RESTful API built with Laravel, demonstrating how to create and protect API endpoints using Laravel Sanctum. The API includes user authentication (registration, login, and logout) and a product management system.

## Features
1. User authentication (registration, login, and logout) using Laravel Sanctum.
2. Protected API routes that require authentication.
3. CRUD operations for products, including search functionality.

## Prerequisites
Before running this project, ensure you have the following installed:

```bash
PHP
Composer
Laravel
MySQL
```
## Getting Started
### Installation

1. **Clone the repository:**
```bash
git clone https://github.com/Ratified/Laravel-API-with-Sanctum-Authentication.git
cd laravel-api-sanctum
```

2. **Install dependencies:**
```bash
composer install
```

3. **Set up the environment:**

4. **Copy the .env.example file and rename it to .env:**
```bash
cp .env.example .env
```

5. **Configure the .env file with your database credentials and other necessary settings.**

6. **Generate an application key:**
```bash
php artisan key:generate
```

7. **Run database migrations:**
```bash
php artisan migrate
```

8. **Run the application:**
```bash
php artisan serve
```

## API Routes
### Public Routes
Register: POST /register

Payload: { "name": "John", "email": "john@example.com", "password": "password", "password_confirmation": "password" }
Login: POST /login

Payload: { "email": "john@example.com", "password": "password" }
Get All Products: GET /products

Get Single Product: GET /products/{id}

Search Products: GET /products/search/{name}

### Protected Routes
These routes require the user to be authenticated via a token.

Create Product: POST /products

Payload: { "name": "Product Name", "slug": "product-slug", "description": "Product description" }
Update Product: POST /products/{id}

Payload: { "name": "Updated Name", "slug": "updated-slug", "description": "Updated description" }
Delete Product: DELETE /products/{id}

Logout: POST /logout

### Authentication
The API uses Laravel Sanctum to protect certain routes. After logging in or registering, users receive a token that they need to include in the Authorization header for subsequent requests to protected routes.

### Conclusion
This project provides a simple yet effective demonstration of how to create and protect Laravel APIs with Laravel Sanctum. It includes user authentication, CRUD operations, and route protection for authenticated users.
