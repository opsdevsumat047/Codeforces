import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int t = fs.nextInt();
        int[] arr = new int[t];
        for (int i = 0; i < t; i++) {
            arr[i] = fs.nextInt();
        }

    int left = 0;
    int right = t - 1;
    int ssum = 0;
    int dsum = 0;

    // Track whose turn it is
    boolean isSerejaTurn = true;

    // Loop runs until all cards are taken
    while (left <= right) {
        int chosenValue;

        // Greedily pick the larger card
        if (arr[left] > arr[right]) {
            chosenValue = arr[left];
            left++;
        } else {
        chosenValue = arr[right];
        right--;
    }

// Give the points to the active player
if (isSerejaTurn) {
    ssum += chosenValue;
} else {
dsum += chosenValue;
}

// Alternate the turn for the next round
isSerejaTurn = !isSerejaTurn;
}

out.println(ssum + " " + dsum);
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
}
}
