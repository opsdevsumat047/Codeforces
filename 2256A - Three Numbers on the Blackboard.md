import java.util.Scanner;
import java.util.Arrays;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        if (!sc.hasNextInt()) return;
        int t = sc.nextInt();

        while (t-- > 0) {
            long[] a = new long[3];
            a[0] = sc.nextLong();
            a[1] = sc.nextLong();
            a[2] = sc.nextLong();

            // Sort the array so that a[0] <= a[1] <= a[2]
            Arrays.sort(a);

            // The initial range without any operations
            long initialRange = a[2] - a[0];

            // The range if we replace the largest element with the sum of the two smaller ones
            long modifiedRange = a[1];

            // Print the minimum of the two possibilities
            System.out.println(Math.min(initialRange, modifiedRange));
        }

    sc.close();
}
}
