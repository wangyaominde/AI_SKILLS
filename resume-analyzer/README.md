# Resume Analyzer / 简历分析器

> Analyze and improve resumes/CVs with brutally honest, actionable, visual feedback.
>
> 以犀利、可执行的方式分析和优化简历，提供可视化反馈。

## What it does / 功能介绍

Upload a resume (PDF or DOCX), this skill will:

上传一份简历（PDF 或 DOCX），该 Skill 会：

1. **Extract / 提取** — Extract the full text from the resume / 提取简历全文
2. **Analyze / 分析** — Analyze across 7 dimensions / 从 7 个维度进行分析：quantified impact, action verbs, keyword optimization, structure & format, conciseness, language polish, content gaps（量化成果、行动动词、关键词优化、结构格式、精简冗余、表达润色、内容补充）
3. **Generate / 生成** — Generate an interactive HTML report with every suggestion shown inline / 生成交互式 HTML 报告，逐条展示原文与修改建议

## Trigger / 触发方式

- Upload a resume file and ask for review / 上传简历文件并要求分析
- Or mention / 或提及：`简历分析` / `简历优化` / `resume review` / `CV feedback`

## Analysis Dimensions / 分析维度

| Dimension / 维度 | What it checks / 检查内容 |
|-------------------|--------------------------|
| 📊 Quantified Impact / 量化成果 | Vague achievements → specific numbers/metrics / 模糊描述 → 具体数字和指标 |
| 🎯 Action Verbs / 行动动词 | Weak/passive verbs → strong action verbs / 弱动词 → 有力的行动动词 |
| 🔑 Keyword Optimization / 关键词优化 | Missing industry-standard & ATS keywords / 缺失行业关键词和 ATS 关键词 |
| 📐 Structure & Format / 结构与格式 | Section ordering, date formats, length / 板块顺序、日期格式、篇幅 |
| ✂️ Conciseness / 精简冗余 | Redundant phrases, filler words / 冗余短语、填充词 |
| 🎨 Language Polish / 表达润色 | Grammar, tone, bilingual consistency / 语法、语气、中英一致性 |
| 💡 Content Gaps / 内容补充 | Missing sections, zero-metrics detection / 缺失板块、零指标检测 |

## Output / 输出

A self-contained interactive HTML report featuring:

输出一份独立的交互式 HTML 报告，包含：

- Overall score (0-100) with honest calibration / 总评分（0-100），评分标准严格真实
- Per-dimension bar charts / 各维度柱状图
- Filterable suggestion cards (by category & severity) / 可按类别和严重程度筛选的建议卡片
- Side-by-side original vs. suggested text with `[placeholders]` / 原文与建议并排对比，含 `[占位符]` 提示填入真实数据
- Accept/Skip buttons with progress tracking / 采纳/跳过按钮及进度追踪
- Export accepted changes / 导出已采纳的修改

## Scoring Calibration / 评分标准

| Score / 分数 | Meaning / 含义 |
|--------------|----------------|
| 90-100 | Top-tier, FAANG-ready. Extremely rare. / 顶级水平，可投大厂。极其罕见。 |
| 75-89 | Solid, minor polish needed. ~10% of resumes. / 扎实，需小幅润色。约 10% 的简历。 |
| 60-74 | Decent foundation, significant gaps. / 基础不错，但有明显短板。 |
| 40-59 | Major issues, will get filtered by ATS. / 存在严重问题，大概率被 ATS 过滤。 |
| <40 | Fundamental rethink needed. / 需要从头重新规划。 |

## Supported Formats / 支持的格式

- PDF（text-based and image-based via pdfplumber fallback / 文本型及图片型，通过 pdfplumber 兜底）
- DOCX
- Plain text / Markdown / 纯文本 / Markdown
- Chinese and English resumes / 中英文简历
