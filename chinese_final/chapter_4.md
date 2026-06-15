
## 4.2.6 重要离散随机变量

离散随机变量在许多涉及计数 (counting) 的应用中非常常见。本节将重点介绍与硬盘驱动器信号处理系统相关的伯努利随机变量 (Bernoulli random variable) 和二项随机变量 (binomial random variable)，具体如下：

### 伯努利随机变量

伯努利随机试验 (Bernoulli trial) 是一种随机试验，其结果可以分为两种情况：符合所需特性的结果称为“成功 (success)”，而不符合所需特性的结果称为“失败 (failure)”。例如，抛一枚硬币一次，如果结果为“正面”则视为成功，结果为“反面”则视为失败。另一个例子是，将比特 0 和比特 1 从发送端电路发送到接收端电路，如果发生错误，可将其称为成功；如果没有发生错误，则称为失败。

如果定义 $X$ 为伯努利随机试验的结果，那么 $X$ 就是一个伯努利随机变量，其可能取值为 $\Omega = \{ 0, 1 \}$。通常规定 $X = 1$ 代表成功，$X = 0$ 代表失败。若定义 $q$ 为成功的概率 $( 0 \leq q \leq 1 )$，则伯努利随机变量的概率质量函数定义为：

$$
\mathrm{Pr}\{ X = 0 \} = 1 - q \tag{4.34}
$$

$$
\mathrm{Pr}\{ X = 1 \} = q \tag{4.35}
$$

并且当 $k \neq 0$ 且 $k \neq 1$ 时，$\mathrm{Pr}\{ X = k \} = 0$。对于伯努利随机变量，其平均值为：

$$
E[X] = q \tag{4.36}
$$

其方差为：

$$
\operatorname{Var}(X) = q(1 - q) \tag{4.37}
$$

### 二项随机变量

考虑一个独立重复进行 $n$ 次的随机试验，且每次试验的结果只有两种：成功或失败。如果定义 $Y$ 为在 $n$ 次试验中事件 $A$ 发生的次数，那么随机变量 $Y$ 的所有可能取值为 $\{ 0, 1, \ldots, n \}$。例如，$Y$ 可以是抛硬币 $n$ 次中出现“正面”的次数。

由于每次试验的结果都是一个伯努利随机变量 $X$，因此二项随机变量 (binomial random variable) $Y$ 定义为：

$$
Y = \sum_{i=1}^n X_i \tag{4.38}
$$

其中 $X_i \in \{ 0, 1 \}$ 是第 $i$ 次试验的结果。因此，二项随机变量 $Y$ 的概率质量函数为：

$$
\begin{array}{rcl}
\mathrm{Pr}\{ Y = k \} & = & \binom{n}{k} q^k (1 - q)^{n-k} \\
& = & \frac{n!}{(n - k)! k!} q^k (1 - q)^{n-k}
\end{array} \tag{4.39}
$$

其中 $k = 0, 1, \ldots, n$ 且 $n! = n \times (n - 1) \times \ldots \times 2 \times 1$。对于二项随机变量，其平均值为：

$$
E[Y] = nq \tag{4.40}
$$

其方差为：

$$
\operatorname{Var}(Y) = nq(1 - q) \tag{4.41}
$$

通常，二项随机变量广泛应用于结果仅有两种可能性的试验，例如：正面/反面、正确比特/错误比特、合格零件/缺陷零件等。

**示例 4.6**
比特数据 0 和 1 通过一个含有噪声的信道传输，导致接收端电路以 0.00002 的概率做出错误判断。如果每条信息以数据块 (block) 的形式发送，且每个数据块包含 2000 个比特。
a) 求一个数据块中至少有一个比特发生错误的概率。
b) 如果一组信息包含 20 个数据块，求至少有 2 个数据块发生错误的概率。

**解：**
a) 令 $Y$ 为一个数据块（2000 比特）中发生错误的比特数，$q = 0.00002$ 为接收端电路判断错误的概率。因此，一个数据块中 $Y \geq 1$ 的概率可通过方程 (4.39) 计算，即：

$$
\begin{array}{lll}
\mathrm{Pr}\{ Y \geq 1 \} & = & 1 - \mathrm{Pr}\{ Y = 0 \} \\
& = & 1 - \binom{2000}{0} (0.00002)^0 (1 - 0.00002)^{2000-0} \\
& = & 1 - (1)(1)(0.99998)^{2000} \\
& = & 0.03921
\end{array}
$$

b) 令 $Z$ 为 20 个数据块中发生错误的数据块数量，$p$ 为单个数据块发生错误的概率，其值为 (a) 中计算的 0.03921。因此，$Z \geq 2$ 的概率为：

$$
\begin{array}{rcl}
\mathrm{Pr}\{ Z \geq 2 \} & = & 1 - \mathrm{Pr}\{ Z = 0 \} - \mathrm{Pr}\{ Z = 1 \} \\
& = & 1 - \binom{20}{0} (0.03921)^0 (1 - 0.03921)^{20} - \binom{20}{1} (0.03921)^1 (1 - 0.03921)^{19} \\
& = & 1 - (1)(1)(0.96079)^{20} - (20)(0.03921)(0.96079)^{19} \\
& = & 0.184
\end{array}
$$

## 4.3 随机过程

随机过程 (random process) $X(A, t)$ 可以被看作是两个随机变量的函数，一个是事件 $A$ 的随机变量，另一个是时间 $t$ 的随机变量。例如，假设将一个 10 伏特的电压产生器开启 $n$ 次，每次都记录电压随时间的变化情况，如图 4.5 所示。其中 $A_n$ 是开启事件，其原因可能是电压产生器内部的各种噪声。

![](images/chapter_4/be554e3b2a7a215e709b5f399a0bfa3c7da1b4e2fb3ad2819458afa0b243103f.jpg)
图 4.5：每次开启电压产生器时随机过程的示例。

如果仅考虑第 $j$ 次开启电压产生器的事件 $A_j$，则 $X(A_j, t) = X_j(t)$ 是一个样本函数 (sample function)，而所有样本函数的集合被称为“系综 (ensemble)” [36]。同样地，如果仅考虑时刻 $t_k$，则 $X(A, t_k)$ 是一个随机变量 $X(t_k)$，其值取决于事件 $A$。但如果具体到事件 $A = A_j$ 且时刻 $t = t_k$，则 $X(A_j, t_k)$ 将成为一个数值 (number)。为了方便描述随机过程，通常用 $X(t)$ 代替 $X(A, t)$。

### 4.3.1 平均值与自相关函数

与随机变量类似，随机过程必须被转换为确定性值 (deterministic value) 形式，以便于进行数据分析。在将随机过程转换为确定性值的数学工具中，最常用的两种是平均值 (mean) 和自相关函数 (auto-correlation function)。随机过程 $X(t)$ 在时刻 $t = t_k$ 的平均值（或一阶统计量）定义为：

$$
\begin{array}{lll}
m_X(t_k) & = & E[X(t_k)] \\
& = & \int_{-\infty}^{\infty} x p_{X_k}(x) dx
\end{array} \tag{4.42}
$$

其中 $p_{X_k}(x)$ 是时刻 $t_k$ 整个系综的概率密度函数。

同样地，随机过程 $X(t)$ 的自相关函数（或二阶统计量）被定义为两个变量 $t_1$ 和 $t_2$ 的函数，如下所示：

$$
\begin{array}{lll}
R_X(t_1, t_2) & = & E[X(t_1)X(t_2)] \\
& = & \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_{X_1 X_2}(x, y) dx dy
\end{array} \tag{4.43}
$$

其中 $X(t_1)$ 和 $X(t_2)$ 分别是随机过程 $X(t)$ 在时刻 $t_1$ 和 $t_2$ 的随机变量。自相关函数用于衡量来自同一随机过程的两个时刻之间数据的相关程度。也就是说，如果自相关函数的值很大，说明这两组随机变量之间具有很强的相关性。

此外，在某些情况下，需要计算随机过程 $X(t)$ 的“自协方差 (auto-covariance)” [36]，定义如下：

$$
\begin{array}{rcll}
C_X(t_1, t_2) & = & E[\{ X(t_1) - m_X(t_1) \}\{ X(t_2) - m_X(t_2) \}] & (4.44) \\
& = & E[X(t_1)X(t_2)] - E[X(t_1)] m_X(t_2) - m_X(t_1) E[X(t_2)] + m_X(t_1) m_X(t_2) \\
& = & R_X(t_1, t_2) - m_X(t_1) m_X(t_2) & (4.45)
\end{array}
$$

随机过程 $X(t)$ 的相关系数定义为 [36]：

$$
\rho_X(t_1, t_2) = \frac{C_X(t_1, t_2)}{\sqrt{C_X(t_1, t_1)} \sqrt{C_X(t_2, t_2)}} \tag{4.46}
$$

这可以用来衡量在同一随机过程中，利用其他随机变量的线性函数来预测任意时刻随机变量值的能力。

**注：** 两个不同的随机过程可能具有相同的平均值、自相关函数和自协方差函数。

**示例 4.7**
给定随机过程 $X(t) = A \cos(2\pi t)$，其中 $A$ 是一个随机变量。请计算随机过程 $X(t)$ 的平均值、自相关函数和自协方差函数。

**解：** 随机过程 $X(t)$ 的平均值可通过方程 (4.42) 求得，即：

$$
m_X(t) = E[A \cos(2\pi t)] = E[A] \cos(2\pi t)
$$

同样地，$X(t)$ 的自相关函数可通过方程 (4.43) 求得，如下所示：

$$
\begin{array}{rcl}
R_X(t_1, t_2) & = & E[X(t_1)X(t_2)] \\
& = & E[A \cos(2\pi t_1) A \cos(2\pi t_2)] \\
& = & E[A^2] \cos(2\pi t_1) \cos(2\pi t_2)
\end{array}
$$

而自协方差函数可通过方程 (4.45) 求得，即：

$$
\begin{array}{llll}
C_X(t_1, t_2) & = & R_X(t_1, t_2) - m_X(t_1) m_X(t_2) \\
& = & \{ E[A^2] - (E[A])^2 \} \cos(2\pi t_1) \cos(2\pi t_2) \\
& = & \sigma_A^2 \cos(2\pi t_1) \cos(2\pi t_2)
\end{array}
$$

由此可见，随机过程 $X(t)$ 的平均值 $m_X(t)$、自相关函数 $R_X(t_1, t_2)$ 和自协方差函数 $C_X(t_1, t_2)$ 均为时间的函数。

### 4.3.2 平稳性

如果一个随机过程的所有阶统计量都不随时间而变化，则称该随机过程具有“严平稳 (strict-sense stationary, SSS)”特性。严平稳随机过程易于分析，但在实际中并不常见，因为大多数通信系统不具备严平稳特性。同样地，如果一个随机过程仅一阶和二阶统计量不随时间而变化，则称其具有“宽平稳 (wide-sense stationary, WSS)”特性，即：

$$
E[X(t)] = m_X(t) = m_X \tag{4.47}
$$

其中 $m_X$ 是一个常数，且

$$
R_X(t_1, t_2) = R_X(t_1 - t_2) = R_X(\tau) = E[X(t + \tau) X(t)] \tag{4.48}
$$

其中 $\tau = t_1 - t_2$ 是时间差。因此，可以说 $R_X(t_1, t_2) = R_X(t_3, t_4)$ 当且仅当 $t_1 - t_2 = t_3 - t_4$。也就是说，自相关函数不取决于具体的时刻，而仅取决于时间差。WSS 的要求比 SSS 宽松，使得系统更接近实际情况，同时仍保持分析的便捷性。

因此，任何 SSS 随机过程必然是 WSS 的，但反之不一定成立。也就是说，一个 WSS 随机过程不一定是 SSS 的，除非该随机过程是高斯随机过程 (Gaussian random process)，在这种情况下，WSS 随机过程也是 SSS 的 [36]。因此，在分析通信系统时，通常假设信息信号和噪声信号为 WSS 随机过程，以简化数据分析。

**注：** 虽然随机过程通常不会在整个时间轴上保持平稳，但在实际操作中，仅关注其处于平稳状态的时间段就足以进行数据分析。

### 4.3.3 宽平稳随机过程的自相关

与使用方差衡量随机变量的随机性 (randomness) 类似，自相关函数被用于衡量随机过程的随机性。根据方程 (4.48)，自相关函数 $R_X(\tau)$

![](images/chapter_4/0881993fdbcf52504e911c0f141d34138418aaf9cc48c552c714b0a80a456675.jpg)
图 4.6：系统模型示例。

仅是时间差 $\tau = t_1 - t_2$ 的函数，其中 $-\infty < \tau < \infty$。

对于平均值为零的 WSS 随机过程 $X(t)$，其 $R_X(\tau)$ 还能揭示该随机过程相关的频率响应 (frequency response)。也就是说，如果 $R_X(\tau)$ 在 $\tau$ 从零开始增加时变化缓慢，意味着在时间段 $t = t_1$ 到 $t = t_1 + \tau$ 内，随机过程 $X(t)$ 的数据值在平均意义上较为接近。因此，若将 $X(t)$ 变换到频域，其频率响应将集中在低频区域。相反，如果 $R_X(\tau)$ 随 $\tau$ 的增加而迅速下降，则可以预见 $X(t)$ 在时域中变化剧烈，其频率响应将集中在高频区域。

1) $R_X(\tau) = R_X(-\tau)$ （关于 $\tau = 0$ 对称）
2) $| R_X(\tau) | \leq R_X(0)$ 对于所有 $\tau$ 成立（Cauchy-Schwarz 不等式）
3) $| R_X(\tau) | \Longleftrightarrow G_X(f)$ （傅里叶变换对）
4) $R_X(0) = E[X^2(t)]$ （$X(t)$ 的平均功率）

**示例 4.8**
考虑图 4.6 中的模型。设 $X(t)$ 是一个平均值为 $m_X$ 且自相关函数为 $R_X(\tau)$ 的 WSS 随机过程。请计算随机过程 $Y(t)$ 的平均值 $m_Y$ 和自相关函数 $R_Y(\tau)$。

**解：** 根据图 4.6 所示的模型，可得：

$$
Y(t) = X(t) - X(t - T)
$$

其中 $T$ 是一个比特的时间周期。因此，平均值 $m_Y$ 可由以下方式求得：

$$
\begin{array}{lll}
m_Y & = & E[Y(t)] \\
& = & E[X(t) - X(t - T)] \\
& = & E[X(t)] - E[X(t - T)] \\
& = & m_X - m_X \\
& = & 0
\end{array}
$$

同样地，自相关函数 $R_Y(\tau)$ 可由以下方式求得：

$$
\begin{array}{rcl}
R_Y(\tau) & = & E[Y(t + \tau) Y(t)] \\
& = & E[\{ X(t + \tau) - X(t + \tau - T) \} \{ X(t) - X(t - T) \}] \\
& = & E[X(t + \tau) X(t)] - E[X(t + \tau - T) X(t)] - E[X(t + \tau) X(t - T)] + E[X(t + \tau - T) X(t - T)] \\
& = & R_X(\tau) - R_X(\tau - T) - R_X(\tau + T) + R_X(\tau) \\
& = & 2 R_X(\tau) - R_X(\tau - T) - R_X(\tau + T)
\end{array}
$$

由于平均值 $m_Y = 0$ 与时间无关，且自相关函数 $R_Y(\tau)$ 仅取决于时间差 $\tau$，因此可以认为 $Y(t)$ 也是一个 WSS 随机过程。

**示例 4.9**
正弦波产生器产生一个频率为 $f_0$、幅度为 $A$ 的正弦信号，其方程为：

$$
X(t) = A \cos(2\pi f_0 t + \phi)
$$

其中 $\phi$ 是一个具有均匀分布 (uniform distribution) 的相位角随机变量，其概率密度函数为 $p_\Phi(\phi) = 1 / (2\pi)$。请计算随机过程 $X(t)$ 的平均值 $m_X$ 和自相关函数 $R_X(\tau)$。

**解：** 平均值 $m_X$ 可由以下方式求得：

$$
\begin{array}{rcl}
m_X & = & E\{ X(t) \} \\
& = & E\{ A \cos(2\pi f_0 t + \phi) \} \\
& = & A \int_0^{2\pi} \cos(2\pi f_0 t + \phi) p_\Phi(\phi) d\phi \\
& = & \frac{A}{2\pi} \int_0^{2\pi} \cos(2\pi f_0 t + \phi) d\phi \\
& = & \frac{A}{2\pi} [ \sin(2\pi f_0 t + \phi) ]_0^{2\pi} \\
& = & 0
\end{array}
$$

同样地，自相关函数 $R_X(\tau)$ 可由以下方式求得：

$$
\begin{array}{lll}
R_X(\tau) & = & E[X(t + \tau) X(t)] \\
& = & E[A^2 \cos(2\pi f_0 (t + \tau) + \phi) \cos(2\pi f_0 t + \phi)] \\
& = & \frac{A^2}{2} E[ \cos(2\pi f_0 \tau) + \cos(2\pi f_0 (2t + \tau) + 2\phi) ] \\
& = & \frac{A^2}{2} \cos(2\pi f_0 \tau) + \frac{A^2}{2} \underbrace{E[ \cos(2\pi f_0 (2t + \tau) + 2\phi) ]}_{= 0} \\
& = & \frac{A^2}{2} \cos(2\pi f_0 \tau)
\end{array}
$$

因此，$X(t)$ 是一个 WSS 随机过程，因为平均值 $m_X = 0$ 与时间无关，且自相关函数 $R_X(\tau)$ 仅取决于时间差 $\tau$。

### 4.3.4 各态历经过程

从方程 (4.42) 和 (4.33) 可以看出，为了计算随机过程的平均值和自相关函数，必须已知一阶和二阶联合概率密度函数。然而，在大多数实际应用中，很难获知所需的联合概率密度函数具体为何值。

对于一类特殊的随机过程，称为“各态历经过程 (ergodic process)”，其具有一个特性：时间平均值 (time average) 等于系综平均值。因此，可以通过计算单个样本函数的时间平均值来确定该随机过程的统计特性。通常，任何 SSS 随机过程都是各态历经的（但反之不一定成立）[9]。但在分析通信系统时，通常仅关注满足 WSS 条件的平均值和自相关函数。

因此，如果满足以下条件，则随机过程 $X(t)$ 被认为是“平均值各态历经 (ergodic in the mean)”的：

$$
m_X = \langle X(t) \rangle = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T X(t) dt \tag{4.49}
$$

该值等于系综平均值 $E[X(t)]$。同样地，如果满足以下条件，则随机过程 $X(t)$ 被认为是“自相关函数各态历经 (ergodic in the auto-correlation function)”的：

$$
R_X(\tau) = \langle X(t + \tau) X(t) \rangle = \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T X(t + \tau) X(t) dt \tag{4.50}
$$

该值等于 $E[X(t + \tau) X(t)]$。

测试一个随机过程是否具有各态历经性是非常困难的。因此，在分析通信系统时，通常假设系统中的随机信号（如信息信号和噪声信号）具有平均值各态历经和自相关函数各态历经特性，以简化数据分析。这是因为各态历经过程的时间平均值等于其系综平均值，且各种电学工程参数（如直流分量、平均功率等）与各态历经随机过程的矩相关 [9]。

**示例 4.10**
参考示例 4.9，正弦波产生器产生如下正弦信号：

$$
X(t) = A \cos(2\pi f_0 t + \phi)
$$

其中 $A$ 是信号幅度，$f_0$ 是频率，$\phi$ 是具有均匀分布的相位角随机变量。请计算随机过程 $X(t)$ 的时间平均值和时间自相关函数。

**解：** 时间平均值可通过以下方式求得：

$$
\begin{array}{lll}
\langle X(t) \rangle & = & \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T X(t) dt \\
& = & \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T A \cos(2\pi f_0 t + \phi) dt \\
& = & 0
\end{array}
$$

该值与示例 4.9 中的平均值 $m_X$ 相等。

同样地，时间自相关函数可通过以下方式求得：

$$
\begin{array}{rcl}
\langle X(t + \tau) X(t) \rangle & = & \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T A^2 \cos(2\pi f_0 (t + \tau) + \phi) \cos(2\pi f_0 t + \phi) dt \\
& = & \frac{A^2}{2} \lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T \{ \cos(2\pi f_0 \tau) + \cos(2\pi f_0 (2t + \tau) + 2\phi) \} dt \\
& = & \frac{A^2}{2} \cos(2\pi f_0 \tau) + \frac{A^2}{2} \underbrace{\lim_{T \to \infty} \frac{1}{2T} \int_{-T}^T \cos(2\pi f_0 (2t + \tau) + 2\phi) dt}_{= 0} \\
& = & \frac{A^2}{2} \cos(2\pi f_0 \tau)
\end{array}
$$

该值与示例 4.9 中的自相关函数 $R_X(\tau)$ 相等。因此，$X(t)$ 是一个 WSS 随机过程，并且具有平均值各态历经和自相关函数各态历经特性。

### 4.3.5 功率谱密度

随机过程 $X(t)$ 通常被归类为功率信号 (power signal)，其功率谱密度 (power spectral density) 为：

$$
G_X(f) = \mathcal{F}[ R_X(\tau) ] = \int_{-\infty}^{\infty} R_X(\tau) e^{-j 2\pi f \tau} d\tau \tag{4.51}
$$

也就是说，功率谱密度是自相关函数 $R_X(\tau)$ 的傅里叶变换。功率谱密度揭示了信号功率在频域中的分布情况，从而可以得知信号在每个频率分量上的功率值。

对于实值函数随机过程 $X(t)$，其功率谱密度具有以下重要性质：

1) $G_X(f) \geq 0$ 且为实函数。
2) $G_X(f) = G_X(-f)$ （关于 $f = 0$ 对称）。
3) $G_X(f)$ 与 $R_X(\tau)$ 互为傅里叶变换对。
4) 总功率 $P_X$ 为：
$$
P_X = \int_{-\infty}^{\infty} G_X(f) df
$$

**示例 4.11**
已知随机电报过程 (random telegraph process) $X(t)$ 的自相关函数为：

$$
R_X(\tau) = e^{-2\alpha |\tau|}
$$

其中 $\alpha$ 为信号的平均变化率。请计算 $X(t)$ 的功率谱密度。

**解：** $X(t)$ 的功率谱密度可通过方程 (4.51) 求得，即：

$$
\begin{array}{lll}
G_X(f) & = & \mathcal{F}[ R_X(\tau) ] \\
& = & \int_{-\infty}^0 e^{2\alpha \tau} e^{-j 2\pi f \tau} d\tau + \int_0^{\infty} e^{-2\alpha \tau} e^{-j 2\pi f \tau} d\tau \\
& = & \frac{1}{2\alpha - j 2\pi f} + \frac{1}{2\alpha + j 2\pi f} \\
& = & \frac{4\alpha}{4\alpha^2 + 4\pi^2 f^2}
\end{array}
$$

**示例 4.12**
设 $X(t)$ 是一个 WSS 白噪声过程 (white noise process)，在频带 $-W < f < W$ 范围内，其功率谱密度为 $N_0/2$（其中 $W$ 为 $X(t)$ 的带宽）。请计算 $X(t)$ 的总功率和自相关函数。

**解：** $X(t)$ 的总功率可通过以下方式求得：

$$
P_X = \int_{-W}^W \frac{N_0}{2} df = N_0 W
$$

而 $X(t)$ 的自相关函数是功率谱密度的傅里叶逆变换，即：

$$
\begin{array}{rcl}
R_X(\tau) & = & \mathcal{F}^{-1} [ G_X(f) ] \\
& = & \int_{-\infty}^{\infty} \frac{N_0}{2} e^{j 2\pi f \tau} df \\
& = & \frac{N_0}{2} \frac{e^{-j 2\pi W \tau} - e^{j 2\pi W \tau}}{-j 2\pi \tau} \\
& = & \frac{N_0}{2} \frac{\sin(2\pi W \tau)}{\pi \tau} \\
& = & N_0 W \operatorname{sinc}(2 W \tau)
\end{array}
$$

其中 $\operatorname{sinc}(t) = \sin(\pi t) / (\pi t)$ 为 sinc 函数。

在通信系统中，白噪声 (white noise) 通常指一个 WSS 随机过程 $W(t)$，其在所有频带 $(-\infty < W < \infty)$ 内的功率谱密度均为 $N_0/2$，即：

$$
G_W(f) = \frac{N_0}{2}
$$
