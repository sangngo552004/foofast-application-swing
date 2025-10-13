# FooFast Application - Swing Product Management System

[![Java](https://img.shields.io/badge/Java-8%2B-blue)](https://www.oracle.com/java/) [![Swing](https://img.shields.io/badge/Java%20Swing-GUI-green)](https://docs.oracle.com/javase/tutorial/uiswing/) [![MySQL](https://img.shields.io/badge/MySQL-Database-orange)](https://www.mysql.com/) [![JDBC](https://img.shields.io/badge/JDBC-Connectivity-purple)](https://docs.oracle.com/javase/tutorial/jdbc/)

## Overview

**FooFast Application** is a **Product Management System** built with **Java Swing** following the **MVC (Model-View-Controller) architecture**. This project uses **MySQL** for data storage and **JDBC** for direct database interaction. It represents my first step into **Object-Oriented Programming (OOP)** and backend logic in Java.

The application provides a desktop GUI for managing products, including CRUD (Create, Read, Update, Delete) operations. Designed as a learning project, it demonstrates core concepts like event-driven programming, database connectivity, and separation of concerns through MVC.

This is an ongoing educational project—future updates may include advanced search features, reporting tools, and migration to more modern UI frameworks!

## Features

- **Product CRUD Operations**: Add, view, edit, and delete products via an intuitive Swing GUI.
- **Database Integration**: Seamless connection to MySQL using JDBC for persistent storage.
- **MVC Architecture**: Clean separation of UI (View), business logic (Controller), and data models (Model).
- **Data Validation**: Basic input validation for product fields (e.g., name, price, quantity).
- **Search and Filter**: Simple search functionality to query products by name or category.
- **User-Friendly Interface**: Responsive Swing components with tables, forms, and buttons.

## Technologies

- **Language**: Java 8+
- **UI Framework**: Java Swing
- **Database**: MySQL
- **Connectivity**: JDBC
- **Architecture**: MVC Pattern
- **Build Tool**: None (standard Java compilation; IDE-based)
- **IDE**: IntelliJ IDEA or Eclipse recommended

## Prerequisites

- Java Development Kit (JDK) 8 or higher
- MySQL Server 5.7+ installed and running
- IDE (IntelliJ IDEA, Eclipse, or NetBeans)
- MySQL Workbench or similar tool for database management (optional)

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/sangngo552004/foofast-application-swing.git
   cd foofast-application-swing
   ```

2. **Set Up the Database**:
   - Create a MySQL database named `foofast_db`.
   - Run the provided SQL script (if available) or create tables manually:
     ```sql
     CREATE TABLE products (
         id INT PRIMARY KEY AUTO_INCREMENT,
         name VARCHAR(255) NOT NULL,
         category VARCHAR(100),
         price DECIMAL(10,2),
         quantity INT
     );
     ```
   - Update database connection details in the source code (e.g., `DatabaseConnection.java`).

3. **Compile and Run**:
   - Open the project in your IDE.
   - Compile the Java files: `javac -cp "path/to/mysql-connector.jar" src/*.java`
   - Run the main class: `java -cp ".:path/to/mysql-connector.jar" com.example.foofast.Main`
   - Or use IDE's run configuration for `Main.java`.

   **Note**: Download the MySQL JDBC driver (`mysql-connector-java-x.x.xx.jar`) from the official MySQL site and add it to your classpath.

## Configuration

Database connection is handled in a dedicated class (e.g., `DatabaseConnection.java`). Key settings:

- **JDBC URL**: `jdbc:mysql://localhost:3306/foofast_db`
- **Username**: `root` (default; update as needed)
- **Password**: Your MySQL password
- **Driver**: `com.mysql.cj.jdbc.Driver`

Example configuration in code:
```java
String url = "jdbc:mysql://localhost:3306/foofast_db";
String user = "root";
String password = "yourpassword";
Connection conn = DriverManager.getConnection(url, user, password);
```

For production, consider using properties files for sensitive data.

## Usage

### Launching the Application
- Run `Main.java` to open the main dashboard.
- Use the menu or buttons to navigate to Product Management.

### Example Operations
1. **Add Product**:
   - Click "Add Product" button.
   - Enter details: Name, Category, Price, Quantity.
   - Click "Save" to insert into MySQL.

2. **View Products**:
   - Products display in a JTable.
   - Use search bar to filter by name.

3. **Edit/Delete**:
   - Select a row in the table.
   - Click "Edit" or "Delete" and confirm.

Sample GUI screenshot (conceptual):
- Main window with toolbar, product table, and form panel.

## Project Structure

```
foofast-application-swing/
├── src/
│   └── com/
│       └── example/
│           └── foofast/
│               ├── model/          # Entity classes (e.g., Product.java)
│               ├── view/           # Swing UI components (e.g., ProductView.java)
│               ├── controller/     # Logic handlers (e.g., ProductController.java)
│               ├── dao/            # Data Access Objects (e.g., ProductDAO.java)
|               |__ dto/            # Data transfer object 
│               ├── util/           # Utilities (e.g., DatabaseConnection.java)
│               └── Main.java       # Entry point
├── lib/                           # External JARs (e.g., mysql-connector.jar)
├── database/                      # SQL scripts (e.g., schema.sql)
├── README.md                      # This file
└── LICENSE                        # License file
```

## Testing

- **Manual Testing**: Run the app and perform CRUD operations; verify data in MySQL.
- **Unit Tests**: Add JUnit tests in `test/` folder for models and DAOs (future enhancement).
- Run tests: Use IDE or `javac` with JUnit JAR.


## Future Enhancements

- Advanced reporting and export to CSV/PDF.
- User authentication and multi-user support.
- Migration to JavaFX for modern UI.
- Integration with REST APIs for web connectivity.
- Automated unit/integration tests with JUnit.

---

*Built with ❤️ for learning Java OOP and Swing. Star the repo if it helps you!*
