# LaTeX 学术写作零基础教程

结合顶级学术会议要求，为您提炼最常用、最核心的 LaTeX 语法规则。左侧学习语法，右侧实时预览公式，快速掌握排版技巧。

---

## 1. 导言：理解 LaTeX 的核心逻辑
**标签**: `核心逻辑`, `入门`

### Abstract
本指南旨在帮助初学者快速掌握 LaTeX 的核心概念与文档组织结构。与传统的“所见即所得”（WYSIWYG）文字处理软件（如 Word）不同，LaTeX 采用“内容与格式分离”的设计哲学。作者只需专注于学术内容的逻辑表达，而复杂的排版细节（如页码、交叉引用、公式样式、参考文献）则由系统自动完成。

---

## 2. LaTeX 文档的基本骨架
**标签**: `基本结构`, `模板`

### 2.1 核心结构
一个完整的 LaTeX 文档由两个核心部分组成：
* **导言区 (Preamble)**：从 `\documentclass` 开始到 `\begin{document}` 之前的部分。用于定义文档类型、加载宏包、设置全局样式及元数据。
* **正文区 (Document Body)**：位于 `document` 环境内部（即 `\begin{document}` 与 `\end{document}` 之间）。这里存放文章的实际内容。

### 2.2 基础模板
以下是写出一篇标准学术文章最基本的代码框架：

```latex
\documentclass[12pt, a4paper]{article} % 1. 文档声明

% --- 2. 导言区：配置中心 ---
\usepackage[utf8]{inputenc}
\usepackage{amsmath}  % 提供高级数学功能
\usepackage{amssymb}  % 提供数学符号
\title{学术论文排版示例}
\author{张三}
\date{\today}

% --- 3. 正文区：内容呈现 ---
\begin{document}
\maketitle             % 生成标题
\section{引言}
在此输入您的正文内容...
\end{document}
```

---

## 3. 导言区详解：文档的“指挥部”
**标签**: `导言区`, `宏包`

导言区定义了文档的全局规则。

### 3.1 文档类型 (Document Class)
常用类名包括：
* **article**：期刊论文、作业、短报告。
* **report**：较长的报告、毕业论文。
* **book**：正式书籍。
* **beamer**：学术演示文稿 (PPT)。

### 3.2 宏包加载 (Packages)
* `amsmath`, `amssymb`：数学排版核心。
* `graphicx`：插图支持。
* `geometry`：页边距设置。
* `booktabs`：学术三线表标准。
* `hyperref`：PDF 交互链接。

```latex
\usepackage{amsmath, amssymb}     % 核心数学包
\usepackage{graphicx}             % 插入图片
\usepackage[margin=1in]{geometry} % 设置页边距
\usepackage{booktabs}             % 专业表格
```

---

## 4. 正文区详解：内容的艺术
**标签**: `正文区`, `文本格式`, `章节`

### 4.1 文本格式设置
* **加粗**：`\textbf{文字}`
* *斜体*：`\textit{文字}`
* **等宽字体**：`\texttt{文字}`
* **改变字号**：`{\small 小字}`, `{\large 大字}`

```latex
\textbf{这是加粗文字}
\textit{这是斜体文字}
\texttt{这是等宽字体}
{\large 这是大号字}
```

### 4.2 层次化章节划分
LaTeX 会自动为章节编号并生成目录。标准的层级如下：
```latex
\section{引言}              % 1
\subsection{研究背景}       % 1.1
\subsubsection{国内外现状}   % 1.1.1
```

### 4.3 列表环境
* **itemize**：无序列表。
* **enumerate**：有序列表。
* **description**：关键词描述。

```latex
\begin{itemize}
  \item 第一项
  \item 第二项
\end{itemize}

\begin{enumerate}
  \item 第一步
  \item 第二步
\end{enumerate}
```

---

## 5. 数学表达式深度指南
**标签**: `数学公式`, `KaTeX`, `符号`

LaTeX 是排版复杂数学公式的黄金标准，其语法逻辑严密且具有高度可扩展性。以下将从 18 个维度深入剖析数学公式的排版技巧。

---

## 5.1 基本结构 (Basic Structure)
**标签**: `基础`, `公式模式`

LaTeX 提供行内与独立两种公式模式，这是所有数学排版的基础。
* **行内公式**：使用 `$ ... $`，公式将嵌入文字流中，如 `$E=mc^2$`。
* **独立公式**：使用 `\[ ... \]` 或 `$$ ... $$`，公式将独占一行并居中。
* **编号公式**：使用 `\begin{equation} ... \end{equation}` 环境，系统会自动为公式编号。

**示例**:
```latex
\text{行内公式示例：} \quad a^2 + b^2 = c^2 \\[12pt]
\text{独立公式示例：} \quad \int_0^1 x^2 \, dx = \frac{1}{3}
```

---

## 5.2 上标与下标 (Scripts)
**标签**: `基础语法`

上下标是数学公式中最常用的结构，通过 `^` 和 `_` 快速实现。
* **基本用法**：`x^2` → $x^2$ (上标)，`a_i` → $a_i$ (下标)。
* **多字符包裹**：如果内容超过一个字符，必须使用 `{}` 包裹，如 `x^{n+1}` → $x^{n+1}$，`a_{i,j}` → $a_{i,j}$。
* **组合使用**：`x_i^2` → $x_i^2$ 会同时显示上下标，顺序不限。

**示例**:
```latex
x_{i+1}^{2n} + a_{i,j} = \sum_{k=0}^{n} c_k x^k
```

---

## 5.3 分式与根式 (Fractions & Roots)
**标签**: `除法`, `开方`

分式与根式在学术排版中极其常见，LaTeX 提供了优雅的比例控制。
* **分式**：`\frac{a}{b}` → $\frac{a}{b}$。
* **强制大小**：行内推荐 `\tfrac{a}{b}` → $\tfrac{a}{b}$ (缩小) 或 `\dfrac{a}{b}` → $\dfrac{a}{b}$ (放大)。
* **根式**：`\sqrt{x}` → $\sqrt{x}$ 为二次根式，`\sqrt[3]{x}` → $\sqrt[3]{x}$ 为三次根式。

**示例**:
```latex
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
```

---

## 5.4 希腊字母 (Greek Letters)
**标签**: `符号`, `常用`

希腊字母是数学语言的核心组成部分。

**常用小写字母**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\alpha` | $\alpha$ | `\beta` | $\beta$ | `\gamma` | $\gamma$ | `\delta` | $\delta$ |
| `\epsilon` | $\epsilon$ | `\zeta` | $\zeta$ | `\eta` | $\eta$ | `\theta` | $\theta$ |
| `\lambda` | $\lambda$ | `\mu` | $\mu$ | `\pi` | $\pi$ | `\sigma` | $\sigma$ |
| `\phi` | $\phi$ | `\psi` | $\psi$ | `\omega` | $\omega$ | `\rho` | $\rho$ |

**常用大写字母**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\Gamma` | $\Gamma$ | `\Delta` | $\Delta$ | `\Theta` | $\Theta$ | `\Lambda` | $\Lambda$ |
| `\Sigma` | $\Sigma$ | `\Phi` | $\Phi$ | `\Psi` | $\Psi$ | `\Omega` | $\Omega$ |

**变体形式**：`\varepsilon` → $\varepsilon$，`\varphi` → $\varphi$，`\vartheta` → $\vartheta$

**示例**:
```latex
\Delta = \sum_{i=1}^n \alpha_i \cdot \beta_i + \gamma \omega
```

---

## 5.5 运算符 (Operators)
**标签**: `算术`, `逻辑`

除了基本的 `+, -, *, /`，LaTeX 提供了丰富的特殊算子。

**四则运算**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\pm` | $\pm$ | `\mp` | $\mp$ | `\times` | $\times$ | `\div` | $\div$ |
| `\cdot` | $\cdot$ | `\ast` | $\ast$ | `\star` | $\star$ | `\circ` | $\circ$ |

**特殊算子**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\oplus` | $\oplus$ | `\otimes` | $\otimes$ | `\odot` | $\odot$ | `\setminus` | $\setminus$ |

**省略号**：`\dots` → $\dots$，`\cdots` → $\cdots$，`\vdots` → $\vdots$，`\ddots` → $\ddots$

**示例**:
```latex
A \oplus B \otimes C \setminus \{ \emptyset \} \cdots D
```

---

## 5.6 关系符号 (Relations)
**标签**: `等式`, `包含`

描述变量之间的逻辑关系。

**比较关系**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\neq` | $\neq$ | `\approx` | $\approx$ | `\le` | $\le$ | `\ge` | $\ge$ |
| `\ll` | $\ll$ | `\gg` | $\gg$ | `\sim` | $\sim$ | `\simeq` | $\simeq$ |

**集合关系**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\in` | $\in$ | `\notin` | $\notin$ | `\subset` | $\subset$ | `\supset` | $\supset$ |
| `\subseteq` | $\subseteq$ | `\supseteq` | $\supseteq$ | `\equiv` | $\equiv$ | `\propto` | $\propto$ |

**示例**:
```latex
x \approx y \implies x \equiv y \pmod{n}
```

---

## 5.7 求和、积分与极限 (Calculus)
**标签**: `微积分`, `大型算子`

这些符号通常带有上下限。

**求和与乘积**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|
| `\sum` | $\sum$ | `\prod` | $\prod$ | `\coprod` | $\coprod$ |

**积分**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\int` | $\int$ | `\iint` | $\iint$ | `\iiint` | $\iiint$ | `\oint` | $\oint$ |

**极限**：`\lim_{x \to \infty}` → $\lim_{x \to \infty}$

> **注**：上下限会自动根据公式模式（行内/独立）调整位置。

**示例**:
```latex
\sum_{i=1}^\infty \frac{1}{i^2} = \frac{\pi^2}{6} \quad \text{and} \quad \int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
```

---

## 5.8 嵌套分式 (Nested Fractions)
**标签**: `分式`, `高级`

当分式层级较多时，普通 `\frac` 会使字体过小。
* **推荐**：使用 `\cfrac` (Continued Fraction) 保持各层级字体大小一致，常用于连分数。

**示例**:
```latex
x = a_0 + \cfrac{1}{a_1 + \cfrac{1}{a_2 + \cfrac{1}{a_3 + \dots}}}
```

---

## 5.9 括号与分隔符 (Delimiters)
**标签**: `括号`, `自适应`

普通括号 `()` 不会自动缩放。
* **自动缩放**：使用 `\left(` 和 `\right)`。支持 `()`, `[]`, `\{\}`, `\vert` (绝对值), `\Vert` (范数)。
* **单边括号**：使用 `.\ ` 匹配缺失的一边，如 `\left\{ ... \right.`。

**示例**:
```latex
P = \left( \sum_{i=1}^n x_i \right)^2 \le n \sum_{i=1}^n x_i^2
```

---

## 5.10 函数 (Functions)
**标签**: `直立字体`

数学函数名应使用直立罗马字体，而非斜体变量形式。

**内置函数一览**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\sin` | $\sin$ | `\cos` | $\cos$ | `\tan` | $\tan$ | `\exp` | $\exp$ |
| `\log` | $\log$ | `\ln` | $\ln$ | `\min` | $\min$ | `\max` | $\max$ |
| `\det` | $\det$ | `\ker` | $\ker$ | `\lim` | $\lim$ | `\inf` | $\inf$ |

* **自定义函数**：若内置没有，可用 `\operatorname{softmax}` → $\mathrm{softmax}$。

**示例**:
```latex
\ln(x) + \sin^2(\theta) + \cos^2(\theta) = 1
```

---

## 5.11 向量与矩阵 (Matrices)
**标签**: `线性代数`, `环境`

矩阵排版是 LaTeX 的强项。

**向量表示**：`\vec{a}` → $\vec{a}$，`\mathbf{v}` → $\mathbf{v}$

**矩阵环境**：

| 环境 | 说明 | 示例渲染 |
|------|------|------|
| `pmatrix` | 圆括号 | $\begin{pmatrix} a & b \end{pmatrix}$ |
| `bmatrix` | 方括号 | $\begin{bmatrix} a & b \end{bmatrix}$ |
| `vmatrix` | 行列式 | $\begin{vmatrix} a & b \end{vmatrix}$ |
| `Bmatrix` | 花括号 | $\begin{Bmatrix} a & b \end{Bmatrix}$ |

**示例**:
```latex
\mathbf{A} = \begin{bmatrix} a & b \\ c & d \end{bmatrix}, \quad \det(\mathbf{A}) = \begin{vmatrix} a & b \\ c & d \end{vmatrix}
```

---

## 5.12 对齐 / 多行公式 (Alignment)
**标签**: `对齐`, `多行`

推导过程需要多行对齐。
* **环境**：使用 `aligned` (在数学模式内)。
* **语法**：`&` 标记对齐位置（通常在等号前），`\\ ` 强制换行。

**示例**:
```latex
\begin{aligned} 
(a+b)^2 &= (a+b)(a+b) \\ 
&= a^2 + ab + ba + b^2 \\ 
&= a^2 + 2ab + b^2 
\end{aligned}
```

---

## 5.13 分段函数 (Piecewise)
**标签**: `条件`, `环境`

用于定义分段逻辑。
* **环境**：使用 `cases` 环境。
* **结构**：每行以 `条件` 结尾，用 `&` 分隔公式与条件。

**示例**:
```latex
f(n) = \begin{cases} 
n/2, & \text{if } n \text{ is even} \\ 
3n+1, & \text{if } n \text{ is odd} 
\end{cases}
```

---

## 5.14 标注符号 (Accents)
**标签**: `修饰`, `变量`

在变量上方添加修饰符。

**单字符标注**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|
| `\hat{a}` | $\hat{a}$ | `\bar{a}` | $\bar{a}$ | `\tilde{a}` | $\tilde{a}$ |
| `\dot{a}` | $\dot{a}$ | `\ddot{a}` | $\ddot{a}$ | `\vec{a}` | $\vec{a}$ |

**宽标注**：`\widehat{ABC}` → $\widehat{ABC}$，`\overline{ABC}` → $\overline{ABC}$，`\underbrace{x+y}` → $\underbrace{x+y}$，`\overbrace{x+y}` → $\overbrace{x+y}$

**示例**:
```latex
\hat{y} = \theta_0 + \theta_1 \bar{x} + \tilde{\epsilon}
```

---

## 5.15 箭头 (Arrows)
**标签**: `逻辑推导`, `映射`

表达方向与逻辑流。

**常用箭头**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|
| `\to` | $\to$ | `\leftarrow` | $\leftarrow$ | `\uparrow` | $\uparrow$ |
| `\downarrow` | $\downarrow$ | `\leftrightarrow` | $\leftrightarrow$ | `\Leftrightarrow` | $\Leftrightarrow$ |
| `\mapsto` | $\mapsto$ | `\implies` | $\implies$ | `\iff` | $\iff$ |
| `\Rightarrow` | $\Rightarrow$ | `\Leftarrow` | $\Leftarrow$ | `\hookrightarrow` | $\hookrightarrow$ |

**示例**:
```latex
A \xrightarrow{f} B \leftrightarrow C \implies D
```

---

## 5.16 集合与逻辑 (Sets & Logic)
**标签**: `集合`, `量词`

离散数学与形式逻辑常用符号。

**量词**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|
| `\forall` | $\forall$ | `\exists` | $\exists$ | `\nexists` | $\nexists$ |

**逻辑连接符**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\land` | $\land$ | `\lor` | $\lor$ | `\neg` | $\neg$ | `\therefore` | $\therefore$ |
| `\because` | $\because$ | `\implies` | $\implies$ | `\iff` | $\iff$ | | |

**集合运算**：

| 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 | 源码 | 渲染 |
|------|------|------|------|------|------|------|------|
| `\emptyset` | $\emptyset$ | `\cup` | $\cup$ | `\cap` | $\cap$ | `\complement` | $\complement$ |

**示例**:
```latex
\forall x \in \mathbb{R}, \exists y > x : y = x + \delta
```

---

## 5.17 数学模式中的文本 (Text)
**标签**: `中文字符`, `单位`

在数学公式中直接输入文本会变成斜体且间距异常。
* **解决方法**：使用 `\text{...}` 插入普通文本或中文字符。
* **样式**：`\mathrm, \mathbf, \mathsf` 也可以用于切换字体样式。

**示例**:
```latex
v = \frac{d}{t} \quad \text{(速度 = 距离 / 时间)}
```

---

## 5.18 间距 (Spacing)
**标签**: `微调`, `排版`

手动微调公式间的空隙。
* **正间距**：`\,` (极小), `\;` (中), `\quad` (一个字符), `\qquad` (两个字符)。
* **负间距**：`\!` (缩小间距，常用于积分号与被积函数间)。

**示例**:
```latex
\int f(x) dx \quad \text{vs} \quad \int f(x) \, dx
```

---

## 6. 专业规范：学术三线表
**标签**: `三线表`, `表格`

学术论文通常严禁使用纵线。通过加载 `booktabs` 宏包，可以制作优雅的三线表：
* `\toprule`：顶部粗线。
* `\midrule`：表头下方的细线。
* `\bottomrule`：底部粗线。

*(注：为方便实时预览，下方示例使用 array 环境模拟效果)*

**示例**:
```latex
\begin{array}{ccc}
\hline
\textbf{Method} & \textbf{Accuracy} & \textbf{F1-Score} \\
\hline
\text{Baseline} & 85.2\% & 0.84 \\
\text{Ours} & 92.4\% & 0.91 \\
\hline
\end{array}
```

---

## 7. 图片插入与排版
**标签**: `插图`, `graphicx`, `浮动体`

### 7.1 宏包引入
在 LaTeX 中，我们使用 `graphicx` 宏包来处理图像。

### 7.2 基础命令
最核心的命令是 `\includegraphics[选项]{文件名}`。

### 7.3 标准插图环境
学术论文通常将图片放在 `figure` 浮动环境中，以便系统自动优化排版位置并添加标题。

```latex
\usepackage{graphicx} % 导言区加载

\begin{figure}[htbp]
  \centering % 居中
  \includegraphics[width=0.7\textwidth]{figure_name}
  \caption{图题内容}
  \label{fig:example} % 标签用于交叉引用
\end{figure}
```

---

## 8. 超链接与 PDF 交互
**标签**: `hyperref`, `URL`, `跳转`

### 8.1 宏包功能
`hyperref` 宏包能够将文档内的引用（如目录、图表引用）转化为可点击的超链接，并支持外部 URL。

### 8.2 常用语法
* **自动显示链接**：`\url{https://...}`
* **自定义显示文本**：`\href{URL}{显示文字}`

```latex
\usepackage[colorlinks=true, linkcolor=blue]{hyperref} % 建议配置

相关资源请参考 \href{https://www.latex-project.org}{LaTeX 官网}。
或者直接访问 \url{https://ctan.org}。
```

---

## 9. 交叉引用：自动化的灵魂
**标签**: `label`, `ref`, `自动编号`

### 9.1 核心逻辑
LaTeX 的交叉引用遵循“标签-引用”机制。无论章节或图表如何重新排序，编号都会自动更新，无需手动维护。

### 9.2 实现步骤
1. **打标签**：在目标位置使用 `\label{unique_key}`。
2. **引标签**：在正文中使用 `\ref{unique_key}` 引用编号，`\pageref{unique_key}` 引用页码。

```latex
\section{方法论} \label{sec:method}

如第 \ref{sec:method} 节所述，我们在公式 (\ref{eq:mass}) 中定义了能量守恒。

\begin{equation}
  E = mc^2 \label{eq:mass}
\end{equation}
```

---

## 10. 参考文献管理 (BibTeX)
**标签**: `BibTeX`, `cite`, `学术规范`

### 10.1 文献数据库
将所有参考文献以特定的 BibTeX 格式保存在 `.bib` 文件中（如 `refs.bib`）。

### 10.2 正文引用
使用 `\cite{key}` 命令引用文献，系统会自动处理引用格式。

### 10.3 生成列表
在文档末尾指定引用样式并加载数据库文件。

```latex
% 1. 正文引用
根据 Knuth 的经典研究 \cite{knuth1984}...

% 2. 文档末尾生成列表
\bibliographystyle{plain} % 样式选择：plain, alpha, unsrt, IEEEtran 等
\bibliography{refs}      % 加载当前目录下的 refs.bib 文件
```

---

## 11. 综合实战：完整学术页面示例
**标签**: `实战`, `模板`

掌握 LaTeX 结构化写作是学术研究的基本功。以下是一个完整的代码框架，涵盖了文档结构、数学公式及表格排版等核心要素。

```latex
\documentclass[11pt, a4paper]{article}
\usepackage{amsmath}
\usepackage{booktabs}
\title{基于 LaTeX 的学术写作实践}
\author{Antigravity 研究组}
\begin{document}
\maketitle
\begin{abstract}
本文展示了 LaTeX 在学术写作中的基本应用...
\end{abstract}
\section{核心公式}
\[ E = mc^2 \]
\end{document}
```

**示例**:
```latex
\begin{aligned}
\text{掌握 LaTeX} & \to \text{专注研究} \\
\text{自动化排版} & \to \text{提升效率}
\end{aligned}
```
