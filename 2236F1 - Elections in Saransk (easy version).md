import java.io.*;
import java.util.*;

public class Main {
    // The maximum value of a_i according to the problem constraints
    static final int MAXA = 500005;

    // SPF (Smallest Prime Factor) array for O(log N) fast factorization
    static int[] spf = new int[MAXA];

    // Precompute the Smallest Prime Factor for every number using a Sieve
    static void computeSPF() {
        for (int i = 2; i < MAXA; i++) spf[i] = i;
        for (int i = 2; i * i < MAXA; i++) {
            if (spf[i] == i) { // i is prime
                for (int j = i * i; j < MAXA; j += i) {
                    if (spf[j] == j) spf[j] = i;
                }
        }
}
}

public static void main(String[] args) throws Exception {
    // Run the Sieve once before processing any test cases
    computeSPF();

    FastScanner fs = new FastScanner(System.in);
    PrintWriter out = new PrintWriter(System.out);

    int t = fs.nextInt();
    long MOD = 1000000007;

    // This array keeps track of the total exponent count for each prime
    int[] totalExponents = new int[MAXA];

    // This list remembers which primes we actually saw so we can
    // quickly reset the totalExponents array without looping 500,000 times
    List<Integer> usedPrimes = new ArrayList<>();

    while (t-- > 0) {
        int n = fs.nextInt();
        int x = fs.nextInt(); // x is always 1 in the easy version

        for (int i = 0; i < n; i++) {
            int a = fs.nextInt();

            // Fast prime factorization of 'a' using the SPF array
            while (a > 1) {
                int p = spf[a];
                int count = 0;

                // Count how many times this prime factor divides 'a'
                while (a % p == 0) {
                    count++;
                    a /= p;
                }

            // If this is the first time we've seen this prime in the test case, track it
            if (totalExponents[p] == 0) {
                usedPrimes.add(p);
            }

        // Add the exponent count to the grand total for this prime
        totalExponents[p] += count;
    }
}

// Calculate the total number of valid ideal arrays
long ans = 1;
for (int p : usedPrimes) {
    // For each prime, the number of choices is (Total Exponent + 1)
    // We multiply this to our running total, taking the modulo at each step
    ans = (ans * (totalExponents[p] + 1)) % MOD;

    // Reset the array back to 0 to prep for the next test case
    totalExponents[p] = 0;
}

// Clear our tracking list for the next test case
usedPrimes.clear();

out.println(ans);
}

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
}
}
