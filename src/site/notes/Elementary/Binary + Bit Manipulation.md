---
{"dg-publish":true,"permalink":"/elementary/binary-bit-manipulation/"}
---

***
## How does C++ store `int`s in memory?
![Pasted image 20241001191313.png|600](/img/user/Attachments/Pasted%20image%2020241001191313.png)
- The number is stored in binary, with the left-ward remaining spaces filled with 0s
- Same funda for float, long long (64 bits), etc.
***
## Decimal to Binary

Mathematical concept :
![Screenshot 2024-10-01 155441.png|500](/img/user/Attachments/Screenshot%202024-10-01%20155441.png)

Code :
```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

vector<int> decToBinary(int n) {
    // Vector for storing binary number
    std::vector<int> binaryNum;
    
    while (n > 0) {
        // Storing remainder in binary array
        binaryNum.push_back(n % 2);
        n = n / 2;
    }

    // Reversing the binary array
    std::reverse(binaryNum.begin(), binaryNum.end());
    
    return binaryNum;
}
```

***
## Binary to Decimal

Mathematical concept :
![Pasted image 20241001182514.png|500](/img/user/Attachments/Pasted%20image%2020241001182514.png)

Code :
```cpp
int binToDecimal(int n) {
    // Vector for storing decimal number 
    int decNum = 0;
    int b = 1;
    int d;
    
    while (n > 0) {
        // Storing remainder in binary array
        d = n % 10;
        decNum = decNum + (d*b);
        n = n / 10;
        b = b * 2;
    }
    
    return decNum;
}
```

***
## 1s and 2s complement
> Funda : Convert the number to binary, and flip the bits.

Mathematical concept :
![m.png|400](/img/user/Attachments/m.png)

***
## AND, OR, NOT, SHIFT

Truth Tables :
![Pasted image 20241003093144.png|600](/img/user/Attachments/Pasted%20image%2020241003093144.png)
### C++ examples :
- `&` operator : `13 & 7 = 5`
- `|` operator : `13 | 7 = 15`
- `!` operator : !13 
- `<<` operator : 
  Formula : `n << k = n * 2ᵏ`
  Example : `13 << 2 = 52 = 13*2*2 = 13*(2²)`
- `>>` operator : 
  Formula : `n >> k = n / 2ᵏ`
  Example : `13 >> 2 = 3 = 13/2/2 = 13/(2²)`
***
## XOR
- Formula : 
	- If bits are same, result is 0
	- If bits are different, result is 1
***
## Storing negative numbers
- **Signed** numbers are used to store +ve and -ve numbers
- They mark a number as positive or negative using the MSB (left-most bit) as :
	- 0 for +ve
	- 1 for -ve
- So to get 1 at the MSB, computers just store the negative numbers in their 2s complement
- Therefore, range of int in a n-bit system is `-2ⁿ⁻¹ (INT_MIN)` to `2ⁿ⁻¹ - 1 (INT_MAX)`
#### Example :
Storing `-13` in an `8-bit` system :  
- Binary value of `13` : `00001101`
- `1s` complement : `11110010`
- `2s` complement : `11110011`
- So the computer stores `11110011` in its memory
- Here, the 2s comp. can be used directly in mathematical calculation
- When needed, the computer reverses the process, and displays `-13` to the user
***