# Class and Object level lock

**1. Object-Level Lock**

**What It Is:** An object-level lock is a lock associated with a specific instance of a class. When a thread acquires an object-level lock, it prevents other threads from accessing synchronized code for that particular instance.

**How It Works:** When a thread enters a synchronized instance method or block, it locks the object on which the method was called. Other threads attempting to enter any synchronized code on the same instance are blocked until the lock is released.

```java
public class MyClass {
    public synchronized void instanceMethod() {
        // Code here is protected by an object-level lock
        // Only one thread can execute this method on the same instance
    }
}
```

**2. Class-Level Lock**

**What It Is:** A class-level lock is a lock associated with the Class object of a particular class. It ensures that only one thread can execute static synchronized methods or blocks for a particular class at a time, regardless of the instance.

**How It Works:** When a thread acquires a class-level lock, it locks the entire class, blocking access to all other threads that want to execute any static synchronized code in that class. The lock is placed on the Class object itself, which is shared across all instances.

```java
public class MyClass {
    public static synchronized void staticMethod() {
        // Code here is protected by a class-level lock
        // Only one thread can execute this method for this class, regardless of the instance
    }
}
```
