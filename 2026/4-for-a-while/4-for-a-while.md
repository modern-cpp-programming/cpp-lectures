---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
# <p id = "small-caps">4. &nbsp; For $\ldots$</p>

<br>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Sep. 28, 2026

---
# Review
<br>

<font color = red>

### While Statement
### Loop Invariant
### `break` Statement

</font>

---
# Overview
<br>

<font color = red>

### `for` Statement
### Nested Loops

</font>
<br>

<font color = blue>

### Selection Sort

</font>

---
![w:700](figs/lets-code.jpeg)

## <mark>min-array.cpp &ensp; palindrome.cpp &ensp; stars.cpp</mark>
## <mark>primes.cpp &ensp; selection-sort.cpp</mark>

---
# min of an Array

$\min(23, 56, 19, 11, 78) = \min(\min(\min(\min(23, 56), 19), 11), 78)$

<br>

Iteratively compute pairwise minimum.

---
# while version: three things scattered

```cpp
int min{numbers[0]};
int i{1};                  // (1) init
while (i < NUM) {          // (2) condition
  if (numbers[i] < min) {
    min = numbers[i];
  }
  i++;                     // (3) update
}
```

<br>

<mark>Init, condition, update are scattered in 3 places.</mark>

---
# for version: three things together

```cpp
int min{numbers[0]};
for (int i{1}; i < NUM; i++) {
  if (numbers[i] < min) {
    min = numbers[i];
  }
}
```

<br>

<mark>Init, condition, update are in one place — easy to see.</mark>

---
# for Syntax

# <!--fit--> <code><font color = yellow>for (<font color = red>init-clause</font>; <font color = blue>cond-expression</font>; <font color = green>iteration-expression</font>) loop-statement</font></code>

<br>

* `init-clause`: executed **once** before the loop
* `cond-expression`: checked before **each** iteration
* `iteration-expression`: executed at the end of **each** iteration
* All three are optional, but the two `;` are required
* Empty condition = <mark>infinite loop</mark>

---
# for Semantics

```cpp
  for (int i{1};     // (1) init
              i < NUM;  // (2) condition
                      i++)  // (3) iteration
                           {  // (4) body
    ...
  }
  // (5) after the loop
```

(1) → (2) → {(4) → (3) → (2)} → (5)

---
# Array Bounds

<br>

<code><font color = "yellow" size = "7">for (int i{0}; i < NUM; i++)</font></code>

<br>

#### NOT `i <= NUM`!

<br>

Accessing `numbers[NUM]` is <mark>out of bounds = Undefined Behavior</mark>.

---
# for Scope

```cpp
for (int i{0}; i < NUM; i++) {
  ...
}
// i is NOT accessible here.
```

<br>

* `i` declared in `init-clause` is local to the `for` loop.
* Two loops can both use `i` without conflict.
* <mark>Keep scopes small (CG ES.5)</mark>

---
# Palindrome: for version

```cpp
for (std::size_t left{0}, right{s.size() - 1};
     left < right; ++left, --right) {
  if (s.at(left) != s.at(right)) {
    is_palindrome = false;
    break;
  }
}
```

<br>

* Init: declare **two** variables
* Iteration: comma expression updates **both**

---
# Stars Pyramid

![w:500](figs/stars.jpg)

<br>

Outer loop: which row. Inner loops: spaces then stars.

---
# Stars: Nested Loops

```cpp
for (int i{0}; i < lines; i++) {
  for (int j{0}; j < lines - 1 - i; j++) {
    std::cout << ' ';
  }
  for (int j{0}; j < 2 * i + 1; j++) {
    std::cout << '*';
  }
  std::cout << '\n';
}
```

---
# Prime Numbers

![w:400](figs/prime.jpg)

<br>

A prime is $>1$ with no divisors other than $1$ and itself.

---
# primes: Brute Force

```cpp
for (int i{2}; i <= n; i++) {
  bool is_prime{true};
  for (int j{2}; j < i; j++) {
    if (i % j == 0) {
      is_prime = false;
    }
  }
  if (is_prime) std::cout << i << ' ';
}
```

<br>

Flag variable: assume true, set false on counterexample.

---
# primes: with break

```cpp
for (int j{2}; j < i; j++) {
  if (i % j == 0) {
    is_prime = false;
    break;  // found a factor; stop!
  }
}
```

<br>

* `break` exits the **innermost** loop only.
* Saves time: no need to keep dividing after finding a factor.

---
# primes: sqrt Optimization

If $i = a \times b$, then one of $a, b \leq \sqrt{i}$.

<br>

```cpp
for (int j{2}; j <= i / j; j++) {
  if (i % j == 0) {
    is_prime = false;
    break;
  }
}
```

<br>

Use `j <= i / j`, **not** `j * j <= i` — <mark>signed overflow is UB!</mark>

---
# Performance

| n | primes-bf | primes-break | primes (final) |
|---|-----------|-------------|----------------|
| 10,000 | 103 ms | 11.8 ms | 0.50 ms |
| 100,000 | 10.1 s | 828 ms | 7.3 ms |
| 1,000,000 | — | — | 277 ms |

<br>

### <mark>Smaller search range + early exit = huge speedup</mark>

---
# Selection Sort

![w:600](figs/selection-sort.png)

<br>

Find the minimum in `[i .. n-1]`, swap with `numbers[i]`.

---
# Selection Sort: Loop Invariant

<br>

$$\boxed{\texttt{numbers[0..i-1]} \text{ is sorted \& correct}}$$

<br>

Iteration $i$: find min of `numbers[i .. n-1]`, swap into position $i$.

---
# Swapping Two Variables

<br>

```cpp
int temp{a};
a = b;
b = temp;
```

<br>

<mark>Need a temporary variable!</mark> Direct assignment overwrites.

---
# Complexity

<br>

For an array of size $n$:

* Comparisons: $\sim n^2$
* <mark>Quadratic</mark> time complexity

<br>

Better algorithms (merge sort, quicksort): $O(n \log n)$.

---
![bg w:600](figs/see-you.jpeg)
