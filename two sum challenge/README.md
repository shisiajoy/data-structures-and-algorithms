# Two Sum (Array search)

## PROBLEM

Given an array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length. Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

Tests are generated such that there is exactly one solution. You may not use the same element twice. Solution must use only constant extra space.

Example 1: Input: numbers = [2,7,11,15], target = 9 Output: [1,2] Explanation: The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2.

Example 2: Input: numbers = [2,3,4], target = 6 Output: [1,3] Explanation: The sum of 2 and 4 is 6. Therefore index1 = 1, index2 = 3.

Example 3: Input: numbers = [-1,0], target = -1 Output: [1,2] Explanation: The sum of -1 and 0 is -1. Therefore index1 = 1, index2 = 2.

### Input Format

1. numbers: An array of integers that has the length >= 2

2. target: An integer which two integers in numbers should sum up to

### Constraints

1. 2 <= numbers.length <= 3 * 104
   
2. 1000 <= numbers[i] <= 1000
   
3. numbers is sorted in non-decreasing order.
   
4. 1000 <= target <= 1000
   
5. The tests are generated such that there is exactly one solution.

### Output Format

An array of length 2 containing indices of the two numbers. Note that the the output index is added to 1 to avoid typical zero-indexing in programming languages.


## SOLUTION.

### goal.

1. Find two numbers in the list that, when added together, give you exactly the target number.
   
2. Return the positions (or "indices") of these two numbers as a list. But there's a twist: instead of starting the count from zero (like we usually do in programming), we’re going to count from one. So, if you found the numbers at positions 0 and 1, you’d return [1, 2].
   
Example Walkthroughs


     Example 
     Input list: [2, 7, 11, 15]

     Target: 9

     We need to find two numbers in [2, 7, 11, 15] that add up to 9.

     If we start with the first number, 2, and add it to the next number, 7, we get:

     2 + 7 = 9

     2+7=9

     The positions of 2 and 7 in the list are 0 and 1. But since we’re supposed to start counting from 1, we return:

    [ 1, 2 ]

### How to Solve This Efficiently.

Since the list is already sorted, we can avoid going through all possible pairs.

1. Start with two pointers: one at the very beginning of the list (let's call it left) and one at the very end of the list (let's call it right).
   
2. Check the sum of the numbers at these two positions.
   
3. If the sum is too big, move the right pointer one step to the left (since we need a smaller sum).
   
4. If the sum is too small, move the left pointer one step to the right (since we need a larger sum).
   
5. If the sum is just right (equal to the target), we’ve found our solution!
   
6. By adjusting only these two pointers, we avoid using extra space and solve the problem quick.

### Example Scenario

     Suppose we have:

     A list: [1, 2, 4, 6, 10]
     
     Target: 6
     


    Initialize Pointers: left starts at the beginning (index 0), and right starts at the end of the list (index 4).

    Step-by-Step Process:

    Check numbers[left] + numbers[right]:
    
    1 + 10 = 11, which is too large.
    
    Move the right pointer left by one (to index 3).
    
    Repeat the Check:

    Now, numbers[left] + numbers[right]:
    
    1 + 6 = 7, which is still too large.
    
    Move the right pointer left by one (to index 2).
    
    Check Again:

    Now, numbers[left] + numbers[right]:

    1 + 4 = 5, which is too small.

    Move the left pointer right by one (to index 1).

    Finally, Check for the Solution:

    Now, numbers[left] + numbers[right]:
    
    2 + 4 = 6, which is exactly our target!
    
### Result


    We found the numbers 2 and 4 at indices 1 and 2.
    
    Since the problem specifies that we need 1-based indices, we return [2, 3].
    
### Summary
The two-pointer approach guarantees that:

1. We'll find the correct pair even if they’re separated by several indices.

   
2. We systematically move closer to each other until we reach the correct sum, or the pointers meet.
