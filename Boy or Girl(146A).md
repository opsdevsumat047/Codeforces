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
    String us = sc.next();
    Set<String> set = new HashSet<>(Arrays.asList(us.split("")));
    if(set.size()%2 != 0){
        System.out.println("IGNORE HIM!");
    } else{
    System.out.println("CHAT WITH HER!");

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
