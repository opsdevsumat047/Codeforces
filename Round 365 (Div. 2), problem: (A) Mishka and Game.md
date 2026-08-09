import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);
        int t = fs.nextInt();
        int mishkaWins = 0;
        int chrisWins = 0;

        while (t-- > 0) {
            int n1 = fs.nextInt(); // Mishka's dice value
            int n2 = fs.nextInt(); // Chris's dice value

            // Check who won this specific round
            if (n1 > n2) {
                mishkaWins++;
            } else if (n2 > n1) {
            chrisWins++;
        }
    // If n1 == n2, it's a tie for this round, so no one's counter increases
}

// Compare total round wins to determine the overall game winner
if (mishkaWins > chrisWins) {
    out.println("Mishka");
} else if (chrisWins > mishkaWins) {
out.println("Chris");
} else {
out.println("Friendship is magic!^^"); // Fixed missing carets
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

long nextLong() throws IOException {
    return Long.parseLong(next());
}
}
}
