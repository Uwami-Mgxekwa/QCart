# 🛒 QuickCart

<div align="center">
  <img src="https://img.shields.io/badge/Java-17%2B-orange" alt="Java 17+"/>
  <img src="https://img.shields.io/badge/UI-Swing-blue" alt="Swing UI"/>
  <img src="https://img.shields.io/badge/License-MIT-green" alt="MIT License"/>
  <img src="https://img.shields.io/badge/Platform-Desktop-lightgrey" alt="Desktop Platform"/>
</div>

**QuickCart** is a lightweight, Java-based **food ordering application** that delivers a seamless and interactive desktop experience. Designed with simplicity, speed, and modularity in mind, the system allows users to browse a menu, manage item quantities, and view real-time order summaries. Ideal for quick-service environments, kiosks, or personal projects exploring modern Java UI design.

## 📋 Table of Contents

- [Features](#-features)
- [Architecture](#-architecture-overview)
- [Technology Stack](#-technology-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [API Reference](#-api-reference)
- [Configuration](#-configuration)
- [Contributing](#-contributing)
- [Troubleshooting](#-troubleshooting)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)
- [Contact](#-contact)

## 🍔 Features

### Core Functionality
- **📋 Interactive Menu System** — Browse food items with prices and detailed descriptions
- **➕➖ Quantity Management** — Intuitive increment/decrement controls for item quantities
- **🧾 Real-Time Order Summary** — Dynamic shopping cart that updates instantly as selections change
- **💰 Smart Price Calculation** — Automatic total cost computation with tax calculations
- **🎨 Modern UI/UX** — Clean, borderless layout designed with Swing for professional appearance

### Advanced Features
- **🔍 Search & Filter** — Quick item search and category filtering
- **💾 Order History** — Save and review previous orders
- **🖼️ Visual Menu** — Support for item images and descriptions
- **⚡ Performance Optimized** — Efficient memory usage and fast response times
- **🌐 Responsive Design** — Adaptable to different screen sizes and resolutions

## 🧱 Architecture Overview

QuickCart follows a clean, layered architecture pattern designed for maintainability and scalability:

```
┌─────────────────────────────────────────────────────────────┐
│                    Presentation Layer                       │
│              (Swing UI Components)                          │
├─────────────────────────────────────────────────────────────┤
│                    Business Logic Layer                     │
│           (CartManager, MenuController)                     │
├─────────────────────────────────────────────────────────────┤
│                    Data Access Layer                        │
│            (MenuItems, OrderItems, Pricing)                 │
└─────────────────────────────────────────────────────────────┘
```

### Layer Responsibilities

- **Presentation Layer**: Handles all user interface interactions using Swing components (`JPanel`, `JTable`, custom buttons)
- **Business Logic Layer**: Manages application state, cart operations, quantity updates, and pricing calculations
- **Data Access Layer**: Represents menu items, order data, and configuration settings

## 🛠️ Technology Stack

| Component | Technology | Version | Purpose |
|-----------|------------|---------|---------|
| **Language** | Java | 17+ | Core development language |
| **UI Framework** | Swing | Built-in | Desktop GUI framework |
| **Layout Management** | Custom Layout Managers | - | Responsive UI design |
| **Build Tool** | Maven/Gradle | Latest | Dependency management |
| **Platform** | Desktop | Cross-platform | Windows, macOS, Linux |
| **Architecture** | MVC Pattern | - | Clean separation of concerns |

## 🚀 Installation

### Prerequisites

Before running QuickCart, ensure you have the following installed:

- **Java Development Kit (JDK)** 17 or higher
- **Git** for version control
- **Maven** or **Gradle** (optional, for dependency management)

### Quick Start

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Uwami-Mgxekwa/QCart.git
   cd QCart
   ```

2. **Compile the Application**
   ```bash
   # Using javac directly
   javac -d bin src/**/*.java
   
   # Or using Maven
   mvn compile
   
   # Or using Gradle
   ./gradlew build
   ```

3. **Run the Application**
   ```bash
   # Using java directly
   java -cp bin com.quickcart.Main
   
   # Or using Maven
   mvn exec:java -Dexec.mainClass="com.quickcart.Main"
   
   # Or using Gradle
   ./gradlew run
   ```

### Alternative Installation Methods

#### Using JAR File
```bash
# Create executable JAR
jar -cvfe QuickCart.jar com.quickcart.Main -C bin .

# Run the JAR
java -jar QuickCart.jar
```

#### Development Setup
```bash
# For development with IDE
# Import project into your preferred IDE (IntelliJ IDEA, Eclipse, VS Code)
# Ensure Java 17+ is configured as project SDK
# Run Main.java directly from IDE
```

## 📱 Usage

### Getting Started

1. **Launch the Application**
   - Run the compiled application using the installation instructions above
   - The main window will display the food menu interface

2. **Browse Menu Items**
   - View available food items with prices and descriptions
   - Use search functionality to find specific items
   - Filter by categories (appetizers, mains, desserts, beverages)

3. **Add Items to Cart**
   - Click on menu items to view details
   - Use **+** and **-** buttons to adjust quantities
   - Items automatically added to your cart summary

4. **Review Order**
   - Monitor real-time order total in the cart summary
   - Review selected items and quantities
   - Modify or remove items as needed

5. **Complete Order**
   - Review final order summary
   - Confirm order details
   - Print receipt or save order history

### Menu Items Available

The application comes with a default menu including:

- **🍔 Burger and Chips** - R50
- **🌯 Grilled Chicken Wrap** - R50
- **🍟 French Fries** - R50
- **🍕 Pizza** - R50

*Note: Menu items and prices can be customized in the configuration files.*

## 📁 Project Structure

```
QCart/
├── src/                              # Source code directory
│   ├── main/
│   │   ├── java/
│   │   │   └── com/
│   │   │       └── quickcart/
│   │   │           ├── Main.java     # Application entry point
│   │   │           ├── ui/           # User interface components
│   │   │           │   ├── MainWindow.java
│   │   │           │   ├── MenuPanel.java
│   │   │           │   ├── CartPanel.java
│   │   │           │   └── components/
│   │   │           │       ├── CustomButton.java
│   │   │           │       └── QuantityControl.java
│   │   │           ├── core/         # Business logic
│   │   │           │   ├── CartManager.java
│   │   │           │   ├── MenuController.java
│   │   │           │   └── OrderProcessor.java
│   │   │           ├── model/        # Data models
│   │   │           │   ├── MenuItem.java
│   │   │           │   ├── OrderItem.java
│   │   │           │   └── Order.java
│   │   │           └── utils/        # Utility classes
│   │   │               ├── PriceCalculator.java
│   │   │               └── UIUtils.java
│   │   └── resources/                # Application resources
│   │       ├── images/               # Menu item images
│   │       ├── config/               # Configuration files
│   │       │   └── menu-config.properties
│   │       └── styles/               # UI styling resources
│   └── test/                         # Test files
│       └── java/
│           └── com/
│               └── quickcart/
│                   ├── core/
│                   └── model/
├── docs/                             # Documentation
│   ├── API.md
│   ├── USER_GUIDE.md
│   └── DEVELOPMENT.md
├── bin/                              # Compiled classes (generated)
├── target/                           # Build output (Maven)
├── build/                            # Build output (Gradle)
├── pom.xml                           # Maven configuration
├── build.gradle                      # Gradle configuration
├── .gitignore                        # Git ignore rules
├── LICENSE                           # License file
└── README.md                         # This file
```

## 🔧 API Reference

### Core Classes

#### `CartManager`
Manages shopping cart operations and state.

```java
public class CartManager {
    public void addItem(MenuItem item, int quantity)
    public void removeItem(String itemId)
    public void updateQuantity(String itemId, int newQuantity)
    public double getTotal()
    public List<OrderItem> getItems()
    public void clearCart()
}
```

#### `MenuController`
Handles menu data and operations.

```java
public class MenuController {
    public List<MenuItem> getAllItems()
    public List<MenuItem> getItemsByCategory(String category)
    public MenuItem getItemById(String id)
    public List<MenuItem> searchItems(String query)
}
```

#### `MenuItem`
Represents a food item in the menu.

```java
public class MenuItem {
    private String id;
    private String name;
    private double price;
    private String description;
    private String category;
    private String imagePath;
    
    // Constructors, getters, and setters
}
```

#### `OrderItem`
Represents an item in the shopping cart.

```java
public class OrderItem {
    private MenuItem menuItem;
    private int quantity;
    private double subtotal;
    
    // Constructors, getters, and setters
}
```

## ⚙️ Configuration

### Menu Configuration

Edit `src/main/resources/config/menu-config.properties` to customize menu items:

```properties
# Menu Items Configuration
menu.item.1.id=burger-chips
menu.item.1.name=Burger and Chips
menu.item.1.price=50.00
menu.item.1.category=mains
menu.item.1.description=Delicious beef burger with crispy chips
menu.item.1.image=burger-chips.jpg

menu.item.2.id=chicken-wrap
menu.item.2.name=Grilled Chicken Wrap
menu.item.2.price=50.00
menu.item.2.category=mains
menu.item.2.description=Grilled chicken wrapped in fresh tortilla
menu.item.2.image=chicken-wrap.jpg

# Add more items as needed
```

### Application Settings

Create `application.properties` for general settings:

```properties
# Application Configuration
app.name=QuickCart
app.version=1.0.0
app.window.width=800
app.window.height=600
app.window.resizable=true

# UI Configuration
ui.theme=modern
ui.font.family=Arial
ui.font.size=12

# Business Configuration
currency.symbol=R
tax.rate=0.15
```

## 🤝 Contributing

We welcome contributions to QuickCart! Here's how you can help:

### Getting Started

1. **Fork the Repository**
   ```bash
   # Fork the repo on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/QCart.git
   cd QCart
   ```

2. **Create a Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Follow the existing code style and conventions
   - Add appropriate comments and documentation
   - Include unit tests for new functionality

4. **Test Your Changes**
   ```bash
   # Run existing tests
   mvn test
   
   # Test the application manually
   java -cp bin com.quickcart.Main
   ```

5. **Submit a Pull Request**
   - Push your changes to your fork
   - Create a pull request on GitHub
   - Describe your changes and their purpose

### Code Style Guidelines

- Use **camelCase** for variable and method names
- Use **PascalCase** for class names
- Add **JavaDoc** comments for public methods
- Follow **Java naming conventions**
- Keep methods focused and concise
- Use meaningful variable names

### Reporting Issues

If you find a bug or have a suggestion:

1. Check existing issues first
2. Create a new issue with:
   - Clear description of the problem
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if applicable

## 🔍 Troubleshooting

### Common Issues

#### Application Won't Start
```bash
# Check Java version
java -version

# Ensure Java 17+ is installed
# Verify JAVA_HOME is set correctly
echo $JAVA_HOME
```

#### Compilation Errors
```bash
# Clean and rebuild
mvn clean compile

# Or with Gradle
./gradlew clean build
```

#### UI Display Issues
- Ensure you're running on a system with GUI support
- Check display scaling settings
- Try running with different Java versions

#### Performance Issues
- Monitor memory usage with Java profiler
- Reduce menu item count if needed
- Check for memory leaks in custom components

### Debug Mode

Enable debug logging by setting system property:
```bash
java -Ddebug=true -cp bin com.quickcart.Main
```

## 🚧 Future Enhancements

### Planned Features

- **💳 Payment Integration**
  - Credit/debit card processing
  - Digital wallet support (PayPal, Apple Pay)
  - Cash payment tracking

- **🎯 Advanced Features**
  - Customer loyalty program
  - Discount and promo code system
  - Order scheduling and delivery tracking

- **📊 Analytics & Reporting**
  - Sales reports and analytics
  - Popular item tracking
  - Customer behavior insights

- **🎨 UI/UX Improvements**
  - Animated transitions and effects
  - Theme customization
  - Mobile-responsive design

- **🔧 Technical Enhancements**
  - Database integration (MySQL, PostgreSQL)
  - REST API backend
  - Multi-language support
  - Cloud deployment options

### Contribution Opportunities

- Database integration development
- Payment gateway implementation
- UI/UX design improvements
- Mobile app development
- API development
- Testing and quality assurance

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 Uwami Mgxekwa

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## 📧 Contact

**Uwami Mgxekwa**  
*Java Developer | UI Innovator | System Design Enthusiast*

- **GitHub**: [@Uwami-Mgxekwa](https://github.com/Uwami-Mgxekwa)
- **Email**: [contact@uwami.dev](uwamimcdonald@gmail.com)
- **LinkedIn**: [Uwami Mgxekwa](https://www.linkedin.com/in/uwami-mgxekwa-bb8235283?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app)

---

### 🙏 Acknowledgments

- Thanks to all contributors who have helped improve QuickCart
- Special thanks to the Java Swing community for UI inspiration
- Appreciation to the open-source community for continuous support

---

<div align="center">
  <p>⭐ Star this repository if you find it helpful!</p>
  <p>Made with ❤️ and ☕ by Uwami Mgxekwa</p>
</div>

---

*Ready to take this to the next level? Let's connect and discuss database integration, REST API backend, or GUI enhancements with animated transitions and theme customization. Always excited to collaborate on innovative projects! 🛠️*