# Markdown + LaTeX Cheat Sheet

Quick reference for writing Jupyter markdown cells in this textbook (rendered with Quarto).

---

# Part 1: Markdown

## Headings and text

```markdown
# Heading 1
## Heading 2          ← chapter sections
### Heading 3         ← exercise titles

**bold**   *italic*   ***bold italic***   ~~strikethrough~~
`inline code`         ← variable names, e.g. `alphas_1d`
```

A blank line starts a new paragraph. A single newline does **not** break the line.

## Lists

```markdown
- bullet
- another
    - nested (indent 4 spaces)

1. numbered
2. numbered

- (a) exercise parts in this notebook use this style
```

## Code blocks

````markdown
```python
grid_search.fit(X_cos, y_cos)
```
````

## Links and images

```markdown
[link text](https://scikit-learn.org)
![alt text](images/figure.png)
```

## Tables

```markdown
| Situation | Strategy        | Grouped on |
|-----------|-----------------|------------|
| (a)       | Time series     | time       |
| (b)       | Group K-fold    | blade      |
```

Alignment with colons: `|:---|` left, `|:---:|` center, `|---:|` right.

## Quotes and horizontal rule

```markdown
> This is a block quote.

---
```

## Quarto extras (used in this textbook)

### Callout boxes

```markdown
::: {.callout-note appearance="simple" icon=false}
### Exercise 2 (~3 min): Title
Exercise text...
:::
```

- Types: `.callout-note`, `.callout-tip`, `.callout-warning`, `.callout-important`, `.callout-caution`
- Add `collapse="true"` to make it collapsible (the solutions use this for derivations).
- Every `:::` opener needs a closing `:::`. A missing one breaks the rendering of everything after it.

### Code cell options

These go on the first line(s) of a **code** cell:

```python
#| echo: false        ← hide the code, show only the output
#| code-fold: false   ← show the code unfolded
```

---

# Part 2: LaTeX math

## Inline vs. display

```markdown
Inline: the penalty $\alpha$ shrinks the weights.

Display (own line, centered):
$$
\mathrm{MSE} = \frac{1}{n}\sum_{i=1}^{n} (y_i - \hat{y}_i)^2
$$
```

No spaces just inside the dollar signs: write `$x$`, not `$ x $`.

## Basics

| You want | Type |
|---|---|
| superscript / subscript | `x^2`, `x_i`, `x^{10}`, `w_{ij}` |
| fraction | `\frac{a}{b}` |
| square root | `\sqrt{x}`, `\sqrt[3]{x}` |
| sum / product | `\sum_{i=1}^{n}`, `\prod_{i=1}^{n}` |
| integral | `\int_0^1 f(x)\,dx` |
| limit | `\lim_{n \to \infty}` |
| derivative | `\frac{dy}{dx}`, `\frac{\partial L}{\partial w}` |
| gradient | `\nabla_w L` |
| hat / bar / tilde | `\hat{y}`, `\bar{x}`, `\tilde{x}` |
| bold vector | `\mathbf{x}`, `\boldsymbol{\mu}` |
| blackboard (sets, expectation) | `\mathbb{R}^n`, `\mathbb{E}[X]` |
| calligraphic | `\mathcal{N}`, `\mathcal{L}` |
| upright text | `\text{if } x > 0`, `\mathrm{UCB}` |

Use braces for anything longer than one character: `x^{10}`, not `x^10`.

## Greek letters

```
\alpha \beta \gamma \delta \epsilon \varepsilon \theta \lambda
\mu \sigma \Sigma \phi \pi \rho \tau \omega \Omega \Gamma
```

Capitalize the command for the uppercase letter: `\sigma` → σ, `\Sigma` → Σ.

## Operators and relations

```
\times  \cdot  \pm  \leq  \geq  \neq  \approx  \propto  \sim
\in  \subset  \to  \infty  \|x\|  \lvert x \rvert  X^\top (transpose)
\arg\min_w  \arg\max_x  \log  \exp  \sin
```

## Auto-sized brackets

```latex
\left( \frac{a}{b} \right)    \left[ ... \right]    \left\{ ... \right\}
```

## Matrices

```latex
$$
\mathbf{A} = \begin{bmatrix} a & b \\ c & d \end{bmatrix}
$$
```

`pmatrix` gives round brackets, `vmatrix` gives determinant bars.

## Multi-line aligned equations

```latex
$$
\begin{aligned}
L(w) &= \|y - Xw\|^2 + \alpha \|w\|^2 \\
\nabla L &= -2X^\top(y - Xw) + 2\alpha w
\end{aligned}
$$
```

`&` marks the alignment point, `\\` ends a line.

## Cases (piecewise)

```latex
$$
f(x) = \begin{cases} x & x \geq 0 \\ 0 & \text{otherwise} \end{cases}
$$
```

## Spacing

| Command | Space |
|---|---|
| `\,` | small (use before `dx`) |
| `\;` | medium |
| `\quad` | large |
| `\qquad` | extra large |

## Examples from the cross-validation chapter

```latex
$\mathrm{UCB}(x) = \mu(x) + \kappa\,\sigma(x)$

$p(\mathbf{x}) \propto e^{-\|\mathbf{x}\|^2/2}$

$\mathcal{N}(\ln x;\mu,\sigma) = \frac{1}{\sigma\sqrt{2\pi}} \exp\left[-\frac{(\ln x - \mu)^2}{2\sigma^2}\right]$
```
