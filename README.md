import java.util.Scanner;

public class student {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        
        System.out.print("Enter the number of subjects or assignments: ");
        int Sub = sc.nextInt();
        
    
        double[] grades = new double[Sub];
        double sum = 0;


        for (int i = 0; i < Sub; i++) {
            System.out.print("Enter grade for subject/assignment " + (i + 1) + ": ");
            grades[i] = sc.nextDouble();
            sum += grades[i];
        }

    
        double averageGrade = sum / Sub;
        System.out.println("Average Grade: " + averageGrade);
        String letterGrade = getLetterGrade(averageGrade);
        double gpa = getGPA(averageGrade);

        
        System.out.println("Overall Grade: " + letterGrade);
        System.out.println("GPA: " + gpa);
        
        sc.close();
    }


    private static String getLetterGrade(double average) {
        if (average >= 90) {
            return "A";
        } else if (average >= 80) {
            return "B";
        } else if (average >= 70) {
            return "C";
        } else if (average >= 60) {
            return "D";
        } else {
            return "F";
        }
    }

   
    private static double getGPA(double average) {
        if (average >= 90) {
            return 4.0;
        } else if (average >= 80) {
            return 3.0;
        } else if (average >= 70) {
            return 2.0;
        } else if (average >= 60) {
            return 1.0;
        } else {
            return 0.0;
        }
    }
}
