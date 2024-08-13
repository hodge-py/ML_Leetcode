# Data Structures & Algorithms Learning

- [ ] DSA Arrays
- [ ] DSA Bubble Sort
- [ ] DSA Selection Sort
- [ ] DSA Insertion Sort
- [ ] DSA Quick Sort
- [x] DSA Counting Sort
      
```md
Manual Run Through
Before we implement the Counting Sort algorithm in a programming language, let's manually run through a short array, just to get the idea.

Step 1: We start with an unsorted array.

myArray = [ 2, 3, 0, 2, 3, 2]
Step 2: We create another array for counting how many there are of each value. The array has 4 elements, to hold values 0 through 3.

myArray = [ 2, 3, 0, 2, 3, 2]
countArray = [ 0, 0, 0, 0]
Step 3: Now let's start counting. The first element is 2, so we must increment the counting array element at index 2.

myArray = [ 2, 3, 0, 2, 3, 2]
countArray = [ 0, 0, 1, 0]
Step 4: After counting a value, we can remove it, and count the next value, which is 3.

myArray = [ 3, 0, 2, 3, 2]
countArray = [ 0, 0, 1, 1]
Step 5: The next value we count is 0, so we increment index 0 in the counting array.

myArray = [ 0, 2, 3, 2]
countArray = [ 1, 0, 1, 1]
Step 6: We continue like this until all values are counted.

myArray = [ ]
countArray = [ 1, 0, 3, 2]
Step 7: Now we will recreate the elements from the initial array, and we will do it so that the elements are ordered lowest to highest.

The first element in the counting array tells us that we have 1 element with value 0. So we push 1 element with value 0 into the array, and we decrease the element at index 0 in the counting array with 1.

myArray = [ 0]
countArray = [ 0, 0, 3, 2]
Step 8: From the counting array we see that we do not need to create any elements with value 1.

myArray = [ 0]
countArray = [ 0, 0, 3, 2]
Step 9: We push 3 elements with value 2 into the end of the array. And as we create these elements we also decrease the counting array at index 2.

myArray = [ 0, 2, 2, 2]
countArray = [ 0, 0, 0, 2]
Step 10: At last we must add 2 elements with value 3 at the end of the array.

myArray = [0, 2, 2, 2, 3, 3]
countArray = [ 0, 0, 0, 0]
Finally! The array is sorted.

```

- [ ] DSA Radix Sort
- [ ] DSA Merge Sort
- [ ] DSA Linear Search
- [ ] DSA Binary Search
