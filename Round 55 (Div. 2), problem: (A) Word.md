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
        String s = sc.next();
        if (s == null) return; // Safety check for empty input
        
        int upperCount = 0;
        int lowerCount = 0;
        
        // Loop through the word and count
        for (int i = 0; i < s.length(); i++) {
            if (Character.isUpperCase(s.charAt(i))) {
                upperCount++;
            } else {
                lowerCount++;
            }
        }
        
        // Apply your exact conditional logic
        if (upperCount > lowerCount) {
            out.println(s.toUpperCase());
        } else {
            out.println(s.toLowerCase());
        }
    }

    // ==========================================================
    // FAST I/O CLASS
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
