# 论文撰写格式标准

医学论文与统计分析报告的 Word 投稿稿件格式模板。核心文件是 `reference.docx`，可作为 R Markdown 或 Quarto 渲染 Word 文档时的 `reference_docx`。

## 下载

- 仓库地址：https://github.com/zhaohongxin0/statistical-analysis-paper-writing-format-standard
- 直接下载 `reference.docx`：
  https://raw.githubusercontent.com/zhaohongxin0/statistical-analysis-paper-writing-format-standard/main/reference.docx

命令行下载：

```bash
curl -L -o reference.docx "https://raw.githubusercontent.com/zhaohongxin0/statistical-analysis-paper-writing-format-standard/main/reference.docx"
```

## R Markdown 使用

把 `reference.docx` 放在项目根目录，然后在 `.Rmd` 文件 YAML 中写：

```yaml
---
title: "Manuscript Title"
author: "Author Names"
output:
  word_document:
    reference_docx: reference.docx
---
```

渲染：

```r
rmarkdown::render("manuscript.Rmd")
```

## Quarto 使用

把 `reference.docx` 放在项目根目录，然后在 `.qmd` 文件 YAML 中写：

```yaml
---
title: "Manuscript Title"
author: "Author Names"
format:
  docx:
    reference-doc: reference.docx
---
```

渲染：

```bash
quarto render manuscript.qmd
```

## 模板样式

`reference.docx` 采用医学期刊投稿稿件常见格式：

- A4 页面，1 inch 页边距
- 连续行号
- 页脚页码
- 正文 Times New Roman 12 pt，双倍行距
- 标题页、Key Points、结构式摘要、IMRAD 正文、参考文献样式
- 表格标题、图题、表格正文、图注、表注等独立样式，便于 `flextable`、`officer`、R Markdown 或 Quarto 复用

## 文件

- `reference.docx`: Word reference document
- `template.Rmd`: 最小 R Markdown 示例
