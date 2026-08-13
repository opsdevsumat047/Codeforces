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

            // Check if we can build an infinite water generator
            if (s.contains("...")) {
                out.println(2);
            } else {
            // Otherwise, we must manually fill every empty spot
            int count = 0;
            for (int i = 0; i < n; i++) {
                if (s.charAt(i) == '.') {
                    count++;
                }
        }
    out.println(count);
}
}

out.flush();
}

// Standard FastScanner for competitive programming
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
