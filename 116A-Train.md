import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        int maxLength = 0;
        int currentLength = 0;
        while (t-- > 0) {
            int a = fs.nextInt();
            int b = fs.nextInt();
            currentLength = currentLength - a + b;
            maxLength = Math.max(maxLength, currentLength);
        }
    out.println(maxLength);
    // n stops; 1 - to - n
    // ith stop ai passenger exits and bi enters
    // before first stop (before a[0]) - train empty - a1 =0
    // a[last] after a[n] train is empty
    // calculate tram's capacity so that people could never exceed the capacity
    // bn =0
    // at each stop all of them exits
    // stacks
    //

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
