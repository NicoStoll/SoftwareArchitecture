#pattern #structuralPattern

**Definition:** Is a special object, that converts the interface of one object so that another object can understand it. It is also known as a wrapper. The adapter allows adaption of interfaces.

![[Pasted image 20240525095054.png]]

```java
// RoundHole class
class RoundHole {
    private double radius;

    public RoundHole(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }

    public boolean fits(RoundPeg peg) {
        return this.getRadius() >= peg.getRadius();
    }
}

// RoundPeg class
class RoundPeg {
    private double radius;

    public RoundPeg(double radius) {
        this.radius = radius;
    }

    public double getRadius() {
        return radius;
    }
}

// SquarePeg class
class SquarePeg {
    private double width;

    public SquarePeg(double width) {
        this.width = width;
    }

    public double getWidth() {
        return width;
    }
}

// SquarePegAdapter class
class SquarePegAdapter extends RoundPeg {
    private SquarePeg peg;

    public SquarePegAdapter(SquarePeg peg) {
        super(0); // Call to the parent constructor
        this.peg = peg;
    }

    @Override
    public double getRadius() {
        // Calculate a radius that could fit the square peg
        return peg.getWidth() * Math.sqrt(2) / 2;
    }
}

// Client code
public class Main {
    public static void main(String[] args) {
        RoundHole hole = new RoundHole(5);
        RoundPeg rpeg = new RoundPeg(5);
        System.out.println(hole.fits(rpeg)); // true

        SquarePeg smallSqPeg = new SquarePeg(5);
        SquarePeg largeSqPeg = new SquarePeg(10);

        // The following line won't compile because of incompatible types:
        // hole.fits(smallSqPeg);

        SquarePegAdapter smallSqPegAdapter = new SquarePegAdapter(smallSqPeg);
        SquarePegAdapter largeSqPegAdapter = new SquarePegAdapter(largeSqPeg);
        System.out.println(hole.fits(smallSqPegAdapter)); // true
        System.out.println(hole.fits(largeSqPegAdapter)); // false
    }
}


```

**Pros:**
- Single Responsibility Principle: Interface is separated from the data conversion
- Open-Closed-Principle: New adapters can be introduced without breaking the existing client code

**Cons:**
- Increased Complexity
