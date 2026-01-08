# Emerson_EPIC_2.0_Java_Project

# EMPLOYEE MANAGEMENT APPLICATION SETUP GUIDE

PREREQUISITES
- Docker Desktop
- IntelliJ IDEA
- Node.js and npm

--------------------------------------------------
DATABASE SETUP (CASSANDRA USING DOCKER)
--------------------------------------------------

Step 1: Launch Docker Desktop.

Step 2: Open Command Prompt (CMD) and pull the Cassandra image:
docker pull cassandra:4.1

Step 3: Run the Cassandra container:
docker run -d ^
  --name cassandra ^
  -p 9042:9042 ^
  cassandra:4.1

Step 4: Connect to Cassandra using cqlsh:
docker exec -it cassandra cqlsh
(Note: If it fails initially, wait a few seconds and try again.)

Step 5: Inside cqlsh, run the following commands in one line:
CREATE KEYSPACE employee_keyspace WITH replication = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
USE employee_keyspace;
CREATE TABLE employee (
  id UUID PRIMARY KEY,
  name TEXT,
  email TEXT,
  salary DOUBLE
);

Step 6: Exit cqlsh:
exit

Step 7: Database setup is complete.

--------------------------------------------------
BACKEND SETUP (SPRING BOOT)
--------------------------------------------------

Step 8: Open the backend folder in IntelliJ IDEA (first instance).

Step 9: Navigate to:
employee-management\src\main\java\com\example\employee_management\EmployeeManagementApplication.java
Run the application.

--------------------------------------------------
FRONTEND SETUP (UI)
--------------------------------------------------

Step 10: Open the ui folder in IntelliJ IDEA (second instance).

Step 11: Open a new terminal and run:
npm install
(You may ignore warnings.)

Step 12: Start the frontend application:
npm start

--------------------------------------------------
RUNNING THE APPLICATION
--------------------------------------------------

Step 13: The Employee Management application will open in your browser.

Step 14: Enter employee details and test the application.
