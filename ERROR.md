# **Numerical Analysis**

Numerical Analysis is a branch of mathematics that develops, analyzes, and applies algorithms for solving problems involving numerical computations. 

In practical computation (whether on paper or using a computer), errors often occur. Understanding **errors**, their **sources**, **propagation**, and how they can be **estimated** is extremely important.

---

## **1. Errors in Numerical Calculations**
Errors in numerical calculations are **the differences between the true value** and **the approximate (calculated) value**.

### Types of Errors:
- **Absolute Error**
  ```
  Absolute Error = |True Value - Approximate Value|
  ```
  It measures the actual difference between the true and computed value.

- **Relative Error**  
  ```
  Relative Error = Absolute Error/True Value
  ```
  It shows how large the error is relative to the true value — important when the value itself is very large or very small.

- **Percentage Error**
  ```
  Percentage Error = Relative Error X 100\%
  ```
  It expresses the error as a percentage.

---

### Sources of Errors:
Errors can come from several causes:
- **Round-off Errors**:  
  Due to the limitation of storing numbers in finite memory (example: storing pi as 3.1416 instead of ( pi = 3.1415926535...)).
  
- **Truncation Errors**:  
  Arise when an infinite process (like a Taylor series or an iterative method) is cut off after a finite number of steps.

- **Input/Measurement Errors**:  
  Errors in the data provided for the calculation.

- **Algorithmic Errors**:  
  Some numerical methods are approximate by nature. Even if no rounding occurs, the method itself may introduce a small error.

---

## **2. Error Propagation and General Error Formula**

When we perform a **series of operations** (like addition, subtraction, multiplication, etc.), the small errors in each operation can **propagate** (i.e., accumulate or amplify).

### **Error Propagation Rules**:
- **Addition/Subtraction**:  
  Absolute errors add up.  
  Example:  
  If  
  \[
  x = x_{true}\pm \Delta x, \quad y = y_{\text{true}} \pm \Delta y
  \]
  Then  
  \[
  (x+y) = (x_{\text{true}} + y_{\text{true}}) \pm (\Delta x + \Delta y)
  \]
  
- **Multiplication/Division**:  
  Relative errors add up approximately.  
  Example:  
  \[
  z = x \times y
  \]
  Then the relative error in \( z \) is approximately:  
  \[
  \frac{\Delta z}{z} \approx \frac{\Delta x}{x} + \frac{\Delta y}{y}
  \]

- **General Error Formula**:  
  Suppose a function \( f(x_1, x_2, ..., x_n) \) depends on several variables each having small errors, then the total error approximately is:
  \[
  \Delta f \approx \sum_{i=1}^{n} \left| \frac{\partial f}{\partial x_i} \right| \Delta x_i
  \]
  where \( \Delta x_i \) is the error in \( x_i \).

This formula uses **partial derivatives** to estimate how much each variable's error affects the final result.

---

## **3. Taylor Series and Remainders**

Taylor series helps **approximate functions** using polynomials.

### **Taylor Series Expansion:**
For a function \( f(x) \) that is infinitely differentiable at a point \( a \),  
the Taylor series about \( a \) is:
\[
f(x) = f(a) + f'(a)(x-a) + \frac{f''(a)}{2!}(x-a)^2 + \frac{f'''(a)}{3!}(x-a)^3 + \cdots
\]

In numerical analysis, we **truncate** (cut off) the Taylor series after a few terms to get an **approximation** of \( f(x) \).

---

### **Remainders (Error Term)**

If we stop after \( n \) terms, the error (called the **remainder** \( R_n(x) \)) is:
\[
R_n(x) = \frac{f^{(n+1)}(\xi)}{(n+1)!} (x-a)^{n+1}
\]
for some \( \xi \) between \( a \) and \( x \).

This shows:
- How accurate the approximation is.
- How the error depends on the next derivative \( f^{(n+1)}(\xi) \) and the distance \( (x-a) \).

In practical problems, we use Taylor expansions to approximate functions like \( \sin(x) \), \( e^x \), etc., and estimate how large the approximation error is.

---

# **Summary Table**

| Topic | Key Ideas |
|:---|:---|
| Errors | Difference between true and approximate value |
| Types | Absolute, Relative, Percentage Errors |
| Sources | Round-off, Truncation, Input, Algorithmic Errors |
| Error Propagation | How errors accumulate during calculations |
| General Error Formula | Using derivatives to estimate total error |
| Taylor Series | Polynomial approximation of functions |
| Remainders | Estimate of the error when truncating Taylor series |

---
