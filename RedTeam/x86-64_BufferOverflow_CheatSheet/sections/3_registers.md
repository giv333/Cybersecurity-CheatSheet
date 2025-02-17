# 🧠 CPU Registers Explained  

---

### ⚙️ **1️⃣ What Are Registers?**

**Registers** are **super-fast memory cells** inside the CPU.  

| **Register** | **Purpose**                        |
|--------------|------------------------------------|
| **RAX**      | **Stores calculation results**.     |
| **RBX**      | **Holds temporary data**.           |
| **RDI**      | **Holds 1st function argument**.    |
| **RSI**      | **Holds 2nd function argument**.    |
| **RDX**      | **Holds 3rd function argument**.    |
| **RCX**      | **Holds 4th function argument**.    |
| **RSP**      | **Points to the top of the stack**. |
| **RBP**      | **Points to the stack frame base**. |

---

### 🧠 **2️⃣ Register Usage in a Function**

```c
int multiply(int x, int y) {
    return x * y;
}

int main() {
    int product = multiply(3, 2);
    return 0;
}
CPU Actions:

3 → RDI, 2 → RSI.
CPU calculates: 3 * 2 = 6 → stored in RAX.
The result 6 is returned to main().
