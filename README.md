# `Product Management System`

## Table of contents
- [Requirements](#requirements)
- [Getting started](#getting-started)

## Requirements

This was built on Laravel 10 and its requirements are:
- requires a minimum PHP version of 8.1
- requires a minimum Node version of 18
- composer
- MySQL or MariaDB

[Back to the top](#product-management-system)

## Getting started

After cloning this repo:

1. Copy the .env.example

    ```bash
    cp .env.example .env
    ```

2. Within the new `.env` file, update a few values:

    ```
    DB_DATABASE=
    DB_USERNAME=
    DB_PASSWORD=
    ```

3. Run:

    ```bash
    php artisan key:generate
    ```

4. Install Laravel dependencies:

    ```bash
    composer install
    ```

5. Install even more dependencies:

    ```bash
    npm install
    ```

6. Run migrations:

    ```bash
    php artisan migrate
    ```

7. Run seeder:

    ```bash
    php artisan db:seed
    ```

8. Start the application:

    ```bash
    php artisan serve
    ```

9. In a new tab, navigate back to the root of the project and run:

    ```bash
    npm run dev
    ```

10. Navigate to [localhost:8000](http://localhost:8000) in your browser

[Back to the top](#product-management-system)