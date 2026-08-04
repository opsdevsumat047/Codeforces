import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        while (t-- > 0) {
            int n = fs.nextInt();
            int k = fs.nextInt();

            // The only truly impossible case is when k = n - 1
            // This would require NO transitions (e.g., all 0s or all 1s),
            // which breaks the balance rule.
            if (k == n - 1) {
                out.println("-1");
                continue; // Use continue, NOT return!
            }

        // Calculate exact balanced counts
        int totalZeros = (n + 1) / 2; // Ceil of n/2
        int totalOnes = n / 2;        // Floor of n/2

        // Calculate exact number of blocks needed
        int transitions = (n - 1) - k;
        int numBlocks = transitions + 1;

        // How many of those blocks will be '0' blocks and '1' blocks?
        int zeroBlocks = (numBlocks + 1) / 2;
        int oneBlocks = numBlocks / 2;

        // We must put at least one character in every block.
        // Calculate how many "extra" characters are left over to dump into the first blocks.
        int extraZeros = totalZeros - zeroBlocks;
        int extraOnes = totalOnes - oneBlocks;

        StringBuilder sb = new StringBuilder();

        // Build the blocks one by one
        for (int i = 0; i < numBlocks; i++) {
            if (i % 2 == 0) {
                // It's a '0' block
                sb.append('0');
                if (i == 0) {
                    // Dump all extra 0s into the very first '0' block
                    for (int j = 0; j < extraZeros; j++) sb.append('0');
                }
        } else {
        // It's a '1' block
        sb.append('1');
        if (i == 1) {
            // Dump all extra 1s into the very first '1' block
            for (int j = 0; j < extraOnes; j++) sb.append('1');
        }
}
}

out.println(sb.toString());
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
