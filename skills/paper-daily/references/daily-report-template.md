# Daily Report Template

- **File**: `reports/{{date}}_morning.md` (`{{date}}` = today, `YYYY-MM-DD`)
- **Title line**: `# 今日 {topic} Paper 晨报`

Follow the structure below. Under §4.1, name concrete trends found in **today's** papers — do not use a fixed keyword list.

---

# 今日 {topic} Paper 晨报

## 0. 今日结论

Use 3–5 sentences to summarize the most important findings of the day. Answer:

- 今天有没有值得精读的论文？
- 今天最重要的技术趋势是什么？
- 有没有值得作为 related work 的论文？
- 有没有值得作为 baseline 的论文？
- 有没有值得后续追踪的方向？
- 有没有信息不足、需要精读 PDF 的论文？

---

## 1. 今日最值得读的论文 Top 3

For each paper, include:

- 标题
- 链接
- 推荐等级：高 / 中 / 低
- 一句话总结
- 为什么值得读
- 可能用途：related work / baseline / motivation / experiment reference / trend tracking / future reading

Then provide the detailed six-section structure (see `references/summary-format.md`):

**1. Challenge** · **2. Motivation** · **3. Insight** · **4. Main method** · **5. Effect / Results** · **6. Research Value**

---

## 2. 重点论文详细解读

For other high-priority papers, use the same six-section structure:

### Paper: {title}

**1. Challenge** · **2. Motivation** · **3. Insight** · **4. Main method** · **5. Effect / Results** · **6. Research Value**

---

## 3. 所有新论文速览

Use a Markdown table:

```text
标题 | 方向 | 核心贡献 | 研究价值 | 阅读优先级 | 用途
```

The 用途 column should be one or more of:

```text
related work / baseline / motivation / experiment / trend / future reading / skip
```

---

## 4. 对当前研究方向的启发

Organize suggestions by category:

### 4.1 Research Trends

What trends are visible today? Name them from today's papers; do not use a fixed keyword list.

### 4.2 Related Work

Which papers may be useful as related work?

### 4.3 Baselines

Which papers may be useful as baselines?

### 4.4 Methods

Which methods are technically interesting?

### 4.5 Experiments

Any useful metric, benchmark, ablation, or evaluation setup?

### 4.6 Risks and Open Questions

Which papers challenge existing assumptions or need deeper verification?

---

## 5. 可以写进论文的英文句子

Write 3–5 polished English academic sentences, useful for: introduction / related work / motivation / limitations / experiment discussion.

Do not make unsupported claims.

---

## 6. 今天建议精读的论文

List 1–3 papers. For each: why to read it / which sections to focus on / what specific technical question to answer while reading.

---

## 7. 明天继续关注的关键词

List keywords that should be searched tomorrow.

---

## 8. Source and Access Status

Clearly state:

- whether WebSearch was available
- which sources were used
- which sources failed
- whether any PDF was read
- which summaries are based only on title / abstract / project page
