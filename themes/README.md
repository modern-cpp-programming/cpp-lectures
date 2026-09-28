# 2022cpl

主题统一管理背景色（`#FED8B1`）、默认尺寸（1280 × 720，即 16:9）、行内代码颜色与封面间距。
引用主题的幻灯片会继承这些默认样式；单份讲义仍可通过 Marp 指令或 `style` 覆盖。

新讲义使用以下开头即可（需在 Marp 中注册 `themes/2022cpl.css`）：

```markdown
---
marp: true
theme: 2022cpl
class: lead
paginate: true
---
<!-- _class: lead cover -->

# <span id="small-caps">Lecture Title</span>

Author
email@example.com

![w:200](figs/cpp-logo.png)
Date

---
# First Slide
```

`paginate` 控制页码生成，不能通过主题 CSS 开启，因此保留在 frontmatter 中。
`class: lead` 是讲义的布局选择，也保留在 frontmatter 中。
`_class` 只作用于当前页；`cover` 用于封面，标题使用 `<span>`，避免 `<p>` 的额外段落间距。
如需其他比例，可显式指定 `size: 4:3`，继续使用 Gaia 提供的尺寸预设。

参考：[Marp directives](https://github.com/marp-team/marp/blob/main/website/docs/guide/directives.md)。
