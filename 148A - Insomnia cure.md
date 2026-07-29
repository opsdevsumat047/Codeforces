import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);
        //kth dragon = punch
        // lth dragon = tail
        // mth = paws
        // nth = call
        // how many suffered ?
        int k = fs.nextInt();
        int l = fs.nextInt();
        int m = fs.nextInt();
        int n = fs.nextInt();
        int d = fs.nextInt();
        int count = 0;
        boolean visited = false;
        boolean[] ans = new boolean[d+1];
        int tempk = k;
        while(k <= d){
            if(!ans[k]){
                count++;
                ans[k] = true;
            }
        k = k+tempk;
    }
int templ = l;
while(l <= d){
    if(!ans[l]){
        count++;
        ans[l] = true;
    }
l=l+templ;
}
int tempm = m;
while(m <= d){
    if(!ans[m]){
        count++;
        ans[m] = true;
    }
m=m+tempm;
}
int tempn = n;
while(n <= d){
    if(!ans[n]){
        count++;
        ans[n] = true;
    }

n=n+tempn;
}
out.println(count);
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
