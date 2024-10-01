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
##### Find all subsets of array


\
