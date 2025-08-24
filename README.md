# JSP with JDBC Connection  

This project demonstrates how to connect a **JSP page with a MySQL database** using **JDBC**.  
##  Steps in Workflow
1. **Load JDBC Driver**  
   - The driver class is loaded using:  
     ```java
     Class.forName("com.mysql.cj.jdbc.Driver");
     ```
2. **Establish Connection**  
   - Use `DriverManager` to connect JSP with MySQL:  
     ```java
     Connection con = DriverManager.getConnection(
         "jdbc:mysql://localhost:3306/databasename", "username", "password");
     ```
3. **Create Statement**  
   - Prepare a SQL query:  
     ```java
     Statement st = con.createStatement();
     ```
4. **Execute Query**  
   - Run `SELECT`, `INSERT`, `UPDATE`, or `DELETE` queries:  
     ```java
     ResultSet rs = st.executeQuery("SELECT * FROM users");
     ```
5. **Process Results**  
   - Retrieve data from the `ResultSet`:  
     ```java
     while(rs.next()) {
         out.println(rs.getString("name"));
     }
6. **Close Connection**  
   - Always close resources to avoid memory leaks:  
     ```java
     rs.close();
     st.close();
     con.close();
## ✅ Summary
- Import JDBC driver  
- Connect JSP to database  
- Create and execute SQL queries  
- Display results on JSP page  
- Close the connection  

This ensures smooth interaction between **JSP** and **MySQL Database**.


