# Weekly Report Template

- **File**: `reports/{{date}}_weekly.md` (`{{date}}` = today, `YYYY-MM-DD`)
- **Title line**: `# 本周 {topic} 论文周报`

Follow the structure below. In §4, cluster the week's papers into trends relevant to `{topic}`; **name each trend from what you found** (e.g. `4.1 <trend A>`, `4.2 <trend B>`). Do not use a fixed keyword list. The final sub-section is always **Research Gaps**.

---

# 本周 {topic} 论文周报

## 0. 本周核心结论

Use 5–8 sentences to summarize:

- 本周最重要的研究趋势是什么？
- 哪些论文最值得精读？
- 哪些论文可能作为 related work？
- 哪些论文可能作为 baseline？
- 哪些方向正在变热？
- 哪些方法可能改变后续研究路线？
- 哪些论文的信息仍然不足，需要继续精读？

---

## 1. 本周最重要的 5 篇论文

For each paper, include:

- 标题
- 链接
- 推荐等级：高 / 中 / 低
- 一句话总结
- 核心贡献
- 可能用途：related work / baseline / motivation / experiment reference / trend tracking / future reading
- 是否需要精读：Yes / No

Then provide the detailed six-section structure (see `references/summary-format.md` under the `paper-daily` skill):

**1. Challenge** · **2. Motivation** · **3. Insight** · **4. Main method** · **5. Effect / Results** · **6. Research Value**

---

## 2. 本周重点论文深度总结

For additional high-priority papers outside the top 5, use the same six-section structure:

### Paper: {title}

**1. Challenge** · **2. Motivation** · **3. Insight** · **4. Main method** · **5. Effect / Results** · **6. Research Value**

---

## 3. 本周所有论文总览

Use a Markdown table:

```text
标题 | 方向 | 核心贡献 | 研究价值 | 阅读优先级 | 用途
```

The 用途 column should be one or more of:

```text
related work / baseline / motivation / experiment / trend / future reading / skip
```

---

## 4. 本周研究趋势总结

The weekly report must not simply list papers — it must synthesize trends. Cluster the week's papers into trends relevant to `{topic}` and name each trend sub-section from what you actually found (`4.1 <trend>`, `4.2 <trend>`, …). For each trend discuss: which papers define it, what is changing, and why it matters.

The last sub-section is always:

### 4.x Research Gaps

What is still missing in current papers? Which assumptions are not fully tested? Which claims require more careful experimental evidence?

---

## 5. 对当前研究方向的启发

Organize suggestions by category:

### 5.1 Related Work

Which papers should be cited or tracked?

### 5.2 Baselines

Which papers may be useful as direct or indirect baselines?

### 5.3 Methods

Which ideas are technically useful?

### 5.4 Experiments

Which metrics, benchmarks, or ablations are worth adopting?

### 5.5 Risks

Which papers challenge current assumptions or may become strong competing directions?

### 5.6 Reading Plan

Which papers should be read deeply next week?

---

## 6. 可以写进论文的英文 related work 段落

Write one polished English paragraph that can be adapted into a paper, connecting the week's relevant trends. Be conservative; do not make unsupported claims.

---

## 7. 下周建议

Give concrete suggestions:

- papers to read deeply
- baselines to consider
- experiments to run
- metrics to track
- related work to add
- technical questions to verify
- potential risks to address

---

## 8. Source and Access Status

Clearly state:

- which daily reports were read
- which `papers.md` files were read
- whether any PDF was read
- whether WebSearch was available
- which sources failed
- which conclusions are based only on title / abstract / project page
