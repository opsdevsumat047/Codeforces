import java.io.*;
import java.util.*;

public class Main {
    public static void main(String[] args) throws Exception {
        FastScanner fs = new FastScanner(System.in);
        PrintWriter out = new PrintWriter(System.out);

        int[] a = new int[5];
        a[1] = fs.nextInt();
        a[2] = fs.nextInt();
        a[3] = fs.nextInt();
        a[4] = fs.nextInt();

        String str = fs.next();

        int totalCalories = 0;

        for (int i = 0; i < str.length(); i++) {
            int strip = str.charAt(i) - '0';
            totalCalories += a[strip];
        }

    out.println(totalCalories);
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
