# 📊 Mathematical Modeling and Computing – Personal Fork

> 🚀 This is my enhanced and modified version of a classmate's project. It includes additional mathematical methods, comments, and improved explanations.  
> Originally forked from: (https://github.com/Muqtasid-Khan/Mathematical-Modeling-and-Computing)

---

## 📌 What's New in My Version

- ✅ Cleaned and formatted all code
- ✅ Added comments and explanations
- ✅ Improved function structure for better readability
- ✅ Included real-world examples and test cases

---

## 🧠 Numerical Methods Included

### Newton-Raphson Method

```python
def newton_raphson(f, df, x0, tol=1e-7, max_iter=100):
    xn = x0
    for n in range(max_iter):
        fxn = f(xn)
        if abs(fxn) < tol:
            print(f"Found solution after {n} iterations.")
            return xn
        dfxn = df(xn)
        if dfxn == 0:
            print("Zero derivative. No solution found.")
            return None
        xn = xn - fxn / dfxn
    print("Exceeded maximum iterations.")
    return None

# Example usage
f = lambda x: x**3 - x - 2
df = lambda x: 3*x**2 - 1
root = newton_raphson(f, df, 1.5)
print(f"Root: {root}")
Regular Falsi Method
def regular_falsi(f, a, b, tol=1e-7, max_iter=100):
    if f(a) * f(b) >= 0:
        print("Function must change signs on interval.")
        return None

    for n in range(max_iter):
        c = b - f(b) * (b - a) / (f(b) - f(a))
        if abs(f(c)) < tol:
            print(f"Found solution after {n} iterations.")
            return c
        if f(c) * f(a) < 0:
            b = c
        else:
            a = c
    print("Exceeded maximum iterations.")
    return None

# Example usage
f = lambda x: x**3 - x - 2
root = regular_falsi(f, 1, 2)
print(f"Root: {root}")
👩‍💻 Maintainer
Sania Irshad
🤝 Contributions
Feel free to:

Add more methods

Improve code

Suggest real-world models

