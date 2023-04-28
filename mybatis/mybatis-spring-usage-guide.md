[Back to Home](../README.md#mybatis)
# The Overview of MyBatis Spring Usage Guide

In this guide, we will discuss how to use 
MyBatis with Spring to build robust and scalable
Java applications.

**Step 1: Add dependencies**

The first step is to add the necessary dependencies 
to your project. You will need the following 
dependencies:
```xml
<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis</artifactId>
    <version>{version}</version>
</dependency>

<dependency>
    <groupId>org.mybatis</groupId>
    <artifactId>mybatis-spring</artifactId>
    <version>{version}</version>
</dependency>
```
Replace `{version}` with the desired version of MyBatis 
and MyBatis-Spring.

**Step 2: Create a MyBatis configuration file**

MyBatis uses an XML configuration file to define the 
mapping between Java objects and database tables. 
Create a file named `mybatis-config.xml` in your project's
resources folder and add the following content:
```xml
<configuration>
    <typeAliases>
        <!-- Add your type aliases here -->
    </typeAliases>

    <mappers>
        <!-- Add your mappers here -->
    </mappers>
</configuration>
```
You can add your type aliases and mappers to this file later.

**Step 3: Configure Spring to use MyBatis**

To configure Spring to use MyBatis, you need to define a 
`SqlSessionFactory` bean. This bean is responsible for 
creating `SqlSession` instances, which in turn are used 
to execute database queries.

Add the following bean definition to your Spring 
configuration file:
```xml
<bean id="sqlSessionFactory" class="org.mybatis.spring.SqlSessionFactoryBean">
    <property name="dataSource" ref="dataSource"/>
    <property name="configLocation" value="classpath:mybatis-config.xml"/>
</bean>
```
Replace `dataSource` with the name of your `DataSource` bean.

**Step 4: Create a mapper interface**

MyBatis uses interfaces to define database operations.
Create an interface that corresponds to the database 
table you want to interact with.

For example, suppose you have a `users` table in your
database. You can create a `UserMapper` interface like this:
```java
public interface UserMapper {
    User getUserById(int id);
    List<User> getAllUsers();
    void insertUser(User user);
    void updateUser(User user);
    void deleteUser(int id);
}
```

**Step 5: Create a mapper XML file**

Create an XML file that maps the methods in your
`UserMapper` interface to SQL queries. Suppose your 
`users` table has `id`, `name`, and `email` columns. 
You can create a file named `UserMapper.xml` in your
project's resources folder and add the following 
content:
```xml
<mapper namespace="com.example.mapper.UserMapper">
    <select id="getUserById" parameterType="int" resultType="com.example.model.User">
        SELECT * FROM users WHERE id = #{id}
    </select>

    <select id="getAllUsers" resultType="com.example.model.User">
        SELECT * FROM users
    </select>

    <insert id="insertUser" parameterType="com.example.model.User">
        INSERT INTO users (name, email) VALUES (#{name}, #{email})
    </insert>

    <update id="updateUser" parameterType="com.example.model.User">
        UPDATE users SET name = #{name}, email = #{email} WHERE id = #{id}
    </update>
    <update id="updateUser" parameterType="com.example.model.User">
        DELETE FROM users WHERE id = #{id}
    </update>
</mapper>
```

**Step 6: Test mapper interfaces in your Spring components**
```java
@Service
public class UserService {
    @Autowired
    private UserMapper userMapper;
    
    public User getUserById(int id) {
        return userMapper.findById(id);
    }

   public List<User> getAllUsers() {
        return userMapper.getAllUsers();
   }
   
   public void insertUser(User user) {
      userMapper.insertUser(user);
   }
   
   public void updateUser(User user) {
      userMapper.updateUser(user);
   }
   
   public void deleteUser(int id) {
      userMapper.deleteUser(id);
   }
}
```