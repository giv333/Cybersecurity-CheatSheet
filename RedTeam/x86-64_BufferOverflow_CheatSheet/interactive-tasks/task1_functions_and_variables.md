# 🧠 Task 1: Functions, Arguments, and Variables  

---

## 🎯 **Objective:**  
Understand how functions, arguments, and variables work at a CPU level.

---

### 🛠️ **Task Instructions**

1. **Create a simple C program** that adds two numbers.  
2. **Identify the arguments, variables, and return value.**  
3. **Explain how the CPU processes the function call.**

---

### 🧑‍💻 **Sample Code:**

```c
#include <stdio.h>

int add(int x, int y) {
    int result = x + y;
    return result;
}

int main() {
    int sum = add(7, 3);
    printf("Sum: %d\n", sum);
    return 0;
}
🔍 Questions:
What are the arguments passed to the add() function?
Which register stores the return value?
Identify the local variable.
💡 Hints:
Arguments are passed via RDI, RSI, RDX, RCX, R8, and R9.
The return value is stored in the RAX register.

✅ Solutions (Hidden)
Arguments: 7 (RDI), 3 (RSI).
Return Value: RAX holds the result 10.
Local Variable: result.
