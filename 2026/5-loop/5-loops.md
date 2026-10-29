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
Oct. 29, 2026

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
![w:700](figs/lets-code.jpeg)

## <mark>josephus.cpp &ensp; game-of-life.cpp</mark>
## <mark>insertion-sort.cpp &ensp; bubble-sort.cpp</mark>

---

![w:800](figs/J.jpg)

## <mark>''I hate the Josephus Game!''</mark>

---

![w:1100](figs/vector.PNG)

---

![w:800](figs/vector-iterator.PNG)

---

![w:1200](figs/vector-ops.PNG)

---

![w:900](figs/vector-pushback.PNG)

---

![w:1100](figs/vector-erase.PNG)

---

## $J(2^m + l) = 2l + 1 \quad {\small (m \ge 0 \land 0 \le l < 2^m)}$

![w:700](figs/J.jpg)

### $J(12) = J(2^3 + 4) = 2 \times 4 + 1 = 9$

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

### [Glider](https://playgameoflife.com/)

![w:900](figs/glider.png)

---

### [Gosper glider gun](https://en.wikipedia.org/wiki/Gun_(cellular_automaton))

![w:750](figs/Gospers-glider-gun.gif)

---
### [Puffer-type breeder](https://en.wikipedia.org/wiki/Puffer_train)

![w:1000](figs/breeder.gif)

---
<video control width = "1100"> <source src="videos/Conway-Game-of-Life.mp4" type = "video/mp4"> </video>

---
# [Insertion Sort](https://en.wikipedia.org/wiki/Insertion_sort)
![w:600](figs/insertion-sort-poker.png)

---
![w:520](figs/hushi-poker.png) &ensp; ![w:520](figs/ziyou.jpg)

---
![w:1000](figs/insertion-sort-animation.gif)

---
<br>

![w:1100](figs/insertion-sort-before.png)

<br>

![w:1100](figs/insertion-sort-after.png)

---
# [Bubble Sort](https://en.wikipedia.org/wiki/Bubble_sort)

![w:900](figs/bubble-sort.png)

---

![w:1000](figs/bubble-sort-wiki.gif)

---
![bg w:1100](figs/thank-you.png)