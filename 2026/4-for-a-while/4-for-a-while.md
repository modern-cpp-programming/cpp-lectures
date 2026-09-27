---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
style: |
  :not(pre) > code { color: #ffd700; }
  font[color] :not(pre) > code { color: inherit; }
---
# <p id = "small-caps">4. &nbsp; For $\ldots$</p>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Sep. 28, 2026

---
# Review
<br>

<font color = red>

## `while` Statement
## `break` Statement

</font>

<br>

<font color = blue>

## [ ]; std::array
## std::vector

</font>

---
# Overview
<br>
<br>

<font color = red>

## `for` Statement
## Nested Loops

</font>

---
![w:700](figs/lets-code.jpeg)

## <mark>min-array.cpp &ensp; palindrome.cpp &ensp; stars.cpp</mark>
## <mark>primes.cpp &ensp; selection-sort.cpp</mark>

---
# min of an array

<br>

![w:550](figs/minimum.jpg)

$\min(23, 56, 19, 11, 78) = \min(\min(\min(\min(23, 56), 19), 11), 78)$

<br>

---

# <code><font color = yellow>for (<font color = red>init-clause</font>; <font color = blue>cond-expression</font>; <font color = cyan>iteration-expression</font>) loop-statement</font></code>

---
# Palindrome (`for` version)

![w:850](figs/palindrome.png)

---
# Stars Pyramid

![w:750](figs/stars.jpg)

---
# Prime Numbers

![w:400](figs/prime.jpg)

---
# Selection Sort

![w:350](figs/selection-sort.png)

Find the minimum in `[i .. n-1]`, swap with `numbers[i]`.

---
![bg w:600](figs/see-you.jpeg)