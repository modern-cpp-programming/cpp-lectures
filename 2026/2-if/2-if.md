---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
# <p id = "small-caps">2. &nbsp; If, For, Array</p>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@nju.edu.cn

![w:200](figs/C.png)
Oct. 06, 2024

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

<font color = red>

### If Statement (`if` 语句)
### For Statement (`for` 语句)
### Logical Expressions (逻辑表达式)
</font>
<br>

### <font color = blue>Array (数组)</font>
---
![w:700](figs/lets-code.jpeg)

## <mark>min.c &ensp; leap.c &ensp; min-array.c</mark>

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
# Min of a Set of Numbers
<br>

#### Given a set $A$ of integers, to compute their minimum.

$\mathit{min} = \min A$

![w:400](figs/loop.jpg)

$\min\{3, 5, 2, 7\} = \min(\min(\min(3, 5), 2), 7)$

---
# Leap Year

![w:800](figs/leap-year.jpeg)

---
# Leap Year (1): Nested `if/else` (YES)
![w:800](figs/leap-year-flowchart.png)

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
![bg w:600](figs/see-you.jpeg)

---

# If with Initializer (C++17)

Input age; check if adult ($\geq 18$).

<br>

<code><font color = "yellow" size = "6">if (int years = age - 18; years >= 0) {</font></code>

<code><font color = "yellow" size = "6">  // adult: years >= 0</font></code>

<code><font color = "yellow" size = "6">} else {</font></code>

<code><font color = "yellow" size = "6">  // not yet: years < 0</font></code>

<code><font color = "yellow" size = "6">}</font></code>

<br>

<mark>`years` is visible in both branches, but NOT after the `if-else`.</mark>

---

# Variable Scope: Three Ways

| 写法 | 作用域 | 泄漏? | 重复计算? |
|------|--------|:-----:|:---------:|
| 外部声明 | 整个函数 | <font color=red>是</font> | 否 |
| 分支内声明 | 单个分支 | 否 | <font color=red>是</font> |
| <mark>if 初始化器</mark> | 整个 if-else | <mark>否</mark> | <mark>否</mark> |

<br>

### <mark>Keep scopes small (CG ES.5)</mark>

---

# <code><font color = "yellow">==</font></code> vs. <code><font color = "yellow">=</font></code>

<br>

* <code><font color = "yellow">==</font></code>: equality comparison
* <code><font color = "yellow">=</font></code>: assignment

<br>

<code><font color = "green" size = "6">if (year == 0) { ... }</font></code>

<br>

<code><font color = "red" size = "6">if (year = 0) { ... }  // ALWAYS FALSE!</font></code>

---

# Order of Evaluation

<br>

For most operators, operand evaluation order is <mark>unspecified</mark>.

<br>

<code><font color = "red" size = "7">int x{i + i++};  // UNDEFINED BEHAVIOR!</font></code>

<br>

* Side effect on `i` and read of `i` are *unsequenced*.
* Only `&&`, `||`, `?:`, comma have specified order.

---

# <code><font color = "yellow">[[likely]]</font></code> / <code><font color = "yellow">[[unlikely]]</font></code> (C++20)

<br>

<code><font color = "yellow" size = "6">if (leap) <font color = "red">[[unlikely]]</font> {</font></code>

<code><font color = "yellow" size = "6">  // rare: a leap year</font></code>

<code><font color = "yellow" size = "6">} else <font color = "green">[[likely]]</font> {</font></code>

<code><font color = "yellow" size = "6">  // common: a common year</font></code>

<code><font color = "yellow" size = "6">}</font></code>

<br>

* Hint to compiler for branch prediction
* <mark>Does NOT change program semantics</mark>

---

# Next Day Calculator

<br>

Given (year, month, day), print the next day.

<br>

* Compute days-in-month (if-else chain)
* Validate the date before advancing
* Roll over: <mark>month first, then year</mark>

<br>

`2024-2-28 → 2024-2-29` &emsp; `2024-12-31 → 2025-1-1`

---

# days-in-month via if-else

<br>

<code><font color = "yellow" size = "5">if (month == 2) {</font></code>

<code><font color = "yellow" size = "5">  days = leap ? 29 : 28;</font></code>

<code><font color = "yellow" size = "5">} else if (month == 4 || month == 6 ||</font></code>

<code><font color = "yellow" size = "5">          month == 9 || month == 11) {</font></code>

<code><font color = "yellow" size = "5">  days = 30;</font></code>

<code><font color = "yellow" size = "5">} else {</font></code>

<code><font color = "yellow" size = "5">  days = 31;</font></code>

<code><font color = "yellow" size = "5">}</font></code>

---

# switch/case

<br>

<code><font color = "yellow" size = "5">switch (month) {</font></code>

<code><font color = "yellow" size = "5">  case 2:</font></code>

<code><font color = "yellow" size = "5">    days = leap ? 29 : 28;  break;</font></code>

<code><font color = "yellow" size = "5">  case 4: case 6: case 9: case 11:</font></code>

<code><font color = "yellow" size = "5">    days = 30;  break;</font></code>

<code><font color = "yellow" size = "5">  default:</font></code>

<code><font color = "yellow" size = "5">    days = 31;  break;</font></code>

<code><font color = "yellow" size = "5">}</font></code>

<br>

* Condition: <mark>integral or enum</mark>
* `case` labels: <mark>constant expressions</mark>
* Falls through unless `break`

---

# Fall-through & Case Scope

<br>

* Missing `break` = implicit fall-through (usually a bug)
* Intentional fall-through: use `[[fallthrough]]`
* Variables in `case`: use <mark>`{}`</mark> to limit scope

<br>

<code><font color = "yellow" size = "5">case 2: {</font></code>

<code><font color = "yellow" size = "5">  bool leap{...};</font></code>

<code><font color = "yellow" size = "5">  days = leap ? 29 : 28;</font></code>

<code><font color = "yellow" size = "5">  break;</font></code>

<code><font color = "yellow" size = "5">}</font></code>

---

# switch with Initializer (C++17)

<br>

<code><font color = "yellow" size = "5">switch (int temperature{raw + calibration};</font></code>

<code><font color = "yellow" size = "5">        temperature / 10) {</font></code>

<code><font color = "yellow" size = "5">  case 0: case 1:  // heater</font></code>

<code><font color = "yellow" size = "5">  case 2: case 3:  // normal</font></code>

<code><font color = "yellow" size = "5">  case 4: case 5:  // ventilation</font></code>

<code><font color = "yellow" size = "5">  default:          // too hot</font></code>

<code><font color = "yellow" size = "5">}</font></code>

<br>

### <mark>`temperature` is local to the `switch`</mark>

---

# if-else vs. switch

<br>

<br>

<table>
<tr><th></th><th>if-else chain</th><th>switch</th></tr>
<tr><td>Condition</td><td>Any expression</td><td><mark>Integral constant</mark></td></tr>
<tr><td>Range check</td><td>Easy</td><td>Need `/10` trick</td></tr>
<tr><td>Optimization</td><td>—</td><td>Jump table</td></tr>
<tr><td>Readability</td><td>OK for short chains</td><td><mark>Clean for discrete values</mark></td></tr>
</table>

<br>

### Prefer `switch` for discrete constants (CGL ES.70)