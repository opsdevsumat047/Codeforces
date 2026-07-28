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
        if (s == null) return; 

        String[] nums = s.split("\\+");

        Arrays.sort(nums);

        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < nums.length; i++) {
            sb.append(nums[i]);
            
            if (i < nums.length - 1) {
                sb.append("+");
            }
        }

        // Print the final result
        out.println(sb.toString());
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
