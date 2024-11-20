# String Manipulations

This project involves creating a `StringReader` class that performs various manipulations on a string input provided via the command line. The program will modify the string by cutting off the first letter, converting it to uppercase, replacing occurrences of the letter 'A' with 'Z', and appending a suffix.

## Objective

Create a Java program that:

- Defines a `StringReader` class with a `main` method.
- Reads a string from the command line.
- Performs the following manipulations on the string:
    - Cuts off the first letter.
    - Converts all letters to uppercase.
    - Replaces any appearance of the letter 'A' with 'Z'.
    - Concatenates the modified string with "-ready!".
- Prints the final resulting string.

### Example Usage

If the input string is "Berner Fachhochschule", the program should output:

```
ERNER FZCHHOCHSCHULZ-ready!
```

### Example Implementation

```java
public class StringReader {
    public static void main(String[] args) {
        if (args.length == 0) {
            System.out.println("Please provide a string as a command line argument.");
            return;
        }

        String input = args[0];

        // Cut off the first letter
        String modifiedString = input.length() > 1 ? input.substring(1) : "";

        // Convert to uppercase
        modifiedString = modifiedString.toUpperCase();

        // Replace 'A' with 'Z'
        modifiedString = modifiedString.replace('A', 'Z');

        // Concatenate with "-ready!"
        modifiedString += "-ready!";

        // Print the resulting string
        System.out.println(modifiedString);
    }
}
```

## Hints

- Use `substring()` to cut off the first letter of the string.
- Use `toUpperCase()` to convert the string to uppercase.
- Use `replace()` to replace occurrences of 'A' with 'Z'.
- Ensure to handle cases where the input string is empty or has only one character.

## Notes

- Document your code with comments to explain each step of the string manipulation.
- Test the program with various input strings to ensure it behaves as expected.

Happy coding! 🎉