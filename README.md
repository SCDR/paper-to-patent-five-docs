# 论文转专利五书

> 技能：将研究论文/学位论文/技术报告转写为符合专利申请规范的「专利五书」

## 📋 功能概述

将论文、学位论文、技术报告或 LaTeX 项目中的研究内容，转写为一套完整、格式规范的中国专利申请五书：

1. **权利要求书** - 结构化设计独立权利要求和从属权利要求体系
2. **说明书** - 按照「技术领域→背景技术→发明内容→具体实施方式→工业应用前景→附图说明」标准结构撰写
3. **说明书附图** - 统一图号和模块编号，为每幅图编写详细说明
4. **说明书摘要** - 压缩为 400-500 字的规范摘要
5. **摘要附图** - 精选最具代表性的核心框图/流程图

## 🎯 适用场景

- 把已发表论文改写为专利申请文本
- 根据学位论文生成专利五书草稿
- 将技术报告中的创新点整理为可提交的专利文档
- 精修已有专利草稿，使其符合官方格式规范
- 统一权利要求书、说明书和摘要中的术语和编号

## 📖 使用方法

在 Claude Code 中直接触发：

```
/paper-to-patent-five-docs 帮我把这篇论文转成专利五书
```

或自然语言触发：
- "把这篇论文转成专利"
- "帮我生成专利五书"
- "把背景章节改写成专利式背景技术"
- "统一权利要求和说明书的术语"

## 📁 项目结构

```
paper-to-patent-five-docs/
├── SKILL.md          # 技能详细定义（给 Claude 看）
├── README.md         # 本说明文件（给用户看）
├── examples/         # 触发示例
└── references/       # 参考专利文件和写作规范
```

## 💡 工作流程

1. **输入验证** - 确认源材料、参考样本和图表是否足够支撑后续写作
2. **约束锁定** - 固化格式、语言、数据追溯和术语规则
3. **技术映射** - 建立论文段落到专利章节的对应关系
4. **权利要求书** - 先完成并门禁通过，再进入说明书阶段
5. **说明书** - 在已冻结的权利要求基础上展开支撑内容
6. **说明书附图** - 统一图号、模块号并与正文逐条对齐
7. **说明书摘要** - 压缩为专利摘要，并继承说明书与附图口径
8. **摘要附图** - 选取最具代表性的图并与摘要一致
9. **总复核与导出** - 逐项检查一致性、公式格式和最终 Word 输出

### 门禁规则

- 每一步都必须先通过门禁，再进入下一步。
- 当前步骤只产出当前产物，不同时编造后续文件。
- 若信息不明确、规则冲突或材料不足，优先向用户提问或收集信息，再继续推进。
- 公式保持 LaTeX 形式，并在 Word 导出前检查零宽字符和显示一致性。
- 下一阶段必须继承上一阶段已冻结的术语、编号、图号和关键限定。

### 每阶段模板

每一阶段都建议先收集输入，再产出一个可检查的中间结果：

- 输入验证：源材料、参考样本、用户约束。
- 约束锁定：冻结术语、编号、公式和章节规则。
- 技术映射：建立论文段落到专利章节的对应关系。
- 权利要求书：输出独立权利要求、从属权利要求和支撑检查结果。
- 说明书：输出技术领域、背景技术、发明内容、具体实施方式、工业应用前景。
- 说明书附图：输出图号映射、附图说明和图文对齐结果。
- 说明书摘要：输出摘要草案、代表附图引用和一致性检查结果。
- 摘要附图：输出摘要附图说明和最终图号。
- 总复核与导出：输出五份 Markdown、五份 Word 和复核报告。

### Inversion 提问模板

当某一步信息不足或存在多种合理解释时，优先向用户确认。建议按下面结构提问：

- 当前阶段：说明卡在哪一步。
- 问题类型：说明是信息缺失、规则冲突还是术语/图号/公式未定。
- 已确认内容：简述已冻结内容。
- 需要确认：列出 1 到 2 个最关键问题。
- 后续动作：说明收到回复后将继续哪一步。

## 📄 示例输出

参考 `references/` 目录下有完整的五书示例：
- [`100001权利要求书.md`](references/100001权利要求书.md)
- [`100002说明书.md`](references/100002说明书.md)
- [`100003说明书附图.md`](references/100003说明书附图.md)
- [`100004说明书摘要.md`](references/100004说明书摘要.md)
- [`100005摘要附图.md`](references/100005摘要附图.md)

参考 `references/pipeline/` 目录下有按阶段拆分的按需加载参考包：
- [`01_input_validation.md`](references/pipeline/01_input_validation.md)
- [`02_constraints.md`](references/pipeline/02_constraints.md)
- [`03_tech_mapping.md`](references/pipeline/03_tech_mapping.md)
- [`04_claims.md`](references/pipeline/04_claims.md)
- [`05_specification.md`](references/pipeline/05_specification.md)
- [`06_figures.md`](references/pipeline/06_figures.md)
- [`07_abstract.md`](references/pipeline/07_abstract.md)
- [`08_abstract_figure.md`](references/pipeline/08_abstract_figure.md)
- [`08_inversion.md`](references/pipeline/08_inversion.md)
- [`09_final_review.md`](references/pipeline/09_final_review.md)

参考 `references/generator/` 目录下有按需加载的通用生成模板：
- [`00_generator_index.md`](references/generator/00_generator_index.md)
- [`01_global_parameters.md`](references/generator/01_global_parameters.md)
- [`02_claims_template.md`](references/generator/02_claims_template.md)
- [`03_specification_template.md`](references/generator/03_specification_template.md)
- [`04_figures_template.md`](references/generator/04_figures_template.md)
- [`05_abstract_template.md`](references/generator/05_abstract_template.md)
- [`06_abstract_figure_template.md`](references/generator/06_abstract_figure_template.md)
- [`07_format_rules.md`](references/generator/07_format_rules.md)
- [`09_generator_validation.md`](references/generator/09_generator_validation.md)

## 💭 写作原则

- 保留技术核心，使用专利语言重新表述
- 五个文件保持内部一致
- 参考现有专利对齐风格
- 优先最小修改，避免大范围重写
- 性能参数必须可追溯到原始论文
- 去除学术口吻，改用专利直接陈述

## ⚠️ 注意事项

- 需要提供源材料（PDF/LaTeX/论文文件）才能开始
- 如果有参考专利，提供后能生成更贴合目标风格的输出
- 本技能生成专利草稿，建议提交前由专利代理师进行法务润色

