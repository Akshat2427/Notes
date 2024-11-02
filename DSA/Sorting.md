> *Sometimes you need time away to sort thing out in your head. It makes everything clearer* .

##  1. Selection Sorting : 



// Select the minimum / maximum and put it in first place i.e.
 array = 2 , 3 , 1 , 4, 5 
 - find min in loop 1 from array 
 - 1 is the minimum 
 - put it in place of 0th index i.e. swap it with 2
 - new array  = 1 3 2 4 5 
 - do it n times

*Only n swap so less load on CPU , yeah!!!*


// Time and Space Complexity
- TC : 
1. Best Case : n^2
2. Average Case : n^2
3. Worst Case : n^2
- SC:
O(1) in all cases



// Questions One may ask
1. Is selection sort stable ? 
- No , it is not stable i.e. it doesn't maintain relative order.

2. Does it have minimum number of swap as compare to rest algo ? 
- Yes


// Code

```cpp
int arr = [ 5 ,4 ,2 ,1 ,3 ];
 int n = arr.size();

    for (int i = 0; i < n - 1; ++i) {

        // Assume the current position holds
        // the minimum element
        int min_idx = i;

        // Iterate through the unsorted portion
        // to find the actual minimum
        for (int j = i + 1; j < n; ++j) {
            if (arr[j] < arr[min_idx]) {

                // Update min_idx if a smaller
                // element is found
                min_idx = j; 
            }
        }

        // Move minimum element to its
        // correct position
        swap(arr[i], arr[min_idx]);
    }
```




##  2. Bubble Sorting


// Swap till the largest element reach to the largest
array  =  2, 3 , 1, 5, 4
- Check 0th and 1st index 
- Swap if array[1] < array[0] 
- move index by 1 till n-1
- now array  = 2 , 3,  1, 4, 5
- now max is at last repeat same from 0

*If there are only 2 or 4 elements misplaced it is very efficient and helpful*

// Time and Space Complexity
- TC : 
1. Best Case : n
2. Average Case : n^2
3. Worst Case : n^2
- SC:
O(1) in all cases



// Questions One may ask
1. Is Bubble sort stable ? 
- Yes , it is  stable i.e. it  maintain relative order.

2. Does it have minimum number of swap as compare to rest algo ? 
- No , it have too many swaps

3. It should be use if only 2 or 3 swap in total are there in large array


// Code

```cpp
vector<int> arr = {64, 34, 25, 12, 22, 11, 90};
int n = arr.size();
bool swapped;
for (int i = 0; i < n - 1; i++)
{ 
swapped = false; // Last i elements are already sorted 
for (int j = 0; j < n - i - 1; j++)
{ 
if (arr[j] > arr[j + 1]) {
// Swap adjacent elements if they are in the wrong order 
swap(arr[j], arr[j + 1]);
swapped = true; 
} 
} 
// If no elements were swapped, the array is already sorted 
if (!swapped) 
break; 
}
```



##  3. Insertion Sorting

// Choose an element and place it in the correct place in left sorted sub-array
array  =  2, 3 , 1, 5, 4
- Check 0th index element is at correct position , yes it is  
- same goes for 3 
- but for 1 it is wrong position at sub-array it should be at first
- swap 3 , 1 and then swap 2, 1
- now 5 is correct but 4 is not so swap 4 with 5 and we are good to go

*Thing to note is that here we maintain order of elements i.e. if  first 4 element are sorted , then rest 4 are all at there relative order which was missing in previous 2*

// Time and Space Complexity
- TC : 
1. Best Case : n
2. Average Case : n^2
3. Worst Case : n^2
- SC:
O(1) in all cases

// Questions One may ask
1. Is Insertion sort stable ? 
- Yes , it is  stable i.e. it  maintain relative order.

2. Does it have minimum number of swap as compare to rest algo ? 
- No , it have too many swaps


// Code

```cpp

 vector<int> arr = {12, 11, 13, 5, 6};
    int n = arr.size();
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        
        // Move elements of arr[0...i-1] that are greater than key
        // to one position ahead of their current position
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j = j - 1;
        }
        arr[j + 1] = key;
    }

```

