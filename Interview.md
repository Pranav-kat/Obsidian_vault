---
share: true
---

### Question 1: Trim function implementation

**Answer**:

```java
public class CustomTrimExample {
    public static void main(String[] args) {
        // Sample input string with leading and trailing spaces
        String inputString = "   Hello, World!   ";

        // Calling the customTrim method to remove leading and trailing spaces
        String trimmedString = customTrim(inputString);

        // Displaying the original and trimmed strings
        System.out.println("Original String: '" + inputString + "'");
        System.out.println("Trimmed String: '" + trimmedString + "'");
    }

    public static String customTrim(String input) {
        int start = 0;
        int end = input.length() - 1;

        // Find the index of the first non-space character from the start
        while (start <= end && input.charAt(start) == ' ') {
            start++;
        }

        // Find the index of the first non-space character from the end
        while (end >= start && input.charAt(end) == ' ') {
            end--;
        }

        // Extract the substring without leading and trailing spaces
        return input.substring(start, end + 1);
    }
}
```

### Question 3:

**User**: Write a program to count occurrence of each character in a string in java

**Answer**:

```java
import java.util.HashMap;
import java.util.Map;

public class CharacterCountExample {
    public static void main(String[] args) {
        // Sample input string with leading and trailing spaces
        String inputString = "programming is fun";

        // Create a HashMap to store character counts
        Map<Character, Integer> charCountMap = new HashMap<>();

        // Convert the string to a character array
        char[] charArray = inputString.toCharArray();

        // Iterate through the character array
        for (char c : charArray) {
            // Check if the character is not a space
            if (c != ' ') {
                // If the character is already in the map, increment its count
                if (charCountMap.containsKey(c)) {
                    charCountMap.put(c, charCountMap.get(c) + 1);
                } else {
                    // If the character is not in the map, add it with a count of 1
                    charCountMap.put(c, 1);
                }
            }
        }

        // Display the character counts
        System.out.println("Character Counts:");
        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            System.out.println("'" + entry.getKey() + "': " + entry.getValue());
        }
    }
}
```

### Question 4:

**User**: Program to get the 2nd most frequent character of string.

**Answer**:

```java
import java.util.HashMap;
import java.util.Map;

public class SecondMostFrequentCharacter {
    public static void main(String[] args) {
        // Sample input string
        String inputString = "programming is fun";

        // Create a HashMap to store character counts
        Map<Character, Integer> charCountMap = new HashMap<>();

        // Convert the string to a character array
        char[] charArray = inputString.toCharArray();

        // Iterate through the character array
        for (char c : charArray) {
            // Check if the character is not a space
            if (c != ' ') {
                // If the character is already in the map, increment its count
                if (charCountMap.containsKey(c)) {
                    charCountMap.put(c, charCountMap.get(c) + 1);
                } else {
                    // If the character is not in the map, add it with a count of 1
                    charCountMap.put(c, 1);
                }
            }
        }

        // Find the second most frequent character
        char secondMostFrequent = findSecondMostFrequent(charCountMap);

        // Display the result
        System.out.println("Second Most Frequent Character: '" + secondMostFrequent + "'");
    }

    public static char findSecondMostFrequent(Map<Character, Integer> charCountMap) {
        int maxFrequency = Integer.MIN_VALUE;
        int secondMaxFrequency = Integer.MIN_VALUE;
        char mostFrequentChar = '\0';
        char secondMostFrequentChar = '\0';

        for (Map.Entry<Character, Integer> entry : charCountMap.entrySet()) {
            int count = entry.getValue();

            if (count > maxFrequency) {
                secondMaxFrequency = maxFrequency;
                secondMostFrequentChar = mostFrequentChar;

                maxFrequency = count;
                mostFrequentChar = entry.getKey();
            } else if (count > secondMaxFrequency && count != maxFrequency) {
                secondMaxFrequency = count;
                secondMostFrequentChar = entry.getKey();
            }
        }

        return secondMostFrequentChar;
    }
}
```

### Question 5:

**User**: Implement the Merge step of the merge sort algorithm in java

**Answer**:

```java
public class MergeSort {
    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6, 7};
        
        System.out.println("Original Array:");
        printArray(arr);
        
        mergeSort(arr, 0, arr.length - 1);
        
        System.out.println("\nSorted Array:");
        printArray(arr);
    }

    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;
            
            // Sort the first and second halves
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);
            
            // Merge the sorted halves
            merge(arr, left, mid, right);
        }
    }

    public static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        // Create temporary arrays
        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        // Copy data to temporary arrays leftArray[] and rightArray[]
        for (int i = 0; i < n1; i++)
            leftArray[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            rightArray[j] = arr[mid + 1 + j];

        // Merge the temporary arrays back into arr[left...right]
        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (leftArray[i] <= rightArray[j]) {
                arr[k] = leftArray[i];
                i++;
            } else {
                arr[k] = rightArray[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of leftArray[], if any
        while (i < n1) {
            arr[k] = leftArray[i];
            i++;
            k++;
        }

        // Copy remaining elements of rightArray[], if any
        while (j < n2) {
            arr[k] = rightArray[j];
            j++;
            k++;
        }
    }

    public static void printArray(int[] arr) {
        for (int value : arr) {
            System.out.print(value + " ");
        }
        System.out.println();
    }
}
```

### Question 6:

**User**: Implementing a simple hashmap in Java

**Answer**:

```java
import java.util.LinkedList;

class MyHashMap<K, V> {
    private static final int DEFAULT_CAPACITY = 16;
    private LinkedList<Entry<K, V>>[] buckets;
    private int capacity;

    private static class Entry<K, V> {
        K key;
        V value;

        Entry(K key, V value) {
            this.key = key;
            this.value = value;
        }
    }

    public MyHashMap() {
        this(DEFAULT_CAPACITY);
    }

    public MyHashMap(int capacity) {
        this.capacity = capacity;
        buckets = new LinkedList[capacity];
        for (int i = 0; i < capacity; i++) {
            buckets[i] = new LinkedList<>();
        }
    }

    private int hash(K key) {
        return key.hashCode() % capacity;
    }

    public void put(K key, V value) {
        int index = hash(key);
        LinkedList<Entry<K, V>> bucket = buckets[index];

        for (Entry<K, V> entry : bucket) {
            if (entry.key.equals(key)) {
                entry.value = value; // Update the value if the key already exists
                return;
            }
        }

        bucket.add(new Entry<>(key, value)); // Add a new entry if the key doesn't exist
    }

    public V get(K key) {
        int index = hash(key);
        LinkedList<Entry<K, V>> bucket = buckets[index];

        for (Entry<K, V> entry : bucket) {
            if (entry.key.equals(key)) {
                return entry.value; // Return the value if the key is found
            }
        }

        return null; // Key not found
    }

    public void remove(K key) {
        int index = hash(key);
        LinkedList<Entry<K, V>> bucket = buckets[index];

        for (Entry<K, V> entry : bucket) {
            if (entry.key.equals(key)) {
                bucket.remove(entry); // Remove the entry if the key is found
                return;
            }
        }
    }

    public static void main(String[] args) {
        MyHashMap<String, Integer> hashMap = new MyHashMap<>();
        hashMap.put("one", 1);
        hashMap.put("two", 2);
        hashMap.put("three", 3);

        System.out.println("Get 'two': " + hashMap.get("two")); // Should print 2
        System.out.println("Get 'four': " + hashMap.get("four")); // Should print null

        hashMap.remove("three");
        System.out.println("Get 'three' after removal: " + hashMap.get("three")); // Should print null
    }
}
```

### Question 7:

**User**: Quick sort, merge sort difference in tabular format

**Answer**:

| Aspect                  | Quick Sort                           | Merge Sort                           |
|-------------------------|-------------------------------------|-------------------------------------|
| **Algorithm Type**      | Comparison-based sorting algorithm  | Comparison-based sorting algorithm  |
| **Divide and Conquer**  | Yes                                 | Yes                                 |
| **Worst-Case Time**     | O(n^2)                              | O(n log n)                          |
| **Average Time**        | O(n log n)                          | O(n log n)                          |
| **Best-Case Time**      | O(n log n)                          | O(n log n)                          |
| **Space Complexity**    | O(log n)                            | O(n)                                |
| **Stability**           | Not stable (may change the order of equal elements) | Stable (equal elements maintain their order) |
| **Adaptive**            | Not adaptive (performance doesn't improve if the input is partially sorted) | Adaptive (performance can be better if the input is partially sorted) |
| **In-Place Sorting**    | Yes (usually performed in-place with low memory overhead) | No (requires additional memory for merging) |

---
