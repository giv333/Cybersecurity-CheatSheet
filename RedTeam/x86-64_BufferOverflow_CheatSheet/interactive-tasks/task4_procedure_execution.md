### 🧠 **Task 4: Procedure Execution**

**File:** `task4_procedure_execution.md`

```markdown
# 🔍 Task 4: Procedure Execution  

---

## 🎯 **Objective:**  
Understand how **the CPU executes functions** and manages the stack.

---

### 🛠️ **Task Instructions**

1. **Trace the execution of the code** provided.  
2. **Predict stack pointer (RSP) changes**.  
3. **Draw the stack** before and after the function runs.

---

### 🧑‍💻 **Sample Code (Python):**

```python
def execute_procedure():
    a = 3
    b = 7
    result = a * b
    return result

x = execute_procedure()
print(x)


🔍 Questions:
Which variables are stored on the stack?
What happens to the stack pointer (RSP)?
Which register stores the return value?
💡 Hints:
The stack frame is created when the function is called.
Local variables are stored in the stack.

✅ Solutions (Hidden)
Variables: a, b, result are in the stack.
RSP moves downward during function execution.
RAX stores the return value (21).

