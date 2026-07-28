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
        int k = sc.nextInt();
        long p = sc.nextLong();
        long q = sc.nextLong();

        long sumM = 0;
        long[] penaltyA = new long[n];
        long[] penaltyB = new long[n];

        for (int i = 0; i < n; i++) {
            long val = sc.nextLong();
            long pathA = val % p;
            long pathB = (val % q) % p;

            long minPath = Math.min(pathA, pathB);
            sumM += minPath;

            penaltyA[i] = pathA - minPath;
            penaltyB[i] = pathB - minPath;
        }

    long minPenalty = Long.MAX_VALUE;
    long currentPenaltyA = 0;
    long currentPenaltyB = 0;

    for (int i = 0; i < k; i++) {
        currentPenaltyA += penaltyA[i];
        currentPenaltyB += penaltyB[i];
    }
minPenalty = Math.min(minPenalty, currentPenaltyA);
minPenalty = Math.min(minPenalty, currentPenaltyB);

for (int i = k; i < n; i++) {
    currentPenaltyA += penaltyA[i] - penaltyA[i - k];
    currentPenaltyB += penaltyB[i] - penaltyB[i - k];

    minPenalty = Math.min(minPenalty, currentPenaltyA);
    minPenalty = Math.min(minPenalty, currentPenaltyB);
}

out.println(sumM + minPenalty);
}
}

static class FastScanner {
    BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
    StringTokenizer st = new StringTokenizer("");

    String next() {
        while (!st.hasMoreTokens()) {
            try { st = new StringTokenizer(br.readLine()); }
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
