[Back to Home](../README.md#mybatis)
# The Overview of MyBatis Java Enterprise Usage Guide
Here's a step-by-step guide to using MyBatis 
in a Java Enterprise application:

1. **Add the MyBatis dependency to your project**:
You can add the MyBatis dependency to your project 
by downloading the JAR files from the MyBatis website
or using a build tool like Maven or Gradle. 
Here's an example of how to add the MyBatis 
dependency using Maven:
    ```xml
    <dependency>
        <groupId>org.mybatis</groupId>
        <artifactId>mybatis</artifactId>
        <version>3.5.7</version>
    </dependency>
    ```

2. **Configure MyBatis**:
MyBatis uses an XML-based configuration file to define 
how SQL statements are mapped to Java objects. 
Here's an example of how to configure MyBatis:
    ```xml
    <configuration>
        <environments default="development">
            <environment id="development">
                <transactionManager type="JDBC"/>
                <dataSource type="POOLED">
                    <property name="driver" value="com.mysql.jdbc.Driver"/>
                    <property name="url" value="jdbc:mysql://localhost:3306/mybatis_example"/>
                    <property name="username" value="root"/>
                    <property name="password" value=""/>
                </dataSource>
            </environment>
        </environments>
        <mappers>
            <mapper resource="com/example/mappers/EmployeeMapper.xml"/>
        </mappers>
    </configuration>
    ```
   This configuration file specifies the database connection 
   details and the SQL statements you want to use.

3. **Define data models**:
MyBatis uses Java objects to represent database tables. 
You can define data models that map to the database 
tables you want to work with.
Here's an example of how to define a data model:
    ```java
    public class Employee {
        private int id;
        private String firstName;
        private String lastName;
        private String email;
    
        // getters and setters
    }
    ```

4. **Write mapper interfaces**:
Mapper interfaces define the SQL statements you want 
to execute. You can write mapper interfaces that 
define methods for each SQL statement, and MyBatis
will generate the implementation at runtime. 
Here's an example of how to write a mapper interface:
    ```java
    public interface EmployeeMapper {
        @Select("SELECT * FROM employee WHERE id = #{id}")
        Employee findById(int id);
    
        @Insert("INSERT INTO employee (firstName, lastName, email) VALUES (#{firstName}, #{lastName}, #{email})")
        void insert(Employee employee);
    
        @Update("UPDATE employee SET firstName = #{firstName}, lastName = #{lastName}, email = #{email} WHERE id = #{id}")
        void update(Employee employee);
    
        @Delete("DELETE FROM employee WHERE id = #{id}")
        void delete(int id);
    }
    ```

5. **Use MyBatis in your code**:
You can use the mapper interfaces to execute SQL statements 
and perform database operations in your Java code. 
Here's an example of how to use MyBatis in your code:
    ```java
    SqlSessionFactory sessionFactory = new SqlSessionFactoryBuilder().build(Resources.getResourceAsStream("mybatis-config.xml"));
    SqlSession session = sessionFactory.openSession();
    EmployeeMapper employeeMapper = session.getMapper(EmployeeMapper.class);
    
    // insert a new employee
    Employee newEmployee = new Employee();
    newEmployee.setFirstName("John");
    newEmployee.setLastName("Doe");
    newEmployee.setEmail("johndoe@example.com");
    employeeMapper.insert(newEmployee);
    int newEmployeeId = newEmployee.getId();
    
    // find an employee by id
    Employee employee = employeeMapper.findById(newEmployeeId);
    
    // update an employee
    employee.setEmail("newemail@example.com");
    employeeMapper.update(employee);
    
    // delete an employee
    employeeMapper.delete(newEmployeeId);
    
    session.commit();
    session.close();
    ```