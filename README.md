import java.util.ArrayList;
import java.util.Scanner;

public class StudentGradeTracker {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        ArrayList<String> studentNames = new ArrayList<>();
        ArrayList<Integer> studentGrades = new ArrayList<>();

        System.out.println("===== Student Grade Tracker =====");

        while (true) {
            System.out.print("Enter Student Name (or type 'exit' to finish): ");
            String name = sc.nextLine();

            if (name.equalsIgnoreCase("exit")) {
                break;
            }

            System.out.print("Enter Grade for " + name + ": ");
            int grade = sc.nextInt();
            sc.nextLine();  // buffer clear

            studentNames.add(name);
            studentGrades.add(grade);

            System.out.println("Student Added Successfully!\n");
        }

        System.out.println("\n===== Summary Report =====");

        if (studentGrades.size() == 0) {
            System.out.println("No student data available.");
            return;
        }

        int sum = 0;
        int highest = studentGrades.get(0);
        int lowest = studentGrades.get(0);

        for (int grade : studentGrades) {
            sum += grade;
            if (grade > highest) {
                highest = grade;
            }
            if (grade < lowest) {
                lowest = grade;
            }
        }

        double average = (double) sum / studentGrades.size();

        System.out.println("\nTotal Students: " + studentGrades.size());
        System.out.println("Average Score: " + average);
        System.out.println("Highest Score: " + highest);
        System.out.println("Lowest Score: " + lowest);

        System.out.println("\n----- Student Grades -----");
        for (int i = 0; i < studentNames.size(); i++) {
            System.out.println(studentNames.get(i) + " : " + studentGrades.get(i));
        }

        System.out.println("\n===== End of Report =====");
    }
}
