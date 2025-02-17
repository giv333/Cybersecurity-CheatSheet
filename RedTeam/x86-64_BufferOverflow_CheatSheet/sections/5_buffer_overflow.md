# 💥 Buffer Overflow Basics  

---

### 🚨 **1️⃣ What Is a Buffer Overflow?**

A **buffer overflow** occurs when **more data** is written to a **memory buffer** than it can handle.

---

### 🧠 **2️⃣ How It Works**

- **Memory layout** → Fixed-size buffer is allocated.  
- **Overflow** → Input exceeds the buffer size.  
- **EIP control** → The **saved return address** is overwritten.

---

### 💻 **3️⃣ Exploit in Action**

```c
#include <stdio.h>
#include <string.h>

void vulnerable() {
    char buffer[16];
    printf("Input: ");
    gets(buffer);  // Unsafe: Allows overflow
    printf("You entered: %s\n", buffer);
}

int main() {
    vulnerable();
    return 0;
}

🔍 4️⃣ Step-by-Step Breakdown
1️⃣ Input is stored in the stack.
2️⃣ Input exceeds buffer size → Overwrites adjacent memory.
3️⃣ Return address is overwritten → Execution jumps to attacker-controlled code.

💡 Tip:

Use cyclic from Pwntools to find the offset.
EIP control is the main objective of a buffer overflow exploit.
