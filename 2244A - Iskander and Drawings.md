import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        if (!scanner.hasNextInt()) return;
        int t = scanner.nextInt();

        while (t-- > 0) {
            int n = scanner.nextInt();
            String s = scanner.next();

            int maxLength = 0;
            int currentLength = 0;

            // 1. Find the longest sequence of '#'
            for (int i = 0; i < n; i++) {
                if (s.charAt(i) == '#') {
                    currentLength++;
                    maxLength = Math.max(maxLength, currentLength);
                } else {
                // Reset the current streak if we hit an empty spot '*'
                currentLength = 0;
            }
    }

// 2. Apply the mathematical formula to find the time
int maxTime = (maxLength + 1) / 2;

System.out.println(maxTime);
}

scanner.close();
}
}
