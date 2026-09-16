---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
# <p id = "small-caps">1. &nbsp; Variables, Types, I/O</p>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Sep. 16, 2026

---
# Overview

**<font color = green size = 8>Program = <font color = purple>Input</font> + <font color = blue>Data </font> + <font color = red>Operations</font> + <font color = purple>Output</font>**</font>

![w:950](figs/io-process.png)

---
# Overview

### <font color = "blue">Variables (变量) &emsp; Data Types (数据类型)</font>

<br>

### <font color = "red">Operators (运算符) &emsp; Expressions (表达式)
### Assignment Statements (赋值语句)</font>

<br>

### <font color = "purple">I/O (Input/Output; 输入输出)</font>

---
![w:600](figs/lets-code.jpeg)

## <mark>circle.c &ensp; sphere.c</mark>
## <mark>admin.c &ensp; admin-cin.c</mark>

---
# Circle

<font size = "8">Given a **radius** (say $10$) of a circle,
to compute its **circumference** and **area**.</font>

<br>

$L = 2\pi r$ &emsp; $S = \pi r^2$

<br>

- 每个结果各占一行
- 小数点后保留两位

---
# Declaration/Definition (声明/定义)
<code><font color = "yellow" size = "7">int radius{10};</font></code>

<br>

* <mark>Declare/Define</mark> a *variable* called `radius`.
* `radius` refers to a <mark>location</mark> in memory.
* The <mark>type</mark> of `radius` is `int` (integer).
* `radius` is <mark>initialized</mark> to $10$.
* You can <mark>assign</mark> other integers to `radius`.

---
# Identifiers (标识符)

<code><font color = "yellow" size = "7">int radius{10};</font></code>

<br>

`radius` is an *identifier*.

**Warning:** Do *not* start with <code><font color = "yellow">_</font></code>, which are reserved by C++.

<br>

#### Always use <mark>meaningful</mark> identifiers in a <mark>uniform</mark> style!!!

---
<code><font color = "red" size = "7">int radius;</font></code>

<code><font color = "yellow" size = "7">cout << radius;</font></code>

![bg left w:500](figs/ub.jpg)

<br>

#### [Undefined Behavior (UB)](https://pvs-studio.com/en/blog/posts/cpp/1129/)

---
# Operators \& Expressions

<br>
<br>
<br>

<code><font color = "yellow" size = "8">double circumference{2 * PI * radius};</font></code>

---
# Sphere

<font size = "7">Given a <mark>radius</mark> (say $100$) of a sphere,
to compute its <mark>surface area</mark> and <mark>volume</mark>.</font>

$A = 4 \pi r^2\quad V = \frac{4}{3} \pi r^3$

- 每个结果占 $1$ 行
- 小数点后保留 $4$ 位
- 每个结果至少占 $15$ 字符, 左对齐
  - `_______________ : surface_area`
  - `_______________ : volume`

<!-- ---
# mol
<font size = "7">$6$ 克氧气的分子数是多少?</font>

<br>

$Q = 6 / 32 \times 6.02 \times 10^{23}$

<br>

使用<mark>科学计数法</mark>表示, 保留 <mark>$5$ 位有效数字</mark> -->

---
# Input/output manipulators (操纵符)

<code><font color = "yellow" size = "8">#include \<iomanip\></font></code>
<br>
<br>

# <!--fit--> [https://en.cppreference.com/cpp/io/manip](https://en.cppreference.com/cpp/io/manip)

---

# <code><font color = "yellow" size = "8">std::format</font></code>

<br>
<br>

# <!--fit--> [https://en.cppreference.com/cpp/utility/format/spec](https://en.cppreference.com/cpp/utility/format/spec)

---
### <mark>Format Specification</mark>
# <!--fit--> <code><font color = yellow><font color = blue>{</font>:[align][width][.precision]<font color = red>[type]</font><font color = blue>}</font></font></code>

- <code><font color = red size = 7>%d</font></code>: decimal `int`
- <code><font color = red size = 7>%f</font></code>: `double`
- <code><font color = red size = 7>%s</font></code>: `string` (not necessarily)
- <code><font color = red size = 7>%c</font></code>: `char` (not necessarily)

---
# <!--fit--> <code><font color = yellow><font color = blue>{</font>:<font color = red>[align]</font>[width][.precision][type]<font color = blue>}</font></font></code>

<br>
<br>

- $<$: left-justified
- $>$: right-justified
- $\hat{}$: centered

---
# <!--fit--> <code><font color = yellow><font color = blue>{</font>:[align]<font color = red>[width]</font>[.precision][type]<font color = blue>}</font></font></code>

<br>
<br>

- minimum field width
- padded with spaces if it has fewer characters

---
# <!--fit--> <code><font color = yellow><font color = blue>{</font>:[align][width]<font color = red>[.precision]</font>[type]<font color = blue>}</font></font></code>

<br>
<br>

* `%f`: <mark>number</mark> of digits after `.`
* `%s`: <mark>maximum number</mark> of characters


---
# A (Naive) Administration System

<div class="columns">

<div>
<br>
<br>

- Name (EN)

- Gender (F/M)

- Birthday (mm-dd-yyyy)

- Weekday (Xyz.)
</div>

<div>
<br>

- C++
- Music
- Medicine
<br>
- Mean (.d)
- Standard Deviation (.dd)
- Ranking ($\%$)
</div>

</div>

---
![bg left w:500](figs/weilai.jpg)

<br>

### For 罗大佑 only:
<br>

- 每组信息占一行
- 各项信息使用 `\t` 间隔
- 各项信息遵循特定格式要求

---
# <code><font color = yellow>char</font></code>

![w:650](figs/ASCII.png)

A `char` is actually an `int`.

---
# C++ String

<br>
<br>

<code><font color = yellow size = 8>std::string first_name{"Tayu"};</code></font>

---
![w:500](figs/weilai.jpg)

# [未来的主人翁](https://www.bilibili.com/video/BV1324y1f7jV/)

---
# Review

**<font color = green size = 8>Program = <font color = purple>Input</font> + <font color = blue>Data </font> + <font color = red>Operations</font> + <font color = purple>Output</font>**</font>

![w:950](figs/io-process.png)