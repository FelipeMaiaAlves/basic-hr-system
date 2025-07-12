basic-hr-system 💼🧑‍💻
A simple Human Resources (HR) system developed in Java with MySQL database integration.

📋 Description
This project is a basic HR system that allows managing departments and employees, storing data in a MySQL database. The system provides features to:

🏢 Register departments and employees
📄 List registered departments and employees
💾 Export the employee list to a CSV file
📊 Generate salary charts in PNG format

The system uses JDBC for database connection and the JFreeChart library for chart generation.

🚀 Features
Department Registration 🏢
Add new departments to the database.

Department Listing 📋
Display all registered departments.

Employee Registration 👩‍💼
Add employees linked to departments, with salary data.

Employee Listing 📃
Display all employees with their respective departments and salaries.

CSV Export 💾
Generate an employees.csv file with employee data.

Salary Chart 📈
Create a bar chart (salary_chart.png) showing employee salaries.

📁 Project Structure
src/ — Java source code:

Connection.java — Class for MySQL connection using JDBC 🔗

Department.java — Department model 🏢

DepartmentDAO.java — CRUD operations for departments 🛠️

Employee.java — Employee model 👤

EmployeeDAO.java — CRUD operations for employees and CSV export 📄

ChartGenerator.java — Salary chart generation using JFreeChart 📊

Main.java — Command-line interface to interact with the system 🖥️

lib/ — Dependencies (e.g., JDBC driver, JFreeChart) 📦
bin/ — Compiled .class files 💾
employees.csv — Generated CSV file 💿
salary_chart.png — Generated salary chart image 🖼️

🛠️ Technologies Used
Java 8+ ☕

MySQL 🐬

JDBC 🔗

JFreeChart 📊

⚙️ How to Use
Set up MySQL database
Create the rh database and the tables departamentos and funcionarios:

sql
Copiar
Editar
CREATE DATABASE rh;
USE rh;

CREATE TABLE departamentos (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(255) NOT NULL
);

CREATE TABLE funcionarios (
  id INT AUTO_INCREMENT PRIMARY KEY,
  nome VARCHAR(255) NOT NULL,
  departamento_id INT,
  salario DOUBLE,
  FOREIGN KEY (departamento_id) REFERENCES departamentos(id)
);
Adjust connection credentials
In the Connection.java file, set your MySQL username and password:

java
Copiar
Editar
private static final String USUARIO = "root";
private static final String SENHA = "password";
Compile and run
Compile the project and run the Main class to open the command menu. ▶️

System usage
Use the command-line menu to register, list, export, and generate salary charts.
