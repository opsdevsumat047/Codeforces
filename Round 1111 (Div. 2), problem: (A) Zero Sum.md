import java.io.*;
import java.util.*;

public class Main {
    static FastScanner sc = new FastScanner();
    static PrintWriter out = new PrintWriter(System.out);

    public static void main(String[] args) {
        solve();
        out.flush();
        out.close();
    }

static void solve() {
    int t = sc.nextInt();

    while (t-- > 0) {
        int n = sc.nextInt();

        int[] a = new int[n];
        for (int i = 0; i < n; i++) {
            a[i] = sc.nextInt();
        }

    if (n % 2 != 0) {
        out.println("NO");
        continue;
    }

int sum = 0;
for (int i = 0; i < n; i++) {
    sum += a[i];
}

boolean canBeZero = (sum % 4 == 0);

if (canBeZero) {
    out.println("YES");
} else {
out.println("NO");
}
}
}

// ==========================================================
// FAST I/O CLASS (Includes our EOF safety checks!)
// ==========================================================
static class FastScanner {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    StringTokenizer st = new StringTokenizer("");

    String next() {
        while (st == null || !st.hasMoreTokens()) {
            try {
                String line = br.readLine();
                if (line == null) return null; // Safe EOF check
                st = new StringTokenizer(line);
            }
        catch (IOException e) { e.printStackTrace(); }
    }
return st.nextToken();
}

int nextInt() {
    return Integer.parseInt(next());
}

long nextLong() {
    return Long.parseLong(next());
}
}
}
