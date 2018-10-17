---
tags:
  - data-structures-and-algo
---

# Insertion sort
void insertionSort(int* array, int lenght) {
    for (int i = 1; < length; i++) {
        for (int idx = i; idx > 0 && array[idx] < array [idx - 1]; idx--) {
            swap(array[idx], array[idx - 1]);
        }
    }
}

- time complex: O(n^2)
- space complex: O(1)
- online: 
