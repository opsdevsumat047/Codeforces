import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        while (t-- > 0) {
            int n = fs.nextInt();
            String s = fs.next();

            // Step 1: Calculate the original compressed length
            int compressedLength = 1;
            for (int i = 1; i < n; i++) {
                if (s.charAt(i) != s.charAt(i - 1)) {
                    compressedLength++;
                }
        }

    int minCompressed = compressedLength; // Worst case scenario

    // Step 2: Test the exact mathematical impact of deleting each valid character
    for (int i = 1; i < n - 1; i++) {
        // How many boundaries existed BEFORE deleting s[i]?
        int leftBoundary = (s.charAt(i - 1) != s.charAt(i)) ? 1 : 0;
        int rightBoundary = (s.charAt(i) != s.charAt(i + 1)) ? 1 : 0;

        // How many boundaries exist AFTER deleting s[i]?
        int newBoundary = (s.charAt(i - 1) != s.charAt(i + 1)) ? 1 : 0;

        // Calculate the new total length
        int newLength = compressedLength - leftBoundary - rightBoundary + newBoundary;

        // Track the absolute smallest length we can achieve
        minCompressed = Math.min(minCompressed, newLength);
    }

out.println(minCompressed);
}

out.flush();
}

static class FastScanner {
    private final BufferedReader br;
    private StringTokenizer st;

    FastScanner(InputStream in) {
        br = new BufferedReader(new InputStreamReader(in));
    }

String next() throws IOException {
    while (st == null || !st.hasMoreTokens()) {
        String line = br.readLine();
        if (line == null) return null;
        st = new StringTokenizer(line);
    }
return st.nextToken();
}

int nextInt() throws IOException {
    return Integer.parseInt(next());
}
}
}
