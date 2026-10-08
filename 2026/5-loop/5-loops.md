---
marp: true
theme: 2022cpl
class:
  - lead

paginate: true
---
<!-- _class: lead cover -->

# <span id = "small-caps">5. &nbsp; Loop</span>

<br>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Oct. 09, 2026

---
# Review
<br>
<br>

<font color = red>

## `for` Statement
## Nested Loops

</font>

---
# Overview

### <font color = red>Loops (More Examples)</font>
<br>

### <font color = blue>vector</font>

### <font color = blue>Multi-dimensional Arrays (多维数组)</font>

---
![w:800](figs/lets-code.jpeg)

## <mark>josephus.cpp &ensp; game-of-life.cpp &ensp; insertion-sort.cpp</mark>

---

![w:800](figs/J.jpg)

## <mark>''I hate the Josephus Game!''</mark>

---

<!-- ![w:800](figs/J.jpg) -->

## $J(2^m + l) = 2l + 1 \quad {\small (m \ge 0 \land 0 \le l < 2^m)}$

---
# [Conway's Game of Life @ wiki](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life)

![w:500](figs/Conway.jpg)
#### John Horton Conway ($1937 \sim 2020$)

---
### [playgameoflife.com (Cellular Automata; 元胞自动机)](https://playgameoflife.com/)
<br>
<br>

* Any <font color = blue>**live**</font> cell with two or three live neighbours survives.
* All other <font color = blue>**live**</font> cells die in the next generation.
<br>

* Any <font color = red>**dead**</font> cell with three live neighbours becomes a live cell.
* All other <font color = red>**dead**</font> cells stay dead.

---
<br>

![left w:500](figs/Gospers-glider-gun.gif) &ensp; ![right w:600](figs/breeder.gif)

---
<video control width = "1100"> <source src="videos/Conway-Game-of-Life.mp4" type = "video/mp4"> </video>

---
# Insertion Sort
![w:600](figs/insertion-sort-poker.png)

---
![w:520](figs/hushi-poker.png) &ensp; ![w:520](figs/ziyou.jpg)

---
![w:1000](figs/insertion-sort-animation.gif)

---
<br>

![w:1100](figs/insertion-sort-before.png)

<br>

![w:1100](figs/insertion-sort-before.png)

---
# Bubble Sort

![w:900](figs/bubble-sort.png)

---

![w:1000](figs/bubble-sort-wiki.gif)

---
![bg w:600](figs/see-you.jpeg)