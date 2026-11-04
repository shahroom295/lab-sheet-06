# lab-sheet-06
code

// Q1. Handling ArithmeticException
class Q1 {
    static void run() {
        try {
            int a = 10, b = 0;
            System.out.println(a / b);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero");
        }
    }
}

// Q2. Handling ArrayIndexOutOfBoundsException
class Q2 {
    static void run() {
        try {
            int arr[] = {10, 20, 30, 40, 50};
            java.util.Scanner sc = new java.util.Scanner(System.in);

            System.out.print("Enter index: ");
            int i = sc.nextInt();

            System.out.println(arr[i]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Invalid Array Index");
        }
    }
}

// Q3. Handling NumberFormatException
class Q3 {
    static void run() {
        try {
            String s = "ABC";
            int n = Integer.parseInt(s);
            System.out.println(n);
        } catch (NumberFormatException e) {
            System.out.println("Invalid Number");
        }
    }
}

// Q4. Multiple Catch Blocks
class Q4 {
    static void run() {
        try {
            java.util.Scanner sc = new java.util.Scanner(System.in);

            System.out.print("Enter two numbers: ");
            int a = sc.nextInt();
            int b = sc.nextInt();

            System.out.println("Division: " + (a / b));

            int arr[] = {10, 20, 30, 40, 50};

            System.out.print("Enter index: ");
            int i = sc.nextInt();

            System.out.println("Element: " + arr[i]);

        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero");
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Invalid Array Index");
        } catch (NumberFormatException e) {
            System.out.println("Invalid Number Format");
        }
    }
}

// Q5. Using finally
class Q5 {
    static void run() {
        try {
            int a = 10, b = 0;
            System.out.println(a / b);
        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero");
        } finally {
            System.out.println("Program execution completed.");
        }
    }
}

// Q6. Using throw
class Q6 {
    static void run() {
        try {
            int marks = 120;

            if (marks < 0 || marks > 100) {
                throw new ArithmeticException("Invalid Marks");
            }

            System.out.println("Marks: " + marks);

        } catch (ArithmeticException e) {
            System.out.println(e.getMessage());
        }
    }
}

// Q7. Using throws
class Q7 {
    static void checkAge(int age) throws Exception {
        if (age < 18) {
            throw new Exception("Not Eligible");
        } else {
            System.out.println("Eligible");
        }
    }

    static void run() {
        try {
            checkAge(16);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}

// Q8. Nested try-catch
class Q8 {
    static void run() {
        try {
            int a = 10, b = 0;

            try {
                int arr[] = {10, 20, 30};
                System.out.println(arr[5]);
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Invalid Array Index");
            }

            System.out.println(a / b);

        } catch (ArithmeticException e) {
            System.out.println("Cannot divide by zero");
        }
    }
}

// Q9. Exception Propagation
class Q9 {
    static void method3() {
        int a = 10, b = 0;
        System.out.println(a / b);
    }

    static void method2() {
        method3();
    }

    static void method1() {
        method2();
    }

    static void run() {
        try {
            method1();
        } catch (ArithmeticException e) {
            System.out.println("Exception Handled in Main");
        }
    }
}

// MAIN CLASS
public class Main {
    public static void main(String[] args) {

        System.out.println("Q1");
        Q1.run();

        System.out.println("\nQ2");
        Q2.run();

        System.out.println("\nQ3");
        Q3.run();

        System.out.println("\nQ4");
        Q4.run();

        System.out.println("\nQ5");
        Q5.run();

        System.out.println("\nQ6");
        Q6.run();

        System.out.println("\nQ7");
        Q7.run();

        System.out.println("\nQ8");
        Q8.run();

        System.out.println("\nQ9");
        Q9.run();
    }
}
