Prerequisites

1. Java JDK (version 8 or later)
2. NetBeans IDE
3. MySQL Server (e.g., XAMPP, WAMP, MySQL Workbench)
4. MySQL Connector/J (JDBC Driver) – .jar file

Step 1: Setup MySQL Database
1. Open MySQL Workbench (or XAMPP phpMyAdmin).
2. Create a new database:
   CREATE DATABASE login_db;
3. Create users table inside login_db:
   CREATE TABLE users (
     id INT AUTO_INCREMENT PRIMARY KEY,
     username VARCHAR(50) NOT NULL,
     password VARCHAR(50) NOT NULL
   );
4. Insert sample user:
   INSERT INTO users (username, password) VALUES ('test', '1234');

Step 2: Import the Project in NetBeans
1. Open NetBeans.
2. Go to File > New Project > Java with Ant > Java Application.
3. Name the project (e.g., LoginApp) and choose a location.
4. Add the following Java files in the com.mycompany.loginapp package:
   - LoginApp.java
   - LoginForm.java
   - Homepage.java
   - DatabaseConnection.java

Step 3: Add MySQL Connector/J to the Project
1. Download the connector from:
   https://dev.mysql.com/downloads/connector/j/
2. Extract and find the .jar file (e.g., mysql-connector-java-8.0.xx.jar).
3. In NetBeans:
   - Right-click Libraries under your project.
   - Select Add JAR/Folder.
   - Browse to and add the .jar file.
   - Click OK.

Step 4: Configure Database Connection
private static final String URL = "jdbc:mysql://localhost:3306/login_db";
private static final String USER = "root";         // your MySQL username
private static final String PASSWORD = "";         // your MySQL password

Step 5: Run the App
You can run the app in two ways:
Option 1: From LoginApp.java
(Modify the main method to launch the form)
public static void main(String[] args) {
    new LoginForm().setVisible(true);
}
Then right-click LoginApp.java and click Run File.
Option 2: Directly run LoginForm.java
Right-click on LoginForm.java and select Run File.

Step 6: Test the Login
1. On the LoginForm, enter:
   - Username: test
   - Password: 1234
2. Click Login
3. If credentials are correct:
   - You’ll see a success message
   - The Homepage opens with greeting Hello, test!
4. If credentials are incorrect:
   - You’ll see an error popup
