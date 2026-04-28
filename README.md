# Practical Lab 3


 Program 1 : Quick Sort

 Aim
To develop a program for Quick Sort by dividing the array with a pivot element.


 Variables
- arr[] : List of numbers to be sorted  
- low : Initial index of current section  
- high : Final index of current section  
- pivot : Reference element for splitting  
- i, j : Position counters used in partitioning  
- loc : Correct position of pivot  
- begin, finish, timeTaken : For performance calculation  

Steps

QuickSort(arr, low, high)

if low < high

    loc = Partition(arr, low, high)

    QuickSort(arr, low, loc - 1)

    QuickSort(arr, loc + 1, high)


Partition(arr, low, high)

pivot = arr[low]
i = low + 1
j = high

while i <= j

    while i <= high and arr[i] <= pivot
        i = i + 1

    while arr[j] > pivot
        j = j - 1

    if i < j
        exchange arr[i], arr[j]

exchange arr[low], arr[j]

return j

 Complexity;
Best Case : O(n log n)
Average Case : O(n log n)
Worst Case : O(n²)

 Program 2 : Merge Sort
 Aim-To implement Merge Sort using non-recursive bottom-up merging process.

Variables
arr[] : Original array elements
n : Total size of array
left : Starting point of first part
mid : Boundary between two parts
right : Ending point of second part
i, j, k : Counters for merge operation
temp[] : Helper array for storing merged values
block : Current group size
begin, finish, timeTaken : For execution timing

Steps
MergeSort(arr, n)
Create temp array of size n
for block = 1 while block < n
    for left = 0 to n - block step 2 * block
        mid = left + block - 1
        right = minimum(left + 2 * block - 1, n - 1)
        Merge(arr, left, mid, right, temp)


Merge(arr, left, mid, right, temp)

i = left
j = mid + 1
k = left

while i <= mid and j <= right

    if arr[i] <= arr[j]
        temp[k] = arr[i]
        i++, k++

    else
        temp[k] = arr[j]
        j++, k++

while i <= mid
    temp[k++] = arr[i++]

while j <= right
    temp[k++] = arr[j++]

Copy temp values back into arr

 Complexity
Best Case : O(n log n)
Average Case : O(n log n)
Worst Case : O(n log n)
