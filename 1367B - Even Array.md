import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        while (t-- > 0) {
            int n = fs.nextInt();
            int[] arr = new int[n];

            int wrongEven = 0; // Even index holding an odd number
            int wrongOdd = 0;  // Odd index holding an even number

            for (int i = 0; i < n; i++) {
                arr[i] = fs.nextInt();

                // Check if the parities do not match
                if (i % 2 != arr[i] % 2) {
                    if (i % 2 == 0) {
                        wrongEven++;
                    } else {
                    wrongOdd++;
                }
        }
}

// If the counts are equal, they can pair up perfectly
if (wrongEven == wrongOdd) {
    out.println(wrongEven);
} else {
out.println("-1");
}
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
