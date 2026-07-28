import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        while (t-- > 0) {
            int n = fs.nextInt();
            int temp = n;
            int[] arr = new int[6];
            for (int i = 0; i < 6; i++) {
                int digits = temp % 10;
                temp /= 10;
                arr[i] = digits;
            }
        int rt[] = new int[3];
        int lt[] = new int[3];
        for (int i = 0; i < 3; i++) {
            rt[i] = arr[5 - i];
            lt[i] = arr[i];
        }
    int rsum = 0;
    for (int nums : rt) {
        rsum += nums;
    }
int lsum = 0;
for (int nums : lt) {
    lsum += nums;
}
if (rsum == lsum) {
    out.println("YES");
} else {
out.println("NO");
}
}

out.flush();
out.close();
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
