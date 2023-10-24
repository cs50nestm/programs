# Selection Sort

In this lab you will learn about:

- How selection sort works
- Computational Complexity

## What is Selection Sort?

Bubble sort sure involved a lot of swapping! Let's take a look at another sorting algorithm, **selection sort**. 

![Selection_Sort](https://raw.githubusercontent.com/cs50nestm/cs50labs/2019/selectionsort/selection_sort.gif)

First, we go over the entire list, and look for the smallest number. Then we select that number, and put it at the front of our list, swapping it with whatever was originally at that position. We then look through the list for the second smallest number and swap this with the element that is second from the left in our list.

As we continue, we build a sorted list, one element at a time.

The pseudocode for **selection sort** would look like this:

```
for i from 0 to n-1
    find smallest element between i'th and n-1'th
    swap smallest with i'th element
```

## Computational Complexity

Even though we are doing fewer swaps with **selection sort** than we are in **bubble sort**, we are looking through our array `n - 1` times, and doing up to `n - 1` swaps, so our worst case scenario involves looking at n<sup>2</sup> elements. Unfortunately, our best case and worst case scenarios are the same here. We wouldn't know if our array starts out sorted, since we are looking through the array one element at a time. So using **big O** notation, we can say that **selection sort** has a running time of **O(n<sup>2</sup>)**.

## Your Turn

Complete the `selection_sort()` function on the right to sort the supplied array. 

Note that this function has a return type of `void`. This means the function doesn't return anything. What it does do is sort the array.

The `print_array()` function is given to you to print out the array after you've sorted it, to make sure your algorithm works properly.

<details>
  <summary>
    <span style="font-weight: bold;">
    Hint
    </span>
  </summary>
<br>
  <ol>
    <li>You might want to start this by simply using an outer <code>for</code> loop that iterates <code>n - 1</code> times, which corresponds to <code>n - 1</code> passes through the array. You may want to use <code>i</code> as your loop counter variable.</li>
    <li>Create a variable, <code>min</code>, to keep track of the index of the element with the smallest value. Initialize its value to <code>i</code>.</li>
    <li>Create an inner <code>for</code> loop. If you use <code>j</code> for your counter, you could start <code>j</code> at <code>i + 1</code> and repeat through the last element in the array.</li> 
    <li>Compare each element in the array to the element stored at index, <code>min</code>. If <code>arr[j] < arr[min]</code>, assign to <code>min</code> the value of <code>j</code>, since the element at this index is the smallest so far.</li>
    <li>After this inner <code>for</code> loop complete, the value stored in <code>min</code> will be the index of the smallest element in the unsorted portion of the array. Now it's time to swap <code>arr[min]</code> with <code>arr[i]</code>.</li>
</li>
  </ol>
</details>


Once you have your function sorting properly, is there something else you can do to make it more efficient? Does it make sense to use a counter like in bubble sort?

While it might seem like a good idea to check if the entire array is sorted after every successful swap to avoid additional passes through the array, this would come at a cost, because then there would be even more comparisons to be made. 

This is why we say that the worst case and best case scenarios for **selection sort** are both on the order of n<sup>2</sup>.

[Download our CS50 Reference sheet on Selection Sort](https://cs50.harvard.edu/ap/2020/assets/pdfs/selection_sort.pdf)
