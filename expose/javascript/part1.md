### 1. What is printed by line 9?

Line 9 prints: values added: 20
Explanation: The `if (add)` condition is true because `add` is passed as `true`. So, `result` is computed as `10 + 10 = 20` and logged inside the if block.

---

### 2. What is printed by line 13?

The code returns an **error** at line 13: ReferenceError: result is not defined
Explanation: The `result` variable is declared using `var` inside the `if` block, so it is function-scoped. However, if the code execution reaches line 13, it might still access `result`, but **the main issue here is if `add` is false**, the `else return;` statement prevents `result` from being declared or assigned. But when `add` is true (as in this case), line 13 works **only because `result` is in the same function scope due to `var`**, even though it’s declared in the `if` block. This is a confusing and unsafe behavior.

So, **no error occurs in this specific call**, and line 13 will print: final result: 20
But this could fail in other cases, e.g., when `add` is `false`.

---

### 3. Why should you not use `var`?

You should avoid using `var` because:
- `var` is **function-scoped**, not block-scoped, which can lead to unexpected behavior when variables "leak" out of blocks like `if`, `for`, or `while`.
- It allows **variable hoisting**, which can lead to bugs if you reference a variable before it's assigned.
- `let` and `const` are block-scoped and make your code **easier to reason about** and less error-prone.

### 4. What is printed by line 9?

**Output:** values added: 20

### 5. What is printed by line 13?

**Output:** ReferenceError: result is not defined

**Explanation:**  
The variable `result` is declared using `let` inside the `if` block. Since `let` is block-scoped, `result` does not exist outside the `if` block.  
Line 13 attempts to access `result` outside its scope, which causes a `ReferenceError`.

### 🔹 Question 6: What is printed by line 9?

**Nothing is printed.**  
The code throws a **TypeError** on line 7 before it reaches line 9.

#### ❌ Error Explanation:
- On line 6, `result` is declared with `const`, which means it cannot be reassigned.
- On line 7, the code tries to reassign `result` with `result = num1 + num2;`, which causes the following error: TypeError: Assignment to constant variable.
---

### 🔹 Question 7: What is printed by line 13?

**Nothing is printed.**  
Due to the error on line 7, the function halts execution, and **line 13 is never reached**.

---

