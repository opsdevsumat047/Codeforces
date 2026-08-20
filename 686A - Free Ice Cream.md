import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int n = fs.nextInt();
        // 1. Read x as a long
        long x = fs.nextLong(); 
        
        // 2. total must be a long to prevent overflow
        long total = x; 
        int count = 0;
        
        while (n-- > 0) {
            char c = fs.next().charAt(0);
            // 3. Read d as a long
            long d = fs.nextLong(); 
            
            if (c == '+') {
                total = total + d;
            } else {
                // Alternatively, you can just check BEFORE subtracting!
                if (total >= d) {
                    total = total - d;
                } else {
                    count++;
                }
            }
        }
        
        out.println(total + " " + count);
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
