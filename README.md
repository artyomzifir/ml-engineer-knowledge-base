


# ML / CV / Robotics Knowledge Base

[Link to knowledge base](https://artyomzifir.github.io/ml-engineer-knowledge-base/)

A concept-oriented knowledge base covering Machine Learning, Computer Vision, Robotics, and their mathematical foundations. Written in Markdown, published as a static digital garden via [Quartz](https://quartz.jzhao.xyz/).

---

## Structure

```text
content/
  math/
  cs/
  ml/
  cv/
  robotics/
  physics/
  systems/
  misc/
```

- One concept = one file
- No duplication
- Everything is linkable via `[[...]]`

---

## Fill Priorities

| Priority | Domain | Topics |
|----------|--------|--------|
| **P0** | Mathematics | Linear Algebra, Calculus, Probability, Optimization |
| **P0** | Machine Learning | ML fundamentals, Deep learning basics |
| **P0** | Computer Vision | Camera model, Epipolar geometry, Stereo |
| **P0** | Robotics | Kinematics, State estimation |
| **P1** | CS Foundations | Algorithms & DS, OS, Computer Architecture |
| **P1** | Software | Software Design, Physics (applied) |
| **P2** | Optional | English notes, Philosophy, Product thinking, Misc |

---

## Workflow

1. **Pick task** — check `content/TODO.md`
2. **Create note** — `touch content/ml/fundamentals/loss-functions.md`
3. **Write** — follow the [style guide](STYLE.md)
4. **Preview** — `npx quartz build --serve`
5. **Commit** — `git commit -m "docs: add loss functions"`

---

## What NOT to do

- Do not duplicate concepts
- Do not mix temporary drafts into `content/`
- Do not break naming consistency

---

## Long-term Goal

Build a connected knowledge graph that supports interview prep, accelerates learning, and serves as a public technical portfolio.

---

## License

See [LICENSE](LICENSE) for details.