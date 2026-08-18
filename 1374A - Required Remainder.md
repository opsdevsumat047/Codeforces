import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        // Read the number of test cases
        int t = fs.nextInt();
        
        while (t-- > 0) {
            long x = fs.nextLong();
            long y = fs.nextLong();
            long n = fs.nextLong();
            
            // 1 & 2. Find the largest perfect multiple of x that is <= n
            long base = n - (n % x);
            
            // 3. Add our target remainder y
            long ans = base + y;
            
            // 4. If adding y pushed us past n, step back exactly one cycle of x
            if (ans > n) {
                ans -= x;
            }
            
            out.println(ans);
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

        long nextLong() throws IOException {
            return Long.parseLong(next());
        }
    }
}
