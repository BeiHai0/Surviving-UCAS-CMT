# 中文数学与物理讲义模板

所有源文件均为 UTF-8 编码。编译入口为 `main.tex`；章节文件不能单独编译。

## 目录结构

```text
chinese-lecture-template/
├── main.tex                       # 编译入口、标题、章节导入及参考文献
├── lecturemath.sty                # 可复制到其他项目的数学讲义宏包
├── chapters/
│   ├── 01-environments.tex         # 八种数学环境的最简单示例
│   ├── 02-math-physics.tex         # 公式、Dirac 记号、交叉引用、三线表
│   └── 03-new-chapter.tex          # 可复制的新章节起点
├── README.md
├── references.bib                 # 独立的 BibTeX 参考文献数据库
└── main.pdf                       # 已编译的预览
```

## 使用 XeLaTeX 编译

推荐安装完整的 TeX Live（包含中文支持）。本模板使用 `ctexbook` 与 TeX Live
自带的 Fandol 中文字体，无需依赖操作系统中的宋体。MiKTeX 用户需安装相应宏包及字体。

解压 ZIP 后，在包含 `main.tex` 的目录运行：

```sh
xelatex -interaction=nonstopmode -halt-on-error main.tex
bibtex main
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

BibTeX 从 `references.bib` 生成文献列表；后两次 XeLaTeX 编译更新引用、目录与页码，结果为 `main.pdf`。也可以使用：

```sh
latexmk -xelatex -interaction=nonstopmode -halt-on-error main.tex
```

在编辑器中将编译引擎设为 **XeLaTeX**，主文档设为 `main.tex`。
在 Overleaf 中上传整个项目，并在项目设置中选择 XeLaTeX。
不要使用 pdfLaTeX 编译本模板。

## 内容与约定

- 主文件通过 `\input{chapters/...}` 导入三个章节，新增章节时照此添加一行。
- 主文件通过 `\usepackage{lecturemath}` 加载 `lecturemath.sty`；宏包、页边距、链接颜色和数学环境集中在该文件中修改。
- 参考文献保存在 `references.bib`，正文用 `\cite{条目键}` 引用。添加条目后按上述顺序重新编译。
- `definition`、`theorem`、`lemma`、`proposition`、`corollary`、`example`、`remark`
  共享编号；`ctexbook` 按章重置，`ctexart` 按节重置。`proof` 由 `amsthm` 提供，中文标题为“证明”，末尾自动添加证毕符号。
- `amsmath` 提供基础公式环境，`amssymb` 提供符号，`mathtools` 提供扩展。
- Dirac 记号使用 `braket`：`\Bra{\psi}`、`\Ket{\psi}`、
  `\Braket{\phi|\psi}`、`\Braket{\psi|\hat{A}|\psi}`。
  本模板无需加载 `physics`；若自行添加，请先检查重名命令兼容性。
- 自然常数始终写作 `\mathrm{e}`，例如 `\mathrm{e}^{x}`。
- `\dd` 表示正体微分符号；`\bm{r}` 表示粗体向量；`\R`、`\C` 表示实数域与复数域。
- 以 `\label`、`\ref` 和 `\eqref` 维护引用；新增内容时使用唯一标签。
- 修改标题页时，同时更新主文件 `\hypersetup` 中的 PDF 标题和作者。

## 迁移到其他项目

将 `lecturemath.sty` 复制到新项目的主 `.tex` 文件同级目录，并在导言区加入：

```latex
\documentclass[UTF8,fontset=fandol]{ctexart} % 也可使用 ctexbook
\usepackage{lecturemath}             % 建议在其他普通宏包之后加载
\hypersetup{pdftitle={新项目标题},pdfauthor={作者姓名}}
\begin{document}
\section{开始}
\begin{theorem}对任意 $x\in\R$，有 $x^2\geq 0$。\end{theorem}
\begin{proof}实数的平方非负。\end{proof}
\end{document}
```

`lecturemath.sty` 依赖标准 TeX Live 宏包，中文环境标题以 `ctexbook`、`ctexart` 为目标。
它不包含项目标题、作者、章节内容或参考文献数据库。若新项目有自己的页边距，
可在加载该宏包后使用 `\geometry{margin=...}` 覆盖。

## 常见问题

- 出现缺少 `.sty` 或 Fandol 字体的错误：使用发行版包管理器安装所缺组件，或安装完整 TeX Live。
- 引用出现 `??`：在项目根目录再编译一次主文件。
- 文献引用显示为 `[?]`：确认 `.bib` 中存在对应条目，然后运行 `bibtex main`，再运行 XeLaTeX 两次。
- 新增章节未显示：检查主文件中的 `\input` 路径是否与文件名一致。

`main.pdf` 是随项目附带的预览；修改源文件后重新编译即可覆盖更新。
