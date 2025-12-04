# 🔍 Comprehensive Python Code Review Prompt

## Python Code Review & Analysis Request

Please perform a comprehensive code review of the following Python file(s). Analyze the code across ALL categories below and provide a detailed report.

---

## 📋 Analysis Categories

### 1. Syntax & Style Issues
- PEP 8 compliance (naming conventions, indentation, line length)
- Proper use of Python idioms
- Code formatting consistency
- Import organization
- Docstring presence and quality
- Type hints usage and correctness

### 2. Logic & Correctness
- Off-by-one errors
- Incorrect boolean logic
- Edge case handling (empty inputs, None values, boundary conditions)
- Unreachable code / dead code
- Incorrect operator precedence
- Missing return statements
- Improper exception handling flow
- Variable shadowing issues
- Mutable default arguments

### 3. Security Vulnerabilities
- SQL injection risks
- Command injection (subprocess, os.system)
- Path traversal vulnerabilities
- Insecure deserialization (pickle, yaml.load)
- Hardcoded secrets/credentials
- Insufficient input validation/sanitization
- Insecure random number generation (for crypto)
- XML External Entity (XXE) attacks
- Server-Side Request Forgery (SSRF) risks
- Insecure file permissions
- Use of eval(), exec(), compile() with user input
- Prototype pollution / mass assignment

### 4. Performance Issues
- Inefficient algorithms (O(n²) when O(n) possible)
- Unnecessary nested loops
- Repeated expensive operations in loops
- Missing caching opportunities
- Inefficient string concatenation
- Loading entire files into memory unnecessarily
- N+1 query problems
- Inefficient data structure choices
- Redundant computations
- Missing generator usage for large datasets

### 5. Concurrency & Multi-threading
- Race conditions
- Deadlock potential
- Missing locks/synchronization
- Thread-unsafe operations on shared state
- Improper use of global variables in threads
- GIL-related issues
- Missing thread pool cleanup
- Incorrect async/await usage
- Blocking calls in async code
- Resource leaks in concurrent code

### 6. Memory Management
- Memory leaks (circular references, unclosed resources)
- Unbounded data structures
- Missing context managers (with statements)
- Large object retention
- Inefficient copying of large objects

### 7. Error Handling
- Bare except clauses
- Swallowing exceptions silently
- Too broad exception handling
- Missing finally blocks for cleanup
- Incorrect exception chaining
- Custom exceptions without proper inheritance

### 8. Maintainability & Code Quality
- Code duplication (DRY violations)
- Functions/methods that are too long
- High cyclomatic complexity
- Poor separation of concerns
- Magic numbers/strings without constants
- Unclear variable/function names
- Missing or outdated comments
- Tightly coupled components

### 9. Testing & Reliability
- Untestable code patterns
- Missing input validation
- Assertions that could be bypassed
- Non-deterministic behavior

### 10. Python-Specific Anti-patterns
- Using `type()` instead of `isinstance()`
- Using `==` for None/True/False instead of `is`
- Not using enumerate() for index loops
- Manual file handling instead of context managers
- Using `.keys()` unnecessarily in dict iteration
- Catching mutable default argument bugs
- String formatting with % instead of f-strings
- Not using pathlib for file paths

---

## 📊 Output Format

For each issue found, provide:

```
### [SEVERITY: CRITICAL/HIGH/MEDIUM/LOW] Issue Title

**Category:** [Category Name]
**Location:** Line X-Y (or function/class name)
**Issue:** Clear description of the problem
**Impact:** What could go wrong

**Current Code:**
```python
# problematic code snippet
```

**Suggested Fix:**
```python
# corrected code snippet
```

**Explanation:** Why this fix addresses the issue
```

---

## 📝 Summary Section

After analysis, provide:

1. **Total Issues Found** by severity
2. **Top 3 Critical Issues** to address immediately
3. **Overall Code Health Score** (1-10)
4. **Recommended Priority Order** for fixes

---

## ✅ Confirmation & Fix Mode

After reviewing the analysis:

- Reply **"FIX ALL"** to apply all suggested fixes
- Reply **"FIX [issue numbers]"** to fix specific issues (e.g., "FIX 1,3,5")
- Reply **"EXPLAIN [issue number]"** for deeper explanation
- Reply **"SKIP [issue numbers]"** to exclude from fixes

I will then provide the complete corrected code with all approved fixes applied.

---

## 🎯 Code to Analyze

```python
# [PASTE YOUR PYTHON CODE HERE OR PROVIDE FILE PATH]
```

---

## 🔧 Additional Context (Optional)

| Field | Value |
|-------|-------|
| **Python Version** | (e.g., 3.9, 3.11) |
| **Framework/Libraries** | (e.g., Django, FastAPI, asyncio) |
| **Deployment Environment** | (e.g., AWS Lambda, Docker, bare metal) |
| **Specific Concerns** | (any particular areas to focus on) |

---

## 💡 Usage Tips

1. **For single files:** Paste the code directly after "Code to Analyze"
2. **For multiple files:** List each file with its path and contents
3. **Add context:** The more context you provide about the environment and purpose, the better the analysis
4. **Iterative review:** After fixes, you can ask for a re-review to catch any new issues

