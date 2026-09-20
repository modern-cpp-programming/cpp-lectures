---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
# <p id = "small-caps">2. &nbsp; If $\ldots$</p>

<br>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/C.png)
Sep. 20, 2024

---
# Review

### <font color = "blue">Variables (变量) &emsp; Data Types (数据类型)</font>

<br>

### <font color = "red">Operators (运算符) &emsp; Expressions (表达式)
### Assignment Statements (赋值语句)</font>

<br>

### <font color = "purple">I/O (Input/Output; 输入输出)</font>

---
# Overview
<br>
<br>

<font color = red>

# If Statement (`if` 语句)
# Switch Statement (`switch` 语句)
</font>
<br>
<br>

---
![w:700](figs/lets-code.jpeg)

## <mark>min.cpp &ensp; adult.cpp &ensp; leap.cpp &ensp; next-day.cpp</mark>

---
# Min of Two
<br>
<br>

#### Given two integers $a$ and $b$, to compute their minimum.
<br>

$min = \min\{a, b\}$

---
<br>
<br>

## <code><font color = yellow>min = a >= b <font color = red>?</font> b <font color = red>:</font> a;</font></code>
#### (三目运算符)
<br>

## Do Not Use it Too Much!

<!-- ---
# Min of Two
<br>

Given two <font color = red size = 8>double</font>s $a$ and $b$, to compute their minimum.
<br>

$\mathit{min} = \min\{a, b\}$ -->

---
# Min of Three
<br>
<br>

#### Given three integers $a$, $b$, and $c$, to compute their minimum.
<br>

$\mathit{min} = \min\{a, b, c\}$

---

# If with Initializer (C++17)

<br>

## Input age; check if adult ($\geq 18$).

<br>

## <mark>adult-outside.cpp &ensp; adult-inside.cpp
## <mark>adult-if-init.cpp</mark>

---

# Variable Scope: Three Ways

| 写法 | 作用域 | 泄漏? | 重复代码? |
|------|--------|:-----:|:---------:|
| 外部声明 | 整个函数 | <font color=red>是</font> | 否 |
| 分支内声明 | 单个分支 | 否 | <font color=red>是</font> |
| <mark>if 初始化器</mark> | 整个 if-else | <mark>否</mark> | <mark>否</mark> |

<br>

### <mark>Keep scopes small (CG ES.5)</mark>

---
# Leap Year

![w:800](figs/leap-year.jpeg)

---
# Leap Year (1): Nested `if/else` (YES)
![w:800](figs/leap-year-flowchart.png)

---

# <code><font color = "yellow">==</font></code> vs. <code><font color = "yellow">=</font></code>

<br>

<code><font color = "green" size = "10">if (year == 0) { ... }</font></code>

<br>

<code><font color = "red" size = "8">if (year = 0) { ... }  // ALWAYS FALSE!</font></code>

---
# Leap Year (2): Nested `if/else` (NO)

![w:800](figs/leap-year-flowchart.png)

---
# Leap Year (3): `else if`
<br>

![w:1200](figs/leap-year-wiki.png)

---
# Leap Year (4): The Ultimate Version
<br>

## A year is a <mark>**leap year**</mark> if
<br>

<font size = 8>

- it is divisible by $4$ but not by $100$,
- except that years divisible by $400$ are leap years.
</font>

---
# Short-circuit Evaluation (短路求值)

![w:950](figs/leap.png)

---

# Order of Evaluation

<br>
<br>

## For most operators (except `&&`, `||`, `?:`), operand evaluation order is <mark>unspecified</mark>.

---

<code><font color = "red" size = "10">int x{i + i++};  </font></code>

<br>

![w:500](figs/ub.jpg)

---

# <code><font color = "yellow">[[likely]]</font></code> / <code><font color = "yellow">[[unlikely]]</font></code> (C++20)

<br>
<br>
<br>

### (Only) a hint to compiler for branch prediction

---

# Next Day Calculator

<br>

## Given (year, month, day), print the next day.

<br>

### `2024-2-28 → 2024-2-29`

### `2024-12-31 → 2025-1-1`

---
![w:700](figs/lets-code.jpeg)
<br>

### <mark>days-of-month.cpp &ensp; temperature-control.cpp </mark>

---

# Fall-through & Case Scope

<br>
<br>

* Missing `break` = implicit fall-through (usually a bug)
* Intentional fall-through: use `[[fallthrough]]`
* Variables in `case`: use <mark>`{}`</mark> to limit scope

---

# switch with Initializer (C++17)

<br>
<br>

## Temperature Control


---

# if-else vs. switch

<br>
<br>

### Prefer `switch` for discrete constants (CGL ES.70)

---
![bg w:600](figs/see-you.jpeg)