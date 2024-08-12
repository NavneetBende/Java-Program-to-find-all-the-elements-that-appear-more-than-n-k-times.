Elements that appear more than “n/k” times in Java
Here, on this page, we will discuss the program to find all the elements that appear more than “n/k” times in Java. We are given an array of size n, find all elements in the array that appear more than n/k times.

Example :

Input : arr[ ] : {3, 1, 2, 2, 1, 2, 3, 3} and k = 4,
Output : 2, 3
Explanation: As, size of array i.e, n = 8 so, n/k => 2 and in the given input array 2 and 3 occur 3 and 3 times respectively. 
Java Program to find all the elements that appear more than ” nk ” times.
Method 1 (Brute force Approach) :
In this approach we will discuss the naive approach to solve this problem.

Iterate over the array and count its frequency.
If count is more than n/k times then print that element.
Now, here we need to handle the duplicate printing, so for that make every j-th element to -1 (Here, we are assuming that array will contain only positive elements).
Code to find all Elements that appear more than " n/k " times in Java
Run
import java.util.*;
public

  class Main {
  public
  static void morethanNdK(int a[], int n, int k) {
    int x = n / k;

  // Hash map initialization
    HashMap<Integer, Integer> y = new HashMap<>();
  // count the frequency of each element.

  for (int i = 0; i < n; i++) {
  // is element doesn't exist in hash table
    if (!y.containsKey(a[i])) y.put(a[i], 1);

    // if element does exist in the hash table
    else {
    int count = y.get(a[i]);
    y.put(a[i], count + 1);
    }
  }
    for (Map.Entry m : y.entrySet()) {
      Integer temp = (Integer)m.getValue();
      if (temp > x) System.out.println(m.getKey());
    }
  }
    // Driver Code
    public static void main(String[] args) {
    int a[] = new int[]{1, 1, 2, 2, 3, 5, 4, 2, 2, 3, 1, 1, 1};

    int n = 12;
    int k = 4;

     morethanNdK(a, n, k);
   }
 }
1
2
Time and Space complexity of above approach
Time - complexity : O(n^2) Space-complexity - O(1)
Related Pages
Given an array which consists of only 0, 1 and 2

Move all the negative elements to one side of the array

Find the Union and Intersection of the two sorted arrays

Find Largest sum contiguous Subarray

Minimize the maximum difference between heights 

Method 2 (Using Hash-map) 
In this approach we will discuss the efficient approach . We will use map to store the frequency of the element.

Declare a hash map.
Iterate over the array and increase that value in map by 1.
Now, iterate over the map and check if frequency is found to be greater than n / k, then print that key value.
Time and Space complexity
Time and Space complexity of above approach Time - complexity : O(n ) Space-complexity - O(n)
Elements that occur more than n/k times
Run
import java.util.*;
  public
  class Main {
  public
  static void morethanNdK(int a[], int n, int k) {
  int x = n / k;

  HashMap<Integer, Integer> y = new HashMap<>();
  // count the frequency of each element.
  for (int i = 0; i < n; i++) {
  // is element doesn't exist in hash table
 
  if (!y.containsKey(a[i])) y.put(a[i], 1);
  // if lement does exist in the hash table
 
  else {
    int count = y.get(a[i]);
    y.put(a[i], count + 1);
  }
}

  for (Map.Entry m : y.entrySet()) {
  Integer temp = (Integer)m.getValue();
  if (temp > x) System.out.println(m.getKey());
  }
}
// Driver Code
public
  static void main(String[] args) {
  int a[] = new int[]{1, 1, 2, 2, 3, 5, 4, 2, 2, 3, 1, 1, 1};
  int n = 12;
  int k = 4;
  morethanNdK(a, n, k);
 }
}
 

1
2
