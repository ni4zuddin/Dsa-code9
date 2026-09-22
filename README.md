#include <stdio.h>
int* binarySearch(int *start, int *end, int target) {
    while (start <= end) {
        int *mid = start + (end - start) / 2;
        if (*mid == target) {
            return mid; 
        }
        if (*mid > target) {
            end = mid - 1;
        } 
        else {
            start = mid + 1;
        }
    }
    return -1;
}
int main() {
    // Binary search requires a sorted array
    int arr[] = {2, 5, 8, 12, 16, 23, 38, 56, 72, 91};
    int n = sizeof(arr) / sizeof(arr[0]);
    int target = 23;
    int *result = binarySearch(arr, arr + (n - 1), target);
    if (result != -1) {
        printf("Element %d found at index: %ld\n", target, result - arr);
    } else {
        printf("Element %d not found in the array.\n", target);
    }
    return 0;
}
