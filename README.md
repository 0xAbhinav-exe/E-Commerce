# 🛒 E-Commerce Desktop Application

A full-featured desktop e-commerce application built with **Java** and **JavaFX**, featuring role-based access control, product management, shopping cart functionality, and order processing.

![Java](https://img.shields.io/badge/Java-17+-orange?style=flat&logo=java)
![JavaFX](https://img.shields.io/badge/JavaFX-25.0.1-blue?style=flat)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=flat&logo=mysql)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

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

## 🛠 Technologies

- **Language**: Java 17+
- **GUI Framework**: JavaFX 25.0.1
- **Database**: MySQL 8.0
- **JDBC Driver**: MySQL Connector/J 9.5.0

## 📦 Installation

### Prerequisites
- Java JDK 17 or higher
- JavaFX SDK 25.0.1
- MySQL Server 8.0
- MySQL Connector/J 9.5.0

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

4. **Run the Application**
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

## 🎓 OOP Concepts Implemented

- **Polymorphism**: Abstract methods with different implementations
- **Inheritance**: Product hierarchy (Product → Electronic, SmartDevice, Accessory)
- **Encapsulation**: Private fields with getters/setters
- **Exception Handling**: Custom DatabaseException
- **Collections & Generics**: Type-safe collections
- **Multithreading**: Background tasks for database operations

## 👨‍💻 Author

**Abhinav Kumar**
- GitHub: [@yourusername](https://github.com/yourusername)

---

⭐ **Star this repository if you found it helpful!**

