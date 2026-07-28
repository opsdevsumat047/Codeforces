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
    String first = sc.next();
    String second = sc.next();
    String comb = sc.next();

    String temp = first + second;
    if (comb.length() != temp.length()) {
        out.println("NO");
        return;
    }
char[] com = comb.toCharArray();
Arrays.sort(com);
char[] tem = temp.toCharArray();
Arrays.sort(tem);
if (Arrays.equals(com, tem)) {
    out.println("YES");
} else {
out.println("NO");
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
