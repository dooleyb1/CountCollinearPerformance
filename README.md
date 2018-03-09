# CountCollinearPerformance
Java program comparing the performance of algorithms with regards to space and time on data sets of various sizes and structure.

Array a1, a2 and a3 contain points on the horizontal line y=1, y=2 and y=3, respectively. A non-horizontal line will have to cross all three of these lines. Thus **we are looking for 3 points**, each in a1, a2, a3 which lie on the same line. Three points (x1, y1), (x2, y2), (x3, y3) are collinear (i.e., they are on the same line) if x1(y2−y3)+x2(y3−y1)+x3(y1−y2)=0. In our case y1=1, y2=2, y3=3.

## Algorithms Compared

* **static int countCollinear** - Brute force implementation checking each element with every other element through three for loops.

* **static int countCollinearFast** - This implementation makes use of [Insertion Sort](https://en.wikipedia.org/wiki/Insertion_sort) and [Binary Search](https://en.wikipedia.org/wiki/Binary_search_algorithm) to enhance the searching performance.

## Performance Results & Analysis (Brute Force)

```
* Experimental Performance:
     * -------------------------
     *  Write the running time of the algorithm when run with the following input sizes
     *  
     *  Input Size N      Running Time (sec)
     *  ------------------------------------
     *  1000              0.392
     *  2000              2.898
     *  4000              22.862	
     *  5000			  42.798
     *
     *  Assuming that the running time of your algorithm is of the form aN^b,
     *  estimate 'b' and 'a' by fitting a line to the experimental points:
     *
     *  b = 2.93297
     *  a = 6.228 * 10^-10 
     *
     *  What running time do you predict using your results for input size 5000?
     *  What is the actual running time you get with such an input?
     *  What is the error in percentage?
     *
     *  Error = ( (Actual time) - (Predicted time) ) * 100 / (Predicted time)
     *
     *  Input Size N      Predicted Running Time (sec)        Actual Running Time (sec)       Error (%)
     *  ------------------------------------------------------------------------------------------------
     *  5000              43.98622157                         42.798                           2.701
     * 
```

**Order of growth:** O(n^3)

**Explanation:** This algorithm has an order of growth of n^3. The program contains three loops iterating over every element in every array and comparing it to every element in all the other arrays. Therefore if there is n=100 elements in total, there will be 100^3 array accesses. Therefore this program does not scale well, as can be seen in the above results.


## Performance Results & Analysis (Brute Force)

```
* Experimental Performance:
     * -------------------------
     *  Write the running time of the algorithm when run with the following input sizes
     *  
     *  Input Size N      Running Time (sec)
     *  ------------------------------------
     *  1000              0.392
     *  2000              2.898
     *  4000              22.862	
     *  5000			  42.798
     *
     *  Assuming that the running time of your algorithm is of the form aN^b,
     *  estimate 'b' and 'a' by fitting a line to the experimental points:
     *
     *  b = 2.93297
     *  a = 6.228 * 10^-10 
     *
     *  What running time do you predict using your results for input size 5000?
     *  What is the actual running time you get with such an input?
     *  What is the error in percentage?
     *
     *  Error = ( (Actual time) - (Predicted time) ) * 100 / (Predicted time)
     *
     *  Input Size N      Predicted Running Time (sec)        Actual Running Time (sec)       Error (%)
     *  ------------------------------------------------------------------------------------------------
     *  5000              43.98622157                         42.798                           2.701
     * 
```

**Order of Growth:** O(n^2 * logn)

**Explanation:** Sorting array a3 has an order of growth of O(n^2) time as explained earlier on. This is then followed by a binary search in a3 for T-(a2[j] + a1[i]) which has an order of growth of O(logn). So the overall order of growth of the program is therefore O(n^2 * logn).