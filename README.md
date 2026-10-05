# Café Midori

A full-stack café web application built with **PHP, MySQL, HTML, CSS, and JavaScript**.

Café Midori provides a complete customer-facing café experience with user authentication, menu browsing, shopping cart and checkout, order tracking, customer profiles, messaging, reviews, blog content, product search, and interactive café-themed activities.

**Live Demo:** https://cafemidori.infinityfreeapp.com
**Repository:** https://github.com/LaLia63/CafeMidori

---

## Features

### Authentication & Accounts

* User registration and login
* Session-based authentication
* Logout
* User profile management
* Profile image upload and preview
* Password update
* Account status handling
* Personality test during registration
* Personalized drink recommendation based on personality-test results

### Menu & Products

Products are organized into multiple café categories:

* Coffee
* Drinks
* Bakery
* Fast Food
* Breakfast
* Healthy
* Combo Sets

The menu supports:

* Database-driven product listings
* Product categories
* Product images
* Product prices in MMK
* Quantity selection
* Pagination
* Add-to-cart functionality

### Shopping Cart

The cart is managed using PHP sessions and supports:

* Add products to cart
* Increase quantity
* Decrease quantity
* Remove items
* Update quantities
* Automatic item totals
* Grand total calculation
* Continue shopping
* Checkout

### Checkout & Orders

Customers can place orders by providing:

* Phone number
* Region
* Delivery address

Orders are stored in the database together with their individual order items.

Customers can view:

* Current orders
* Order ID
* Ordered products
* Quantity
* Price
* Subtotal
* Order date
* Order status

Supported order states include:

* Pending
* Preparing
* Ready
* Delivered
* Cancelled

Cancelled orders can also display the cancellation reason.

### Order History

Completed and cancelled orders are separated into an order-history view.

The history includes:

* Order details
* Products
* Quantities
* Prices
* Order status
* Cancellation reason when applicable

### Search

The product search functionality can search by:

* Product name
* Price
* Category

Search results are retrieved from the MySQL database.

### Blog / Midori Journal

The application includes a database-driven blog section featuring café-related content.

Blog functionality includes:

* Blog posts
* Images
* Titles
* Full article content
* Published timestamps
* Read-more pages
* New-post notification count

### Customer Messaging

Customers can send messages through the contact page.

The messaging system supports:

* Sending customer messages
* Admin replies
* Reply notifications
* Read/unread message state
* Displaying previous replies

Cancelled-order notifications are also displayed through the customer notification area.

### Customer Reviews

The home page displays customer reviews retrieved from the database, including:

* Customer name
* Profile image
* Rating
* Review message
* Review date

The homepage also calculates and displays popular products based on order quantities.

### Café Fun Zone

Café Midori also includes an interactive **Fun Zone**.

The project contains a café-themed quiz system covering topics such as:

* Coffee basics
* Brewing methods
* Café culture
* Coffee equipment
* Flavor profiles
* Coffee history
* Coffee myths and facts
* Caffeine
* Coffee and art
* Coffee and music
* Famous cafés
* Coffee and books
* Seasonal drinks
* Coffee around the world
* Coffee and health
* Coffee pairings
* Advanced barista skills
* Coffee innovation
* Coffee trivia

The `game.php` interface is also designed to provide access to additional interactive activities such as memory, latte-art, escape-room, and endless-catch experiences.

---

## Tech Stack

### Frontend

* HTML5
* CSS3
* JavaScript
* jQuery
* Bootstrap 5.3.3
* Font Awesome
* Google Fonts

### Backend

* PHP
* PHP Sessions
* MySQLi
* Prepared Statements

### Database

* MySQL / MariaDB
* phpMyAdmin SQL dump

### Development

* Git
* GitHub
* Visual Studio Code

### Deployment

* InfinityFree

---

## Database

The project includes a database dump in:

```text
cafe.sql
```

The database contains tables for the application's core functionality, including:

```text
admin
blog
categories
contact
orders
order_item
products
region
reviews
users
```

The database is used for user accounts, products, categories, orders, order items, regions, customer reviews, contact messages, blog content, and administrative data.

---

## Application Flow

```text
                    ┌───────────────┐
                    │     User      │
                    └───────┬───────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │ Authentication    │
                  │ Login / Register  │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │      Home         │
                  │ Menu / Blog /     │
                  │ Reviews / Search  │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │      Menu         │
                  │    Products       │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │   Shopping Cart   │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │     Checkout      │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │      Orders       │
                  │   Order Items     │
                  └─────────┬─────────┘
                            │
                            ▼
                  ┌───────────────────┐
                  │  Order Tracking   │
                  │   & History       │
                  └───────────────────┘

                         MySQL
                           ▲
                           │
                    PHP / MySQLi
```

---

## Project Structure

```text
CafeMidori/
│
├── DbConnect.php
├── cafe.sql
│
├── home.php
├── about.php
├── menu.php
├── blog.php
├── readmore.php
├── contact.php
├── message.php
│
├── login.php
├── Register.php
├── logout.php
├── profile.php
│
├── cart.php
├── checkout.php
├── order.php
├── orderHistory.php
│
├── search.php
│
├── coffee.php
├── drink.php
├── bakery.php
├── breakfast.php
├── fastFood.php
├── healthy.php
├── comboSet.php
│
├── quiz.php
├── game.php
│
├── header.php
├── footer.php
│
├── style.css
├── style1.css
│
└── README.md
```

---

## UI & Interaction

The interface uses a café-inspired visual design with:

* Green-based color palette
* Playfair Display typography
* Quicksand typography
* Responsive layouts
* Product cards
* Navigation states
* Image-based product presentation
* Shopping cart interactions
* Profile dropdown
* Notification badges
* Homepage image slider
* Product pagination
* Interactive quiz interface

The shared `header.php` provides the main authenticated navigation, search, cart access, notification area, profile menu, and background audio functionality.

---

## Homepage

The homepage includes:

* Image slider
* Product-category navigation
* Coffee
* Drinks
* Bakery
* Fast Food
* Best-seller section
* Customer review section

Best sellers are calculated from the quantity of products appearing in `order_item`.

---

## User Registration

Registration collects:

* Full name
* Email
* Password
* Password confirmation
* Profile image

The registration process also includes a personality-based drink recommendation.

The selected personality result determines one of:

```text
Green → Matcha Latte
Red   → Strawberry Latte
Black → Chocolate Latte
```

A new user receives a corresponding free-drink message after successful registration.

---

## Local Development

### Requirements

You need a PHP-compatible local development environment with:

* PHP 8+
* MySQL or MariaDB
* Apache or another PHP-compatible web server
* phpMyAdmin

The SQL dump was generated using:

```text
PHP 8.2.12
MariaDB 10.4.32
phpMyAdmin 5.2.1
```

---

### 1. Clone the repository

```bash
git clone <repository_url>
cd CafeMidori
```

### 2. Create the database

Create a database named:

```text
cafe
```

Import:

```text
cafe.sql
```

using phpMyAdmin.

### 3. Configure the database connection

Update the credentials in:

```text
DbConnect.php
```

according to your local MySQL/MariaDB environment.

### 4. Start the application

Place the project inside your local web-server directory, for example:

```text
htdocs/CafeMidori
```

Then start Apache and MySQL.

Open:

```text
http://localhost/CafeMidori/home.php
```

---

## Deployment

The application is currently deployed on InfinityFree.

**Live Application:**

https://cafemidori.infinityfreeapp.com

The repository is configured with the live website as its project homepage.

---

## Project Highlights

This project demonstrates practical experience with:

* Server-side PHP development
* MySQL database integration
* Relational data and joins
* CRUD-style database operations
* PHP sessions
* Authentication flows
* Form processing
* File uploads
* Prepared SQL statements
* Shopping cart state management
* Order processing
* User profiles
* Search functionality
* Pagination
* Notification systems
* Dynamic database-driven content
* JavaScript interactions
* Responsive UI development
* Git/GitHub workflow
* Deployment

---

## Author

**Hsu Yati Zaw (Lia)**

Full Stack Developer & UI/UX Designer

GitHub: https://github.com/LaLia63

---

## License

This project is a personal/portfolio project.

All rights reserved unless otherwise stated.
