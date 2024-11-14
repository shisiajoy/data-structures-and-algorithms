# Big sorting 

## PROBLEM

Consider an array of numeric strings where each string is a positive number with anywhere from 1 to 10^6 digits. Sort the array's elements in non-decreasing, or ascending order of their integer values and return the sorted array.

### Example

Unsorted = ['1', '200', '150', '3']

Return the array ['1', '3', '150', '200'].

#### Function Description

bigSorting has the following parameter(s):

- string unsorted[n]: an unsorted array of integers as strings
  
#### Returns

- string[n]: the array sorted in numerical order
  
#### Input Format

The first line contains an integer, , the number of strings in .
Each of the  subsequent lines contains an integer string, .

#### Constraints

- ![Screenshot 2024-11-15 022345](https://github.com/user-attachments/assets/fda49c79-3ba7-44e4-b5d5-36aaf23b6a41)


- Each string is guaranteed to represent a positive integer.
  
- There will be no leading zeros.

- The total number of digits across all strings in  is between  and  (inclusive).


## SOLUTION

### Approach

#### Sorting by Length First:

- Since shorter strings represent smaller numbers, first sort the strings based on their length.
  
#### Sorting Lexicographically for Same Length:

- For strings of the same length, relyed on Python's default lexicographical (dictionary) comparison, which works as expected for numeric strings of equal length.
  
#### Custom Sorting Key:

- Python's built-in sorted() function with a custom key is used. The sorting key is a tuple (len(x), x), where len(x) sorts the strings by their length, and x ensures that strings of the same length are sorted lexicographically.
  
#### Efficient Sorting:

- The solution sorts the strings in 𝑂(𝑛 log 𝑛) time, which is efficient for typical sorting tasks.


