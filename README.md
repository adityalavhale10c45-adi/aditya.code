import java.util.Scanner;

public class LCMCalculator {

    // Method to compute GCD using Euclidean algorithm
    public static int gcd(int a, int b) {
        while (b != 0) {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return Math.abs(a); // Always return positive GCD
    }

    // Method to compute LCM
    public static int lcm(int a, int b) {
        if (a == 0 || b == 0) {
            return 0; // LCM involving zero is zero
        }
        return Math.abs(a * b) / gcd(a, b);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        try {
            System.out.print("Enter first integer: ");
            int num1 = scanner.nextInt();

            System.out.print("Enter second integer: ");
            int num2 = scanner.nextInt();

            int result = lcm(num1, num2);
            System.out.println("LCM of " + num1 + " and " + num2 + " is: " + result);

        } catch (Exception e) {
            System.out.println("Invalid input. Please enter integers only.");
        } finally {
            scanner.close();
        }
    }
}

