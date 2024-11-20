# Online Statistics

This project involves creating a class `OnlineStatistics` that computes and maintains various statistical properties on a sequence of integers using an online algorithm. The statistics are updated dynamically as new values are added, allowing for real-time querying.

## Objective

Create a Java program that:

- Defines the `OnlineStatistics` class with methods to manage and compute statistical properties of a sequence of integers.
- Allows for querying of statistical values at any time after values have been added.
- Implements the following methods:
  - `void addValue(int value)`: Adds a new value to the dataset.
  - `int getSum()`: Returns the sum of values added so far.
  - `double getAverage()`: Returns the average of values added so far.
  - `int getMax()`: Returns the largest value added so far.
  - `int getMin()`: Returns the smallest value added so far.
  - `void reset()`: Resets the internal state to zero.

### Example Implementation

```java
public class OnlineStatistics {
    private int sum;
    private int count;
    private int max;
    private int min;

    public OnlineStatistics() {
        reset();
    }

    public void addValue(int value) {
        sum += value;
        count++;

        if (count == 1) {
            max = value;
            min = value;
        } else {
            if (value > max) {
                max = value;
            }
            if (value < min) {
                min = value;
            }
        }
    }

    public int getSum() {
        return sum;
    }

    public double getAverage() {
        return count == 0 ? 0 : (double) sum / count;
    }

    public int getMax() {
        return count == 0 ? Integer.MIN_VALUE : max;
    }

    public int getMin() {
        return count == 0 ? Integer.MAX_VALUE : min;
    }

    public void reset() {
        sum = 0;
        count = 0;
        max = Integer.MIN_VALUE;
        min = Integer.MAX_VALUE;
    }
}
```

### Testing the OnlineStatistics Class

Create a test class named `OnlineStatisticsTest` to validate the functionality of the `OnlineStatistics` class.

```java
public class OnlineStatisticsTest {
    public static void main(String[] args) {
        OnlineStatistics stats = new OnlineStatistics();

        stats.addValue(10);
        stats.addValue(20);
        stats.addValue(5);

        System.out.println("Sum: " + stats.getSum()); // Output: 35
        System.out.println("Average: " + stats.getAverage()); // Output: 11.666...
        System.out.println("Max: " + stats.getMax()); // Output: 20
        System.out.println("Min: " + stats.getMin()); // Output: 5

        stats.reset();

        System.out.println("After reset:");
        System.out.println("Sum: " + stats.getSum()); // Output: 0
        System.out.println("Average: " + stats.getAverage()); // Output: 0.0
        System.out.println("Max: " + stats.getMax()); // Output: Integer.MIN_VALUE
        System.out.println("Min: " + stats.getMin()); // Output: Integer.MAX_VALUE
    }
}
```

## Hints

- Keep track of the current values of the statistics using appropriate instance variables.
- Use `Integer.MIN_VALUE` and `Integer.MAX_VALUE` to initialize `max` and `min` respectively.
- Ensure that the `getAverage` method handles the case when no values have been added to avoid division by zero.

## Notes

- Document your code with comments to explain the logic behind each method.
- Test the program with various inputs to ensure it behaves as expected.

Happy coding! 🎉