# 🐚 Shellcode Injection Explained  

---

### 🚀 **1️⃣ What Is Shellcode?**

**Shellcode** is **machine-level code** designed to **spawn a shell** or **execute commands**.

---

### 🧠 **2️⃣ How Shellcode Works**

1️⃣ **Inject malicious instructions** into memory.  
2️⃣ **Overwrite EIP** to point to **shellcode address**.  
3️⃣ **Execute code** when the CPU **reaches the modified EIP**.  

---

### 💻 **3️⃣ Simple Shellcode (Python)**

```python
from pwn import asm, shellcraft

# Generate shellcode to open a calculator
shellcode = asm(shellcraft.linux.sh())
print(shellcode)

🧩 4️⃣ Interactive Task
1️⃣ Generate shellcode for Windows calculator.
2️⃣ Inject it into the vulnerable program.
3️⃣ Observe behavior using Immunity Debugger.

🔍 Key Insight:

Shellcode must avoid bad characters like \x00.
Use Mona's !mona shellcode command to generate safe shellcode.
