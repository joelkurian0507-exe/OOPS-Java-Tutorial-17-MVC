# OOPS-Java-Tutorial-17-MVC
## About the Project
This project demonstrates the **Model-View-Controller (MVC) architecture** in Java by creating a simple Visitor Counter application using Java Swing and MySQL.

Whenever a user clicks the button, the application increments the visitor count stored in the database and displays the updated count on the GUI.

## Technologies Used
- Java
- Java Swing
- JDBC (Java Database Connectivity)
- MySQL
- MVC Architecture

## Project Structure

```text
OOPS-Java-Tutorial-17-MVC/
├── CounterModel.java
├── CounterView.java
├── CounterController.java
├── Main.java
└── README.md
```

## MVC Architecture

### 1. Model - `CounterModel.java`
- Handles database connectivity using JDBC.
- Retrieves the current visitor count from MySQL.
- Increments and updates the visitor count.
- Inserts the initial count if the database table is empty.

### 2. View - `CounterView.java`
- Creates the graphical user interface using Java Swing.
- Displays a button to check the visitor count.
- Shows the updated visitor number using a label.

### 3. Controller - `CounterController.java`
- Connects the Model and View.
- Handles button-click events.
- Calls the Model to update the visitor count.
- Updates the View with the new count.

### 4. Main Class - `Main.java`
- Creates the Model, View, and Controller objects.
- Starts the application and displays the GUI.

## Database Configuration

Create a MySQL database named `mydb`:

```sql
CREATE DATABASE mydb;
USE mydb;

CREATE TABLE counter (
    visitor_count INT NOT NULL
);

INSERT INTO counter (visitor_count) VALUES (0);
```

Update the database credentials in `CounterModel.java` according to your MySQL configuration:

```java
private static final String URL =
    "jdbc:mysql://localhost:3306/mydb";
private static final String USER = "root";
private static final String PASSWORD = "password";
```

Replace `password` with your actual MySQL password.

Make sure the MySQL JDBC driver is added to your project's classpath.

## How to Run

1. Install Java JDK and MySQL.
2. Create the database and table using the SQL commands above.
3. Add the MySQL JDBC driver to your Java project.
4. Update the database credentials in `CounterModel.java`.
5. Compile all four Java files.
6. Run the `Main` class.

## Expected Output

A window titled **Visitor Counter** appears with a button labeled:

`Click Here to See Visitor Count`

When the button is clicked, the visitor number is displayed.

Example:

```text
Click Here to See Visitor Count

You are visitor No: 1
```

Clicking the button again increments the count:

```text
You are visitor No: 2
```

The count is stored in the MySQL database, so it can persist between application runs.

## Concepts Learned

- Model-View-Controller (MVC) architecture
- Java Swing GUI development
- JDBC database connectivity
- MySQL database operations
- Event handling using `ActionListener`
- Separation of concerns
- Object-oriented programming in Java

## Author

Created as part of my Java OOPS tutorial and practice.
