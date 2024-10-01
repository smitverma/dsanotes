---
{"dg-publish":true,"permalink":"/elementary/binary-bit-manipulation/"}
---

***
## How does C++ store `int`s in memory?
![Pasted image 20241001191313.png|600](/img/user/Attachments/Pasted%20image%2020241001191313.png)
- The number is stored in binary, with the left-ward remaining spaces filled with 0s. 

## Decimal to Binary

Mathematical concept :
![Screenshot 2024-10-01 155441.png|400](/img/user/Attachments/Screenshot%202024-10-01%20155441.png)

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

