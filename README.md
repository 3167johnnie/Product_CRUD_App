# Product_CRUD_App

import project as MAven project
👀👀👀👀Always remember the pom dependency version for  mysql connector should same version of msql version.


To create a Java utility that executes a given SQL query, extracts data, and writes it to a file, we need to follow these steps:

1. **Set Up the Project in Eclipse:**
    - Create a new Dynamic Web Project in Eclipse.
    - Set up the directory structure, including source folders and dependencies.

2. **Create a JDBC Utility:**
    - Write code to connect to the database using JDBC.
    - Execute the query and fetch the result.

3. **Write to a File:**
    - Create a file with the name as `FILE_NAME`.
    - Write the first query as a comment.
    - Fetch the result of the second query and append it to the file.

4. **Build and Deploy as a JAR:**
    - Compile the code.
    - Export the project as a JAR.
    - Deploy it on Apache Tomcat.

Let's go through the steps in detail:

### Step 1: Set Up the Dynamic Web Project in Eclipse

1. Open Eclipse and create a new Dynamic Web Project:
   - `File` → `New` → `Dynamic Web Project`.
   - Enter the project name, e.g., `QueryFileUtility`.
   - Click `Next`, select the runtime (Apache Tomcat), and finish.

2. Create the folder structure:
   - `src/main/java` for Java files.
   - `src/main/resources` for configuration files.

3. Add necessary libraries:
   - Add the JDBC driver for your database (e.g., MySQL, PostgreSQL).

### Step 2: Create the JDBC Utility

1. Create a class `DatabaseUtility` to handle database connections and queries.

```java
package com.example.utility;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;

public class DatabaseUtility {

    private static final String DB_URL = "jdbc:your_database_url";
    private static final String USER = "your_db_user";
    private static final String PASS = "your_db_password";

    public static Connection getConnection() throws Exception {
        // Load the database driver
        Class.forName("com.your_database.Driver");
        // Return the connection object
        return DriverManager.getConnection(DB_URL, USER, PASS);
    }

    public static ResultSet executeQuery(String query) throws Exception {
        Connection conn = getConnection();
        Statement stmt = conn.createStatement();
        return stmt.executeQuery(query);
    }
}
```

2. Create another class `QueryFileUtility` to write the result to the file.

```java
package com.example.utility;

import java.io.File;
import java.io.FileWriter;
import java.io.PrintWriter;
import java.sql.ResultSet;

public class QueryFileUtility {

    public static void main(String[] args) {
        try {
            // First query
            String query1 = "SELECT * FROM ACHHEADER WHERE SETTLEMENT_DATE='2022-02-23' AND FILE_NAME='abc';";
            // File name as per the query
            String fileName = "abc.txt";

            // Write first query to the file
            File file = new File(fileName);
            FileWriter fw = new FileWriter(file);
            PrintWriter pw = new PrintWriter(fw);
            pw.println(query1);

            // Execute second query and write the result to the file
            String query2 = "SELECT * FROM ACHFILEDR WHERE SETTLEMENT_DATE='2022-02-23' AND FILE_NAME='abc';";
            ResultSet rs = DatabaseUtility.executeQuery(query2);

            // Write result set to the file
            while (rs.next()) {
                // Assuming the table has columns named 'column1', 'column2', etc.
                pw.println(rs.getString("column1") + ", " + rs.getString("column2") + ", " + rs.getString("column3"));
            }

            // Close the print writer
            pw.close();
            fw.close();
            System.out.println("File written successfully!");

        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

### Step 3: Build and Deploy as a JAR

1. **Build the JAR File:**
   - Right-click on the project → `Export` → `JAR File`.
   - Select the source and resources.
   - Specify the destination JAR file name and location.
   - Click `Finish`.

2. **Deploy on Apache Tomcat:**
   - Copy the JAR file to the `WEB-INF/lib` directory of your web application in Tomcat.
   - Restart the Tomcat server.

3. **Run the Utility:**
   - You can run this Java utility directly from Eclipse using the `main` method or create a servlet to call this utility if needed.

### Notes:
- **Database Driver:** Ensure the correct database driver (JAR) is added to your project.
- **File Permissions:** The utility should have permission to write to the desired directory.
- **Exception Handling:** Add robust exception handling and logging as needed.

This utility will execute the specified queries and write the results to a text file, as requested.
