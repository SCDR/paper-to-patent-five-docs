# Generator 索引（按需加载）

用途：在不同项目中使用统一的五书生成结构，并按阶段加载最小模板。

## 推荐加载顺序

1. `references/generator/01_global_parameters.md`
2. `references/generator/07_format_rules.md`
3. 当前阶段对应模板（02~06）
4. `references/generator/09_generator_validation.md`

## 阶段模板映射

- 权利要求书：`references/generator/02_claims_template.md`
- 说明书：`references/generator/03_specification_template.md`
- 说明书附图：`references/generator/04_figures_template.md`
- 说明书摘要：`references/generator/05_abstract_template.md`
- 摘要附图：`references/generator/06_abstract_figure_template.md`

## 与 Pipeline 的关系

- Generator 模板提供“产物骨架”和“字段占位”。
- Pipeline 模板负责“阶段门禁”和“回退规则”。
- 两者并行使用：先套模板，再过门禁。
