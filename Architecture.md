# High-Level System Architecture

The system is built using a modular full-stack architecture consisting of a React frontend, a Flask backend API, a SQLite database, and a data analysis component. Users interact with a web-based interface developed in React to enter or view their transaction data and review summary reports. The frontend communicates with the Flask backend through RESTful API endpoints, which handle business logic, validation, and data persistence. The backend stores user and transaction data in a SQLite database and invokes a simple analysis module to group and summarize expenses by category or date. The application is containerized using Docker for consistency across development and production environments, and it includes unit tests to validate core API and analysis functionality.

+---------------------------+
|      React Frontend      |
|---------------------------|
| - Expense Entry Form     |
| - Spending Summary View  |
| - Calls Flask API        |
+------------+--------------+
             |
             v
+---------------------------+
|        Flask API          |
|---------------------------|
| - /transactions (POST)    |
| - /summary (GET)          |
| - Input validation        |
| - Calls analyzer function |
+------------+--------------+
             |
             v
+---------------------------+
|     Spend Analyzer        |
|---------------------------|
| - Group by category       |
| - Aggregate totals        |
+------------+--------------+
             |
             v
+---------------------------+
|     SQLite Database       |
|---------------------------|
| - Users Table             |
| - Transactions Table      |
+---------------------------+

(Separate Component)
+---------------------------+
|      Unit Tests           |
|---------------------------|
| - Test API routes         |
| - Test analyzer logic     |
+---------------------------+
