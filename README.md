# Day_5
Q1:Write a Java program that takes two integers as input and performs division. The program should handle exceptions for invalid input (non-integer input) and division by zero. The program should continue to prompt the user for valid input until successful division is performed.
import java.util.InputMismatchException;
import java.util.Scanner;

class Test {
    public static void main(String args[] ) throws Exception {
        
        // Write your code here
        Scanner sc = new Scanner(System.in);
while (true) {
    try {
        int num1 = sc.nextInt();
        int num2 = sc.nextInt();
        int result = num1 / num2;
        System.out.println("Result: " + result);
        break;
    } catch (InputMismatchException e) {
        System.out.println("Invalid input. Please enter an integer.");
        sc.nextLine();
    } catch (ArithmeticException e) {
        System.out.println("Cannot divide by zero. Please enter a valid divisor.");
    }
}

    }
}
Q2:You are required to catch Arithmetic or number format exceptions if present using multiple catch blocks in the code for finding of 99 with the number entered by user, else print "n is a factor of 99" or "n is not a factor of 99".
import java.util.Scanner;
public class Test {

    public static void main(String[] args) {
        Scanner scn = new Scanner(System.in);
        //write your answer here
        try {
    String input = scn.nextLine();
    int n = Integer.parseInt(input);
    if(99 % n == 0) {
        System.out.println(n + " is a factor of 99");
    } else {
        System.out.println(n + " is a not a factor of 99");
    }
} catch (ArithmeticException e) {
    System.out.println("Arithmetic Exception " + e);
} catch (NumberFormatException e) {
    System.out.println("Number Format Exception " + e);
}
    }
}
Q3:Write a Java program to create a method that takes a string as input and throws an exception if the string does not contain vowels.
import java.util.Scanner;
public class Main {

    public static void main(String[] args) {
  Scanner s=new Scanner(System.in);
		   
			  try {
          String text = s.nextLine();
          checkVowels(text);
          System.out.println("String contains vowels.");
} catch (NoVowelsException e) {
    System.out.println("String does not contain any vowels");
}
        //write your answer here
        
    }
    
      public static void checkVowels(String text) 
      {
        
      }
}
class NoVowelsException 
{
  
}
Q4:Generic Data Analysis using JAVA
import java.util.*;

public class DataAnalyzer<T extends Number & Comparable<T>> {
   //define the required methods
   
    private T[] data;
    
    public DataAnalyzer(T[] data) {
        this.data = data;
    }

    public double calculateAverage() {
        double sum = 0.0;
        for (T val : data) {
            sum += val.doubleValue();
        }
        return sum / data.length;
    }

    public T findMaximum() {
        T max = data[0];
        for (T val : data) {
            if (val.compareTo(max) > 0) {
                max = val;
            }
        }
        return max;
    }

    public void dataSummary() {
        System.out.println("Data Summary:");
        System.out.println("Average: " +  calculateAverage());
        System.out.println("Maximum: " + findMaximum());
    }

    public static void main(String[] args) {
        // Example with integers
        Scanner sc = new Scanner(System.in);
        int ch = sc.nextInt();
        
          int size = sc.nextInt();
        if(ch==1)
        {
        Integer[] integerData = new Integer[size];
        for(int i=0;i<size;i++)
        {
          integerData[i] = sc.nextInt();
        }
        DataAnalyzer<Integer> integerAnalyzer = new DataAnalyzer<>(integerData);
        integerAnalyzer.dataSummary();
        }
        else if(ch==2)
        {
        // Example with doubles
        Double[] doubleData = new Double[size];
        for(int i=0;i<size;i++)
        {
          doubleData[i] = sc.nextDouble();
        }
        
        DataAnalyzer<Double> doubleAnalyzer = new DataAnalyzer<>(doubleData);
        doubleAnalyzer.dataSummary();
        }
        else if(ch==3)
        {
        // Example with doubles
        Short[] shortData = new Short[size];
        for(int i=0;i<size;i++)
        {
          shortData[i] = sc.nextShort();
        }
        
        DataAnalyzer<Short> doubleAnalyzer = new DataAnalyzer<>(shortData);
        doubleAnalyzer.dataSummary();
        }
        else if(ch==4)
        {
        // Example with doubles
        Float[] floatData = new Float[size];
        for(int i=0;i<size;i++)
        {
          floatData[i] = sc.nextFloat();
        }
        
        DataAnalyzer<Float> doubleAnalyzer = new DataAnalyzer<>(floatData);
        doubleAnalyzer.dataSummary();
        }
    }
}

