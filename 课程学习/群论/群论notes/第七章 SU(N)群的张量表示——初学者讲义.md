# 第七章 $\mathrm{SU}(N)$ 群的张量表示——初学者讲义

依据：[[群论大纲]]第七章，1 学时。配套：[[第七章讲义生成提示词]]。先修：[[第五章 置换群——初学者讲义]]、[[第六章 三维转动群——初学者讲义]]。

## 阅读安排

这一章不要求一小时内掌握全部最高权理论。核心目标是会做三件事：写张量怎样变换；用对称与反对称、迹与无迹找到不变子空间；用杨图辨认结果。

建议核心阅读 1.1—1.7；1.8—1.10 是与第五章衔接的选读。所有表示默认在复数域上，$N\ge2$。粗体 $\mathbf N$ 表示基本表示的维数标签，不是群名；具体群名写为 $\mathrm{SU}(N)$。

## 第 1 节 $\mathrm{SU}(N)$ 群的张量表示

### 1.1 基本表示：每个矢量有 $N$ 个复分量

定义

$$
\mathrm{SU}(N)=\{U\in\operatorname{Mat}_N(\mathbb C):U^\dagger U=I,\ \det U=1\}.
$$

它自然作用于 $V=\mathbb C^N$：

$$
v'^i=U^i{}_jv^j.
$$

上下重复指标求和，范围为 $1,\ldots,N$。上标在这里是分量指标，不是乘方。这个 $N$ 维表示称基本表示。

取单位元附近 $U=I-i\epsilon T+O(\epsilon^2)$。幺正性给 $T^\dagger=T$；由 $\det e^{-i\epsilon T}=e^{-i\epsilon\operatorname{tr}T}=1$，得 $\operatorname{tr}T=0$。厄米矩阵有 $N^2$ 个实参数，无迹条件减去一个，因此群的实参数维数是 $N^2-1$。

例如 $\mathrm{SU}(3)$ 的基本表示三维，但群有八个独立生成元。这两种维数不应混淆。

**自测。** $\mathrm{SU}(2)$ 的生成元空间几维？答案：3，与三个 Pauli 矩阵对应。

### 1.2 基本、共轭与对偶表示

基本矢量按 $U$ 变换；它的复共轭分量按 $U^*$ 变换，这定义共轭表示 $\overline V$。对偶向量 $w$ 则是作用在 $v$ 上给出一个数的线性函数，写为 $w_iv^i$。

要求配对不变，得到

$$
w'_i=w_j(U^{-1})^j{}_i,\qquad w'_iv'^i=w_iv^i.
$$

如果把对偶分量排成列，其矩阵是 $(U^{-1})^{\mathsf T}=U^*$，所以对幺正群，$V^*$ 与 $\overline V$ 等价。但 $V$ 本身不一定与它们等价。

例如 $\mathrm{SU}(3)$ 中 $\mathbf3$ 与 $\overline{\mathbf3}$ 不等价：中心元 $zI$，$z=e^{2\pi i/3}$，在两者上分别作用为 $zI$、$z^{-1}I$。标量矩阵不能靠相似变换改变，因此不存在统一换基将二者等同。

**自测。** 为什么不能把上下指标仅当排版习惯？因为它们记录 $U$ 与逆矩阵两种不同的变换规则。

### 1.3 两个指标意味着两个因子同时变换

张量积 $V\otimes V$ 的基是 $e_i\otimes e_j$，共有 $N^2$ 个。一般元素不必能写成单个 $v\otimes u$，而是它们的线性组合。

二阶张量变换为

$$
T'^{ij}=U^i{}_aU^j{}_bT^{ab}.
$$

每个上指标都乘一个基本矩阵。混合张量则每个下指标乘逆矩阵，例如

$$
T'^{ij}{}_k=U^i{}_aU^j{}_b(U^{-1})^c{}_kT^{ab}{}_c.
$$

这些公式由两个或三个因子独立作用得到。它们定义表示，但表示常常可约：有些对称性条件在任意 $U$ 下都会保留。

**自测。** 三个基本指标的完整空间几维？答案：$N^3$；限制对称性以后才可能降低维数。

### 1.4 对称化与反对称化：第一种分解

交换算符 $P(v\otimes u)=u\otimes v$ 满足 $P^2=I$，并且与 $U\otimes U$ 对易。于是它的两个投影

$$
P_+=\frac{I+P}{2},\qquad P_-=\frac{I-P}{2}
$$

产生不变子空间。对任意 $T^{ij}$，

$$
T^{ij}=S^{ij}+A^{ij},\qquad
S^{ij}=\frac{T^{ij}+T^{ji}}2,\qquad
A^{ij}=\frac{T^{ij}-T^{ji}}2.
$$

对称部分有 $N$ 个对角分量、$N(N-1)/2$ 个非对角独立分量；反对称部分对角为零，只剩后者。因此

$$
\boxed{V\otimes V=\operatorname{Sym}^2V\oplus\bigwedge^2V,}
$$

$$
\dim\operatorname{Sym}^2V=\frac{N(N+1)}2,\qquad
\dim\bigwedge^2V=\frac{N(N-1)}2.
$$

取原基正交归一，对称基为 $e_i\otimes e_i$ 和 $(e_i\otimes e_j+e_j\otimes e_i)/\sqrt2$，$i<j$；反对称基为 $(e_i\otimes e_j-e_j\otimes e_i)/\sqrt2$，$i<j$。

这两块在 $\mathrm{SU}(N)$ 下不可约；一般结论来自杨图张量构造，此处先使用它。维数检查为 $N(N+1)/2+N(N-1)/2=N^2$。

特别提醒：$\mathrm{SU}(N)$ 一般不保持 $\sum_i v^iv^i$。它保持的是带复共轭的厄米内积，因此不能在纯上指标对称张量中随便“去掉一个迹”。这与 $\mathrm{SO}(3)$ 的二阶实张量分解不同。

**自测。** $N=3$ 时得到哪两块？答案：六维对称块和三维反对称块；后者的准确标签下一小节解释。

### 1.5 不变张量：为什么反对称块会是共轭表示？

混合 Kronecker 张量 $\delta^i{}_j$ 不变，允许一个上指标与一个下指标缩并。完全反对称张量规定 $\epsilon_{12\cdots N}=1$，满足

$$
\epsilon_{i_1\cdots i_N}U^{i_1}{}_{j_1}\cdots U^{i_N}{}_{j_N}
=(\det U)\epsilon_{j_1\cdots j_N}
=\epsilon_{j_1\cdots j_N}.
$$

最后一步正是“特殊幺正”中行列式为 1 的作用。由此 $\bigwedge^N V$ 是一维平凡表示。

若 $A^{i_1\cdots i_{N-1}}$ 完全反对称，定义

$$
w_j=\frac1{(N-1)!}\epsilon_{j i_1\cdots i_{N-1}}A^{i_1\cdots i_{N-1}}.
$$

利用上述不变性，把 $N-1$ 个 $U$ 化成剩余指标上的一个逆矩阵，得到 $w'_j=w_k(U^{-1})^k{}_j$。该映射可逆，故

$$
\boxed{\bigwedge^{N-1}V\cong V^*.}
$$

对 $N=3$，$w_k=\frac12\epsilon_{kij}A^{ij}$，例如 $w_1=A^{23}$。因此三维反对称块实际是 $\overline{\mathbf3}$，而不是 $\mathbf3$：

$$
\mathbf3\otimes\mathbf3=\mathbf6\oplus\overline{\mathbf3}.
$$

对 $N=2$，$\bigwedge^2V$ 是单态，所以 $\mathbf2\otimes\mathbf2=\mathbf3\oplus\mathbf1$。同时 $\bigwedge^{N-1}V=V\cong V^*$，说明二重态与共轭等价；这种等价借助反对称张量，不表示所有矩阵都能同时取成实数。

**自测。** 对 $\mathrm{SU}(4)$，$\bigwedge^2V$ 是 $\overline{\mathbf4}$ 吗？不是，它维数为 6；$\bigwedge^3V$ 才是四维共轭基本表示。

### 1.6 迹与无迹：第二种分解

混合张量 $M^i{}_j$ 是一个线性算符，其变换为

$$
M'=UMU^{-1}.
$$

迹不变，所以可以拆成

$$
M=\frac{\operatorname{tr}M}{N}I+\left(M-\frac{\operatorname{tr}M}{N}I\right).
$$

第一块一维，全部群元素都不改变它；第二块无迹，维数 $N^2-1$。相应投影为

$$
P_{\mathbf1}(M)=\frac{\operatorname{tr}M}{N}I,\qquad
P_{\mathrm{Adj}}(M)=M-\frac{\operatorname{tr}M}{N}I.
$$

两者幂等且互相正交，直和为恒等映射。因此

$$
\boxed{V\otimes V^*\cong\mathbf1\oplus\mathrm{Adj}.}
$$

无迹矩阵在共轭下的作用是复化伴随表示。$\mathrm{SU}(N)$ 的李代数实维数为 $N^2-1$；本处无迹复矩阵空间的复维数也为 $N^2-1$，但这两个空间的数域与实际元素不同。其不可约性对应复李代数 $\mathfrak{sl}_N(\mathbb C)$ 的单性。

对 $\mathrm{SU}(3)$ 得 $\mathbf3\otimes\overline{\mathbf3}=\mathbf1\oplus\mathbf8$。例如 $M=\operatorname{diag}(1,0,0)$ 分成 $I/3$ 与 $\operatorname{diag}(2/3,-1/3,-1/3)$。

**自测。** 纯张量 $T^{ij}$ 的“对称分解”和混合张量 $M^i{}_j$ 的“迹分解”能直接互换吗？不能，它们变换规则不同。

### 1.7 一课内应会算的三个结果

| 群与张量积 | 不可约分解 | 原因 |
|---|---|---|
| $\mathrm{SU}(2)$：$\mathbf2\otimes\mathbf2$ | $\mathbf3\oplus\mathbf1$ | 对称三维；完全反对称一维 |
| $\mathrm{SU}(3)$：$\mathbf3\otimes\mathbf3$ | $\mathbf6\oplus\overline{\mathbf3}$ | 对称六维；反对称张量可映为下指标 |
| $\mathrm{SU}(3)$：$\mathbf3\otimes\overline{\mathbf3}$ | $\mathbf8\oplus\mathbf1$ | 无迹矩阵加迹 |

一个实用流程是：先写清每个指标按什么变换；再找保持的对称性或缩并；数维数；最后识别不可约标签。只看维数相同，不足以判断两个表示等价。

## 选读补充：杨图与表示标签

### 1.8 同一张杨图为什么有两种维数？

对 $k$ 个基本张量指标，可用第五章杨算符按行对称、列反对称，从 $V^{\otimes k}$ 中构造子空间。由于 $U$ 对每个指标都同样作用，置换指标与 $U^{\otimes k}$ 对易，所以杨投影的像在群作用下不变。

纯基本张量的杨图若超过 $N$ 行，就要求反对称化超过 $N$ 个取值范围只有 $N$ 的指标，结果为零。若有一整列 $N$ 格，该列对应行列式因子；在 $\mathrm{SU}(N)$ 上是平凡的，因此删除它得到等价表示。可用至多 $N-1$ 行的图作为标准标签。

对最多 $N$ 行的图，维数由钩长–内容公式给出：

$$
\boxed{d_N(\lambda)=\prod_{(i,j)\in\lambda}\frac{N+j-i}{h_{ij}},}
$$

其中 $i,j$ 为行列位置，$h_{ij}$ 是钩长。这个公式与杨图张量方法可参看[矩阵群表示课程的维数部分](https://tomaszlukowski.github.io/Groups-and-representations-lecture-notes/Lectures/Lecture10.html#dimensions)。以下计算直接代入公式。

对形状 $(2,1)$，钩长依次为 $3,1,1$。在 $\mathrm{SU}(3)$ 中分子是 $3,4,2$，故

$$
d_3(2,1)=\frac{3\cdot4\cdot2}{3\cdot1\cdot1}=8.
$$

但在 $\mathrm{S}_3$ 中，维数是 $f^{(2,1)}=3!/(3\cdot1\cdot1)=2$。图相同，作用的群和承载空间不同，所以维数不同。

### 1.9 两个八维副本来自哪里？

在 $V^{\otimes k}$ 上，$\mathrm{SU}(N)$ 作用于指标取值，$\mathrm{S}_k$ 作用于指标位置，两种作用对易。Schur–Weyl 分解为

$$
V^{\otimes k}\cong\bigoplus_{\lambda\vdash k,\,\ell(\lambda)\le N}
V_\lambda^{(N)}\otimes M_\lambda.
$$

$\ell(\lambda)$ 是行数，$V_\lambda^{(N)}$ 是相应的 $\mathrm{SU}(N)$ 模，$M_\lambda$ 是维数 $f^\lambda$ 的 $\mathrm{S}_k$ 不可约模。忽略置换群作用时，后者就成为前者的副本空间。一般定理的完整证明不在本章展开。

对 $N=k=3$，三种图分别给出

$$
\begin{array}{c|ccc}
\lambda&(3)&(2,1)&(1,1,1)\\
d_3(\lambda)&10&8&1\\
f^\lambda&1&2&1
\end{array}
$$

所以

$$
\boxed{\mathbf3^{\otimes3}=\mathbf{10}\oplus\mathbf8\oplus\mathbf8\oplus\mathbf1,\qquad 27=10+8+8+1.}
$$

两个八维副本没有变成一个十六维不可约表示；群可以分别按相同的八维规律作用。副本之间的混合由与群对易的算符决定。

### 1.10 选读：Dynkin 标签与 LR 乘积

给杨图补零到 $N$ 行，并删除完整 $N$ 格列后，定义

$$
a_i=\lambda_i-\lambda_{i+1},\qquad i=1,\ldots,N-1.
$$

这些非负整数称 Dynkin 标签。它们不受所有行同时增加一个格的影响，因此自动忽略行列式因子。

$\mathrm{SU}(3)$ 用 $(p,q)$ 两个标签：基本表示为 $(1,0)$，共轭基本表示为 $(0,1)$，伴随为 $(1,1)$。维数是

$$
d(p,q)=\frac{(p+1)(q+1)(p+q+2)}2.
$$

代入分别得到 3、3、8；共轭对应 $(p,q)\mapsto(q,p)$。

纯张量杨图的乘积可用第五章 LR 规则计算，再删去超过 $N$ 行的零项，并把整列 $N$ 格作平凡行列式处理。这和第五章同一个 $\mathrm{S}_k$ 内部张量积的 Kronecker 规则不是一回事。LR 同时出现于对称群的诱导外积和这里的张量积，是两套表示理论之间的联系。

## 章末练习与解答

1. **数维数。** 分解 $\mathrm{SU}(4)$ 的 $\mathbf4\otimes\mathbf4$。解：对称十维加反对称六维，$16=10+6$；这里六维不是伴随表示，伴随维数为 15。
2. **混合张量。** 分解 $\mathbf4\otimes\overline{\mathbf4}$。解：$\mathbf1\oplus\mathbf{15}$，来自迹与无迹。
3. **反对称。** 为什么 $\mathrm{SU}(3)$ 的四阶完全反对称基本张量为零？解：四个指标只能取三个值，至少重复一个；交换重复指标使张量等于自身的负数。
4. **不变单态。** 在 $\mathrm{SU}(3)$ 中写三基本表示的单态。解：$\frac1{\sqrt6}\sum_{i,j,k}\epsilon_{ijk}e_i\otimes e_j\otimes e_k$，由行列式为 1 保持。
5. **投影。** 对 $M=\operatorname{diag}(2,1,0)$ 作迹分解。解：$M=I+\operatorname{diag}(1,0,-1)$。
6. **杨图。** 在 $\mathrm{SU}(3)$ 中算 $(3)$ 的维数。解：$3\cdot4\cdot5/(3\cdot2\cdot1)=10$。
7. **比较。** $(1,1,1)$ 在 $\mathrm{S}_3$ 与 $\mathrm{SU}(3)$ 中都一维，是否含义相同？解：前者是置换符号表示，后者是行列式为 1 的平凡表示；不能把标签跨群直接等同。
8. **共轭。** 为什么 $\mathbf3\otimes\mathbf3$ 没有单态而 $\mathbf3\otimes\overline{\mathbf3}$ 有？解：前者中心元作用为 $z^2\ne1$，不可能有不变向量；后者可作上下指标缩并。

### 最后检查

- [ ] 能区分基本表示维数 $N$、群参数维数 $N^2-1$ 和张量积维数。
- [ ] 能写上、下指标变换，不把纯张量和混合张量混同。
- [ ] 能推导两指标对称/反对称维数与混合张量迹分解。
- [ ] 能用 $\epsilon$ 解释共轭基本表示的来源。
- [ ] 能区分同一杨图在置换群和特殊幺正群中的维数。

本章的核心不是记住几个维数等式，而是理解：指标的变换规则决定了哪些对称化、反对称化和缩并能产生不变子空间。
