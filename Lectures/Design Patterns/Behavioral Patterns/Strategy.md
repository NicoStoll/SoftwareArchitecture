#pattern #behavioralPattern

The strategy pattern is a behavioral pattern, that allows you to define a family of algorithms, encapsulate each one as a separate class and make them interchangeable. This lets the algorithm vary independently from the clients that use it.

![[StrategyPattern.png]]

```java

public interface Strategy {
    int doOperation(int num1, int num2);
}

public class AdditionStrategy implements Strategy {
    @Override
    public int doOperation(int num1, int num2) {
        return num1 + num2;
    }
}

public class SubtractionStrategy implements Strategy {
    @Override
    public int doOperation(int num1, int num2) {
        return num1 - num2;
    }
}

public class MultiplicationStrategy implements Strategy {
    @Override
    public int doOperation(int num1, int num2) {
        return num1 * num2;
    }
}

public class Context {
    private Strategy strategy;

    public Context(Strategy strategy) {
        this.strategy = strategy;
    }

    public void setStrategy(Strategy strategy) {
        this.strategy = strategy;
    }

    public int executeStrategy(int num1, int num2) {
        return strategy.doOperation(num1, num2);
    }
}

```