With the help of threading print two tables concurrently, print one table number of student roll number e.g. 2019-SE-092 and second number should be date of birth e.g. 05-April.

    import java.util.Scanner;
    class Wasay1 extends Thread {
    int num;
    Wasay1(int num) {
        this.num = num;
    }
    public void run() {
        for (int i = 1; i <= 10; i++) {
            System.out.println("RollNo Table: " + num + " x " + i + " = " + (num * i));
        }
    }
    }

    class Wasay2 extends Thread {
    int num;
    Wasay2(int num) {
        this.num = num;
    }
    public void run() {
        for (int i = 1; i <= 10; i++) {
            System.out.println("DOB Table: " + num + " x " + i + " = " + (num * i));
        }
    }
    }

    public class Wasay {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter roll number (digits only): ");
        int roll = sc.nextInt();
        System.out.print("Enter birth day: ");
        int dob = sc.nextInt();

        Wasay1 t1 = new Wasay1(roll);
        Wasay2 t2 = new Wasay2(dob);

        t1.start();
        t2.start();
    }
}
