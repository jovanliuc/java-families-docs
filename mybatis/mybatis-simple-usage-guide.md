[Back to Home](../README.md#mybatis)
# The Overview of MyBatis Simple Usage Guide
Here's a simple usage guide for MyBatis:

1. Define your database schema: Before you can
use MyBatis, you need to have a database 
schema defined. This includes tables, columns,
and relationships.

2. Create your data model: Next, you need to create 
your data model in Java. This data model should 
correspond to the database schema. You can use 
annotations to map the data model to the database 
schema. For example, if you have a table called 
users with columns id, name, and email, you could 
create a Java class like this:
    ```java
    public class User {
      private int id;
      private String name;
      private String email;
    
      // Getters and setters
    }
    ```
   
    You can use annotations like `@Table` and `@Column`
    to specify the database table and column names:

    ```java
    @Table(name = "users")
    public class User {
      @Column(name = "id")
      private int id;
      
      @Column(name = "name")
      private String name;
      
      @Column(name = "email")
      private String email;
    
      // Getters and setters
    }
    ```

3. Create your MyBatis configuration file: You need to create
a MyBatis configuration file that specifies the database
connection details and mappings between SQL queries and
Java methods. Here's an example of a simple MyBatis 
configuration file:
    ```xml
    <?xml version="1.0" encoding="UTF-8" ?>
    <!DOCTYPE configuration PUBLIC "-//mybatis.org//DTD Config 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-config.dtd">
    <configuration>
      <environments default="development">
        <environment id="development">
          <transactionManager type="JDBC"/>
          <dataSource type="POOLED">
            <property name="driver" value="com.mysql.jdbc.Driver"/>
            <property name="url" value="jdbc:mysql://localhost:3306/mydatabase"/>
            <property name="username" value="myuser"/>
            <property name="password" value="mypassword"/>
          </dataSource>
        </environment>
      </environments>
      <mappers>
        <mapper resource="com/example/mapper/UserMapper.xml"/>
      </mappers>
    </configuration>
    ```
    In this example, the configuration file specifies the JDBC
    driver, database URL, username, and password. It also 
    includes a mapper file that contains SQL statements.

4. Create your MyBatis mapper file: The MyBatis mapper file 
contains SQL queries and maps them to Java methods. 
Here's an example of a simple mapper file:
    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN"
        "http://mybatis.org/dtd/mybatis-3-mapper.dtd">
    <mapper namespace="com.example.mapper.UserMapper">
        <select id="getUserById" parameterType="int" resultType="com.example.model.User">
            SELECT * FROM users WHERE id = #{id}
        </select>
    </mapper>
    ```
    In this example, the mapper file specifies a select 
    statement that retrieves a user by ID.

5. Use MyBatis APIs to execute queries: Finally, you can
use MyBatis APIs to execute SQL queries. Here's an
example of how to use MyBatis to retrieve a user by ID:
    ```java
    String resource = "mybatis-config.xml";
    InputStream inputStream = Resources.getResourceAsStream(resource);
    SqlSessionFactory sqlSessionFactory = new SqlSessionFactoryBuilder().build(inputStream);
    
    SqlSession session = sqlSessionFactory.openSession();
    try {
      UserMapper mapper = session.getMapper(UserMapper.class);
      User user = mapper.getUserById(1);
    } finally {
      session.close();
    }
    ```
   
