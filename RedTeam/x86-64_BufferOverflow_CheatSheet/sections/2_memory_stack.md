# 🏗️ Memory, Stack, and Stack Frames  

---

### 🛠️ **1️⃣ What Is Memory?**

**Memory is like a notebook** the CPU uses to **track tasks**.  

- **Stack** → Temporary notes (fast, grows downward).  
- **Heap** → Long-term storage (grows upward).  
- **Data Segment** → Permanent notes (global variables).  
- **Text Segment** → Program instructions.  

---

### 🧠 **2️⃣ How the Stack Works**

When a function is called:

1. **The CPU pushes arguments** to the **stack**.  
2. **It reserves space for local variables**.  
3. **It tracks the return address** (to **return** after finishing).  

🖼️ **Stack Layout:**

+-------------------+ <- RSP (Top of stack) | Local Variables | | Saved Registers | | Return Address | | Arguments | +-------------------+ <- RBP (Stack frame start)

---

💡 **The stack helps the CPU keep track of multiple tasks efficiently.**
