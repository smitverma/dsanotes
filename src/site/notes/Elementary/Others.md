---
{"dg-publish":true,"permalink":"/elementary/others/"}
---


- When you pass a C-style array to a function, it decays into a pointer, so you cannot use the parameter for stuff like :
	- foreach loop
	- sizeof(arr)
	
	The solution is to use a C++ std::array / std::vector, or to calculate size locally and send it as argument (and then use index-based for loop).

 - 