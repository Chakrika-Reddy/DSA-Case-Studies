import java.util.Arrays;

public class CO6_HeldKarpTSP {

    static final int INF = 1000000;

    static int heldKarp(int[][] dist) {

        int n = dist.length;

        int[][] dp = new int[1 << n][n];

        for (int[] row : dp)
            Arrays.fill(row, INF);

        dp[1][0] = 0;

        for (int mask = 1; mask < (1 << n); mask++) {

            for (int v = 0; v < n; v++) {

                if ((mask & (1 << v)) == 0)
                    continue;

                if (dp[mask][v] == INF)
                    continue;

                for (int u = 0; u < n; u++) {

                    if ((mask & (1 << u)) != 0)
                        continue;

                    int newMask = mask | (1 << u);

                    dp[newMask][u] = Math.min(
                            dp[newMask][u],
                            dp[mask][v] + dist[v][u]);
                }
            }
        }

        int fullMask = (1 << n) - 1;

        int answer = INF;

        for (int v = 1; v < n; v++) {

            answer = Math.min(
                    answer,
                    dp[fullMask][v] + dist[v][0]);
        }

        return answer;
    }

    public static void main(String[] args) {

        int[][] dist = {
            {0,10,15,20,12},
            {10,0,35,25,30},
            {15,35,0,30,20},
            {20,25,30,0,15},
            {12,30,20,15,0}
        };

        System.out.println(
                "Optimal Tour Cost = "
                + heldKarp(dist) + " km");
    }
}
