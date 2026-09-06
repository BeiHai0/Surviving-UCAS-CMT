# 第2节 态矢、算符与 Dirac 记号

[[高等量子力学总目录|总目录]] · 先修：[[量子力学基本原理|基本原理]] · 下一节：[[表象与表象变换|表象与表象变换]]

**约定：** 内积对右侧线性、对左侧反线性；保留 $\hbar$，使用 $\mathrm{i}$、$\mathrm{e}$。以下算符代数在有限维中直接成立；涉及无界算符时，必须保证所写内积、乘积与期望值有定义。

## 2.1 左矢、右矢与内积

右矢 $|\psi\rangle$ 属于 Hilbert 空间 $\mathcal H$，对应左矢 $\langle\psi|$ 是连续线性泛函。右矢到左矢的对应为反线性：对复数 $a,b$，

$$
(a|\psi\rangle+b|\phi\rangle)^\dagger
=a^*\langle\psi|+b^*\langle\phi|.
$$

内积满足共轭对称性与正定性：

$$
\langle\phi|\psi\rangle=\langle\psi|\phi\rangle^*,
\qquad \|\psi\|^2=\langle\psi|\psi\rangle\ge0,
$$

且范数为零当且仅当向量为零。在正交归一基中，若两态分量分别为 $d_n,c_n$，则 $\langle\phi|\psi\rangle=\sum_n d_n^*c_n$。归一化纯态间的跃迁概率是 $|\langle\phi|\psi\rangle|^2$。

## 2.2 外积与投影

内积是复数，外积是算符。外积的定义由它对任意输入的作用给出：

$$
(|u\rangle\langle v|)|w\rangle
=|u\rangle\langle v|w\rangle.
$$

因此，外积乘法只需收缩中间的内积：

$$
(|u\rangle\langle v|)(|s\rangle\langle t|)
=\langle v|s\rangle|u\rangle\langle t|.
$$

对非零 $|u\rangle$，沿其方向的正交投影为

$$
P_u=\frac{|u\rangle\langle u|}{\langle u|u\rangle},
\qquad P_u^2=P_u=P_u^\dagger.
$$

一般外积不一定是投影。对于完备正交归一基 $\{|n\rangle\}$，$\sum_n|n\rangle\langle n|=I$；只对部分基矢求和，得到的是子空间投影。完备关系将抽象态与具体表象连接起来，详见第3节。

## 2.3 线性与反线性算符

线性算符 $A$ 与反线性算符 $C$ 的区别在于复系数是否共轭：

$$
\begin{aligned}
A(a|\psi\rangle+b|\phi\rangle)
&=aA|\psi\rangle+bA|\phi\rangle,\\
C(a|\psi\rangle+b|\phi\rangle)
&=a^*C|\psi\rangle+b^*C|\phi\rangle.
\end{aligned}
$$

固定一个正交归一基，定义分量复共轭算符 $K$：

$$
K\sum_n c_n|n\rangle=\sum_n c_n^*|n\rangle,
\qquad K^2=I.
$$

任意反线性算符可写为 $C=MK$，其中 $M=CK$ 线性。两次反线性复合为线性；线性与反线性复合仍为反线性。$K$ 的定义依赖基底。

可逆反线性算符 $\Theta$ 若满足

$$
\langle\Theta\phi|\Theta\psi\rangle
=\langle\phi|\psi\rangle^*,
$$

则称为反幺正算符，可写成 $\Theta=UK$，其中 $U$ 幺正。它保持跃迁概率，但共轭内积。时间反演的重要特征正是 $\Theta\mathrm{i}\Theta^{-1}=-\mathrm{i}$。反线性本身不保证保持范数；“反线性”也不同于“反厄米”。

## 2.4 伴随与厄米性

**定义。** 对线性算符 $A$，伴随算符 $A^\dagger$ 由

$$
\langle\phi|A\psi\rangle
=\langle A^\dagger\phi|\psi\rangle
$$

定义。因此

$$
\langle\phi|A|\psi\rangle^*
=\langle\psi|A^\dagger|\phi\rangle,
\qquad
(A|\psi\rangle)^\dagger=\langle\psi|A^\dagger.
$$

在正交归一基中，$(A^\dagger)_{jk}=A_{kj}^*$，即转置并复共轭。常用规则为

$$
\begin{aligned}
(aA+bB)^\dagger&=a^*A^\dagger+b^*B^\dagger,\\
(AB)^\dagger&=B^\dagger A^\dagger,\\
(|u\rangle\langle v|)^\dagger&=|v\rangle\langle u|.
\end{aligned}
$$

乘积倒序来自连续两次移动算符：$\langle\phi|AB\psi\rangle=\langle A^\dagger\phi|B\psi\rangle=\langle B^\dagger A^\dagger\phi|\psi\rangle$。无界乘积的伴随等式还须满足相应定义域条件。上述规则按线性算符使用，不能不加区分地套给反线性算符。

有限维中，$A^\dagger=A$ 称为厄米或自伴，$A^\dagger=-A$ 称为反厄米。任意矩阵 $M$ 都可分解为 $M=X+\mathrm{i}Y$，其中

$$
X=\frac{M+M^\dagger}{2},
\qquad Y=\frac{M-M^\dagger}{2\mathrm{i}},
\qquad X^\dagger=X,\quad Y^\dagger=Y.
$$

无穷维中，“对称”只要求在 $D(A)$ 上有 $\langle\phi|A\psi\rangle=\langle A\phi|\psi\rangle$；“自伴”还要求 $D(A)=D(A^\dagger)$，其中 $D$ 表示定义域。对微分算符，边界条件属于算符定义的一部分。

## 2.5 厄米算符的主要性质

设 $A|a\rangle=a|a\rangle$，$|a\rangle\ne0$。由于

$$
a\langle a|a\rangle
=\langle a|A|a\rangle
=a^*\langle a|a\rangle,
$$

故 $a$ 为实数。对两个本征态，同理有 $(a-b)\langle a|b\rangle=0$，因此不同本征值对应的本征态正交。简并子空间内部可另选正交归一基。

有限维厄米算符具有完备正交本征基，因而

$$
A=\sum_a aP_a,
\qquad f(A)=\sum_a f(a)P_a,
$$

其中 $P_a$ 是本征子空间投影，$f$ 是定义在谱上的函数。连续谱应使用谱测度，不应理解成总有一组可归一化的普通本征矢。

在归一化态中，$\langle A\rangle$ 为实数。定义涨落算符 $\delta A=A-\langle A\rangle I$ 与标准差 $\Delta A$，则

$$
(\Delta A)^2
=\langle A^2\rangle-\langle A\rangle^2
=\|\delta A|\psi\rangle\|^2\ge0.
$$

因此 $\Delta A=0$ 当且仅当该纯态属于 $A$ 的某个本征子空间。几何上，$A|\psi\rangle=\langle A\rangle|\psi\rangle+\delta A|\psi\rangle$，第二项与原态正交，其长度就是涨落大小。

若 $A,B$ 都厄米，则

$$
(AB)^\dagger=BA,
\qquad [A,B]^\dagger=-[A,B],
\qquad \{A,B\}^\dagger=\{A,B\},
$$

其中 $[A,B]=AB-BA$、$\{A,B\}=AB+BA$。所以对易子的期望值为纯虚数或零。

有限维中，$[A,B]=0$ 当且仅当存在完备共同本征基：对易保证 $B$ 保持 $A$ 的每个本征子空间，再在这些子空间内对角化 $B$ 即可。无穷维自伴算符应使用谱投影彼此对易的强对易条件。

## 2.6 Schwarz 不等式

对任意 $|u\rangle,|v\rangle$，

$$
|\langle u|v\rangle|^2\le\|u\|^2\|v\|^2.
$$

证明只需减去投影。若 $v\ne0$，令 $|w\rangle=|u\rangle-|v\rangle\langle v|u\rangle/\langle v|v\rangle$，则

$$
0\le\|w\|^2
=\|u\|^2-\frac{|\langle v|u\rangle|^2}{\|v\|^2}.
$$

乘以 $\|v\|^2$ 即得结论；$v=0$ 时直接成立。取等当且仅当两向量线性相关，包括某一向量为零的情形。

## 2.7 不确定性关系及取等条件

设 $A,B$ 自伴，态归一化且所需二阶矩、算符乘积有定义。取涨落向量

$$
|f\rangle=\delta A|\psi\rangle,
\qquad |g\rangle=\delta B|\psi\rangle.
$$

其范数平方分别为两个方差，故 Schwarz 不等式给出

$$
(\Delta A)^2(\Delta B)^2
\ge|\langle\delta A\,\delta B\rangle|^2.
$$

利用 $\langle\delta A\delta B\rangle^*=\langle\delta B\delta A\rangle$，定义实的对称协方差 $C_{AB}$，并分解复重叠：

$$
\begin{aligned}
\operatorname{Re}\langle\delta A\delta B\rangle
&=C_{AB}:=\frac12\langle\{\delta A,\delta B\}\rangle,\\
\operatorname{Im}\langle\delta A\delta B\rangle
&=\frac1{2\mathrm{i}}\langle[A,B]\rangle.
\end{aligned}
$$

由复数模平方等于实部、虚部平方之和，得到 Schrödinger–Robertson 关系：

$$
\boxed{
(\Delta A)^2(\Delta B)^2
\ge C_{AB}^2+\frac14|\langle[A,B]\rangle|^2.
}
$$

舍去非负协方差项，再开平方，得到 Robertson 关系：

$$
\boxed{\Delta A\Delta B\ge\frac12|\langle[A,B]\rangle|.}
$$

强关系取等要求两个涨落向量线性相关；弱关系取等还要求 $C_{AB}=0$。若 $\Delta A>0$，弱关系取等可写为 $\delta B|\psi\rangle=\mathrm{i}\lambda\delta A|\psi\rangle$，其中 $\lambda$ 为实数。某个涨落为零时应单独处理，不能除以零。

代入 $[\hat x,\hat p]=\mathrm{i}\hbar I$ 得 $\Delta x\Delta p\ge\hbar/2$。一般下界依赖态；算符不对易不保证每个态的对易子期望值非零。

这里的标准差描述同一制备态的测量分布宽度，不是仪器误差，也不是直接描述先后两次测量的扰动。关系也适用于混合态，只需用 $\langle A\rangle=\operatorname{Tr}(\rho A)$；证明可对 $\delta A\sqrt\rho$、$\delta B\sqrt\rho$ 使用 Hilbert–Schmidt 内积下的 Schwarz 不等式。
