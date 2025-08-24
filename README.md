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

# MVC Architecture using Servlet and JSP

**Date:** 24 August 2025  

---

## 📌 Introduction  

The **MVC (Model–View–Controller)** is a design pattern used to separate concerns in web applications.  
It helps in organizing code for **better readability, maintainability, and scalability**.  

In Java web applications, **Servlets and JSP** are often used to implement MVC:  

- **Model** → Represents data and business logic. (Java Classes, Database interaction with JDBC, Hibernate, etc.)  
- **View** → Presentation layer for displaying data to the user. (JSP pages, HTML, CSS, JS)  
- **Controller** → Handles client requests and coordinates between Model and View. (Servlets)  

##  MVC Workflow with Servlet & JSP  

1. **Client Request**  
   - The user sends a request through a web browser (e.g., form submission, link click).  

2. **Controller (Servlet)**  
   - The servlet receives the request.  
   - It processes the input, interacts with the Model, and decides which View (JSP) to forward the response to.  

3. **Model (Java Class / Database)**  
   - Contains business logic and data.  
   - Handles database operations (via JDBC, Hibernate, etc.).  
   - Returns results to the Controller.  

4. **View (JSP)**  
   - The JSP page displays data sent by the Controller.  
   - It contains presentation logic only (HTML, CSS, JavaScript, JSTL, EL).  

5. **Response to Client**  
   - The processed data is shown to the user through the JSP.  
##  Example MVC Flow  

###  Model (Java Class)
```java
// Student.java (Model)
public class Student {
    private int id;
    private String name;
    private int marks;

    public Student(int id, String name, int marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }
    // Getters and Setters
}



