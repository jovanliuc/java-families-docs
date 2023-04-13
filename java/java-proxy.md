[Back to Home](../README.md)
# The Overview of Java Proxy
In Java, there are two types of proxies: 
dynamic proxies and static proxies.

Dynamic proxies: Dynamic proxies are created
at runtime and allow you to create a proxy object 
that implements one or more interfaces at runtime. 
Dynamic proxies are created using 
the `java.lang.reflect.Proxy` class 
and require an interface to be 
specified at runtime. 
Dynamic proxies are useful 
when you need to create a large number of 
similar proxy objects or when you don't know 
the implementation of the target object 
at compile time. 
Here is an example:

```java
public interface MyInterface {
    void doSomething();
}

public class RealObject implements MyInterface {
    public void doSomething() {
        System.out.println("Doing something");
    }
}

public class DynamicProxy implements InvocationHandler {
    private Object target;

    public DynamicProxy(Object target) {
        this.target = target;
    }

    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
        System.out.println("Before " + method.getName());
        Object result = method.invoke(target, args);
        System.out.println("After " + method.getName());
        return result;
    }
}

MyInterface realObject = new RealObject();
InvocationHandler handler = new DynamicProxy(realObject);
MyInterface proxy = (MyInterface) Proxy.newProxyInstance(
MyInterface.class.getClassLoader(),
new Class<?>[] { MyInterface.class },
handler);
proxy.doSomething();
```

In this example, RealObject is the real object 
that implements the MyInterface interface. 
DynamicProxy is the dynamic proxy class 
that implements the InvocationHandler interface 
and intercepts method calls to the real object. 
When `doSomething()` is called on the proxy object,
it intercepts the call and adds some additional behavior 
before and after calling the real object's 
`doSomething()` method.

Static proxies: Static proxies are created
at compile time and require you to create 
a new class for each proxy object. 
Static proxies are useful
when you need to add behavior to an object 
that cannot be achieved through dynamic proxies
or when you know the implementation of 
the target object at compile time. 
Here is an example:

```java
public interface MyInterface {
    void doSomething();
}

public class RealObject implements MyInterface {
    public void doSomething() {
        System.out.println("Doing something");
    }
}

public class StaticProxy implements MyInterface {
    private RealObject realObject;

    public StaticProxy(RealObject realObject) {
        this.realObject = realObject;
    }

    public void doSomething() {
        System.out.println("Before doing something");
        realObject.doSomething();
        System.out.println("After doing something");
    }
}

MyInterface realObject = new RealObject();
MyInterface proxy = new StaticProxy((RealObject) realObject);
proxy.doSomething();
```

In this example, RealObject is the real object 
that implements the MyInterface interface. 
StaticProxy is the static proxy class 
that also implements the MyInterface interface 
and has a reference to the RealObject. 
When `doSomething()` is called on the proxy object, 
it intercepts the call and adds some additional behavior 
before and after calling the real object's
`doSomething()` method.

# Java Proxy FAQ
## 1. What is a Java Proxy?
In Java, a proxy is an object that stands 
in place of another object and can be used 
to control access to the original object
or to add additional functionality to it.

## 2. What are the types of Java proxies?
There are two types of Java proxies: 
static proxies and dynamic proxies.

## 3. What is a static proxy in Java?
A static proxy is a proxy class that is 
generated at compile time. The proxy class
implements the same interface as the 
original object and delegates all method 
calls to the original object.

## 4. What is a dynamic proxy in Java?
A dynamic proxy is a proxy class that is 
created at runtime. The proxy class implements
the same interface as the original object 
and intercepts method calls to the original object,
allowing the proxy to add additional functionality 
or control access to the original object.

## 5. How do you create a static proxy in Java?
To create a static proxy in Java, 
you create a new class that implements 
the same interface as the original object,
and then create an instance of the original object
and pass it to the constructor of the proxy class. 
In the methods of the proxy class, 
you delegate calls to the original object.

## 6. How do you create a dynamic proxy in Java?
To create a dynamic proxy in Java, 
you use the `java.lang.reflect.Proxy` class.
You create an instance of the Proxy class 
and pass it the `ClassLoader` for the interface 
you want to proxy, an array of interfaces 
to implement, and an InvocationHandler 
that intercepts method calls to the proxy.

## 7. What is an InvocationHandler in Java?
An InvocationHandler is an interface in 
Java that is used to intercept method 
calls to a proxy object. The `InvocationHandler`
has a single method, `invoke()`, which is called 
whenever a method is invoked on the proxy object.

## 8. What are some use cases for Java proxies?
Java proxies can be used for a variety of purposes, such as:
- Implementing remote method invocation (RMI) and distributed computing
- Implementing caching and lazy loading of data
- Implementing security and access control
- Implementing logging and profiling
- Implementing transaction management
- Implementing AOP (aspect-oriented programming)