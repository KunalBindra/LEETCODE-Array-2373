# LEETCODE-Array-2373
Your `largestLocal` method seems to find the largest local value within each 3x3 subgrid of the given grid. Here's a dry run of your code:

1. **Initialization:**
   - Initialize a class `Solution`.
   - It has a private method `FCM` to find the maximum value in a 3x3 subgrid.
   - It has a public method `largestLocal` to find the largest local value in the given grid.

2. **`FCM` Method:**
   - It takes a 2D grid `grid`, a starting row index `row`, and a starting column index `col`.
   - It initializes `maxVal` to 0.
   - It iterates over a 3x3 subgrid starting from `row`, `col`.
   - It updates `maxVal` to the maximum value found in the subgrid.
   - It returns `maxVal`.

3. **`largestLocal` Method:**
   - It takes a 2D grid `grid` as input.
   - It initializes `n` to the length of the grid.
   - It creates a new 2D array `maxLocal` to store the maximum local values. Its dimensions are `(n-2) x (n-2)` because for each 3x3 subgrid, you will only have `n-2` such subgrids.
   - It iterates over each possible starting row and column for a 3x3 subgrid.
   - For each starting position, it calculates the maximum value within the corresponding 3x3 subgrid using the `FCM` method and stores it in `maxLocal`.
   - It returns `maxLocal`.

Here's a dry run with a sample input:

```java
Input grid:
[[1, 2, 3, 4],
 [5, 6, 7, 8],
 [9, 10, 11, 12],
 [13, 14, 15, 16]]

Output maxLocal (after calling largestLocal):

maxLocal:
[[11, 12],
 [15, 16]]
```

Explanation:

- For the first 3x3 subgrid:
  - Starting at (0,0), the maximum value is 11.
  - Starting at (0,1), the maximum value is 12.
- For the second 3x3 subgrid:
  - Starting at (1,0), the maximum value is 15.
  - Starting at (1,1), the maximum value is 16.

The resulting `maxLocal` array holds the maximum values for each 3x3 subgrid.
