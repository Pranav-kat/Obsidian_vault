---
share: true
---

Min heap:
PriorityQueue\<Integer> minHeap = new PriorityQueue<>();

Max heap:
PriorityQueue\<Integer> maxHeap = new PriorityQueue<>((a,b) -> b-a );

### Top K frequent elements:
 ```java
 class Solution {
    public int[] topKFrequent(int[] nums, int k) {
        int[] arr = new int[k];
        Map<Integer,Integer> map  = new HashMap<>();
        for(int num: nums){
            map.put(num, map.getOrDefault(num, 0)+1);
        }

        PriorityQueue<Integer> heap = new PriorityQueue<>((a,b) -> map.get(b) - map.get(a));

        for(int num: map.keySet()){
           heap.offer(num);
        }

        for(int i=0;i<k;i++){
           arr[i] = heap.poll();
        }
        return arr;
    }
 }
 ```


### K closest Points to origin
 ```java
 class Solution {
    public int[][] kClosest(int[][] points, int k) {
        PriorityQueue<int[]> pq = new PriorityQueue<>((a,b)->a[1]-b[1]); // min heap
        //Iterate through the array to calculate the distance^2 and add it to the pq
        for(int i = 0; i < points.length; i++){
            int sum = points[i][0] * points[i][0] + points[i][1] * points[i][1];
            pq.offer(new int[] {i,sum});
        }
        //Create a new response array and poll k elements from the queue into the array
        //That will be the k-smallest distance^2, and we don't have to do the square root necessarily
        int[][] res = new int[k][];
        while(k--> 0){
            res[k] = points[pq.poll()[0]];
        }
        return res;
    }
 }
 ```