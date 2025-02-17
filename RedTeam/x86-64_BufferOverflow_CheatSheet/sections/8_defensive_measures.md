# 🛡️ Defensive Measures Against Buffer Overflows  

---

### 🚀 **1️⃣ Why Do We Need Defensive Measures?**

**Buffer overflows** are a **common attack vector**.  

---

### 🧠 **2️⃣ Protection Techniques**

- **Canaries** → Special **values placed before EIP**.  
- **ASLR** → Randomizes **memory addresses**.  
- **DEP** → Prevents **execution of injected code**.  

---

### 🔍 **3️⃣ Defensive Tasks**

1️⃣ **Identify stack canaries** in a binary.  
2️⃣ **Enable ASLR** for a test program.  
3️⃣ **Run the binary** with and without ASLR.  

---

### 💡 **4️⃣ Tooling Tips**

- **`checksec`** → Check binary protections.  
- **`gdb-peda`** → Inspect runtime behavior.  

---

🔍 **Key Insight:**  
- **Modern systems** rely on **multiple layers of protection**.  


