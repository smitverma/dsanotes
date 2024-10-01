---
{"dg-publish":true,"permalink":"/elementary/array-vector/"}
---

## Array
- Fixed contiguous block of memory
- Holds elements of same data type
- Declaration :
	- `int arr[5];`
- Declare and initialize together :
	- `std::string strArr[] = {"Hello", "Namaste", "Hola"};`
	- `float floatArr[] = {1.2f, 2.3f, 4.9f};`
- Size of array :
	- `int n = sizeof(arr) / sizeof(arr[0]);`
- Accessing elements :
	- Access first element : `arr[0];`
	- Access last element : `arr[ ( sizeof(arr) / sizeof(arr[0]) ) - 1 ];`

##### Multidimensional array 
- Declaration : 
	- `int mat[2][3] = {{1, 2, 3}, {4, 5, 6}};`
- Stored in **row-major order** : such as | 1 | 2 | 3 | 4 | 5 | 6 | (in memory)
## Common operations on array

#### ↣ Reverse an array 
<div style="position: relative; display: inline-block; cursor: pointer;">
  <div style="padding: 10px; background-color: #007bff; color: white; border-radius: 5px;">
    Comp.
  </div>
  <div style="visibility: hidden; position: absolute; background-color: #f9f9f9; border: 1px solid #ccc; padding: 10px; border-radius: 5px; top: 100%; left: 50%; transform: translateX(-50%); white-space: nowrap; z-index: 1;">
    Time complexity : O(n)
	Space complexity : O(1)
  </div>
  <style>
    div:hover div:nth-child(2) {
      visibility: visible;
    }
  </style>
</div>

> Funda : Using two pointers to swap elements from the start and end of the array until the pointers meet in the middle.
```cpp
void reverseArray(int arr[], int size) {
	int left = 0; // Start pointer
	int right = size - 1; // End pointer

	while (left < right) {
		swap(arr[left], arr[right]); // Swap elements
		left++; // Move the start pointer to the right
		right--; // Move the end pointer to the left
	}
}
```



#### ↣ Find all subsets of array

\
