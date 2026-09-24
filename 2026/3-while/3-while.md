---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
# <p id = "small-caps">3. &nbsp; While $\ldots$</p>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Sep. 24, 2026

---
# Review
<br>

<font color = red>

### If Statement
### Switch Statement

<br>

### Logical Expressions
</font>
<br>

---
# Overview
<br>

<font color = red>

### While (Do-While) Statement
<br>

### `break` Statement
</font>

---

while syntax

---

loop invariant

---
![w:700](figs/lets-code.jpeg)

## <mark>euclid.cpp &ensp; fib.cpp &ensp; digits.cpp &ensp; palindrome.cpp &ensp; binary-search.cpp</mark>

---

# Greatest Common Divisor

![w:350](figs/euclid.jpeg)
$\text{gcd}(a, b) = \text{gcd}(b, a \;\%\; b)$

---

loop invariant for euclid

---

# Fibonacci Sequence
<br>

$F_{0} = 0$

$F_{1} = 1$

$F_{n} = F_{n-1} + F_{n-2} \quad (n > 1)$

---

loop invariant for fib

---
# Number of Digits

![w:650](figs/digits.jpg)

---
# Palindrome

![w:900](figs/palindrome.png)

---
# Binary Search

![w:900](figs/binary-search-mario.png)

---
# Array Initializer
<br>

* <code><font color = yellow size = 8>int numbers[NUM] = {1};</font></code>
<br>

* <code><font color = yellow size = 8>int numbers[] = {0, 1, 2};</font></code>
<br>

* <code><font color = yellow size = 8>int numbers[NUM] = {[1] = 1};</font></code>

---
# Array Initializer (DON'T)
<br>

<code><font color = yellow size = 8>int numbers[NUM] = {};</font></code>
<br>

## Forbidden in C99 (Unfortunately!)
## Allowed by GCC by default (Unfortunately!!)
## Allowed in C23 (Fortunately or not???)

---
# Array Initializer (DON'T)
<br>

<code><font color = yellow size = 8>int numbers[NUM];</font></code>
<br>

## `numbers` may contain garbage values;
## always initialize it

---
# Array Initializer (DON'T)
<br>

<code><font color = yellow size = 8>int numbers[];</font></code>
<br>

## You <mark>must</mark> specify the size so that the compiler/runtime can allocate memory for it.

---
![bg w:600](figs/see-you.jpeg)