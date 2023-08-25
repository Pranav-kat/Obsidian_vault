---
share: true
---

Int to String to int
 ```Java
 String.valueOf();
 Integer.parseInt();
	
 int c = a;
  for(int j=0;j<>n;j++){
                c += Math.pow(2, j)*b;
                System.out.printf("%s ",c);
            }
            System.out.println()
```
						
STATIC INITIALIZATION CLASS
 ```java
 static boolean flag = true; 
 static int B,H;
 static{
 Scanner scan = new Scanner(System.in);
 B = scan.nextInt();
 scan.nextLine();
 H = scan.nextInt();
 scan.close();
 if(B>0 && H>0){
 flag = true;
 }else if(B<=0 || H<=0){
 flag=false;
 System.out.println("java.lang.Exception: Breadth and height must be positive");
 }
```
	
HASHMAP
	 
	 static int migratoryBirds(List<Integer> arr) {
        Map<Integer, Integer> birds = new HashMap<>();
        int key = 0;

        for(int i = 0; i < arr.size(); i++){
            if(birds.containsKey(arr.get(i))){
                birds.put(arr.get(i), birds.get(arr.get(i)) + 1);
            }else{
                birds.put(arr.get(i), 1);
            }
        }
        key = Collections.max(birds.entrySet(), Map.Entry.comparingByValue()).getKey();
        return key;
       } 
	
SET
	
	public static int sockMerchant(int n, List<Integer> ar) {
    Set<Integer> colors = new HashSet<>();
    int pairs = 0;
    for (int i = 0; i < n; i++) { //>
        if (!colors.contains(ar.get(i))) {
            colors.add(ar.get(i));
        } else {
            pairs++;
            colors.remove(ar.get(i));
        }
    }
    return pairs;
    }
					
Valleys Problem
	 int countingValleys(int steps, string path) {
     int v = 0;   //# of valleys 
     int lvl = 0; //level
     for(int i=0;i<path.length();i++){ //> 
     if(path[i] == 'U') ++lvl;
     if(path[i] == 'D') --lvl;   
     if(lvl == 0 && path[i] == 'U') // if we just came UP to sea level
     ++v;
     }
     return v;
	 }
	
Math 
	import java.lang.Math;
	Math.abs();
	
Drawing Book Problem
	public static int pageCount(int n, int p) {
    int frontdist = p / 2;
    int backdist = n % 2 == 0 ? (n - p + 1) / 2 : (n - p) / 2;
    return Math.min(frontdist, backdist);
    }
	
Electronic pairs Problem
 static int getMoneySpent(int[] keyboards, int[] drives, int b) {// O(nm) approach 
        int ans = -1;
        for (int i = 0; i < keyboards.length; i++) {
            for (int j = 0; j < drives.length; j++) {
                int sum = keyboards[i] + drives[j];
                if (sum > b)  continue;
                ans = Math.max(ans, sum);
            }  
         }
         return ans;
         } 
 Alternate O(n+mlog(n+m)) approach
	int max = -1;
 for(int i = 0, j = 0; i < n; i++){
 for(; j < m; j++){
 if(keyboards[i]+pendrives[j] > s) break; //This prevents j from incrementing
 if(keyboards[i]+pendrives[j] > max)
 max = keyboards[i]+pendrives[j];
 }
 }
	
Climbing the Leaderboard Problem
 ```java
 public static List<Integer> climbingLeaderboard(List<Integer> ranked, List<Integer> player) {
    List<Integer> ans = new ArrayList<>();
    TreeSet<Integer> copy = new TreeSet<Integer>();
    copy.addAll(ranked);
    TreeSet<Integer> res = (TreeSet<Integer>)copy.descendingSet();  
    for(int i=0;i<player.size();i++) { 
        res.add(player.get(i));
        List<Integer> ans1 = new ArrayList<>(res);
        ans.add(ans1.indexOf(player.get(i))+1);
        res.remove(player.get(i));
     }
     return ans;
     }
 ```

Climbing the Leaderboard Problem Optimized Code
 ```java
 	import java.io.*;
 import java.util.*;
 import java.text.*;
 import java.math.*;
 import java.util.regex.*;

 public class Solution {
    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        int n = in.nextInt();
        int[] scores = new int[n];
        for(int scores_i=0; scores_i < n; scores_i++){
            scores[scores_i] = in.nextInt();
        }
        int m = in.nextInt();
        int[] alice = new int[m];
        for(int alice_i=0; alice_i < m; alice_i++){
            alice[alice_i] = in.nextInt();
        }
        printScores(n, scores, alice);
    }
    
     public static void printScores(int n, int[] scores, int[] alice){
        ArrayList<Integer> places = new ArrayList<Integer>();
        int place = 1;
        places.add(scores[0]);
        for(int i = 1; i < scores.length; i++){
            int currPlace = place-1;
            int currScore = scores[i];
            if(currScore != places.get(currPlace)){
                place++;
                places.add(currScore);
            }
        }
        
        int currPlace = places.size() + 1;
        for(int i = 0; i < alice.length; i++){
            currPlace = getPlace(currPlace, alice[i], places);
            System.out.println(currPlace);
        }
        
    }
    
    public static int getPlace(int currPlace, int currScore, ArrayList<Integer> places){
        for(int i = currPlace - 1; i > 0; i--){
            int index = i - 1;
            if(currScore < places.get(index)){
                return i + 1;
            }
        }
        return 1;
    }   
 } 
 ```

Picking Numbers Problem Optimized Code
 ```java
  import java.io.*;
 import java.util.*;

 public class Solution
 {
    public static void main(String[] args)
    {
        Scanner readIn = new Scanner(System.in);       
        int n = readIn.nextInt();
        int[] frequencie = new int[100];
        for(int ii = 0; ii < n; ii++)
            frequencie[readIn.nextInt()]++;        
        int out = Integer.MIN_VALUE;
        for(int ii = 0; ii < frequencie.length - 1; ii++)
            out = frequencie[ii] + frequencie[ii + 1] > out ? frequencie[ii] + frequencie[ii + 1] : out;  
        System.out.println(out);
    }
 }
 ```

Reverse Integer 
 ```java
 public static int reverse(int m){
    int temp=0;
    for( ;m != 0; m=m/10)   
    {  
    int remainder = m % 10;  
    temp = temp * 10 + remainder;    
    }
    return temp;  
 ```

Minimum  Distance 
 ```java
 public static int minimumDistances(List<Integer> a) {
     Map<Integer, Integer> hm = new HashMap<>();
    int minDist= Integer.MAX_VALUE;
    for(int i=0; i < a.size(); i++){
        if(hm.containsKey(a.get(i))) {
            int x=hm.get(a.get(i));
            int dist = i - x;
            if(dist < minDist) minDist = dist;
        }
        else hm.put(a.get(i),i);            
    }
    if(minDist == Integer.MAX_VALUE) minDist=-1;
    return minDist;
    }
 ```

Extra long integers
 ```java
 BigInteger fact=BigInteger.valueOf(1);
 ```

SkipList
 Skip list is a data structure that can be used as an alternative to balanced binary trees (refer to Trees chapter). As compared to a binary tree, skip lists allow quick search, insertion and deletion of elements. This is achieved by using probabilistic balancing rather than strictly enforce balancing. It is basically a linked list with additional pointers such that intermediate nodes can be skipped. It uses a random number generator to make some decisions.

Union of two sorted arrays
 ```java
 public static int[] union(int[] A, int[] B){
	int i=0;
	int j=0;
	ArrayList<Integer> list = new ArrayList<>();
	while(i<A.length && j<B.length){
	if(A[i]<B[j]){
	if(list.size()==0 || !list.contains(A[i])){
	list.add(A[i]);
	 }
	 i++;
	}else{
	if(list.size==0 || !list.contains(B[j])){
	list.add(B[j]);
	}
	 j++;	}
	}
	while(i<A.length){
	if(list.size()==0 || !list.contains(A[i])){
	list.add(A[i]);
	 }
	 i++;
	}
	while(j<B.length){
	if(list.size()==0 || !list.contains(B[j])){
	list.add(B[j]);
	 }
	 j++;
	}
	return list.toArray();
	}
 ```
