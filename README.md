import java.util.Scanner;

public class ScientificCalculator {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        while (true) {
            System.out.println("\n===== SCIENTIFIC CALCULATOR =====");
            System.out.println("1. Addition");
            System.out.println("2. Subtraction");
            System.out.println("3. Multiplication");
            System.out.println("4. Division");
            System.out.println("5. Power (x^n)");
            System.out.println("6. Square Root");
            System.out.println("7. Sin");
            System.out.println("8. Cos");
            System.out.println("9. Tan");
            System.out.println("10. Log (base 10)");
            System.out.println("11. Natural Log (ln)");
            System.out.println("12. Modulus");
            System.out.println("0. Exit");
            System.out.print("Choose option: ");

            int choice = sc.nextInt();

            if (choice == 0) {
                System.out.println("Exiting calculator...");
                break;
            }

            double num1 = 0, num2 = 0;

            // Only some operations need two numbers
            if (choice <= 4 || choice == 5 || choice == 12) {
                System.out.print("Enter first number: ");
                num1 = sc.nextDouble();
                System.out.print("Enter second number: ");
                num2 = sc.nextDouble();
            } 
            // Others need only 1 number
            else if (choice >= 6 && choice <= 11) {
                System.out.print("Enter number: ");
                num1 = sc.nextDouble();
            }

            switch (choice) {
                case 1 -> System.out.println("Result = " + (num1 + num2));
                case 2 -> System.out.println("Result = " + (num1 - num2));
                case 3 -> System.out.println("Result = " + (num1 * num2));
                case 4 -> {
                    if (num2 == 0) {
                        System.out.println("Error: Cannot divide by zero!");
                    } else {
                        System.out.println("Result = " + (num1 / num2));
                    }
                }
                case 5 -> System.out.println("Result = " + Math.pow(num1, num2));
                case 6 -> System.out.println("Result = " + Math.sqrt(num1));
                case 7 -> System.out.println("Result = " + Math.sin(Math.toRadians(num1)));
                case 8 -> System.out.println("Result = " + Math.cos(Math.toRadians(num1)));
                case 9 -> System.out.println("Result = " + Math.tan(Math.toRadians(num1)));
                case 10 -> System.out.println("Result = " + Math.log10(num1));
                case 11 -> System.out.println("Result = " + Math.log(num1));
                case 12 -> System.out.println("Result = " + (num1 % num2));
                default -> System.out.println("Invalid choice!");
            }
        }

        sc.close();
    }
}



