# Exception Handling in Python

In Python, **try, except, else, and finally** are used for **exception handling** (handling errors during program execution).

---

## 1. try

The `try` block contains code that may cause an error.

```python
try:
    num = 10 / 0
```

---

## 2. except

The `except` block executes if an error occurs in the `try` block.

```python
try:
    num = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
```

### Output

```text
Cannot divide by zero.
```

---

## 3. else

The `else` block executes only if no exception occurs in the `try` block.

```python
try:
    num = 10 / 2
except ZeroDivisionError:
    print("Cannot divide by zero.")
else:
    print("Result:", num)
```

### Output

```text
Result: 5.0
```

---

## 4. finally

The `finally` block executes whether an exception occurs or not. It is commonly used for cleanup tasks such as closing files or database connections.

```python
try:
    num = 10 / 0
except ZeroDivisionError:
    print("Cannot divide by zero.")
finally:
    print("Program execution completed.")
```

### Output

```text
Cannot divide by zero.
Program execution completed.
```

---

# Complete Example

```python
try:
    num = int(input("Enter a number: "))
    result = 100 / num

except ZeroDivisionError:
    print("You cannot divide by zero.")

except ValueError:
    print("Please enter a valid number.")

else:
    print("Result =", result)

finally:
    print("Thank you for using the program.")
```

---

# Summary

| Keyword | Purpose |
|----------|----------|
| `try` | Contains code that may generate an exception |
| `except` | Handles the exception if it occurs |
| `else` | Runs when no exception occurs |
| `finally` | Runs regardless of whether an exception occurs or not |

---

# Flow

```text
try → exception? → except
     ↓ no exception
     else
     ↓
   finally
```