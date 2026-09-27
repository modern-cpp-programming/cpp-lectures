# Task: feishu-ppt

## 中文：根据飞书文档制作 C++ 课堂 PPT

## 任务描述

指定一篇飞书文档（wiki/docx 链接），指定 `cpp-lectures` 仓库下的子目录路径，根据该飞书文档的内容，在指定子目录下自动生成课堂所用的 Marp 幻灯片 Markdown 文件（`.md`）。



***

## 输入参数



| 参数         | 说明                                                     |
| ---------- | ------------------------------------------------------ |
| **飞书文档链接** | 形如 `https://njusecourse.feishu.cn/wiki/xxxx` 的 wiki 链接 |
| **子目录路径**  | 相对于 `cpp-lectures` 仓库根目录的子目录路径，如 `2026/3-while`        |



***

## 执行前确认（必读）

在执行任务之前，必须确认以下信息全部齐备。**缺失任何一项都不得猜测或假设**，必须以提问方式向用户逐一确认，待用户回复后再开始执行：



1. **飞书文档链接**：用户是否提供了有效的 wiki/docx 链接？如果用户只给了讲义名称（如 "第 3 讲"）或本地 `.md` 文件路径，需追问对应的飞书文档 wiki 链接。

2. **仓库子目录路径**：用户是否明确指定了 `cpp-lectures` 仓库下的目标子目录？（如 `2026/3-while`）

3. **追加 / 新建模式**：目标 `.md` 文件是否已存在且非空？如果已存在，用户是否明确指示了操作方式（追加到末尾 / 插入到特定位置 / 整合重排）？未明确则需询问。

> 原则：宁可多问一句，不可擅自假设。



***

## PPT 风格规范

### 1. 整体风格



* **基于 Marp** 的 Markdown 幻灯片，使用仓库自定义主题 `2022cpl`（定义于 `themes/2022cpl.css`，内置导入 gaia 主题）

* **极简风格**：仅展示最关键的知识点，每张幻灯片聚焦一个核心概念，避免大段文字堆砌

* **知识点醒目**：使用 `<mark>` 高亮、彩色字体、大号字等手段让重点信息在投影时清晰可辨

* **C++ 语境**：所有代码示例均使用 C++（`.cpp` 文件、`std::` 前缀、C++20 标准），不要出现 C 语言残留

### 2. Frontmatter（每篇 .md 必须包含）



```
---
marp: true
theme: 2022cpl
class:
  - lead

backgroundColor: #FED8B1
paginate: true
size: 16:9
---
```

> 注意：不要随意修改 
>
> `theme`
>
> 、
>
> `backgroundColor`
>
> 、
>
> `size`
>
>  等全局配置。
> 如需特殊样式（如循环不变量幻灯片的深色主题），可在 frontmatter 中追加 
>
> `style:`
>
>  块，参考 
>
> `3-while.md`
>
> 。

### 3. 标准幻灯片结构

每篇 PPT 应遵循以下结构：



1. **标题页**（见下）

2. **Review**：回顾上一讲的核心知识点（用红色字体列出）

3. **Overview**：本讲将要覆盖的内容大纲

4. **Let's Code**：列出本讲要写的 `.cpp` 文件名（用 `<mark>` 高亮）

5. **正文幻灯片**：按飞书文档的小节顺序展开

6. **结尾**：`![bg w:600](figs/see-you.jpeg)`

### 4. 标题页



```
# <p id = "small-caps">3. &nbsp; While $\ldots$</p>

<br>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Sep. 24, 2026
```



* 标题编号后用 `&nbsp;` 接标题文字

* 如果本讲只覆盖更大主题的一部分，用 `$\ldots$` 省略（如 `"If $\ldots$"`、`"While $\ldots$"`）

* 标题后加 `<br>` 再放作者信息

* 邮箱统一用 `hfwei@hnu.edu.cn`

### 5. 内容排版技巧

以下为本课程 PPT 的惯用写法，新生成的幻灯片应严格遵循：

#### 5.1 基本元素



* **分页符**：幻灯片之间使用 `---` 分隔

* **高亮重点**：使用 `<mark>重点内容</mark>` 标注关键术语

* **注释掉的幻灯片**：使用 `<!-- --- ... --- -->` 包裹，保留备用但不渲染

* **适应幻灯片**：内容过多时在标题后加 `# <!--fit-->` 自动缩放

#### 5.2 图片



* **指定宽度**：`![w:500](figs/filename.png)`（根据内容调整，常用 300–900）

* **背景图**：`![bg 80%](figs/filename.jpg)` 或 `![bg right:48% contain](figs/filename.png)`

* **多图并排**：`![w:450](figs/a.png) ![w:450](figs/b.png)`

* 图片放在子目录的 `figs/` 下

#### 5.3 代码

两种代码展示方式，根据代码长度选择：

**短代码行（1–3 行）**：用内联 `<code>` 标签，黄色字体：



```
<code><font color = "yellow" size = "6">if (int years = age - 18; years >= 0) {</font></code>
```

关键部分可嵌套 `<font color="red">` 或 `<font color="green">` 强调。

**多行代码块**：用 fenced code block，配合 `class:` 或自定义样式：



````
```cpp
// initialize
while (condition) {
  // body + update
}
```
````

#### 5.4 数学公式



* 行内：`$...$`，如 `$\geq 18$`、`$\gcd(a,b)$`

* 独立行：`$$...$$`

* 关键不变量 / 核心公式用 `\boxed{...}` 突出：

  $\boxed{\gcd(a,b)=\gcd(a_0,b_0)}$

* 箭头推导用 `\xrightarrow{...}`：

  $(a,b)\;\xrightarrow{\;b\ne0\;}\;(b,\;a \;\%\; b)$

#### 5.5 彩色字体约定



| 内容类型             | 颜色               |
| ---------------- | ---------------- |
| Input / Output   | `purple`         |
| Data / 类型        | `blue`           |
| Operations / 运算符 | `red`            |
| 总结性语句            | `green`          |
| 代码默认             | `yellow`（在深色主题上） |
| 正确示例             | `green`          |
| 错误 / 警告          | `red`            |

示例：



```
**<font color = "green" size = 8>Program = <font color = purple>Input</font> + <font color = blue>Data </font> + <font color = red>Operations</font> + <font color = purple>Output</font>**</font>
```

#### 5.6 DO / DON'T 模式

对于最佳实践，使用成对的幻灯片：



* **DO** 幻灯片：展示正确写法，每个示例后附简短说明

* **DON'T** 幻灯片：展示错误写法，用红色标注

标题格式：`# Array Initializer (DO)` / `# Array Initializer (DON'T)`

#### 5.7 表格对比

用 Markdown 表格做多方案对比，关键结论列用 `<mark>` 高亮，缺点用红色标注：



```
| 写法 | 作用域 | 泄漏? | 重复代码? |
|------|--------|:-----:|:---------:|
| 外部声明 | 整个函数 | <font color=red>是</font> | 否 |
| 分支内声明 | 单个分支 | 否 | <font color=red>是</font> |
| <mark>if 初始化器</mark> | 整个 if-else | <mark>否</mark> | <mark>否</mark> |
```

### 6. 内容与飞书文档的对应关系

飞书文档是完整的课堂讲义（详细讲解、代码示例、拓展阅读），PPT 是提炼后的投影材料。对应原则：



* 飞书文档中**每个一级 / 二级小节**，提炼为 1～3 张幻灯片

* **代码示例**：只提取核心代码行，不要贴完整程序；配合关键说明

* **图片 / 图表**：按需截取或自制

* **注意事项 / 常见错误**：单独一张幻灯片，用红色或 `Warning` 标注

* **C++ Core Guidelines 引用**：在相关幻灯片底部用 `<mark>` 标注，如 `Keep scopes small (CG ES.5)`

* **算法 / 概念类**：抽象为 "循环不变量" 等核心概念，用 `\boxed{}` 突出

### 7. 参考示例

以下 PPT 是本课程的标准风格参考，新 PPT 应与之一致：



| 讲次                       | 飞书文档                                                                 | 本地 PPT                          |
| ------------------------ | -------------------------------------------------------------------- | ------------------------------- |
| 0. Introducing C++       | [飞书](https://njusecourse.feishu.cn/wiki/IVfewixASiQIR6kbTsHcy2Twnsf) | `2026/0-intro/0-intro.md`       |
| 1. Variables, Types, I/O | [飞书](https://njusecourse.feishu.cn/wiki/Te8Ow2HnRikFfzkjEpxcRmyKn2d) | `2026/1-types-io/1-types-io.md` |
| 2. If $\ldots$           | [飞书](https://njusecourse.feishu.cn/wiki/UyiWwh9qaiXkeekffCXcZWGqnyh) | `2026/2-if/2-if.md`             |
| 3. While $\ldots$        | —                                                                    | `2026/3-while/3-while.md`       |

重点参考：



* **0-intro**：课堂互动、书籍推荐、评分等开场内容的风格

* **1-types-io**：代码讲解、格式说明、配色约定

* **2-if**：条件语句、逻辑表达式、switch/case 的展开方式

* **3-while**：循环不变量、`\boxed{}` 公式、多行代码块、自定义 `style:` 块



***

## 图片规范



* 存放位置：子目录下的 `figs/` 目录

* **来源**：自制（流程图、示意图）或权威来源（[cppreference](https://en.cppreference.com/)、Wikipedia、官方文档）

* **质量**：宽度 ≥ 800px（建议 1200px+），裁剪掉多余白边

* **格式**：PNG（截图 / 图表）或 JPG（照片 / 插画）

* **命名**：小写连字符，如 `while-semantics.png`、`euclid.jpeg`



***

## 已有内容的处理

如果指定子目录下的 `.md` PPT 文件**已存在且非空**：



1. **保留原有内容**，不得覆盖或删除

2. 默认在**末尾追加**新幻灯片

3. 也可以在已有内容之间插入（用户指定位置时）

4. **如果用户未明确指示方式，先询问**

如果 `.md` 文件不存在或为空，则从头创建（包含完整 frontmatter 和标题页）。



***

## 技术规范参考



* [Marp 官方文档](https://marpit.marp.app/) — Markdown 语法与指令

* [Marp Core](https://github.com/marp-team/marp-core) — 支持的 HTML 标签与 CSS

* [KaTeX 支持函数](https://katex.org/docs/supported.html) — 数学公式

* [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/) — 代码规范引用



***

## 输出交付



1. 在指定子目录下生成（或追加）`.md` 文件

2. 图片放入该子目录的 `figs/` 目录

3. 完成后简要汇报：新增幻灯片数量、覆盖了哪些飞书章节、使用了哪些图片、有无需用户确认之处

---

# Task: marp-export

## 中文：Marp 导出

## 任务描述

将指定的 Marp Markdown 文件导出为 PDF、PowerPoint (PPTX)、PNG 图片等格式，输出到 Markdown 文件所在目录。

---

## 输入参数

| 参数 | 说明 |
|------|------|
| **Marp Markdown 文件路径** | 相对于 `cpp-lectures` 仓库根目录的 `.md` 文件路径，如 `2026/4-for-a-while/4-for-a-while.md` |

---

## 执行前确认（必读）

1. **文件路径**：用户是否提供了有效的 `.md` 文件路径？该文件是否存在？
2. **导出格式**：默认导出全部格式（PDF + PPTX + PNG）。如用户指定了特定格式，按用户要求。
3. **覆盖确认**：如果目标目录下已存在同名的 PDF/PPTX/PNG 文件，导出会覆盖。如需保留旧版本，先询问用户。

---

## 导出方式

使用 `@marp-team/marp-cli`（VS Code Marp 插件底层工具）从仓库根目录执行导出。

### 导出命令

```powershell
cd <cpp-lectures 仓库根目录>
npx @marp-team/marp-cli@latest <相对路径/xxx.md> `
  --pdf --pptx --images png `
  --theme-set themes/2022cpl.css `
  --allow-local-files
```

### 参数说明

| 参数 | 作用 |
|------|------|
| `--pdf` | 导出 PDF |
| `--pptx` | 导出 PowerPoint (PPTX) |
| `--images png` | 将每张幻灯片导出为 PNG 图片 |
| `--theme-set themes/2022cpl.css` | 加载自定义主题（仓库根目录下的 themes/2022cpl.css） |
| `--allow-local-files` | 允许访问本地图片文件（figs/ 目录下的图片） |

### 输出文件

所有输出保存在 `.md` 文件所在目录，文件名与 `.md` 同名：

| 格式 | 输出文件 |
|------|----------|
| PDF | `xxx.pdf` |
| PowerPoint | `xxx.pptx` |
| PNG | `xxx.001.png`、`xxx.002.png`、...（每页一张） |
| HTML | `xxx.html`（如需导出，追加 `--html` 参数） |

---

## 注意事项

1. **工作目录**：必须在 `cpp-lectures` 仓库根目录下执行命令，否则 `themes/2022cpl.css` 和 `figs/` 相对路径会找不到。
2. **首次运行**：`npx` 会自动下载 marp-cli，首次可能需要等待较长时间。
3. **Chromium 依赖**：PDF 和 PPTX 导出需要 Chromium。如果报错缺少浏览器，执行 `npx puppeteer browsers install chrome`。
4. **自定义 style 块**：如果 `.md` 的 frontmatter 中包含 `style:` 块（如 3-while.md），marp-cli 会自动识别，无需额外参数。
5. **导出后验证**：导出完成后，检查输出文件是否存在且非空；如果 marp-cli 报错，根据错误信息排查（常见：图片路径错误、主题文件缺失、Chromium 未安装）。

---

## 输出交付

1. 在 `.md` 文件同目录下生成 PDF、PPTX、PNG 等文件
2. 完成后汇报：导出了哪些格式、共多少张幻灯片、是否有报错或警告