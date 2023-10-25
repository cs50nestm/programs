# Binary Search

### Using a Loop

```c
// implement binary search function

#include <cs50.h>
#include <stdio.h>

#define NUMBERS 9

bool bin_search(int value, int values[], int size);

int main(void)
{
    int arr[] = {2, 4, 6, 7, 8, 11, 14, 18, 20};

    int target = get_int("Enter a number: ");

    if (bin_search(target, arr, NUMBERS))
    {
        printf("Found\n");
    }
    else
    {
        printf("Not found!\n");
    }
}

bool bin_search(int value, int values[], int size)
{
    // Search for value
    int min = 0;
    int max = size - 1;

    while (min <= max)
    {
        // Find index of middle of array
        int middle = (min + max) / 2;
        if (value < values[middle])
        {
            max = middle - 1;
        }
        else if (value > values[middle])
        {
            min = middle + 1;
        }
        else if (value == values[middle])
        {
            return true;
        }
    }
    return false;
}
```

### Using Recursion

```c
// implement binary search function

#include <cs50.h>
#include <stdio.h>

#define NUMBERS 9

bool bin_search(int value, int values[], int start, int end);

int main(void)
{
    int arr[] = {2, 4, 6, 7, 8, 11, 14, 18, 20};

    int target = get_int("Enter a number: ");

    if (bin_search(target, arr, 0,  NUMBERS - 1))
    {
        printf("Found\n");
    }
    else
    {
        printf("Not found!\n");
    }
}

bool bin_search(int value, int values[], int start, int end)
{
    // if the "end" comes before the "start" then the element can't be in the array
    if (end < start)
    {
        return false;
    }

    // Calculate the midpoint of the current array
    int midpoint = (start + end) / 2;

    // if we found what we're looking for in the middle, return true
    if (value == values[midpoint])
    {
        return true;
    }
    // If the element at the midpoint is too large, repeat with the left half of the array
    else if (value < values[midpoint])
    {
        return bin_search(value, values, start, midpoint - 1);
    }
    // Otherwise, repeat with the right half of the array
    else
    {
        return  
    }
}

```
