# LaTeX Academic Writing: A Beginner's Tutorial

Refining the most common and core LaTeX syntax rules based on top academic conference requirements. Learn the syntax on the left and preview the formulas in real-time on the right to quickly master typesetting techniques.

---

## 1. Introduction: Understanding the Core Logic of LaTeX
**Tags**: `Core Logic`, `Getting Started`

### Abstract
This guide is designed to help beginners quickly grasp the core concepts and document organization structure of LaTeX. Unlike traditional "What You See Is What You Get" (WYSIWYG) word processing software (such as Microsoft Word), LaTeX adopts the design philosophy of "Separation of Content and Format." Authors only need to focus on the logical expression of academic content, while complex typesetting details (such as page numbers, cross-references, formula styles, and bibliographies) are automatically completed by the system.

---

## 2. The Basic Skeleton of a LaTeX Document
**Tags**: `Basic Structure`, `Template`

### 2.1 Core Structure
A complete LaTeX document consists of two core parts:
* **Preamble**: The part starting from `\documentclass` until `\begin{document}`. It is used to define the document type, load packages, set global styles, and metadata.
* **Document Body**: Located inside the `document` environment (i.e., between `\begin{document}` and `\end{document}`). This is where the actual content of the article is stored.

### 2.2 Basic Template
Below is the most basic code framework for writing a standard academic article:

```latex
\documentclass[12pt, a4paper]{article} % 1. Document Declaration

% --- 2. Preamble: Configuration Center ---
\usepackage[utf8]{inputenc}
\usepackage{amsmath}  % Provides advanced mathematical functions
\usepackage{amssymb}  % Provides mathematical symbols
\title{Academic Paper Typesetting Example}
\author{John Doe}
\date{\today}

% --- 3. Document Body: Content Presentation ---
\begin{document}
\maketitle             % Generate the title
\section{Introduction}
Enter your body content here...
\end{document}
```

---

## 3. Preamble in Detail: The "Command Center"
**Tags**: `Preamble`, `Packages`

The preamble defines the global rules for the document.

### 3.1 Document Class
Common class names include:
* **article**: For journal articles, assignments, and short reports.
* **report**: For longer reports and dissertations.
* **book**: For formal books.
* **beamer**: For academic presentations (slides).

### 3.2 Loading Packages
* `amsmath`, `amssymb`: Core for mathematical typesetting.
* `graphicx`: Support for inserting images.
* `geometry`: Page margin settings.
* `booktabs`: Standard for academic three-line tables.
* `hyperref`: Interactive links in PDFs.

```latex
\usepackage{amsmath, amssymb}     % Core math packages
\usepackage{graphicx}             % Inserting images
\usepackage[margin=1in]{geometry} % Setting margins
\usepackage{booktabs}             % Professional tables
```

---

## 4. Document Body in Detail: The Art of Content
**Tags**: `Document Body`, `Text Formatting`, `Sections`

### 4.1 Text Formatting
* **Bold**: `\textbf{text}`
* *Italic*: `\textit{text}`
* **Monospace**: `\texttt{text}`
* **Changing Font Size**: `{\small small text}`, `{\large large text}`

```latex
\textbf{This is bold text}
\textit{This is italic text}
\texttt{This is monospace font}
{\large This is large text}
```

### 4.2 Hierarchical Sectioning
LaTeX automatically numbers sections and generates a table of contents. Standard levels are as follows:
```latex
\section{Introduction}              % 1
\subsection{Research Background}    % 1.1
\subsubsection{Current State}       % 1.1.1
```

### 4.3 Lists
* **itemize**: Unordered lists.
* **enumerate**: Ordered lists.
* **description**: Keyword descriptions.

```latex
\begin{itemize}
  \item First item
  \item Second item
\end{itemize}

\begin{enumerate}
  \item Step one
  \item Step two
\end{enumerate}
```

---

## 5. In-depth Guide to Mathematical Expressions
**Tags**: `Math Formulas`, `KaTeX`, `Symbols`

LaTeX is the gold standard for typesetting complex mathematical formulas, with a rigorous syntax logic and high extensibility. Below is an in-depth analysis of mathematical formula typesetting techniques from 18 dimensions.

---

## 5.1 Basic Structure
**Tags**: `Basics`, `Formula Mode`

LaTeX provides two formula modes: inline and display, which are the foundations of all mathematical typesetting.
* **Inline Formula**: Use `$ ... $`. Formulas are embedded in the text flow, e.g., `$E=mc^2$`.
* **Display Formula**: Use `\[ ... \]` or `$$ ... $$`. Formulas occupy a single line and are centered.
* **Numbered Formula**: Use the `\begin{equation} ... \end{equation}` environment. The system will automatically number the formula.

**Example**:
```latex
\text{Inline formula example:} \quad a^2 + b^2 = c^2 \\[12pt]
\text{Display formula example:} \quad \int_0^1 x^2 \, dx = \frac{1}{3}
```

---

## 5.2 Superscripts and Subscripts
**Tags**: `Basic Syntax`

Superscripts and subscripts are the most common structures in mathematical formulas, quickly implemented via `^` and `_`.
* **Basic Usage**: `x^2` → $x^2$ (superscript), `a_i` → $a_i$ (subscript).
* **Multi-character Wrappings**: If the content exceeds one character, it must be wrapped in `{}`, e.g., `x^{n+1}` → $x^{n+1}$, `a_{i,j}` → $a_{i,j}$.
* **Combined Use**: `x_i^2` → $x_i^2$ displays both, the order doesn't matter.

**Example**:
```latex
x_{i+1}^{2n} + a_{i,j} = \sum_{k=0}^{n} c_k x^k
```

---

## 5.3 Fractions and Roots
**Tags**: `Division`, `Roots`

Fractions and roots are extremely common in academic typesetting. LaTeX provides elegant proportion control.
* **Fractions**: `\frac{a}{b}` → $\frac{a}{b}$.
* **Forcing Size**: For inline, `\tfrac{a}{b}` → $\tfrac{a}{b}$ (small) or `\dfrac{a}{b}` → $\dfrac{a}{b}$ (large) is recommended.
* **Roots**: `\sqrt{x}` → $\sqrt{x}$ for square roots, `\sqrt[3]{x}` → $\sqrt[3]{x}$ for cube roots.

**Example**:
```latex
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
```

---

## 5.4 Greek Letters
**Tags**: `Symbols`, `Commonly Used`

Greek letters are a core component of mathematical language.

**Common Lowercase Letters**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\alpha` | $\alpha$ | `\beta` | $\beta$ | `\gamma` | $\gamma$ | `\delta` | $\delta$ |
| `\epsilon` | $\epsilon$ | `\zeta` | $\zeta$ | `\eta` | $\eta$ | `\theta` | $\theta$ |
| `\lambda` | $\lambda$ | `\mu` | $\mu$ | `\pi` | $\pi$ | `\sigma` | $\sigma$ |
| `\phi` | $\phi$ | `\psi` | $\psi$ | `\omega` | $\omega$ | `\rho` | $\rho$ |

**Common Uppercase Letters**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\Gamma` | $\Gamma$ | `\Delta` | $\Delta$ | `\Theta` | $\Theta$ | `\Lambda` | $\Lambda$ |
| `\Sigma` | $\Sigma$ | `\Phi` | $\Phi$ | `\Psi` | $\Psi$ | `\Omega` | $\Omega$ |

**Variant Forms**: `\varepsilon` → $\varepsilon$, `\varphi` → $\varphi$, `\vartheta` → $\vartheta$

**Example**:
```latex
\Delta = \sum_{i=1}^n \alpha_i \cdot \beta_i + \gamma \omega
```

---

## 5.5 Operators
**Tags**: `Arithmetic`, `Logic`

In addition to basic `+, -, *, /`, LaTeX provides a wealth of special operators.

**Arithmetic Operations**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\pm` | $\pm$ | `\mp` | $\mp$ | `\times` | $\times$ | `\div` | $\div$ |
| `\cdot` | $\cdot$ | `\ast` | $\ast$ | `\star` | $\star$ | `\circ` | $\circ$ |

**Special Operators**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\oplus` | $\oplus$ | `\otimes` | $\otimes$ | `\odot` | $\odot$ | `\setminus` | $\setminus$ |

**Ellipses**: `\dots` → $\dots$, `\cdots` → $\cdots$, `\vdots` → $\vdots$, `\ddots` → $\ddots$

**Example**:
```latex
A \oplus B \otimes C \setminus \{ \emptyset \} \cdots D
```

---

## 5.6 Relation Symbols
**Tags**: `Equations`, `Inclusion`

Describe the logical relationships between variables.

**Comparison Relations**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\neq` | $\neq$ | `\approx` | $\approx$ | `\le` | $\le$ | `\ge` | $\ge$ |
| `\ll` | $\ll$ | `\gg` | $\gg$ | `\sim` | $\sim$ | `\simeq` | $\simeq$ |

**Set Relations**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\in` | $\in$ | `\notin` | $\notin$ | `\subset` | $\subset$ | `\supset` | $\supset$ |
| `\subseteq` | $\subseteq$ | `\supseteq` | $\supseteq$ | `\equiv` | $\equiv$ | `\propto` | $\propto$ |

**Example**:
```latex
x \approx y \implies x \equiv y \pmod{n}
```

---

## 5.7 Sums, Integrals, and Limits
**Tags**: `Calculus`, `Large Operators`

These symbols usually carry upper and lower limits.

**Sums and Products**:

| Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|
| `\sum` | $\sum$ | `\prod` | $\prod$ | `\coprod` | $\coprod$ |

**Integrals**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\int` | $\int$ | `\iint` | $\iint$ | `\iiint` | $\iiint$ | `\oint` | $\oint$ |

**Limits**: `\lim_{x \to \infty}` → $\lim_{x \to \infty}$

> **Note**: Upper and lower limits will automatically adjust position based on the formula mode (inline/display).

**Example**:
```latex
\sum_{i=1}^\infty \frac{1}{i^2} = \frac{\pi^2}{6} \quad \text{and} \quad \int_{-\infty}^{\infty} e^{-x^2} dx = \sqrt{\pi}
```

---

## 5.8 Nested Fractions
**Tags**: `Fractions`, `Advanced`

When there are many fraction levels, normal `\frac` will make the font too small.
* **Recommendation**: Use `\cfrac` (Continued Fraction) to maintain consistent font size across levels, commonly used for continued fractions.

**Example**:
```latex
x = a_0 + \cfrac{1}{a_1 + \cfrac{1}{a_2 + \cfrac{1}{a_3 + \dots}}}
```

---

## 5.9 Brackets and Delimiters
**Tags**: `Brackets`, `Adaptive`

Normal brackets `()` do not scale automatically.
* **Auto-scaling**: Use `\left(` and `\right)`. Supports `()`, `[]`, `\{\}`, `\vert` (absolute value), `\Vert` (norm).
* **Single-sided Brackets**: Use `.\ ` to match a missing side, e.g., `\left\{ ... \right.`.

**Example**:
```latex
P = \left( \sum_{i=1}^n x_i \right)^2 \le n \sum_{i=1}^n x_i^2
```

---

## 5.10 Functions
**Tags**: `Upright Font`

Mathematical function names should use an upright Roman font, not the italic variable form.

**Built-in Functions Overview**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\sin` | $\sin$ | `\cos` | $\cos$ | `\tan` | $\tan$ | `\exp` | $\exp$ |
| `\log` | $\log$ | `\ln` | $\ln$ | `\min` | $\min$ | `\max` | $\max$ |
| `\det` | $\det$ | `\ker` | $\ker$ | `\lim` | $\lim$ | `\inf` | $\inf$ |

* **Custom Functions**: If not built-in, use `\operatorname{softmax}` → $\operatorname{softmax}$.

**Example**:
```latex
\ln(x) + \sin^2(\theta) + \cos^2(\theta) = 1
```

---

## 5.11 Vectors and Matrices
**Tags**: `Linear Algebra`, `Environment`

Matrix typesetting is a strong point of LaTeX.

**Vector Representation**: `\vec{a}` → $\vec{a}$, `\mathbf{v}` → $\mathbf{v}$

**Matrix Environments**:

| Environment | Description | Example Render |
|------|------|------|
| `pmatrix` | Parentheses | $\begin{pmatrix} a & b \end{pmatrix}$ |
| `bmatrix` | Square brackets | $\begin{bmatrix} a & b \end{bmatrix}$ |
| `vmatrix` | Determinant | $\begin{vmatrix} a & b \end{vmatrix}$ |
| `Bmatrix` | Braces | $\begin{Bmatrix} a & b \end{Bmatrix}$ |

**Example**:
```latex
\mathbf{A} = \begin{bmatrix} a & b \\ c & d \end{bmatrix}, \quad \det(\mathbf{A}) = \begin{vmatrix} a & b \\ c & d \end{vmatrix}
```

---

## 5.12 Alignment / Multi-line Formulas
**Tags**: `Alignment`, `Multi-line`

Derivations often require multi-line alignment.
* **Environment**: Use `aligned` (inside math mode).
* **Syntax**: `&` marks the alignment position (usually before the equals sign), `\\ ` forces a new line.

**Example**:
```latex
\begin{aligned} 
(a+b)^2 &= (a+b)(a+b) \\ 
&= a^2 + ab + ba + b^2 \\ 
&= a^2 + 2ab + b^2 
\end{aligned}
```

---

## 5.13 Piecewise Functions
**Tags**: `Conditions`, `Environment`

Used to define piecewise logic.
* **Environment**: Use the `cases` environment.
* **Structure**: Each line ends with a `condition`, using `&` to separate the formula and the condition.

**Example**:
```latex
f(n) = \begin{cases} 
n/2, & \text{if } n \text{ is even} \\ 
3n+1, & \text{if } n \text{ is odd} 
\end{cases}
```

---

## 5.14 Accents
**Tags**: `Decorations`, `Variables`

Add modifiers above variables.

**Single-character Accents**:

| Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|
| `\hat{a}` | $\hat{a}$ | `\bar{a}` | $\bar{a}$ | `\tilde{a}` | $\tilde{a}$ |
| `\dot{a}` | $\dot{a}$ | `\ddot{a}` | $\ddot{a}$ | `\vec{a}` | $\vec{a}$ |

**Wide Accents**: `\widehat{ABC}` → $\widehat{ABC}$, `\overline{ABC}` → $\overline{ABC}$, `\underbrace{x+y}` → $\underbrace{x+y}$, `\overbrace{x+y}` → $\overbrace{x+y}$

**Example**:
```latex
\hat{y} = \theta_0 + \theta_1 \bar{x} + \tilde{\epsilon}
```

---

## 5.15 Arrows
**Tags**: `Logical Derivation`, `Mapping`

Express direction and logical flow.

**Common Arrows**:

| Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|
| `\to` | $\to$ | `\leftarrow` | $\leftarrow$ | `\uparrow` | $\uparrow$ |
| `\downarrow` | $\downarrow$ | `\leftrightarrow` | $\leftrightarrow$ | `\Leftrightarrow` | $\Leftrightarrow$ |
| `\mapsto` | $\mapsto$ | `\implies` | $\implies$ | `\iff` | $\iff$ |
| `\Rightarrow` | $\Rightarrow$ | `\Leftarrow` | $\Leftarrow$ | `\hookrightarrow` | $\hookrightarrow$ |

**Example**:
```latex
A \xrightarrow{f} B \leftrightarrow C \implies D
```

---

## 5.16 Sets and Logic
**Tags**: `Sets`, `Quantifiers`

Common symbols in discrete mathematics and formal logic.

**Quantifiers**:

| Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|
| `\forall` | $\forall$ | `\exists` | $\exists$ | `\nexists` | $\nexists$ |

**Logical Connectives**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\land` | $\land$ | `\lor` | $\lor$ | `\neg` | $\neg$ | `\therefore$ | $\therefore$ |
| `\because` | $\because$ | `\implies` | $\implies$ | `\iff` | $\iff$ | | |

**Set Operations**:

| Code | Render | Code | Render | Code | Render | Code | Render |
|------|------|------|------|------|------|------|------|
| `\emptyset` | $\emptyset$ | `\cup` | $\cup$ | `\cap` | $\cap$ | `\complement` | $\complement$ |

**Example**:
```latex
\forall x \in \mathbb{R}, \exists y > x : y = x + \delta
```

---

## 5.17 Text in Math Mode
**Tags**: `Characters`, `Units`

Typing text directly in a math formula will result in italics and unusual spacing.
* **Solution**: Use `\text{...}` to insert normal text or specific characters.
* **Styles**: `\mathrm, \mathbf, \mathsf` can also be used to switch font styles.

**Example**:
```latex
v = \frac{d}{t} \quad \text{(velocity = distance / time)}
```

---

## 5.18 Spacing
**Tags**: `Fine-tuning`, `Typesetting`

Manually fine-tune the gaps between formula elements.
* **Positive Spacing**: `\,` (tiny), `\;` (medium), `\quad` (one character), `\qquad` (two characters).
* **Negative Spacing**: `\!` (shrink space, often used between integral signs and integrands).

**Example**:
```latex
\int f(x) dx \quad \text{vs} \quad \int f(x) \, dx
```

---

## 6. Professional Standards: Academic Three-Line Tables
**Tags**: `Three-line Table`, `Tables`

Academic papers generally forbid the use of vertical lines. By loading the `booktabs` package, you can create elegant three-line tables:
* `\toprule`: Thick line at the top.
* `\midrule`: Thin line below the header.
* `\bottomrule`: Thick line at the bottom.

*(Note: For real-time preview convenience, the example below uses the array environment to simulate the effect)*

**Example**:
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

## 7. Image Insertion and Layout
**Tags**: `Illustration`, `graphicx`, `Floats`

### 7.1 Importing the Package
In LaTeX, we use the `graphicx` package to handle images.

### 7.2 Basic Commands
The core command is `\includegraphics[options]{filename}`.

### 7.3 Standard Illustration Environment
Academic papers usually place images in a `figure` float environment so the system can automatically optimize typesetting position and add captions.

```latex
\usepackage{graphicx} % Load in preamble

\begin{figure}[htbp]
  \centering % Centering
  \includegraphics[width=0.7\textwidth]{figure_name}
  \caption{Caption content}
  \label{fig:example} % Label for cross-referencing
\end{figure}
```

---

## 8. Hyperlinks and PDF Interaction
**Tags**: `hyperref`, `URL`, `Jump`

### 8.1 Package Functionality
The `hyperref` package can turn internal references (such as TOC, figure/table references) into clickable hyperlinks and supports external URLs.

### 8.2 Common Syntax
* **Display URL automatically**: `\url{https://...}`
* **Custom display text**: `\href{URL}{display text}`

```latex
\usepackage[colorlinks=true, linkcolor=blue]{hyperref} % Recommended configuration

For related resources, please refer to the \href{https://www.latex-project.org}{LaTeX Official Website}.
Or visit \url{https://ctan.org} directly.
```

---

## 9. Cross-referencing: The Soul of Automation
**Tags**: `label`, `ref`, `Auto-numbering`

### 9.1 Core Logic
LaTeX cross-referencing follows a "label-reference" mechanism. No matter how sections or figures are reordered, numbering updates automatically without manual maintenance.

### 9.2 Implementation Steps
1. **Labeling**: Use `\label{unique_key}` at the target location.
2. **Referencing**: Use `\ref{unique_key}` in the body text to reference the number, and `\pageref{unique_key}` to reference the page number.

```latex
\section{Methodology} \label{sec:method}

As described in Section \ref{sec:method}, we define energy conservation in Equation (\ref{eq:mass}).

\begin{equation}
  E = mc^2 \label{eq:mass}
\end{equation}
```

---

## 10. Reference Management (BibTeX)
**Tags**: `BibTeX`, `cite`, `Academic Standards`

### 10.1 Bibliography Database
Save all references in a specific BibTeX format in a `.bib` file (e.g., `refs.bib`).

### 10.2 In-text Citation
Use the `\cite{key}` command to cite literature; the system automatically handles the citation format.

### 10.3 Generating the List
Specify the citation style and load the database file at the end of the document.

```latex
% 1. In-text citation
According to Knuth's classic study \cite{knuth1984}...

% 2. Generate list at the end of the document
\bibliographystyle{plain} % Style choice: plain, alpha, unsrt, IEEEtran, etc.
\bibliography{refs}      % Load refs.bib in the current directory
```

---

## 11. Practical Integration: Complete Academic Page Example
**Tags**: `Practical`, `Template`

Mastering LaTeX structured writing is a basic skill in academic research. Below is a complete code framework covering core elements such as document structure, mathematical formulas, and table typesetting.

```latex
\documentclass[11pt, a4paper]{article}
\usepackage{amsmath}
\usepackage{booktabs}
\title{Academic Writing Practice Based on LaTeX}
\author{Antigravity Research Group}
\begin{document}
\maketitle
\begin{abstract}
This paper demonstrates basic applications of LaTeX in academic writing...
\end{abstract}
\section{Core Formulas}
\[ E = mc^2 \]
\end{document}
```

**Example**:
```latex
\begin{aligned}
\text{Master LaTeX} & \to \text{Focus on Research} \\
\text{Automated Typesetting} & \to \text{Increase Efficiency}
\end{aligned}
```
