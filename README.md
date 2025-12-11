# 🛒 E-Commerce Desktop Application

A full-featured desktop e-commerce application built with **Java** and **JavaFX**, featuring role-based access control, product management, shopping cart functionality, order tracking, and a modern vibrant UI inspired by leading e-commerce platforms.

![Java](https://img.shields.io/badge/Java-17+-orange?style=flat&logo=java)
![JavaFX](https://img.shields.io/badge/JavaFX-25.0.1-blue?style=flat)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=flat&logo=mysql)
![License](https://img.shields.io/badge/License-MIT-green?style=flat)

## ✨ Features

### 👤 Customer Features
- **Product Browsing**: Modern 3-column grid layout with product images
- **Shopping Cart**: Add/remove items, adjust quantities with real-time updates
- **Order Placement**: Seamless checkout with automatic tax calculation (8%)
- **📦 Order History & Tracking**: View all past orders with status tracking
- **Order Details**: Detailed view of items, quantities, and pricing
- **Status Badges**: Color-coded order status (Pending, Processing, Shipped, Delivered, Cancelled)
- **Stock Visibility**: Clear "In Stock" / "Out of Stock" indicators
- **Price Display**: Indian Rupees (₹) currency format

### 👨‍💼 Admin Features
- **Product Management**: Add, modify, and delete products with ease
- **Inventory Control**: Update stock levels and view exact counts
- **Order Management**: View all customer orders in a comprehensive table
- **Order Status Updates**: Change order status with dropdown selection
- **Order Filtering**: Filter orders by status (All, Pending, Processing, etc.)
- **Order Details View**: See complete order information including customer details
- **Product Search**: Quick search products by ID
- **Tabbed Interface**: Organized operations across multiple tabs

## 🎨 Modern UI Design

Vibrant color palette inspired by **Flipkart**, **Amazon**, **Discord**, and **Myntra**:
- 🟣 **Discord Purple** (#5865F2) - Primary buttons & accents
- 🟠 **Flipkart Orange** (#FF6F00) - CTAs & important actions
- 🔵 **Electric Blue** (#2874F0) - Navigation & links
- 💗 **Myntra Pink** (#FF3F6C) - Special badges & alerts
- ⚫ **Dark Theme** (#1A1D29) - Modern dark background
- ✨ **Smooth Animations** - Hover effects and transitions

## 🛠 Technologies

- **Language**: Java 17+
- **GUI Framework**: JavaFX 25.0.1
- **Database**: MySQL 8.0
- **JDBC Driver**: MySQL Connector/J 9.3.0+
- **Architecture**: MVC Pattern with DAO Layer

## 📦 Installation

### Prerequisites
- Java JDK 17 or higher
- JavaFX SDK 25.0.1
- MySQL Server 8.0+
- MySQL Connector/J 9.3.0+

### Quick Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/ecommerce-javafx.git
   cd ecommerce-javafx
   ```

2. **Set up MySQL Database**
   ```bash
   mysql -u root -p < database_setup.sql
   ```
   This will create the database, tables, and insert sample data.

3. **Configure Database Connection**
   
   Edit `src/com/ecommerce/util/DBConnection.java`:
   ```java
   private static final String PASSWORD = "YOUR_MYSQL_PASSWORD";
   ```

4. **Compile the Project**
   ```bash
   javac -d bin -cp "path/to/mysql-connector-j-9.3.0.jar;path/to/javafx-sdk/lib/*" \
     --module-path "path/to/javafx-sdk/lib" \
     --add-modules javafx.controls,javafx.fxml \
     src/com/ecommerce/**/*.java
   ```

5. **Copy Resources**
   ```bash
   copy src\styles.css bin\
   ```

6. **Run the Application**
   ```bash
   java -cp "bin;path/to/mysql-connector-j-9.3.0.jar" \
     --module-path "path/to/javafx-sdk/lib" \
     --add-modules javafx.controls,javafx.fxml \
     com.ecommerce.gui.EcommerceApp
   ```

� **For detailed setup instructions, see [SETUP_GUIDE.md](SETUP_GUIDE.md)**

## 🔐 Default Login Credentials

| Role | Username | Password |
|------|----------|----------|
| Admin | `admin` | `admin123` |
| Customer | `customer` | `customer123` |

## 📂 Project Structure

```
E Commerce/
├── src/
│   ├── com/ecommerce/
│   │   ├── dao/              # Data Access Objects
│   │   │   ├── OrderDAO.java
│   │   │   ├── ProductDAO.java
│   │   │   └── UserDAO.java
│   │   ├── gui/              # JavaFX UI Components
│   │   │   ├── AdminPanel.java
│   │   │   ├── CartView.java
│   │   │   ├── DashboardView.java
│   │   │   ├── LoginView.java
│   │   │   ├── OrderHistoryView.java  # NEW!
│   │   │   └── EcommerceApp.java
│   │   ├── model/            # Data Models
│   │   │   ├── Order.java              # NEW!
│   │   │   ├── OrderItem.java          # NEW!
│   │   │   ├── Product.java
│   │   │   ├── User.java
│   │   │   └── CartItem.java
│   │   ├── service/          # Business Logic
│   │   │   └── OrderService.java
│   │   ├── util/             # Utilities
│   │   │   ├── DBConnection.java
│   │   │   └── DatabaseInitializer.java
│   │   └── exception/        # Custom Exceptions
│   │       ├── DatabaseException.java
│   │       └── OutOfStockException.java
│   └── styles.css            # Application Styling
├── database_setup.sql        # Database Initialization Script
├── SETUP_GUIDE.md           # Quick Setup Guide
├── .gitignore               # Git Ignore Rules
└── README.md                # This File
```

## 🚀 Features Walkthrough

### Customer Workflow
1. **Login** with customer credentials
2. **Browse Products** in the dashboard grid
3. **Add to Cart** - Click "Add to Cart" on desired products
4. **View Cart** - Click the cart button to review items
5. **Checkout** - Complete purchase with automatic calculations
6. **View Orders** - Click "📦 My Orders" to see order history
7. **Track Status** - Monitor order status with color-coded badges

### Admin Workflow
1. **Login** with admin credentials
2. **Manage Products** - Add, modify, or delete products
3. **View Orders** - Navigate to "Order Management" tab
4. **Filter Orders** - Use status dropdown to filter
5. **Update Status** - Select order and update status
6. **View Details** - Click "View Details" for order information

## 🎯 Key Highlights

- ✅ **Order History & Tracking** - Complete order management system
- ✅ **Modern UI** - Vibrant colors inspired by top e-commerce platforms
- ✅ **Role-Based Access** - Separate customer and admin interfaces
- ✅ **Real-Time Updates** - Cart and inventory sync
- ✅ **Database Integration** - MySQL with proper relationships
- ✅ **Exception Handling** - Custom exceptions for better error management
- ✅ **MVC Architecture** - Clean separation of concerns
- ✅ **Responsive Design** - Smooth animations and hover effects

## 🗄️ Database Schema

### Tables
- **users** - User authentication and roles
- **products** - Product catalog with stock management
- **orders** - Customer orders with status tracking
- **order_items** - Individual items within orders

### Relationships
- Users → Orders (One-to-Many)
- Orders → Order Items (One-to-Many)
- Products → Order Items (One-to-Many)

## 🎨 Color Palette

| Color | Hex Code | Usage |
|-------|----------|-------|
| Deep Slate | `#1A1D29` | Background |
| Rich Purple | `#5865F2` | Primary Buttons |
| Vibrant Orange | `#FF6F00` | CTAs |
| Electric Blue | `#2874F0` | Links |
| Hot Pink | `#FF3F6C` | Alerts |
| Warm Orange | `#FF9900` | Prices |

## 🐛 Troubleshooting

| Issue | Solution |
|-------|----------|
| Module javafx.controls not found | Verify JavaFX SDK path in compile/run commands |
| ClassNotFoundException: com.mysql.cj.jdbc.Driver | Check MySQL Connector JAR path |
| Access denied for user | Update password in `DBConnection.java` |
| Database does not exist | Run `database_setup.sql` first |
| Images not showing | Ensure `bin/assets/` folder exists with images |

## 📝 Future Enhancements

- [ ] Email notifications for order status changes
- [ ] Product search and filtering
- [ ] User registration functionality
- [ ] Payment gateway integration
- [ ] Order cancellation by customers
- [ ] Product reviews and ratings
- [ ] Export orders to PDF/Excel

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## � License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👨‍💻 Author
Abhinav Kumar
Created as a semester project demonstrating Java, JavaFX, and MySQL integration.

## 🙏 Acknowledgments

- UI Design inspired by Flipkart, Amazon, Discord, and Myntra
- JavaFX community for excellent documentation
- MySQL for robust database management

---

**⭐ If you find this project useful, please consider giving it a star!**
