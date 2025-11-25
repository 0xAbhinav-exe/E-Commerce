# 🛒 E-Commerce Desktop Application

A full-featured desktop e-commerce application built with **Java** and **JavaFX**, featuring role-based access control, product management, shopping cart functionality, and order processing.

![Java](https://img.shields.io/badge/Java-17+-orange?style=flat&logo=java)
![JavaFX](https://img.shields.io/badge/JavaFX-25.0.1-blue?style=flat)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=flat&logo=mysql)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

## 📋 Table of Contents
- [Features](#-features)
- [Technologies](#-technologies)
- [Architecture](#-architecture)
- [Installation](#-installation)
- [Usage](#-usage)
- [Database Schema](#-database-schema)
- [Project Structure](#-project-structure)
- [OOP Concepts](#-oop-concepts-implemented)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 👤 Customer Features
- **Product Browsing**: View products in a modern 3-column grid layout
- **Shopping Cart**: Add/remove items, adjust quantities with real-time updates
- **Stock Visibility**: Clear "In Stock" / "Out of Stock" indicators
- **Order Placement**: Checkout with automatic tax calculation (8%)
- **Product Images**: Visual product catalog with images
- **Price Display**: Indian Rupees (₹) currency format

### 👨‍💼 Admin Features
- **Product Management**: Add, modify, and delete products
- **Inventory Control**: Update stock levels and view exact counts
- **Product Search**: Search products by ID
- **Comprehensive View**: Tabbed interface for organized operations
- **Real-time Updates**: Instant reflection of changes

### 🔐 Security
- Role-based access control (Customer/Admin)
- Secure authentication system
- SQL injection prevention using PreparedStatements
- Session management

## 🛠 Technologies

- **Language**: Java 17+
- **GUI Framework**: JavaFX 25.0.1
- **Database**: MySQL 8.0
- **JDBC Driver**: MySQL Connector/J 9.5.0
- **Build Tool**: Manual compilation (can be migrated to Maven/Gradle)
- **IDE**: Any Java IDE (Eclipse, IntelliJ IDEA, VS Code)

## 🏗 Architecture

The application follows **MVC (Model-View-Controller)** pattern with **DAO (Data Access Object)** for database operations:

```
├── Model Layer (Entities)
│   ├── Product (Abstract)
│   ├── Electronic, SmartDevice, Accessory
│   ├── User, CartItem, Order
│
├── DAO Layer (Database Operations)
│   ├── ProductDAO
│   ├── UserDAO
│   └── OrderDAO
│
├── Service Layer (Business Logic)
│   ├── OrderService
│   └── OrderCalculations (Interface)
│
├── View Layer (JavaFX GUI)
│   ├── LoginView
│   ├── DashboardView
│   ├── AdminPanel
│   └── CartView
│
└── Utility Layer
    ├── DBConnection
    └── DatabaseInitializer
```

## 📦 Installation

### Prerequisites
- **Java JDK 17** or higher
- **JavaFX SDK 25.0.1**
- **MySQL Server 8.0**
- **MySQL Connector/J 9.5.0**

### Setup Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ecommerce-app.git
   cd ecommerce-app
   ```

2. **Set up MySQL Database**
   ```sql
   CREATE DATABASE ecommerce_db;
   ```

3. **Configure Database Connection**
   
   Update `src/com/ecommerce/util/DBConnection.java`:
   ```java
   private static final String URL = "jdbc:mysql://localhost:3306/ecommerce_db";
   private static final String USER = "root";
   private static final String PASSWORD = "Abhi@123";
   ```

4. **Initialize Database**
   
   Run the database initializer:
   ```bash
   java -cp "bin;lib/mysql-connector-j-9.5.0/mysql-connector-j-9.5.0.jar" com.ecommerce.util.DatabaseInitializer
   ```

5. **Download JavaFX SDK**
   
   Download from [openjfx.io](https://openjfx.io/) and extract to `lib/javafx-sdk-25.0.1/`

6. **Download MySQL Connector**
   
   Download from [MySQL](https://dev.mysql.com/downloads/connector/j/) and extract to `lib/mysql-connector-j-9.5.0/`

7. **Compile the Project**
   ```bash
   javac -d bin --module-path "lib/javafx-sdk-25.0.1/lib" --add-modules javafx.controls,javafx.fxml -cp "lib/mysql-connector-j-9.5.0/mysql-connector-j-9.5.0.jar;src" src/com/ecommerce/gui/EcommerceApp.java
   ```

8. **Run the Application**
   ```bash
   java -cp "bin;lib/mysql-connector-j-9.5.0/mysql-connector-j-9.5.0.jar" --module-path "lib/javafx-sdk-25.0.1/lib" --add-modules javafx.controls,javafx.fxml com.ecommerce.gui.EcommerceApp
   ```

## 🚀 Usage

### Default Login Credentials

**Admin Account:**
- Username: `admin`
- Password: `admin123`

**Customer Account:**
- Username: `customer`
- Password: `customer123`

### Customer Workflow
1. Login with customer credentials
2. Browse products in the dashboard
3. Click "Add to Cart" on desired products
4. Click "Cart" button to view shopping cart
5. Adjust quantities or remove items as needed
6. Click "Proceed to Checkout" to place order

### Admin Workflow
1. Login with admin credentials
2. Access Admin Panel from dashboard
3. Use tabs to:
   - **Add Product**: Create new products
   - **View Products**: See all products with stock
   - **Modify Product**: Update product details
   - **Delete Product**: Remove products from catalog

## 🗄 Database Schema

### Tables

**users**
```sql
id INT PRIMARY KEY AUTO_INCREMENT
username VARCHAR(50) UNIQUE
password VARCHAR(100)
role ENUM('CUSTOMER', 'ADMIN')
```

**products**
```sql
id INT PRIMARY KEY AUTO_INCREMENT
name VARCHAR(100)
category VARCHAR(50)
price DECIMAL(10,2)
stock INT
brand VARCHAR(50)
attributes VARCHAR(255)
image_path VARCHAR(255)
```

**orders**
```sql
id INT PRIMARY KEY AUTO_INCREMENT
user_id INT
total_amount DECIMAL(10,2)
order_date TIMESTAMP
```

**order_items**
```sql
id INT PRIMARY KEY AUTO_INCREMENT
order_id INT
product_id INT
quantity INT
price DECIMAL(10,2)
```

## 📁 Project Structure

```
E Commerce/
├── src/
│   └── com/ecommerce/
│       ├── dao/              # Data Access Objects
│       ├── exception/        # Custom Exceptions
│       ├── gui/              # JavaFX Views
│       ├── model/            # Entity Classes
│       ├── service/          # Business Logic
│       └── util/             # Utilities
├── bin/                      # Compiled Classes
│   └── assets/              # Product Images
├── lib/                      # External Libraries
│   ├── javafx-sdk-25.0.1/
│   └── mysql-connector-j-9.5.0/
└── src/styles.css           # CSS Styling
```

## 🎓 OOP Concepts Implemented

### Polymorphism
- Abstract `getDiscount()` method with different implementations in product subclasses
- Method overriding in Electronic, SmartDevice, and Accessory classes

### Inheritance
- Product hierarchy: `Product` → `Electronic`, `SmartDevice`, `Accessory`
- Constructor chaining

### Encapsulation
- Private fields with public getters/setters
- Data hiding and access control

### Abstraction
- Abstract `Product` class
- `OrderCalculations` interface

### Exception Handling
- Custom `DatabaseException`
- Try-catch blocks for database operations
- User-friendly error messages

### Collections & Generics
- `List<Product>`, `ObservableList<Product>`
- Generic DAO methods
- Type-safe collections

### Multithreading
- Background tasks for database operations
- Synchronized cart operations
- JavaFX Task API

## 🎨 UI Features

- **Modern Design**: Navy blue color palette with gradients
- **Responsive Layout**: Scrollable grids and flexible containers
- **Visual Feedback**: Hover effects and button states
- **Product Cards**: Image, name, brand, price, stock status
- **Enhanced Cart**: Product images, quantity controls, order summary

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request


## 👨‍💻 Author

**Your Name**
- GitHub: [@0xAbhinav-exe ](https://github.com/0xAbhinav-exe)

## 🙏 Acknowledgments

- JavaFX community for excellent documentation
- MySQL for reliable database management
- All contributors and testers


⭐ **Star this repository if you found it helpful!**
