# de-ai-writing (中英文双语自然化写作与降 AI 率 Skill)

一个面向 AI Agent（Antigravity / Claude Code / OpenCode / Cursor 等）的中英文双语自然化写作与去 AI 味规范 Skill。

用于日常起草方案、技术文档、分析报告、博客文章的直接生成，也可对已有文稿进行深度去味改写与降 AI 率处理。

---

## 核心设计

主流大语言模型在生成中文或英文文本时，普遍存在几个固化问题：
- **中文**：滥用“全面赋能、闭环、双刃剑、深入探讨、不可否认的是、值得注意的是”等假大空词汇；机械使用“不仅是……更是……”、“不是……而是……”等二分对照句式。
- **英文**：滥用 `delve`, `tapestry`, `beacon`, `testament`, `pivotal`, `paramount`, `furthermore`, `moreover` 等书面套话；过度使用破折号（`—`）与分号。
- **排版膨胀**：粗体泛滥、无意义 Emoji 点缀、短句强行切碎成密密麻麻的清单点。
- **对话惯性**：频繁附带“好的，为您撰写如下”、“希望对您有所帮助”等前置后置废话。

本 Skill 从**视觉排版、词汇套话、句式结构、语气思维**四个维度建立硬性约束，让模型输出逻辑紧凑、具有长短句呼吸感且保留真实细节的自然文本。

---

## 核心规则概览

### 1. 四大反模式治理
- **排版规范**：严禁粗体泛滥，禁止非必要 Emoji，用连贯段落推进论述，杜绝机械提纲碎片化。中英文及数字间保持标准空格（盘古排版）。
- **词汇黑名单**：全面拦截高频虚词、罐头开头与公文套话。
- **句式重构**：粉碎二分对照壳，消除被动语态与翻译腔，保持长短句交错的节奏感。
- **直接交付**：零回答者惯性，不输出开场白与结尾寒暄，直接交付纯净正文。

### 2. 三大场景分级
- **Mode A (通俗随笔 / 博客 / 社交文案)**：第一人称，强口语呼吸感，细节生动。
- **Mode B (商业分析 / 职场汇报 / PR 稿件 / 技术文档)**：高信息密度，主动语态，动词有力，逻辑严密。
- **Mode C (学术论文 / 专利 / 规范说明)**：严格保留学术逻辑与专有名词，消除被动语态堆叠，绝不滥用口语。

---

## 安装与配置

### 方式 1: Antigravity / OpenCode 全局安装

将技能软链接或复制到全局 skills 目录：

```bash
# 复制到 .agents 全局目录
git clone https://github.com/zyf2492313716-cloud/de-ai-writing.git ~/.agents/skills/de-ai-writing

# 或链接到 Antigravity 配置目录
mkdir -p ~/.gemini/config/skills
ln -s ~/.agents/skills/de-ai-writing ~/.gemini/config/skills/de-ai-writing
```

### 方式 2: 项目级接入

将本仓库作为子模块或直接放入项目根目录的 `.agents/skills/` 路径下：

```bash
mkdir -p .agents/skills
git clone https://github.com/zyf2492313716-cloud/de-ai-writing.git .agents/skills/de-ai-writing
```

### 方式 3: Claude Code / Cursor / 系统提示词接入

直接将 [SKILL.md](SKILL.md) 的正文内容复制到你的 `CLAUDE.md`、`.cursorrules` 或 Agent 系统提示词中作为 Writing Instructions。

---

## 改写效果对比

### 中文商业与分析文稿

- **原始 AI 文本**：
  > “在当今快速发展的**数字化转型浪潮**中，企业引入 AI 工具**不仅是**效率的提升，**更是**核心竞争力的重塑。值得注意的是，这一技术**全面赋能**了业务闭环。总而言之，企业必须把握时代脉搏，方能在激烈的市场竞争中立于不败之地。”
- **去 AI 味重写后**：
  > “企业引入 AI 工具，表面上看是把流程跑快了一点，深层看其实是在重构团队做事的方式。它把很多机械重复的体力活自动化了，让核心人员能抽出精力抓关键决策。跟不上这个节奏的团队，后面的差距只会越拉越大。”

### 英文技术文稿

- **Original AI Slop**：
  > "In today's ever-evolving technological landscape, continuous integration is of paramount importance—fostering seamless collaboration among engineers. Furthermore, it serves as a testament to operational excellence. In conclusion, organizations must leverage modern tooling to thrive."
- **Humanized Version**：
  > "Fast-moving teams rely on continuous integration to catch bugs before they hit production. It cuts deployment friction, keeps builds green, and lets engineers ship code without second-guessing every release."

---

## 开源协议

[MIT License](LICENSE)
