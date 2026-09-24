# Sources for the new while / invariant slides

- `while-semantics.png`: AI-edited companion to `while-flow.png`. Omits the invariant checkpoint; the back edge returns directly to the condition. Used only on the While Statement slide. The original image remains on the invariant slide.

- Full lecture: [3-while](https://njusecourse.feishu.cn/wiki/Xt5XwgZCCiPyugkg2kFch9z4nsd).
- Source actually consulted: repository snapshot [`../../feishu-lectures/3-while.pdf`](../../feishu-lectures/3-while.pdf), with revision entries dated 2026-09-24. The live Feishu page was unavailable during editing; live/snapshot equivalence was not verified.
- Sections 2.1–2.3: while syntax, invariant definition, proof obligations, and abstraction.
- Section 3.4: Euclid invariant, preservation, exit result, and decreasing remainder.
- Section 4.3: Fibonacci adjacent-pair invariant and initialization / maintenance / exit proof. Variable names also checked against `cpp-coding-2026-0/3-while/fib.cpp`.
- `while-flow.png`: original AI-generated flowchart, 2026-09-24. Semantics checked: initialize once, test before execution, back edge returns to the invariant checkpoint, false branch exits. Generated to match the lecture palette; no third-party image copied.
- Google Images was attempted but unavailable; fallback image search returned mostly text-heavy slide screenshots. No search-result images were used. State transitions and invariant equations are native slide math.

The termination measure is separate from invariant preservation. Fibonacci assumes nonnegative input and no overflow in any intermediate result.
