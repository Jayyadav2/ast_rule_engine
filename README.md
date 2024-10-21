Rule Engine with AST
Overview
This project implements a Rule Engine using an Abstract Syntax Tree (AST) representation. The system allows users to:

Create rules based on conditions.
Combine multiple rules.
Evaluate rules against user attributes.
Modify existing rules.
The frontend is developed in React, while the backend is built using Spring Boot with Java. The rule engine uses AST to parse and evaluate conditions dynamically.

Features
Create Rules: Users can define complex rules with logical operators (AND, OR) and conditions.
Combine Rules: Multiple rules can be combined to form more intricate rule sets.
Evaluate Rules: Evaluate the defined rules against provided attributes (e.g., age, department, salary).
Modify Rules: Existing rules can be updated dynamically.
Technologies Used
Backend:
Spring Boot: Java framework for building the backend API.
MySQL: For storing rules and node entities.
JPA: For object-relational mapping with MySQL.
Docker: To containerize the backend and database.
Frontend:
React: JavaScript framework for building the user interface.
Axios: For handling API requests.
CSS: For styling the frontend.
Setup Instructions
Backend Setup
Clone the repository:

bash
Copy code
git clone https://github.com/Jayyadav2/ast_rule_engine-ast.git

Build the Backend: Make sure you have Java and Maven installed. Run the following command to build the project:

bash
Copy code
mvn clean install
Setup MySQL Database: Ensure MySQL is running and create a database:

sql
Copy code
CREATE DATABASE rule_engine;
Configure Application Properties: Update the database credentials in src/main/resources/application.properties:

properties
Copy code
spring.datasource.url=jdbc:mysql://localhost:3306/rule_engine
spring.datasource.username=your-username
spring.datasource.password=your-password
Run the Application: Use the following command to run the Spring Boot application:

bash
Copy code
mvn spring-boot:run
Dockerized MySQL: Alternatively, you can run MySQL in Docker. Pull and run the MySQL image:

bash
Copy code
docker run --name mysql-rule-engine -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=rule_engine -p 3306:3306 -d mysql:latest
Frontend Setup
Navigate to the Frontend Directory:

bash
Copy code
cd ../frontend
Install Dependencies: Ensure you have Node.js installed. Run the following command to install dependencies:

bash
Copy code
npm install
Start the Frontend: Start the React development server:

bash
Copy code
npm start
The frontend will be available at http://localhost:3000.

Running the Application
Create Rule: Enter a rule string in the frontend, e.g., age > 30 AND department = 'Sales', and click "Create Rule."

Combine Rules: Create multiple rules, and then click "Combine Rules" to generate a combined rule.

Evaluate Rule: Enter attributes (age, department, etc.) in the frontend, and evaluate against the created/combined rule.

Modify Rule: Enter a rule ID and a new rule string to modify an existing rule.

Design Choices
Abstract Syntax Tree (AST):

The AST structure allows flexible and efficient rule parsing. Each node in the AST represents a logical operator (AND, OR) or a condition (e.g., age > 30).
This makes it easy to parse, combine, and evaluate rules dynamically.
Separation of Concerns:

The backend handles rule parsing, combination, and evaluation logic.
The frontend is a simple interface for users to interact with the rule engine.
Dynamic Rule Evaluation:

The rule evaluation function checks conditions dynamically against user-provided data, allowing for real-time decision-making.
Dependencies
Backend:
Java 17
Spring Boot 3.0
MySQL 8.0
Docker (optional)
Frontend:
Node.js 18.x
React 18.x
Axios
How to Use Docker (Optional)
To run the backend and MySQL in Docker containers:

Build the Docker image for the backend:

bash
Copy code
docker build -t rule-engine-backend .
Run MySQL in a container:

bash
Copy code
docker run --name mysql-rule-engine -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=rule_engine -p 3306:3306 -d mysql:latest
Run the backend container:

bash
Copy code
docker run -p 8080:8080 --link mysql-rule-engine:mysql rule-engine-backend
Now, the application should be up and running with the backend accessible at http://localhost:8080.

Conclusion
This project demonstrates how to build a rule engine with AST representation, allowing dynamic rule creation, combination, and evaluation. It also showcases the integration of a frontend interface for rule management.

Feel free to modify and extend this project as per your requirements.
