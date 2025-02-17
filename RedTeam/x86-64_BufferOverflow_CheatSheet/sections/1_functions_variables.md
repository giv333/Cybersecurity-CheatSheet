# 🧠 Functions, Arguments, Variables & Local Variables  

---

### 🚀 **1️⃣ What Are Functions?**

Functions are **instructions the CPU follows** to complete tasks.  
**Think of a function like a cooking recipe**:  
- **Arguments** → Ingredients  
- **Function Body** → Instructions  
- **Return Value** → Final Dish  

---

### 🛠️ **2️⃣ Code Example (C)**

```c
#include <stdio.h>

int add(int a, int b) {
    int result = a + b;  // Local variable
    return result;
}

int main() {
    int sum = add(4, 5);
    printf("Sum: %d\n", sum);
    return 0;
}

🧠 3️⃣ CPU's Step-by-Step Process
Push arguments 4 & 5 into registers (RDI & RSI).
Create space for the local variable result on the stack.
Perform addition: 4 + 5 = 9 → stored in RAX.
Return the value from RAX to main().
