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
