import java.util.*;

class Edge {
    int u, v, weight;

    Edge(int u, int v, int weight) {
        this.u = u;
        this.v = v;
        this.weight = weight;
    }
}

public class CO4_BMTC_BellmanFord {

    static int[] bellmanFord(int n, List<Edge> edges, int source) {

        int[] dist = new int[n];
        Arrays.fill(dist, Integer.MAX_VALUE);
        dist[source] = 0;

        for (int i = 0; i < n - 1; i++) {

            for (Edge e : edges) {

                if (dist[e.u] != Integer.MAX_VALUE &&
                    dist[e.u] + e.weight < dist[e.v]) {

                    dist[e.v] = dist[e.u] + e.weight;
                }
            }
        }

        // Negative cycle detection
        for (Edge e : edges) {

            if (dist[e.u] != Integer.MAX_VALUE &&
                dist[e.u] + e.weight < dist[e.v]) {

                throw new RuntimeException(
                    "Negative cycle reachable from source");
            }
        }

        return dist;
    }

    public static void main(String[] args) {

        int n = 7;

        List<Edge> edges = new ArrayList<>();

        edges.add(new Edge(0,1,8));   // MJC->KEM
        edges.add(new Edge(0,2,5));   // MJC->JAY
        edges.add(new Edge(0,3,12));  // MJC->KOR
        edges.add(new Edge(2,3,4));   // JAY->KOR
        edges.add(new Edge(1,4,10));  // KEM->WHF
        edges.add(new Edge(1,5,7));   // KEM->HBR
        edges.add(new Edge(3,4,6));   // KOR->WHF
        edges.add(new Edge(3,6,9));   // KOR->MRT
        edges.add(new Edge(4,6,-3));  // WHF->MRT
        edges.add(new Edge(5,6,11));  // HBR->MRT
        edges.add(new Edge(4,5,3));   // WHF->HBR

        int[] dist = bellmanFord(n, edges, 0);

        String[] hubs = {
            "MJC","KEM","JAY",
            "KOR","WHF","HBR","MRT"
        };

        System.out.println("Shortest Distances:");

        for (int i = 0; i < n; i++) {
            System.out.println(
                hubs[i] + " = " + dist[i]);
        }
    }
}
