# Bubble Sort with Optimization

```c
// complete the bubble_sort function

#include <cs50.h>
#include <stdio.h>

// function prototypes
void bubble_sort(int arr[], int size);
void print_array(int arr[], int size);

// size of array
#define SIZE 10

int main(void)
{
    // initialize array
    int arr[] = {1, 8, 4, 6, 0, 3, 5, 2, 7, 9};

    // sort array
    bubble_sort(arr, SIZE);

    // print out the array
    print_array(arr, SIZE);

    // done
    return 0;
}

// Function to print an array
void print_array(int arr[], int size)
{
    for (int i = 0; i < size; i++)
    {
        printf("%i ", arr[i]);
    }
    printf("\n");
}

// bubble sort
void bubble_sort(int arr[], int size)
{
    for (int i = 0; i < size - 1; i++)
    {
        bool swaps = false;
        for (int j = 0; j < size - 1 - i; j++)
        {
            if (arr[j] > arr[j + 1])
            {
                int temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swaps = true;
            }
        }
        if (swaps == false)
        {
            break;
        }
    }
}
```
