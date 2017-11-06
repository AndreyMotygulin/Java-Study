# Java-Study
Solutions of Java study excercises

import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String string = scanner.nextLine();
        int index;
        boolean rightInput = false;
        do {
            try {
                System.out.print("\nEnter character index (an integer value): ");
                index = scanner.nextInt();
                System.out.printf("\nThe a character at the specified index is: %c",
                        string.charAt(index));
                rightInput = true;
            } catch (InputMismatchException inputMismatch) {
                System.err.println("Inputted value is mismatch to prompt");
                scanner.nextLine();
                System.out.println("try again");
            } catch (StringIndexOutOfBoundsException indexOut) {
                System.err.println("Specified index is out of the string bounds");
                scanner.nextLine();
                System.out.println("try again");
            }
        }
        while (!rightInput);
    }
}
