# 讲义 LaTeX 排版规范

本规范适用于本文件夹及其子目录，继承仓库根目录 `AGENTS.md` 的全部要求。下面将已有约定与本次补充的排版要求汇总在一起；本文件夹内后续编辑均应遵守。

## 1. 数学括号与定界符

数学表达式中的显式括号统一使用自动伸缩的 `\left`、`\right`，行内公式和行间公式采用同一规则。对易子、函数参数、分组、区间、集合、绝对值和范数均适用。

| 用途 | 写法 |
| --- | --- |
| 圆括号、函数参数 | `\left( ... \right)`、`f\left(x\right)` |
| 方括号、对易子 | `\left[ ... \right]`、`\left[\hat A,\hat B\right]` |
| 花括号、集合、反对易子 | `\left\{ ... \right\}` |
| 绝对值、复数模 | `\left| ... \right|` |
| 范数 | `\left\| ... \right\|` |
| 求值竖线 | `\left. ... \right|_{x=0}` |
| 带圆括号的矩阵 | `\left(\begin{matrix} ... \end{matrix}\right)` |

嵌套的每一层括号分别配对。不以裸括号或固定字号的 `\bigl`、`\bigr` 等命令替代上述写法。

以下区别必须保留：

- 命令参数与分组的 `{...}`（如 `\frac{a}{b}`、上下标分组）不是可见花括号，不添加 `\left`、`\right`。
- 宏包选项、环境可选标题、换行间距等 LaTeX 语法中的 `[...]` 不属于数学方括号，不修改。
- 正文标点括号不属于数学定界符。
- `cases` 等标准环境已自动处理其定界符，可保留环境，不重复添加括号。
- 一对 `\left`、`\right` 必须处于同一个数学分组或对齐单元中。跨行公式优先调整断行位置；确需跨行的定界符使用 `\right.` 和 `\left.` 配对，不能直接跨越 `&` 或 `\\`。

## 2. Dirac 记号

统一使用首字母大写且带花括号参数的命令，由现有 `braket` 宏包提供：

```latex
\Bra{\phi}
\Ket{\psi}
\Braket{\phi|\psi}
\Braket{\phi|\hat A|\psi}
\Ket{\psi}\Bra{\phi}
```

不手工拼接尖括号和竖线，不改用首字母小写的同名命令。Dirac 宏已处理伸缩定界符，不在其外重复构造 bra 或 ket。

期望值优先写完整矩阵元 `\Braket{\psi|\hat A|\psi}`。若上下文已明确归一化态，可定义简记 `\Braket{\hat A}`，但不得省略对该简记的说明。

`\Braket{...}` 内的 `|` 是态和算符之间的分隔符，不是绝对值；内积的模应写成：

```latex
\left|\Braket{\phi|\psi}\right|^2
```

态标签内部含函数或集合时，仍遵守数学括号规范，例如 `\Ket{\psi\left(t\right)}` 和 `\Ket{\left\{n_k\right\}}`。

## 3. 算符、常数与微分

- nabla 直接写 `\nabla`，不使用任何加粗命令修饰它。
- 虚数单位写 `\mathrm{i}`，自然指数底数写 `\mathrm{e}`。
- 微分写 `\mathrm{d}`，积分中在微分前使用适当间距，如 `\,\mathrm{d}x`；模板中等价定义的 `\dd` 可按已有约定使用。
- 厄米共轭写 `\dagger`；群名、迹及实虚部等使用正体，例如 `\mathrm{SU}\left(2\right)`、`\mathrm{Tr}\,A`、`\operatorname{Re}`。
- 明确区分抽象算符、矩阵、本征值、态与展开系数，保持已定义的符号意义不变。

例如：

```latex
\left[\hat x,\hat p\right]=\mathrm{i}\hbar\hat I
\hat{\bm p}\leftrightarrow-\mathrm{i}\hbar\nabla
\int f\left(x\right)\,\mathrm{d}x
\mathrm{e}^{-\mathrm{i}\hat Ht/\hbar}
```

## 4. 公式环境与文档结构

- LaTeX 文件沿用现有文档类、宏包和模板，以 XeLaTeX 编译；公式使用 `equation`、`align`、`gather` 等 AMS 环境。
- 公式编号由环境生成，以 `\label`、`\eqref` 管理引用；未经明确要求不使用 `\tag{}` 手工编号。
- Markdown 行内公式用 `$...$`；行间公式的起止 `$$` 各占一行。Markdown 中不使用 `\(...\)` 或 `\[...\]`。
- 只修改任务涉及的内容，保留章节结构与数学含义，不为统一当前讲义而批量修改无关笔记。

## 5. 完成前检查

检查数学定界符的伸缩与配对、Dirac 命令大小写及参数、非加粗 nabla、正体常数与微分、公式引用和符号定义。重新编译 PDF，排除未定义命令、缺失引用及公式越界，并检查实际分页和长公式排版。

根目录原有规范已经规定 Dirac 命令、正体常数、微分与公式环境；“所有数学括号使用 `\left...\right`”和“nabla 不加粗”是本次明确补充的要求。
