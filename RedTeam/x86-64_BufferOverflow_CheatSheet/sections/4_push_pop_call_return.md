# 🔄 Push, Pop, Call, and Return Instructions  

---

### 🚀 **1️⃣ What Do These Instructions Do?**

- **`push`** → **Adds data** onto the **stack**.  
- **`pop`** → **Removes the top data** from the **stack**.  
- **`call`** → **Calls a function** and **pushes the return address**.  
- **`ret`** → **Pops the return address** and **jumps back**.  

---

### 🧠 **2️⃣ CPU Instructions in Action**

```c
#include <stdio.h>

void greet() {
    printf("Hello, Red Teamer!\n");
}

int main() {
    greet();
    return 0;
}
🧩 3️⃣ Step-by-Step Execution
1️⃣ call greet → The return address is pushed onto the stack.
2️⃣ Inside greet(): The CPU executes printf().
3️⃣ ret → The return address is popped, and execution returns to main().

💡 Analogy:
Imagine a bookmark when you leave a book: call adds a bookmark, and ret removes it.
