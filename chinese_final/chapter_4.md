## 第 4 章

## 信号与随机过程

本章将介绍信号与随机过程的基础知识，例如随机变量、系综平均、矩、随机过程、遍历过程、功率谱密度，以及随机过程与线性时不变系统之间的关系等。目的是让读者能够理解如何分析和处理随机信号，因为硬盘驱动器信号处理系统中传输的各种信息具有随机信号的特性。因此，本章的内容将帮助读者更好地理解信号与随机过程的特性，从而使后续章节的内容更容易理解。感兴趣的读者可以参考 [9, 35, 36] 了解更多详情。

## 4.1 引言

通信系统的主要目的是将信息 (information) 从发送端 (transmitter) 通过信道 (channel) 发送到接收端 (receiver)。通常，通信系统中的各种信息信号具有“随机信号 (random signal)”的特性，即在任何给定时刻，无法确定该随机信号的具体属性。随机信号的例子包括信息信号 (message signal) 和噪声 (noise) 等。

在分析随机信号时，通常将其转换为具有确定性信号 (deterministic signal) 特性的形式，以便利用线性时不变 (LTI: linear time-invariant) 系统的各种原理和理论进行分析，并从随机信号中提取所需的信息。用于将随机信号转换为确定性信号的数学工具包括自相关函数 (auto-correlation)、协方差函数 (covariance) 和功率谱密度 (power spectral density) 等。这些函数使用所谓的“期望算子 (expectation operator)”进行计算。因此，可以说期望算子的作用是消除随机信号的不确定性 (uncertainty)。

## 4.2 随机变量

考虑抛一枚硬币的实验，结果有两种可能，即“正面 (head)”或“反面 (tail)”。如果连续抛很多次硬币，通常会期望出现“正面”的次数与出现“反面”的次数大致相等。也就是说，如果定义 $N$ 为抛硬币的总次数，$n_H$ 为出现“正面”的次数，$n_T$ 为出现“反面”的次数，则有：

$$
\frac { n _ { H } } { N } \approx 0 . 5 ; \frac { n _ { T } } { N } \approx 0 . 5
$$

这意味着，如果硬币没有被加权（即公正的），那么结果为“正面”或“反面”的概率相等。在数学上，这两个结果的概率可以表示为：

$$
\mathrm { P r } \{ H \} = 0 . 5 ; \mathrm { P r } \{ T \} = 0 . 5\tag{4.1}
$$

其中 $\operatorname* { P r } \{ x \}$ 是 $x$ 发生的概率，$H$ 表示结果为“正面”，$T$ 表示结果为“反面”。此外，一次实验中所有可能结果的集合称为“样本空间 (sample space)”，用符号 $\Omega$ 表示，其总概率始终等于 1。也就是说：

$$
\mathrm { P r } \{ \Omega \} = 1\tag{4.2}
$$

对于抛硬币实验，其样本空间为：

$$
\Omega = \{ H , T \}
$$

样本空间的子集称为“事件 (event)”，而事件中的每个成员被称为“基本事件 (elementary event)” [35]。对于抛硬币实验，它包含两个基本事件：

$$
\\omega _ { 1 } = \\{ H \\} \\quad ; \\quad \\omega _ { 2 } = \\{ T \\}
$$

如果定义一个实变量 $x$ 来代表抛硬币的结果，规定当结果为“正面”时 $x = 1$，当结果为“反面”时 $x = - 1$。那么，我们可以定义一个从结果集 $\\omega _ { i } \\in \\Omega$ 到实数集 $\\mathbb{R}$ 的映射 $f : \\Omega \\to \\mathbb{R}$，如下所示：

$$
\\begin{array} { r c l } { \\omega _ { 1 } } & { = } & { \\{ H \\} \\implies \\ x = 1 } \\\\ { } & { } & { } \\\\ { \\omega _ { 2 } } & { = } & { \\{ T \\} \\implies \\ x = - 1 } \\end{array}
$$

根据方程 (4.1) 对抛硬币结果赋予的概率，可知 $x = 1$ 或 $x = - 1$ 的概率相等，即：

$$
\\begin{array} { r c l } { { \\mathrm { P r } \\{ x = 1 \\} } } & { { = } } & { { 0 . 5 } } \\\\ { { } } & { { } } & { { } } \\\\ { { \\mathrm { P r } \\{ x = - 1 \\} } } & { { = } } & { { 0 . 5 } } \\end{array}\\tag{4.3}
$$

由于抛硬币的结果只有两种可能（正面或反面），因此变量 $x$ 可能取得的值仅为 1 和 -1。对于其他任何 $x$ 值，其概率均为零，即：

$$
\\operatorname* { P r } \\{ x = \\alpha \\} = 0
$$

其中 $\\alpha \\neq \\pm 1$。而变量 $x$ 取值为 1 或 -1 的总概率为：

$$
\\mathrm { P r } \\{ \\Omega \\} = \\mathrm { P r } \\{ x = \\pm 1 \\} = 1
$$

通过为样本空间 $\Omega$ 中的每个基本事件赋予概率，并将每个基本事件 $\omega _ { i } \in \Omega$ 转换为一个实数，从而定义了“随机变量 (random variable)”。换句话说，随机变量 $X(A)$ 将随机事件 $A$ 转换为一个实数。例如，在一次抛硬币实验中，可能的结果有两种：1（代表正面）和 -1（代表反面），因此 $X(A) \in \{ 1, - 1 \}$。或者在一次掷骰子实验中，可能的结果有六种：1, 2, 3, 4, 5, 6，因此 $X(A) \in \{ 1, 2, 3, 4, 5, 6 \}$。

为样本空间中的每个事件 $A$ 赋予概率（实数）必须符合以下三个公理 (axiom)：

1) $\\operatorname* { P r } \\{ A \\} \\geq 0$，对于所有事件 $A \\in \\Omega$。
2) $\\mathrm { P r } \\{ \\Omega \\} = 1$，对于必然事件。
3) 对于两个互不相容事件 (mutually exclusive events) $A_1$ 和 $A_2$，有：

$$
\\operatorname* { P r } \\{ A _ { 1 } \\cup A _ { 2 } \\} = \\operatorname* { P r } \\{ A _ { 1 } \\} + \\operatorname* { P r } \\{ A _ { 2 } \\}
$$

在定义了样本空间中事件的概率之后，可以定义随机变量 $X$ 的概率。通常，这表现为随机变量 $X$ 取某个特定值或落在某个给定范围内的概率，例如 $\\mathrm { P r } \\{ X = 1 \\}$、$\\operatorname* { P r } \\{ X \\ = \\ - 1 \\}$ 或 $\\operatorname* { P r } \\{ 0 < X \\leq 1 \\}$。在实际操作中，随机变量的概率通常直接通过“概率分布函数 (probability distribution function)”或称为“累积分布函数 (cumulative distribution function)”来定义，定义如下：

$$
F _ { X } ( x ) = \\operatorname* { P r } \\{ X \\leq x \\}\\tag{4.4}
$$

其中 $F_X(x)$ 是随机变量 $X$ 的值小于或等于实数 $x$ 的概率。累积分布函数的重要性质如下：

1) $0 \\leq F _ { X } ( x ) \\leq 1$
2) 当 $x_1 < x_2$ 时，$F _ { X } ( x _ { 1 } ) \\leq F _ { X } ( x _ { 2 } )$
3) $F _ { X } ( - \\infty ) = 0$
4) $F _ { X } ( + \\infty ) = 1$

此外，累积分布函数的导数等于“概率密度函数 (probability density function)”，即：

$$
p _ { X } ( x ) = \\frac { d F _ { X } ( x ) } { d x }\\tag{4.5}
$$

概率密度函数的重要性质如下：

1) $0 \\leq p _ { X } ( x ) \\leq 1$
2) $\\textstyle \\operatorname* { P r } \\{ a \\leq X \\leq b \\} = \\int _ { a } ^ { b } p _ { X } ( x ) d x$
3) $F _ { X } ( x ) = \\int _ { - \\infty } ^ { x } p _ { X } ( \\alpha ) d \\alpha$
4) $\\int _ { - \\infty } ^ { \\infty } p _ { X } ( x ) d x = F _ { X } ( + \\infty ) - F _ { X } ( - \\infty ) = 1$

**示例 4.1**：假设随机变量 $X$ 是信息通过信道所花费的时间，且 $X$ 是一个概率函数为以下形式的指数随机变量 (exponential random variable)：

$$
\\operatorname* { P r } \\{ X > x \\} = e ^ { - \\lambda x } , \\quad x > 0
$$

其中 $x$ 为任意实数，$\\lambda$ 为常数。请计算：

a) 累积分布函数 $F _ { X } ( x )$
![](images/chapter_4/58e2f8b8591ff2973ee5f666d5425825db45d9be48e33d86c28f3bd9d1660f46.jpg)
![](images/chapter_4/9307009b43d829363349046f181e02b5edeabcd1533407ad98e0d25ffb506480.jpg)
图 4.1: (a) 累积分布函数 $F _ { X } ( x )$ 和 (b) 指数随机变量的概率密度函数 $p _ { X } ( x )$。

b) 当 $T = 1 / \\lambda$ 时，$\\operatorname* { P r } \\{ T < X \\leq 2 T \\}$ 的值。
c) 概率密度函数 $p _ { X } ( x )$。

**解**：
a) 累积分布函数可由以下方式求得：
$$
\\begin{array} { l l l } { F _ { X } ( x ) } & { = } & { \\operatorname* { P r } \\{ X \\leq x \\} } \\\\ & { = } & { 1 - \\operatorname* { P r } \\{ X > x \\} } \\\\ & { = } & { 1 - e ^ { - \\lambda x } } \\\\ & { = } & { \\left\\{ \\begin{array} { l l } { 0 , } & { x < 0 } \\\\ { 1 - e ^ { - \\lambda x } , } & { x \\geq 0 } \\end{array} \\right. } \\end{array}
$$
如图 4.1(a) 所示。

b) 根据累积分布函数的性质：
$$
{ \begin{array} { l l l } { \operatorname* { P r } \{ T < X \leq 2 T \} } & { = } & { \operatorname* { P r } \{ X < 2 T \} - \operatorname* { P r } \{ X < T \} } \\ & { = } & { ( 1 - e ^ { - \lambda 2 T } ) - ( 1 - e ^ { - \lambda T } ) } \\ & { = } & { e ^ { - \lambda T } - e ^ { - \lambda 2 T } } \end{array} }
$$
![](images/chapter_4/dae1fc760df8a5d2aed0fb5c9f7ee6bdcf82520300db14931c21ef4c97e467c8.jpg)
图 4.2: (a) 概率密度函数 $p _ { X } ( x )$ 和 (b) 均匀随机变量的累积分布函数 $F _ { X } ( x )$。

因此，当 $T = 1 / \lambda$ 时：
$$
\operatorname* { P r } \{ T < X \le 2 T \} = e ^ { - 1 } - e ^ { - 2 } \approx 0 . 2 3 3
$$

c) 由于 $F _ { X } ( x )$ 在所有 $x$ 值上都是连续的，因此除了 $x = 0$ 以外，其导数在所有 $x$ 处均存在。因此，概率密度函数 $p _ { X } ( x )$ 为：
$$
 p _ { X } ( x ) = \frac { d F _ { X } ( x ) } { d x } = \left\{ \begin{array} { l l } { 0 , } & { x < 0 } \\ { \lambda e ^ { - \lambda x } , } & { x > 0 } \end{array} \right.
$$
如图 4.1(b) 所示。

**示例 4.2**：假设均匀随机变量 (uniform random variable) $X$ 的概率密度函数为：
$$
p _ { X } ( x ) = { \left\{ \begin{array} { l l } { K , } & { a \leq x \leq b } \\ { 0 , } & { { \mathrm { e l s e } } } \end{array} \right. }
$$
如图 4.2(a) 所示。其中 $a$ 和 $b$ 为任意常数。请计算 $K$ 值及累积分布函数 $F _ { X } ( x )$。

**解**：$K$ 值可以通过利用概率密度函数的性质求得，即：
$$
\int _ { - \infty } ^ { \infty } p _ { X } ( x ) d x = 1
$$
$$
\int _ { a } ^ { b } K d x = 1
$$
$$
\begin{array} { l l l } { { K ( b - a ) } } & { { = } } & { { 1 } } \end{array}
$$
$$
\ K \ = \ { \frac { 1 } { b - a } }
$$

同理，累积分布函数可由以下方式求得：
$$
F _ { X } ( x ) = \int _ { - \infty } ^ { x } p _ { X } ( \alpha ) d \alpha
$$
其值为：
$$
F _ { X } ( x ) = { \left\{ \begin{array} { l l } { 0 , } & { x < a } \\ { { \frac { x - a } { b - a } } , } & { a \leq x \leq b } \\ { 1 , } & { x > b } \end{array} \right. }
$$
如图 4.2(b) 所示。

对于离散随机变量 (discrete random variable)，概率质量函数 (probability mass function) 将被用于替代概率密度函数，其定义为：

$$
p _ { X } ( x ) = \sum _ { i } { \mathrm { P r } } \{ x = x _ { i } \} \delta [ x - x _ { i } ]\tag{4.6}
$$

其中 $\delta [ \cdot ]$ 为克罗内克 $\delta$ 函数 (Kronecker delta function)。离散随机变量的累积分布函数可通过以下方式求得：

$$
F _ { X } ( x ) = \int _ { - \infty } ^ { x } p _ { X } ( y ) d y = \sum _ { i } \operatorname* { P r } \{ x = x _ { i } \} u [ x - x _ { i } ]\tag{4.7}
$$

![](images/chapter_4/1f143246ed7780a4d6f9efcaf6fe352a35ea13628e1718d2992bba7636623011.jpg)
图 4.3: (a) 累积分布函数 $F _ { X } ( x )$ 和 (b) 抛硬币实验的概率质量函数 $p _ { X } ( x )$。

其中 $u [ \cdot ]$ 为离散时间单位阶跃函数 (discrete-time unit step function)。例如，对于上述抛硬币实验，可得：

$$
F _ { X } ( x ) = { \left\{ \begin{array} { l l } { 0 , } & { x < - 1 } \\ { 0 . 5 , } & { - 1 \leq x < 1 } \\ { 1 , } & { x \geq 1 } \end{array} \right. }\tag{4.8}
$$

如图 4.3(a) 所示，而抛硬币实验的概率质量函数 $p _ { X } ( x )$ 如图 4.3(b) 所示。
