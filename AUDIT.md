# Code Audit — Python Lecture 4

## 1. Project Overview
This audit reviews the Python programs covered in Lecture 4, including basic output, factorial calculation, Fibonacci series, dictionaries, and conceptual questions comparing C structures with Python dictionaries.

## 2. Code Review

### A. Basic Python Program
**Code:**
```python
print(5)
```
**Status:** ✅ Passed

**Observation:** The program correctly prints the number `5`.

### B. Factorial Program
**Status:** ⚠️ Needs Correction

**Issue:** The loop uses `range(1, 1+n+1)`, which calculates the factorial of `n + 1` instead of `n`.

**Correction:**
```python
n = 5
fact = 1

for i in range(1, n + 1):
    fact *= i

print(fact)
```

**Expected Output:**
```text
120
```

### C. Fibonacci Series
**Status:** ✅ Logic Passed

**Observation:** The program correctly generates the Fibonacci sequence.

**Improvement:** Rename the variable `next` to `next_num` to avoid shadowing Python's built-in `next()` function.

**Improved Code:**
```python
n = 10
a = 0
b = 1

for i in range(n):
    next_num = a + b
    a = b
    b = next_num
    print(a, end=" ")
```

### D. Dictionary Program
**Status:** ✅ Passed

**Observation:** The dictionary correctly stores student information and retrieves values using keys.

**Potential Risk:** Accessing a nonexistent key using square brackets raises a `KeyError`.

**Improvement:** Use the `get()` method when a key might be missing.

```python
print(s1.get("name", "Unknown"))
```

### E. Conceptual Questions
**Status:** ✅ Conceptually Correct

- **Q1:** Correctly explains that Python dictionaries can accept new keys dynamically.
- **Q2:** Correctly explains that Python values have types without requiring explicit type declarations for dictionary entries.

**Improvement:** Python's flexibility does not automatically enforce a fixed set of keys or value types.

## 3. Summary of Findings

| Component | Status | Finding |
|---|---|---|
| Basic Program | Passed | No issues found |
| Factorial | Needs Correction | Incorrect loop range |
| Fibonacci | Passed | Variable naming improvement recommended |
| Dictionary | Passed | Missing-key handling can improve |
| Conceptual Questions | Passed | Minor clarification recommended |

## 4. Recommendations
1. Correct the factorial loop range.
2. Avoid using built-in function names as variable names.
3. Handle missing dictionary keys safely.
4. Test programs with different inputs.
5. Follow consistent naming and indentation conventions.

## 5. Conclusion
The programs demonstrate fundamental Python concepts effectively. The main functional issue is the factorial loop range. The remaining recommendations focus on code readability, reliability, and good programming practices.

**Audit Result:** Passed with minor corrections required.

**Author:** Prerana  
**Language:** Python 3
