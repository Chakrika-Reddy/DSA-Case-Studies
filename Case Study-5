import java.util.*;

public class CO5_Spotify_TopKHeap {

    public static void main(String[] args) {

        int[] listeners = {
            45,12,78,23,56,89,
            34,67,18,91,50,39
        };

        int k = 5;

        PriorityQueue<Integer> minHeap =
                new PriorityQueue<>();

        for (int count : listeners) {

            if (minHeap.size() < k) {
                minHeap.offer(count);
            }
            else if (count > minHeap.peek()) {
                minHeap.poll();
                minHeap.offer(count);
            }
        }

        List<Integer> topK =
                new ArrayList<>(minHeap);

        topK.sort(Collections.reverseOrder());

        System.out.println("Top " + k + " Artists:");

        for (int x : topK) {
            System.out.print(x + " ");
        }
    }
}
