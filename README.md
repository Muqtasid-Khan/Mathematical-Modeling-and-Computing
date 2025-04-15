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
def newton_raphson(f, df, x0, tol=1e-7, max_iter=100):
    """
    Finds the root of a function using the Newton-Raphson method.

    Args:
        f (callable): The function for which to find the root.
        df (callable): The derivative of the function f.
        x0 (float): The initial guess for the root.
        tol (float, optional): The tolerance for convergence. Defaults to 1e-7.
        max_iter (int, optional): The maximum number of iterations. Defaults to 100.

    Returns:
        float or None: The approximate root if found, otherwise None.
    """
    xn = x0
    for n in range(max_iter):
        fxn = f(xn)
        if abs(fxn) < tol:
            print(f"Newton-Raphson: Found solution after {n} iterations.")
            return xn
        dfxn = df(xn)
        if dfxn == 0:
            print("Newton-Raphson: Zero derivative. No solution found.")
            return None
        xn = xn - fxn / dfxn
    print("Newton-Raphson: Exceeded maximum iterations.")
    return None

# Example usage for Newton-Raphson
f_nr = lambda x: x**3 - x - 2
df_nr = lambda x: 3*x**2 - 1
root_nr = newton_raphson(f_nr, df_nr, 1.5)
print(f"Newton-Raphson Root: {root_nr}")

print("\nRegular Falsi Method")
def regular_falsi(f, a, b, tol=1e-7, max_iter=100):
    """
    Finds the root of a function using the Regular Falsi method (False Position).

    Args:
        f (callable): The function for which to find the root.
        a (float): The lower bound of the initial interval.
        b (float): The upper bound of the initial interval.
        tol (float, optional): The tolerance for convergence. Defaults to 1e-7.
        max_iter (int, optional): The maximum number of iterations. Defaults to 100.

    Returns:
        float or None: The approximate root if found, otherwise None.
    """
    if f(a) * f(b) >= 0:
        print("Regular Falsi: Function must change signs on the interval [a, b].")
        return None

    for n in range(max_iter):
        c = b - f(b) * (b - a) / (f(b) - f(a))
        if abs(f(c)) < tol:
            print(f"Regular Falsi: Found solution after {n} iterations.")
            return c

