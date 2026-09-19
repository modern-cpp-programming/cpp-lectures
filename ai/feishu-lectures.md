# Task: feishu-ppt

## 中文：根据飞书文档制作 C++ 课堂 PPT

## 任务描述

指定一篇飞书文档（wiki/docx 链接），指定 `cpp-lectures` 仓库下的子目录路径，根据该飞书文档的内容，在指定子目录下自动生成课堂所用的 Marp 幻灯片 Markdown 文件（`.md`）。

---

## 输入参数

| 参数 | 说明 |
|------|------|
| **飞书文档链接** | 形如 `https://njusecourse.feishu.cn/wiki/xxxx` 的 wiki 链接 |
| **子目录路径** | 相对于 `cpp-lectures` 仓库根目录的子目录路径，如 `2026/3-control-flow` |

---

## 执行前确认（必读）

在执行任务之前，必须确认以下信息全部齐备。**缺失任何一项都不得猜测或假设**，必须以提问方式向用户逐一确认，待用户回复后再开始执行：

1. **飞书文档链接**：用户是否提供了有效的 wiki/docx 链接？如果用户只给了讲义名称（如"第 3 讲"）或本地 `.md` 文件路径，需追问对应的飞书文档 wiki 链接。
2. **仓库子目录路径**：用户是否明确指定了 `cpp-lectures` 仓库下的目标子目录？（如 `2026/3-control-flow`）
3. **追加/新建模式**：目标 `.md` 文件是否已存在且非空？如果已存在，用户是否明确指示了操作方式（追加到末尾 / 插入到特定位置 / 整合重排）？未明确则需询问。

> 原则：宁可多问一句，不可擅自假设。用户提供的信息模糊或不完整时，先提问澄清，再动手执行。

---

## PPT 风格规范

### 1. 整体风格

- **基于 Marp** 的 Markdown 幻灯片，使用仓库自定义主题 `2022cpl`（定义于 `themes/2022cpl.css`，内置导入 gaia 主题）
- **极简风格**：仅展示最关键的知识点，每张幻灯片聚焦一个核心概念，避免大段文字堆砌
- **知识点醒目**：使用 `<mark>` 高亮、彩色字体、大号字等手段让重点信息在投影时清晰可辨

### 2. Frontmatter（每篇 .md 必须包含）

```yaml
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

> 注意：不要随意修改 `theme`、`backgroundColor`、`size` 等全局配置；如需页眉（header），参考 `0-intro.md` 中被注释掉的写法。

### 3. 标题页

每页第一页（标题页）应包含：
- 课程编号与标题，使用 `<p id="small-caps">` 包裹（小大写样式）
- 作者信息：`[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)` 及邮箱 `hfwei@hnu.edu.cn`
- C++ Logo 图片：`![w:200](figs/cpp-logo.png)`
- 授课日期

示例：
```markdown
# <p id = "small-caps">3. &nbsp; Control Flow</p>

[Hengfeng Wei (魏恒峰)](https://hengxin.github.io/)
hfwei@hnu.edu.cn

![w:200](figs/cpp-logo.png)
Oct. 09, 2026
```

### 4. 内容排版技巧

以下为本课程 PPT 的惯用写法，新生成的幻灯片应遵循：

- **分页符**：幻灯片之间使用 `---` 分隔
- **图片宽度**：使用 `![w:XXX](figs/filename.png)` 指定宽度（像素），根据内容调整
- **背景图片**：使用 `![bg 80%](figs/filename.jpg)` 或 `![bg right 90%](figs/filename.jpg)` 等语法
- **高亮重点**：使用 `<mark>重点内容</mark>` 标注关键术语
- **彩色字体**：使用 `<font color="red">` / `blue` / `green` / `purple` 等区分不同类别的内容
  - 推荐配色约定：`Input/Output` 用 purple，`Data` 用 blue，`Operations` 用 red，总结性语句用 green
- **代码高亮**：行内代码使用 `<code><font color="yellow" size="7">int x{0};</font></code>`，关键部分可再嵌套 `<font color="red">`
- **数学公式**：使用 KaTeX 语法，行内 `$...$`，独立行 `$$...$$`
- **双栏布局**：使用 `<div class="columns">` 包裹左右两栏
- **适应幻灯片**：内容过多时在标题后加 `# <!--fit-->` 自动缩放
- **注释掉的幻灯片**：使用 `<!-- --- ... --- -->` 包裹，保留备用但不渲染

### 5. 内容与飞书文档的对应关系

飞书文档是完整的课堂讲义（详细讲解、代码示例、拓展阅读），PPT 是提炼后的投影材料。对应关系原则：

- 飞书文档中的**每个一级/二级小节**，提炼为 1～3 张幻灯片
- 飞书文档中的**代码示例**，提取核心代码行放在幻灯片上，辅以关键说明
- 飞书文档中的**图片/图表**，按需截取或重新制作为 PPT 图片
- 飞书文档中的**拓展内容/注意事项**，可合并为一张"注意"或"Warning"幻灯片
- 参考已有对应关系：
  - 飞书 [0-intro](https://njusecourse.feishu.cn/wiki/IVfewixASiQIR6kbTsHcy2Twnsf) ↔ [`2026/0-intro/0-intro.md`](../2026/0-intro/0-intro.md)
  - 飞书 [1-types-io](https://njusecourse.feishu.cn/wiki/Te8Ow2HnRikFfzkjEpxcRmyKn2d) ↔ [`2026/1-types-io/1-types-io.md`](../2026/1-types-io/1-types-io.md)

---

## 图片规范

- 存放位置：子目录下的 `figs/` 目录（如 `2026/3-control-flow/figs/`）
- **来源要求**：
  - 可自制（如使用绘图工具制作流程图、示意图）
  - 可从权威来源下载（如 [cppreference.com](https://en.cppreference.com/)、Wikipedia、官方文档）
  - 禁止来源不明的低质量图片
- **质量要求**：
  - 分辨率要高（宽度不低于 800px，建议 1200px 以上）
  - 图片外围不要有大片空白（裁剪掉多余白边）
  - 格式优先 PNG（截图/图表）或 JPG（照片/插画）
- **命名**：使用小写字母、连字符分隔的描述性文件名，如 `loop-flowchart.png`、`ascii-table.jpg`

---

## 已有内容的处理

如果指定子目录下的 `.md` PPT 文件**已存在且非空**：

1. **保留原有内容**，不得覆盖或删除
2. 默认在**末尾追加**新生成的幻灯片
3. 也可以在已有内容之间进行整合（插入新幻灯片到合适位置）
4. **如果用户未明确指示追加方式，则先询问用户**：是追加到末尾，还是在特定位置插入，或是需要整合重排

如果 `.md` 文件不存在或为空，则从头创建。

---

## 技术规范参考

- [Marp 官方文档](https://marpit.marp.app/) — Marp Markdown 语法与指令
- [Marp Core](https://github.com/marp-team/marp-core) — 支持的 HTML 标签与 CSS 功能
- [Marpit 的 CSS 主题指南](https://marpit.marp.app/theme-css) — 如需自定义样式
- KaTeX 数学公式语法：参考 [KaTeX 支持的函数](https://katex.org/docs/supported.html)

---

## 输出交付

1. 在指定子目录下生成（或追加）`.md` 文件
2. 图片放入该子目录的 `figs/` 目录
3. 完成后简要汇报：生成了多少张幻灯片、使用了哪些图片、是否有需要用户确认的地方
