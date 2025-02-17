## 🧠 **Task 2: Memory & Stack**

**File:** `task2_memory_and_stack.md`

```markdown
# 🏗️ Task 2: Memory & Stack  

---

## 🎯 **Objective:**  
Understand how **memory is structured** and how **the stack grows** when functions are called.

---

### 🛠️ **Task Instructions**

1. **Run the provided Python code** to visualize memory allocation.  
2. **Identify which section of memory is used** for function calls.  
3. **Draw a stack diagram** for the function `calculate()`.

---

### 🧑‍💻 **Sample Code (Python):**

```python
def calculate(a, b):
    result = a + b
    return result

x = calculate(5, 6)
print(x)
🔍 Questions:
Where is result stored?
What happens to the stack pointer after the function ends?
Which registers store the arguments?
💡 Hints:
The stack grows downward as more functions are called.
The RBP register marks the start of the stack frame.

✅ Solutions (Hidden)
result is stored in the stack memory.
RSP moves back up when the function ends.
RDI stores 5, RSI stores 6.
