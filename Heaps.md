---
share: true
---

Min heap:
PriorityQueue\<Integer> minHeap = new PriorityQueue<>();

Max heap:
PriorityQueue\<Integer> maxHeap = new PriorityQueue<>((a,b) -> b-a );

Top K frequent elements:
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