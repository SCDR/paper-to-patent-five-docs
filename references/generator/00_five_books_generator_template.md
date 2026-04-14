# 五书通用生成模板（兼容入口）

本文件已拆分为按需加载结构。请优先使用：

- `references/generator/00_generator_index.md`

如果调用方仍依赖旧路径，可把本文件视为“索引别名”，不再在此维护完整模板正文。

## 拆分后文件

- `references/generator/01_global_parameters.md`
- `references/generator/02_claims_template.md`
- `references/generator/03_specification_template.md`
- `references/generator/04_figures_template.md`
- `references/generator/05_abstract_template.md`
- `references/generator/06_abstract_figure_template.md`
- `references/generator/07_format_rules.md`
- `references/generator/09_generator_validation.md`

## 说明

使用建议：
1. 新项目调用时从 `00_generator_index.md` 开始。
2. 各阶段仅按需加载对应模板文件。
3. 完成全部阶段后加载 `09_generator_validation.md` 统一校验。
