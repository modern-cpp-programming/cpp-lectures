---
theme: default
title: '0. Introducing C++'
titleTemplate: '%s | Modern C++ Programming'
info: 'Modern C++ Programming — Lecture 0'
author: Hengfeng Wei
language: zh-CN
class: text-center
drawings:
  persist: false
transition: fade-out
mdc: true
---

<div class="cover">
  <div>
    <h1>0. Introducing C++</h1>
    <p><a href="https://hengxin.github.io/">Hengfeng Wei (魏恒峰)</a><br>hfwei@nju.edu.cn</p>
    <img class="title-logo" src="./figs/cpp-logo.png" alt="C++ logo">
    <p>Sep. 19, 2024</p>
  </div>
</div>

---
layout: center
class: no-page
---

<div class="two-images">
  <img src="./figs/2024CPL.jpg" alt="2024 CPL class information">
  <img src="./figs/2024CPL-Notice.jpg" alt="2024 CPL course notice">
</div>

---
class: image-slide
---

# Questionnaire (1)

<img src="./figs/25-75.jpg" alt="25 percent and 75 percent illustration">

<mark>75%</mark> of students are new to programming.

---
class: image-slide
---

# Questionnaire (2)

<img src="./figs/90-10-blackboard.webp" alt="90 percent and 10 percent illustration">

<span class="red">10%</span> of students attended in some programming contests.

---
class: image-slide
---

# Questionnaire (3)

<img src="./figs/know-nothing.webp" alt="Beginner programming illustration">

### <mark>The C++ Beginners (know 0%)</mark>

---
class: image-slide
---

# The C++ Beginners

<img src="./figs/panic.png" alt="Don't panic illustration">

---
class: image-slide
---

# To The C++ Beginners

<img src="./figs/donot-panic.jpg" alt="Do not panic illustration">

---
layout: center
class: text-center
---

# From Beginners to Masters

## Programming

## <span class="red">De-Programming</span>

---
class: image-slide compact-image
---

## [cpl-docs @ docs.cpl.icu](http://docs.cpl.icu)

<img src="./figs/cpl-docs.png" alt="CPL Docs QR code">

---
class: image-slide compact-image
---

## [CPL Docs @ FeiShu](https://ymv59wdgrr.feishu.cn/wiki/A1HzwviAgiFnQwkfRUWcVjqunLf?from=from_copylink)

<img src="./figs/docs.png" alt="CPL Docs QR code in Feishu">

---
class: image-slide
---

## [oj @ oj.cpl.icu; oj @ public.oj.cpl.icu](https://public.oj.cpl.icu/)

<div class="two-images">
  <img src="./figs/oj-0-intro.png" alt="Online judge screenshot">
  <img src="./figs/qrcode-public-oj.png" alt="Online judge QR code">
</div>

---
class: image-slide
---

# [2024cpl @ Zulip](https://2024cpl.zulipchat.com/join/t4kpy6uj6ximq7k3qwve5smj/)

<div class="two-images">
  <img src="./figs/zulip.png" alt="Zulip logo">
  <img src="./figs/zulip-qrcode.png" alt="Zulip QR code">
</div>

---
class: side-image
---

<div>

# Scores

<ul class="score-list">
  <li><span class="muted-strike">考勤 (非必要不点名)</span></li>
  <li><span class="blue">平时编程练习 (10 分)</span></li>
  <li><span class="blue">阶段机试 1 (15 分)</span></li>
  <li><span class="blue">阶段机试 2 (20 分)</span></li>
  <li><span class="blue">期末机试 (30 分)</span></li>
  <li><span class="blue">期末项目 (25 分)</span></li>
</ul>

</div>

<img src="./figs/score.jpg" alt="Score distribution illustration">

---
class: image-slide
---

# No Plagiarism!!!

<img src="./figs/plagiarism.jpg" alt="No plagiarism poster">

<span class="red"><strong>编程练习</strong></span>: 每次扣 5 分, 10 分扣完为止; <span class="red"><strong>期末项目</strong></span>: 项目分数清零

---
class: image-slide
---

<img src="./figs/ask-me-anything.png" alt="Ask me anything">

### <mark>About the 2024CPL Class</mark>

---
layout: center
class: no-page
---

<div class="two-images">
  <img src="./figs/textbook-nju.JPG" alt="C++ programming textbook">
  <img src="./figs/textbook-moderncpp.jpg" alt="Modern C++ textbook">
</div>

---
layout: center
class: no-page
---

<img src="./figs/not-recommended.jpg" alt="Not recommended reading">

---
layout: center
class: no-page
---

<div class="two-images">
  <img src="./figs/textbook-nju.JPG" alt="C++ textbook from Nanjing University">
  <img src="./figs/textbook-moderncpp.jpg" alt="Modern C++ programming textbook">
</div>

---
class: image-slide
---

# C++ Foundations

<div class="three-images">
  <img src="./figs/cpp-logo.png" alt="C++ logo">
  <img src="./figs/textbook-nju.JPG" alt="C++ programming textbook">
  <img src="./figs/textbook-moderncpp.jpg" alt="Modern C++ textbook">
</div>

---
class: image-slide large-image
---

### [C++ and Its C Roots @ cppreference](https://en.cppreference.com/w/cpp/language/history) **[[C++17](https://en.cppreference.com/w/cpp/17); [C++23](https://en.cppreference.com/w/cpp/23)]**

<img src="./figs/c-history.jpg" alt="Programming language history">

You do <em>NOT</em> need to be a <strong>language lawyer</strong>!

---
layout: center
class: no-page
---

<div class="two-images">
  <img src="./figs/poison.jpg" alt="Programming pitfalls">
  <img src="./figs/not-sure-ask.jpg" alt="Ask when unsure">
</div>

---
class: image-slide
---

<img src="./figs/more-books.jpg" alt="More programming books">

### <mark>More Books in the Class …</mark>

---
layout: center
class: no-page
---

<img src="./figs/soft-skills-1.png" alt="Soft skills book">

---
layout: center
class: no-page
---

<img src="./figs/pilao-book.jpg" alt="Programming book">

---
layout: center
class: no-page
---

<img src="./figs/talk-cheap.jpg" alt="Talk is cheap, show me the code">

---
layout: center
class: no-page
---

<img src="./figs/hello-world-logo.jpg" alt="Hello World logo">

---
layout: center
class: no-page
---

<img src="./figs/hello-world-kandr.jpg" alt="Hello World from K&R">

---
class: image-slide
---

# [Game: Guess the Number](https://www.abcya.com/games/guess_the_number)

<img src="./figs/guess-the-number.png" alt="Guess the Number game">

---
layout: center
class: text-center
---

# [Game: Guess the Number](https://www.abcya.com/games/guess_the_number)

<p class="quote">Programming is <em>NOT</em> (only) about languages.</p>

<p class="quote">You learn C++ to express <mark><strong>YOUR IDEAS</strong></mark> with <strong>COMPUTERS</strong>.</p>

---
class: image-slide large-image
---

# [C++ reference](https://en.cppreference.com/w/cpp)

<img src="./figs/huawei-rand.png" alt="C++ random number guidance">

---
layout: center
class: text-center
---

# [Game: Guess the Number](https://www.abcya.com/games/guess_the_number)

<p class="program-equation"><strong><span class="green">Program</span> = <span class="purple">Input</span> + <span class="blue">Data</span> + <span class="red">Operations</span> + <span class="purple">Output</span></strong></p>

---
class: image-slide
---

# Secure Coding in C++

<div class="two-images">
  <img src="./figs/cpp-logo.png" alt="C++ logo">
  <img src="./figs/huawei-rand.png" alt="C++ random number example">
</div>

---
class: image-slide
---

<img src="./figs/ask-me-anything.png" alt="Ask me anything">

---
class: image-slide large-image
---

<img src="./figs/chatgpt.jpg" alt="ChatGPT illustration">

---
layout: center
class: image-slide no-page closing
---

<img src="./figs/thankyou.png" alt="Thank you">
