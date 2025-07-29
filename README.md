# Square-Alphabet-Increasing-Pattern

This C++ program prints a square matrix of characters, starting from `'A'` and continuing through the ASCII sequence, filling `n x n` characters.

Let’s break it down:

### Code Explanation

```cpp
#include <bits/stdc++.h>
using namespace std;

int main() {
    int n;
    cin >> n;              // User input for size of the square
    char ch = 'A';         // Starting character

    for (int i = 0; i < n; i++) {            // Loop for each row
        for (int j = 0; j < n; j++) {        // Loop for each column
            cout << ch << " ";              // Print current character
            ch = ch + 1;                    // Move to the next character in ASCII
        }
        cout << endl;                       // Newline after each row
    }
}
```

### Example Output

For input `n = 3`, the output would be:

```
A B C 
D E F 
G H I 
```

### Potential Issue

If `n` is large, `ch` might go beyond `'Z'` and into other ASCII characters (like `[`, `\`, etc.), which may not be desirable.

### Optional Improvement (Wrap Around A–Z Only)

If you want to wrap the characters from `'A'` to `'Z'` only:

```cpp
ch = (ch == 'Z') ? 'A' : ch + 1;
```

Or use modulo:

```cpp
cout << char('A' + (i * n + j) % 26) << " ";
```

