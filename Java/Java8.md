---
created: 2026-10-26T12:48
updated: 2026-10-28T20:18
---
Functional Interface -> interface that only has 1 abstract method, suitable for use with lambda expressions

```

package java.lang;

@FunctionalInterface
public interface Runnable {
    /**
     * Runs this operation.
     */
    void run();
}
```

see only one abstract methods in Runnable FunctionalInterface

Types of Functional Interface:
Function-> one arg 1 output
Consumer -> only 1 argument no output(void)
Predicate-> [](https://www.geeksforgeeks.org/java/java-8-predicate-with-examples/) a boolean-valued function of one argument. filtering operations in streams.
Supplier-> no arg/input but returns an output

java 8 features:
->lambda expressions: implements functional interface 
-> [[Streams]]