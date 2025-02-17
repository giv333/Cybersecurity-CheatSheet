 **Task 3: Registers in Action**

**File:** `task3_registers.md`

```markdown
# ⚙️ Task 3: CPU Registers in Action  

---

## 🎯 **Objective:**  
Master the roles of **general-purpose registers** in **x86-64 architecture**.

---

### 🛠️ **Task Instructions**

1. **Analyze the code provided** and predict the **register values**.  
2. **Draw a table** showing **register assignments**.  
3. **Run the code** and **compare results**.

---

### 🧑‍💻 **Sample Code (C):**

```c
#include <stdio.h>

int multiply(int x, int y) {
    int result = x * y;
    return result;
}

int main() {
    int product = multiply(4, 2);
    printf("Product: %d\n", product);
    return 0;
}

🔍 Questions:
Which registers store the arguments?
Where is the result stored?
Which registers are callee-saved?
💡 Hints:
RDI and RSI hold the first two arguments.
The RAX register stores return values.

✅ Solutions (Hidden)
Arguments: RDI (4), RSI (2).
Result: Stored in RAX (value: 8).
Callee-saved registers: RBX, RBP, R12-R15.

