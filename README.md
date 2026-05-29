# Spec Clarifier

> A Socratic requirements-clarifier skill for [Claude Code](https://claude.com/claude-code).
> 一个面向 Claude Code 的「苏格拉底式需求澄清」skill。

[English](#english) · [中文](#中文)

---

## English

### What it does

**Spec Clarifier** turns a vague idea into a clean, structured spec *before* any code or work is written. Instead of jumping straight to execution, Claude runs a Socratic interview — asking **one question at a time, always with numbered options** — until five sections are fully covered:

1. **Problem Statement** — what problem are you solving?
2. **Proposed Solution** — what approach addresses it?
3. **Technical Constraints** — what rules, formats, and boundaries apply?
4. **Non-goals** — what should it explicitly *not* do?
5. **Success Criteria** — how will you know it worked?

It has two modes:

- **Mode A – Build from scratch**: you have a one-liner or a rough idea.
- **Mode B – Improve a draft**: you already have a structured prompt/spec, and want the gaps found and filled.

### When it triggers

The skill activates when you signal intent to *think before executing*, e.g.:

> "let's spec this out" · "帮我理清思路" · "让我们细化" · "我有个想法"

### Install

Drop the skill folder into your Claude Code skills directory:

```
~/.claude/skills/spec-clarifier/SKILL.md
```

On Windows that's `C:\Users\<you>\.claude\skills\spec-clarifier\SKILL.md`. Restart Claude Code and the skill will be auto-detected.

### Visualization

[`spec-clarifier-visualization.html`](./spec-clarifier-visualization.html) is a standalone explainer page describing how the skill works. Download it and open it in any browser — no build step needed.

---

## 中文

### 这是什么

**Spec Clarifier** 是一个让你在动手写代码/干活**之前**先把模糊想法理成清晰结构化需求文档的 skill。它不会急着执行，而是用苏格拉底式提问——**每次只问一个问题，且永远给出带编号的选项**——直到下面五个部分都问清楚：

1. **Problem Statement（问题陈述）**——你要解决什么问题？
2. **Proposed Solution（方案设想）**——用什么思路或机制解决？
3. **Technical Constraints（技术约束）**——有哪些规则、格式、工具、边界要遵守？
4. **Non-goals（非目标）**——明确**不**做什么？
5. **Success Criteria（成功标准）**——怎么判断方案成功了？

两种模式：

- **模式 A——从零搭建**：你只有一句话或一个粗略想法。
- **模式 B——改进草稿**：你已经有一份结构化的 prompt/需求文档，想让它找出缺口并补全。

### 何时触发

当你表达出「先想清楚再执行」的意图时自动触发，例如：

> "帮我理清思路" · "让我们细化" · "让我们优化" · "我有个想法" · "let's spec this out"

### 安装

把 skill 文件夹放进 Claude Code 的 skills 目录即可：

```
~/.claude/skills/spec-clarifier/SKILL.md
```

Windows 下路径为 `C:\Users\<你的用户名>\.claude\skills\spec-clarifier\SKILL.md`。重启 Claude Code 后会自动识别。

### 可视化说明页

[`spec-clarifier-visualization.html`](./spec-clarifier-visualization.html) 是一个独立的图文说明页，讲解这个 skill 的工作流程。下载后用任意浏览器打开即可，无需构建。

---

## License

MIT
