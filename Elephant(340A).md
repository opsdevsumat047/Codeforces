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
    int n = sc.nextInt();
    if(n <= 5){
        System.out.println(1);
    }
else{
    if(n%5 == 0){
        System.out.println(n/5);
    }
else{
    System.out.println(n/5+1);
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
