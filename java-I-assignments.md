# Java I: Exercises

### Ex. 1 Uppercase Name
Write a Java program that prompts the user to enter their name, and returns their name in upper case.

Example:

```
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Please enter your name: ");
        String name = scan.nextLine();
        name = name.toUpperCase();
        System.out.println(name);
        System.exit(0);
    }
}

```

### Ex. 2 Count Uppers
Write a Java program that prompts the user to enter a string and counts the number of uppercase letters.

Example:

```
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Input text and the number of uppercase letters will be returned: ");
        String str = scan.nextLine();
        char[] chars = str.toCharArray();
        int count = 0;
        for(int i = 0; i< chars.length;i++){
            if(Character.isUpperCase(chars[i])){
                count++;
            }
        }

        System.out.println(count);
        System.exit(0);

    }
}
```
### Ex. 3 Capitalize Words
Write a Java program that prompts the user to enter a string and capitalizes every other word, starting with the first word.
HINT: The `StringTokenizer` object or `String.split()` method might be useful.

Examples:
```
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Input text and the program will return it with every other word capitalized: ");
        String str = scan.nextLine();
        char[] chars = str.toCharArray();
        int count = 0;
        boolean isCaps = true;
        for(int i = 0; i< chars.length;i++){
            if(chars[i] == ' '){
                isCaps = !isCaps;
            }
            if(isCaps == true){
                chars[i] = Character.toUpperCase(chars[i]);
        }
    }
        str = str.valueOf(chars);

        System.out.println(str);
        System.exit(0);
    }
}

```
```
Enter a string: This is a longer string with more words.
THIS is A longer STRING with MORE words. 

Process finished with exit code 0
```

### Ex. 4 Classic Palidrome
A palidrome is a word, phrase, or sequence that reads the same backward as forward (e.g. radar, madam).

Write a Java program that tests if a word is a palidrome or not.

Examples:
```
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Input text and the program will determine whether or not it is a palindrome: ");
        String str = scan.nextLine();
        char[] chars = str.toCharArray();
        boolean isPal = true;
        for(int i = 0; i < chars.length;i++){
            if(chars[i] != chars[chars.length-i-1]){
                System.out.println(chars[i]);
                System.out.println(chars[chars.length-i-1]);
                isPal = false;
                break;
            }
        }
        System.out.println(isPal == true ? "yes" : "no" );
        System.exit(0);
    }
}

```

```
Enter string: truck
NO

Process finished with exit code 0
```
HINT: The `StringBuilder` might be useful.


### Ex. 5 Consonant and Vowel Count
Write a Java program that prompts the user to enter a string and returns the number of vowels and constants.  The program loops forever until "quit" is entered.  The program does not count whitespace and punctuation.

Example:
```
import java.util.HashSet;
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String str;
        char[] chars;
        HashSet<Character> set = new HashSet<Character>();
        set.add('a');
        set.add('e');
        set.add('i');
        set.add('o');
        set.add('u');
        int vowelCount = 0;
        int consCount = 0;
        while(true){
        System.out.println("Input text and the program will determine how many vowels and consonants there are, input 0 to quit: ");
        str = scan.nextLine();
        if(str.equals("0")){
            System.exit(0);
        }
        chars = str.toCharArray();

        for(int i = 0; i < chars.length;i++){
            if(set.contains(chars[i])){
                vowelCount++;
            } else if(Character.isAlphabetic(chars[i])){
                consCount++;

            }
        }
        System.out.println("Number of Vowels: " + vowelCount + "\nNumber of consonants: " + consCount);
        consCount = 0;
        vowelCount = 0;
        }
    }
}

Enter a string: test
Number of vowels: 1
Number of consonants: 3
Enter a string: TEST
Number of vowels: 1
Number of consonants: 3
Enter a string: This is a test.
Number of vowels: 4
Number of consonants: 7
Enter a string: quit

Process finished with exit code 0
```

### Ex. 6 Add Only Calculator
Write a Java program that prompts the user for two Integers and adds them.

Example:

```
import java.util.HashSet;
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Enter the first number: ");
        int num1 = scan.nextInt();
        System.out.println("Enter the second number: ");
        int num2 = scan.nextInt();

        System.out.println("Result: " + (num1+num2));
    }
}
```

### Ex. 7 Full Calculator
Write a Java program that prompts the user for two Integers and an operation and returns the result.

Examples:


```
import java.util.HashSet;
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        
        System.out.println("Enter your desired operation (+, -, /, *): ");
        String op = scan.nextLine();
        System.out.println("Enter the first number: ");
        int num1 = scan.nextInt();
        System.out.println("Enter the second number: ");
        int num2 = scan.nextInt();
        if(op.equals("+")){
            System.out.println("Your output is: " + (num1+num2));
        }else if(op.equals("-")){
            System.out.println("Your output is: " + (num1-num2));
        }else if(op.equals("/")){
            System.out.println("your output is: " + (num1/num2));
        }else if(op.equals("*")){
            System.out.println("Your output is: " + (num1*num2));
        }else{
            System.out.println("You entered an invalid operator, please try again");
        }

        System.exit(0);
    }
}

Enter first number: 10
Enter second number: 2
Enter operation (add, sub, mul, div): sub
Result: 8
```

```
Enter first number: 3
Enter second number: 2
Enter operation (add, sub, mul, div): add
Result: 5
```

```
Enter first number: 2
Enter second number: 3
Enter operation (add, sub, mul, div): mul
Result: 6
```

```
Enter first number: 10
Enter second number: 5
Enter operation (add, sub, mul, div): div
Result: 2
```

### Ex. 8 Carpet Calculator
Write a Java program that calculates the total price for a carpet installation job.  The program prompts the user to
enter the price of the carpet per square feet, then prompts the user to enter the width and length of all 
the rooms.  When the user enters "done", the program returns the total price of the carpet installation job.

Examples
```
import java.util.HashSet;
import java.util.Scanner;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int sum = 0;
        String[] arr;
        String dimensionStr;
        
        System.out.println("Enter your price per square foot");
        double price = scan.nextDouble();
        scan.nextLine();
        
        while(true){
        System.out.print("Enter more room dimensions(ex: '3 x 10' - input done when finished): ");
        dimensionStr = scan.nextLine();
        if(dimensionStr.equals("done")){
            break;
        }

        arr = dimensionStr.split(" ");
        double dimension1 = Double.parseDouble(arr[0]);
        double dimension2 = Double.parseDouble(arr[2]);
        System.out.println(dimension1 + " " + dimension2);
        sum+= (dimension1*dimension2*price);
        System.out.println(sum);
    
    }
        System.out.println("Total price: " + sum);
    }
}

Enter price per square feet: 3.00
Enter room dimensions (width x height): 10 x 10
Enter room dimensions (width x height): done
Total cost: $300.00
```

```
Enter price per square feet: 4.00
Enter room dimensions (width x height): 10 x 10
Enter room dimensions (width x height): 10 x 10
Enter room dimensions (width x height): done
Total cost: $800.00
```
```
Enter price per square feet: 5.00
Enter room dimensions (width x height): 10 x 20
Enter room dimensions (width x height): 20 x 10
Enter room dimensions (width x height): done
Total cost: $2,000.00

```

### Ex. 9 Random Number Game
Write a Java program that generates a random number between 1 through 5.  The program prompts the user to 
guess the number.  The program loops forever until the number is guessed.

Example
```
import java.util.*;
import java.lang.Math;

public class Java1Exercises {
    public static void main(String[] args) {
        Random rand = new Random();
        int num = rand.nextInt(1,5);
        Scanner scan = new Scanner(System.in);
        int guess;
        while(true){
            System.out.print("Please guess a random number 1-5: ");
            guess = scan.nextInt();
            if(guess == num){
                System.out.println("You got it right, you win! ");
                break;
            }else{
                System.out.println("Wrong, please try again.");
            }

        }
    }
}

Enter a number: 2
Try again...
Enter a number: 1
Try again...
Enter a number: 3
Try again...
Enter a number: 4
You guessed it!!!
```

### Ex. 10 Diagon Alley
Write a Java Program that prompts the user to a enter a string and prints every word diagonally to the console.

Example:
```
import java.util.*;
import java.lang.Math;

public class Java1Exercises {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        System.out.println("Please enter a string: ");
        String input = scan.nextLine();
        String[] strArr = input.split(" ");
        char[] charArr;
        int count = 0;

        for(String s : strArr){
            charArr = s.toCharArray();
            for(int i = 0; i<charArr.length;i++){
                for(int j = 0; j<count; j++){
                    System.out.print(" ");
                }
                System.out.println(charArr[i]);
                count++;
            }
            count = 0;
        }
    }
}
Enter a string: this is a test
t
 h
  i
   s
i
 s
a
t
 e
  s
   t

Process finished with exit code 0
```
