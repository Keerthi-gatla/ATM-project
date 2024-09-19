# ATM Project

This project simulates an ATM system using Java and MySQL. It includes functionalities for account management, customer interactions, and transaction processing.

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Database Schema](#database-schema)
- [Setup Instructions](#setup-instructions)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Introduction
This ATM project is designed to provide a simple and effective way to manage bank accounts and perform transactions. The backend is powered by MySQL, and the frontend is developed using Java in Eclipse IDE.

## Features
- Account creation and management
- Customer login and authentication
- Deposit and withdrawal transactions
- Balance inquiry
- Account deletion

## Database Schema
The database consists of the following tables:
- **account (acc)**: Stores account details.
- **customer**: Stores customer information.

## Setup Instructions

### Prerequisites
- Java Development Kit (JDK)
- Eclipse IDE
- MySQL Server and MySQL Workbench

### Steps to Setup

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/atm-project.git
   cd atm-project
   ```

2. **Install MySQL**
   - Download MySQL from the [official website](https://dev.mysql.com/downloads/installer/).
   - Follow the installation instructions to set up MySQL Server and MySQL Workbench.
   - Create a new database and execute the following SQL commands to create the necessary tables:
     ```sql
     CREATE DATABASE atm_db;
     USE atm_db;

     CREATE TABLE account (
         acc_id INT AUTO_INCREMENT PRIMARY KEY,
         acc_number VARCHAR(20) NOT NULL,
         balance DECIMAL(10, 2) NOT NULL
     );

     CREATE TABLE customer (
         cust_id INT AUTO_INCREMENT PRIMARY KEY,
         name VARCHAR(100) NOT NULL,
         acc_id INT,
         FOREIGN KEY (acc_id) REFERENCES account(acc_id)
     );
     ```

3. **Install Eclipse**
   - Download Eclipse IDE from the [official website](https://www.eclipse.org/downloads/).
   - Follow the installation instructions to set up Eclipse on your system.

4. **Configure Eclipse Project**
   - Open Eclipse IDE and create a new Java project.
   - Add the MySQL Connector/J JAR file to your project's build path.
   - Import the project files into Eclipse.

5. **Database Connection**
   - Update the database connection settings in your Java code:
     ```java
     String url = "jdbc:mysql://localhost:3306/atm_db";
     String username = "your_mysql_username";
     String password = "your_mysql_password";
     Connection conn = DriverManager.getConnection(url, username, password);
     ```

6. **Implement Switch Statements for Login and Delete Options**
   - Add switch statements in your main class to handle different user actions:
     ```java
     switch (option) {
         case 1:
             // Login logic
             break;
         case 2:
             // Delete account logic
             break;
         // Other cases
     }
     ```

## Usage
1. **Run the Application**
   - Right-click on the project in Eclipse and select `Run As -> Java Application`.

2. **Interact with the ATM System**
   - Follow the on-screen prompts to create accounts, log in, perform transactions, and manage accounts.

## Contributing
Contributions are welcome! Please fork the repository and submit a pull request.

## License
This project is licensed under the MIT License.

## Contact
For any questions or support, please contact [Keerthi](mailto:keerthi.ece.software@gmail.com).
