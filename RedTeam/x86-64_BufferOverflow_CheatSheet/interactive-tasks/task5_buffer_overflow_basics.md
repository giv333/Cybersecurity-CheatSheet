### 🧠 **Task 5: Buffer Overflow Basics**

**File:** `task5_buffer_overflow_basics.md`

```markdown
# 💥 Task 5: Buffer Overflow Basics  

---

## 🎯 **Objective:**  
Understand **how buffer overflows occur** and **how attackers exploit them**.

---

### 🛠️ **Task Instructions**

1. **Compile the vulnerable C program** below.  
2. **Enter different inputs** to **observe buffer behavior**.  
3. **Explain how an overflow occurs**.

---

### 🧑‍💻 **Vulnerable Program (C)**

```c
#include <stdio.h>
#include <string.h>

void vulnerable() {
    char buffer[16];
    printf("Enter some input: ");
    gets(buffer); // Vulnerable to buffer overflow!
    printf("You entered: %s\n", buffer);
}

int main() {
    vulnerable();
    return 0;
}

🔍 Questions:
What happens if you input more than 16 characters?
What is overwritten during overflow?
How can this be exploited?
💡 Hints:
The return address gets overwritten during an overflow.
EIP points to the next instruction after the function call.

✅ Solutions (Hidden)
The stack memory after buffer[16] is corrupted.
The saved EIP is overwritten, altering execution flow.
Attackers exploit this by injecting malicious shellcode.
