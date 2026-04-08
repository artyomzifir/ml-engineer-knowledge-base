# Style Guide

Rules for writing and formatting notes in this knowledge base.

---

## Note Structure

Every note must follow this order:

1. **Definition** — what is it, formally and briefly
2. **Intuition** — why it works, what it means geometrically / physically
3. **Formalism** — derivations, proofs, math
4. **Implementation notes** — code, complexity, practical details
5. **Edge cases** — where it breaks, common mistakes
6. **Links** — related concepts via `[[...]]`

---

## File Naming

- Language: **English**
- Format: **kebab-case**

```
epipolar-geometry.md
gradient-descent.md
singular-value-decomposition.md
```

---

## Linking

Use Quartz wikilinks:

```md
[[gradient-descent]]
[[math/linear-algebra/eigenvalues]]
```

---

## Math

Use LaTeX — inline and block:

```md
Inline: $\sigma(x) = \frac{1}{1 + e^{-x}}$

Block:
$$
L = - \sum_i y_i \log \hat{y}_i
$$
```

---

## Code

Use fenced blocks with language tag:

````md
```python
import torch
x = torch.randn(3, 3)
```
````

---

## Assets

Store images in:

```text
content/assets/images/
```

Reference in notes:

```md
![diagram](../assets/images/epipolar-geometry.png)
```

---

## Philosophy

This is a **concept-oriented system**, designed for long-term reuse and cross-domain connections. Write as if explaining to a strong engineer who has never seen this specific concept — precise, dense, no fluff.