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
        /*
        height of friends < h
        one has to bend if want to escape
        height of i-th person is a_i
        width_walking = 1 units
        width_bend = 2 units
        find minimum width of road required so that friends can walk
        n = number of friends
        h = height of the fence
        n[] = i-th element is height of i-th person
        */
        int n = sc.nextInt();
        int h = sc.nextInt();
        int ans = 0;
        for(int i = 0; i<n; i++){
            int val = sc.nextInt();
            if(val<=h){
                ans+=1;
            } else{
                ans+=2;
            }
        }
        out.println(ans);
    
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
