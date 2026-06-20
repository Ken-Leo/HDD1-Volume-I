## 第 5 章

## 基础通信原理

本章将介绍与硬盘驱动器信号处理系统相关的基础通信原理，例如基带传输系统、脉冲编码调制 (PCM)、脉冲幅度调制 (PAM)、匹配滤波器、误码率计算、码间干扰 (ISI)、奈奎斯特定理、采样定理以及各种均衡器等。这是因为硬盘驱动器的信号处理系统可以被视为一种通信系统。因此，读者在理解本章内容后，将有助于更容易地理解后续章节的内容。有关本章中提到的各项理论的详细信息，可参考 [9, 34, 37, 38, 39, 40]。

## 5.1 引言

通信系统 (communication system) 是指将信息从一个点（发送端）传输到另一个点（接收端）的系统，例如无线电通信系统、高速光纤通信系统和移动电话系统等。或者也可以认为，通信系统是将信息从一个时间段（发送端）传输到另一个时间段（接收端）的系统，例如硬盘驱动器的数据记录系统等。也就是说，信息在某一时刻被存储在记录介质 (medium) 中，经过一段时间后，信息再次从记录介质中被读取出来以供使用。通常，通信系统中传输的信息可以是任何形式，如语音、图像、视频、音乐、电子邮件、网页等。通信系统的主要目标是使接收端电路 (receiver) 能够检测并解码出发送端电路 (transmitter) 所发送的信息。

通常，通信系统可分为两大类：模拟通信系统和数字通信系统。这两者之间最显著的区别在于接收端的处理目标不同。模拟通信系统的接收端旨在重建一个与发送端发送的波形尽可能一致的新波形，因此，衡量模拟通信系统性能的指标是信号重建的保真度 (fidelity)。而数字通信系统的接收端则旨在判断发送端发送的波形是什么（并不需要知道发送信号的具体波形形状），因此，衡量数字通信系统性能的指标是接收端在做出判决时产生错误的概率，即误码率 (probability of error)。

读者可能会好奇，为什么早期的通信系统大多采用模拟方式？数字通信系统在过去不受欢迎的主要原因是它需要消耗大量的“带宽 (bandwidth)”，且模拟信号转换为数字信号的过程成本较高（价格昂贵），尽管数字电路具有更高的稳定性。促使人们转向使用数字通信系统的关键因素是各项技术和算法的进步，例如：压缩算法 (compression algorithm) 可减少传输所需的比特数；纠错码 (ECC: error-correction code) 技术可在接收端自动修正错误；数字信号处理 (DSP) 技术以及集成电路 (IC: integrated circuit) 的发展，特别是超大规模集成电路 (VLSI: very large scale integration) 技术的出现，极大地降低了数字电路的生产成本。

如今，数字通信系统已成为各种通信标准的基石，包括局域网 (LAN: local area network)、移动电话、以及各种无线通信系统（如 Bluetooth, Wi-Fi 和 Wi-MAX 等）。这是因为数字信号相比模拟信号具有以下优点：

- 数字信号更容易实现信号重建 (signal reconstruction)。
- 数字信号对失真 (distortion) 和干扰 (interference) 具有更强的鲁棒性。
- 为数字信号设计的电子电路更灵活且成本更低。
- 基于时分复用 (TDM: time division multiplexing) 的数字信号聚合技术比基于频分复用 (FDM: frequency division multiplexing) 的模拟信号聚合技术复杂度更低。
- 语音、图像、音乐和电子邮件等各类信息都可以转换为数字信号，从而方便地进行聚合传输。
- 为支持数字信号而开发的新型处理技术（如纠错码和加密技术 encryption）极大地提升了传输效率和安全性。

尽管数字信号具有诸多优点，但其缺点也可总结如下：

- 数字传输系统需要复杂的同步过程，包括比特 (bit)、符号 (symbol)、帧 (frame) 等的同步，而实现同步的电路复杂度高且价格昂贵。
- 当系统运行在信号功率与噪声功率之比（即信噪比 SNR: signal-to-noise ratio）低于某个阈值 (threshold level) 时，数字通信系统的性能会迅速下降。与之相对，模拟通信系统在相同情况下的性能下降则较为平缓。
- 数字通信系统的中继器 (repeater) 比模拟通信系统的中继器更复杂且成本更高。

然而，从整体上看，数字通信系统的效率远高于模拟通信系统。此外，在带宽有限但对数据传输速率要求不断提高的背景下，采用数字通信系统已成为必然选择。

## 5.1.1 数字通信系统的性能指标

在实际应用中，用于比较数字通信系统性能的指标主要是信噪比 (SNR) 和误码率 (BER: bit-error rate)，具体细节如下：

### 信噪比 (SNR)

SNR 是一个可用于比较系统性能的指标。例如，假设两个系统在检测器 (detector) 输出端的 BER 相同，那么其中发送功率较低（即所需 SNR 较低）的系统被认为效率更高。

在实际操作中，SNR 的定义方式多种多样，具体取决于给定的条件，例如系统中测量 SNR 的参考点位置。此外，在硬盘驱动器信号处理系统的分析中，计算 SNR 时使用的噪声成分可能包含加性噪声 (additive noise) 和介质噪声 (medium noise) 的总和，这取决于具体应用的要求。

### 误码率 (BER)

BER 同样可以用作比较系统性能的指标。也就是说，在相同 SNR 条件下，BER 越低，系统性能越好。通常，BER 是 SNR 的函数，即随着 SNR 的增加，BER 会降低。然而，在实际应用中，不能盲目地要求系统在极高 SNR 下工作，因为这会带来巨大的成本。因此，能够使硬盘驱动器信号处理系统在较低 SNR 水平下正常工作的设计，相当于能够实现更高的数据存储密度。

通常，针对不同应用，BER 被用作确定系统可靠性的标准。例如：语音传输在 $\text{BER} \leq 10^{-3}$ 时质量良好；数据传输在 $\text{BER} \leq 10^{-5}$ 时质量良好；光纤传输在 $\text{BER} \leq 10^{-12}$ 时质量良好；而硬盘驱动器设备则要求 $\text{BER} \leq 10^{-20}$ 才能保证质量良好。

## 5.1.2 基带传输系统

硬盘驱动器的信号处理系统可以被视为一种“基带传输系统 (baseband transmission system)” [5]。其通用模型如图 5.1 所示。也就是说，来自信源 (source) 的信息 (message) 可能是数字信号、数字数据序列，或者是以模拟信号的形式存在。这些信息将被格式化为数字数据序列，其可能的幅度值为 $L$ 个。每个幅度值由 $k = \log_2(L)$ 比特的二进制数据 (binary data) 表示，每个比特的值为 0 或 1。在将比特序列发送至目的地时，发送端电路 (transmitter) 将从符号集 $\{m_i\}$ ($i = 1, 2, \dots, M$) 中选择一个符号 (symbol)，每个符号代表 $k$ 个比特，即 $M = 2^k$。当 $M=2$ 时，所得符号为二进制数据，每个符号称为一个“比特 (bit)”。当 $M > 2$ 时，所得符号为 M 进制数据 (M-ary data)。随后，数据序列 $m_i$ 与脉冲信号 (pulse signal) 进行调制 (modulation)，转换为基带模拟信号 $r_i(t)$，然后发送至通信信道 (communication channel)。通常，不同的通信信道具有不同的特性，这可以通过信道的带宽和频率响应来分析。表 5.1 给出了各种通信系统物理信道的示例。

![](images/chapter_5/6c1f315786fdc771401d0f1372d5c3e805edc184e32d96c1e0a135f4cc01c056.jpg)
图 5.1: 基带传输系统模型

例 5.1: 在将消息 "PIYA" 发送到目的地时，系统将每个字符转换为 ASCII 码。如果使用 8 比特表示每个 ASCII 码，则发送的总比特数为 $4 \times 8 = 32$ 比特。在二进制系统（即 $M=2$）中，系统使用两种不同的信号来每次发送 $k = \log_2(M) = 1$ 比特的数据。例如，使用信号 $r_0(t)$ 表示比特 0，使用信号 $r_1(t)$ 表示比特 1。同样地，在 16-ary 系统（即 $M=16$）中，系统使用 16 种不同的信号来每次发送 $k = \log_2(16) = 4$ 比特的数据，如图 5.2 所示。

表 5.1: 各种通信系统的物理信道示例

<table><tr><td>通信系统</td><td>物理信道</td></tr><tr><td>家庭电话</td><td>电话线</td></tr><tr><td>移动电话</td><td>空气</td></tr><tr><td>卫星通信</td><td>空气, 大气层, 真空</td></tr><tr><td>互联网</td><td>电话线, 电缆, 光纤等</td></tr><tr><td>硬盘驱动器数据记录</td><td>磁记录盘</td></tr></table>

Binary system: $M=2, k=1$
![](images/chapter_5/0eed1b3ba875588115481cd100f141172aa4ba741b85deb9e13f182467887083.jpg)

16-ary system: $M=16, k=4$
![](images/chapter_5/b6d9101e44e57f7631691fdfb0d39d347f2dbbd7c375718868bf353e290cd565.jpg)
图 5.2: 每个字符转换为 ASCII 码的示例

通过信道传输的数据速率可通过“数据传输率 (data rate)” $R$ 来衡量，定义为：
$$
R = \frac{\log_2(M)}{T} = \frac{k}{T} \tag{5.1}
$$
单位为比特每秒 (bps: bit per second)，其中 $M = 2^k$ 是传输中使用的总符号数，$k$ 是代表一个符号的比特数，$T$ 是一个符号（$k$ 比特）的周期，单位为秒。传输通过信道的数据会受到噪声 (noise)、码间干扰 (IS: intersymbol interference) 以及信道带宽限制等因素的影响，导致接收端电路接收到的信号 $p(t)$ 波形与发送的信号 $r_i(t)$ 产生偏差。随后，在接收端，信号 $p(t)$ 经过解调 (demodulation) 和采样 (sampling)，将模拟信号转换为数字序列 $\{y_k\}$，然后发送至检测器，以决定符号 $m_i$ 的估计值（即求 $\hat{m}_i$）。最后，将符号估计值 $\hat{m}_i$ 重新格式化为所需的信息。

例 5.2: 假设一张数字图像的分辨率为 $800 \times 600$ 像素。每个像素由红、绿、蓝三原色组成，每种颜色有 64 个可能的亮度级。如果通过移动电话的 MMS 服务发送这张图像总共耗时 10 秒。
解：由于每个亮度级可以用 $k = \log_2(64) = 6$ 比特表示，因此每个像素总共需要 $3 \times 6 = 18$ 比特。由此，该数字图像总共需要 $800 \times 600 \times 18 = 8,640,000$ 比特。根据公式 (5.1)，该图像的数据传输率为：
$$
R = \frac{8,640,000}{10} = 864,000
$$
比特每秒，即 864 kbps (kilobit per second)。

## 5.1.3 信道容量

通常，数据传输率 $R$ 受多种参数限制，例如发送信号的平均功率、信道的失真 (distortion) 和干扰 (disturbance)、噪声的平均功率、误码率等。在信道不存在失真和干扰的情况下，系统可以用无限的数据传输率进行无误传输。

Claude Elwood Shannon [41] 提出了计算通信系统的信道容量 (channel capacity) $C$（即最大数据传输率）的方法。假设信道带宽限制为 $W$，且系统中仅存在加性高斯白噪声 (white Gaussian noise)，则信道容量 $C$ 可由下式计算 [9, 37, 41]：
$$
C = W \log_2(1 + \mathrm{SNR}) \tag{5.2}
$$
单位为比特每秒 (bps)。

香农定理 (Shannon's theorem) 指出：在设计数据传输率为 $R$ 的数字通信系统时，如果 $R < C$，则可以通过使用纠错码 (ECC) 将接收端电路的误码率 (BER) 降低到任意小的值（甚至为零）。相反，如果 $R > C$，则无法设计出无误的通信系统。

## 5.1.4 脉冲编码调制

参考图 5.1 中的模型，当信息为模拟信号（例如语音、图像等）时，需要通过“脉冲编码调制 (PCM: pulse code modulation)”或 PCM 过程 [9, 38] 将其转换为数字信息。该过程包含三个步骤：采样 (sampling)、量化 (quantization) 和编码 (encoding)，如图 5.3 所示。各步骤的一般工作原理如下：

![](images/chapter_5/d4b98dcde01c834aebce4ac28d118e1b92eeed296007fd9a3be0085a01da5539.jpg)
图 5.3: 脉冲编码调制 (PCM) 过程

### 采样 (Sampling)

采样是指将模拟信号转换为“数值序列 (numeric sequence)”的过程，也称为“模数转换 (analog-to-digital conversion)”。序列中的每个成员被称为一个“采样值 (sample)”，其值为实数。例如，若令 $x(t)$ 为模拟信号，则采样值可通过在每个时刻 $t = kT_s$ 对信号 $x(t)$ 进行采样获得，其中 $k$ 为整数，$T_s$ 为采样周期 (sampling period)。采样的输出结果可以用以下数学表达式表示：
$$
x[k] = x(t)|_{t=kT_s} = x(kT_s) \tag{5.3}
$$
即每个数据 $x[k]$ 之间的时间间隔为 $T_s$。

在实际应用中，用于信号采样的频率（称为采样频率 sampling frequency）$f_s = 1/T_s$ 必须符合“采样定理 (sampling theorem)”，以确保采样得到的数据能够等效地还原为原模拟信号。也就是说，若信号 $x(t)$ 的最高频率为 $f_{\max}$ 赫兹，则符合采样定理的采样频率应满足：
$$
f_s \geq 2 f_{\max} \tag{5.4}
$$

所使用的电子电路必须更加复杂，并且需要大量的寄存器 (register) 来存储采样值 $x[k]$。因此，必须通过一个将采样值 $x[k]$ 近似为有限取值范围的过程来降低电子电路的复杂度，这个过程称为**量化 (quantization)**。

### 量化 (Quantization)

量化是指将具有实数值的采样值近似为有限集合中某个值的过程。其中，每个采样值 $x[k]$ 将被近似为与其最接近的量化电平 (quantization level) 的值。量化后的输出数据称为量化采样值 (quantized sample) $x_q[k]$。通常，量化可分为两种类型：**均匀量化 (uniform quantization)** 和**非线性量化 (nonlinear quantization)**。

均匀量化将信号范围划分为多个等间距的电平，每个电平的间隔 $\Delta$ 相同，如图 5.4 所示。例如，如果使用 8 比特来表示一个采样值 $x_q[k]$，则量化电平总数为 $L = 2^8 = 256$ 个。若模拟信号的幅度在 $\pm V_p$ 伏特之间（即信号峰峰值 $V_{pp} = 2 V_p$），则量化间隔为 $\Delta = 2 V_p / 256 = V_p / 128$ 伏特。与之相反，非线性量化将信号范围划分为多个电平，但各电平的间隔不一定相同。

若信号 $x(t)$ 的幅度在 $\pm V_p$ 伏特范围内，均匀量化得到的采样值为：
$$
x_q[k] = x[k] + e[k] \tag{5.5}
$$
其中 $-\Delta/2 \le e[k] \le \Delta/2$ 称为量化误差 (quantization error)。如果信号 $x(t)$ 的幅度超出 $\pm V_p$ 伏特范围，量化误差将大于 $\Delta/2$，这在实际应用中应尽量避免。因为量化误差就像一种噪声，会干扰从量化采样值 $x_q[k]$ 还原模拟信号 $x(t)$ 的过程。由于量化误差 $e[k]$ 在 $-\Delta/2$ 到 $\Delta/2$ 之间呈均匀分布 (uniform distribution)，因此其概率密度函数 (probability density function) 可写为：
$$
p(e) = \frac{1}{\Delta} \tag{5.6}
$$

### 量化 (Quantization)

量化是指将具有实数值的采样值近似为有限集合中某个值的过程。其中，每个采样值 $x[k]$ 将被近似为与其最接近的量化电平 (quantization level) 的值。量化后的输出数据称为量化采样值 (quantized sample) $x_q[k]$。通常，量化可分为两种类型：**均匀量化 (uniform quantization)** 和**非线性量化 (nonlinear quantization)**。

均匀量化将信号范围划分为多个等间距的电平，每个电平的间隔 $\Delta$ 相同，如图 5.4 所示。例如，如果使用 8 比特来表示一个采样值 $x_q[k]$，则量化电平总数为 $L = 2^8 = 256$ 个。若模拟信号的幅度在 $\pm V_p$ 伏特之间（即信号峰峰值 $V_{pp} = 2 V_p$），则量化间隔为 $\Delta = 2 V_p / 256 = V_p / 128$ 伏特。与之相反，非线性量化将信号范围划分为多个电平，但各电平的间隔不一定相同。

若信号 $x(t)$ 的幅度在 $\pm V_p$ 伏特范围内，均匀量化得到的采样值为：
$$
x_q[k] = x[k] + e[k] \tag{5.5}
$$
其中 $-\Delta/2 \le e[k] \le \Delta/2$ 称为量化误差 (quantization error)。如果信号 $x(t)$ 的幅度超出 $\pm V_p$ 伏特范围，量化误差将大于 $\Delta/2$，这在实际应用中应尽量避免。因为量化误差就像一种噪声，会干扰从量化采样值 $x_q[k]$ 还原模拟信号 $x(t)$ 的过程。由于量化误差 $e[k]$ 在 $-\Delta/2$ 到 $\Delta/2$ 之间呈均匀分布 (uniform distribution)，因此其概率密度函数 (probability density function) 可写为：
$$
p(e) = \frac{1}{\Delta} \tag{5.6}
$$
因此，$e[k]$ 的平均值 (mean) 为：
$$
\begin{array}{lll} 
m_e & = & E[e] \\
& = & \displaystyle \int_{-\Delta/2}^{\Delta/2} e p(e) de \\
& = & \displaystyle \left. \frac{1}{\Delta} \left[ \frac{e^2}{2} \right]_{e=-\Delta/2}^{\Delta/2} \right. \\
& = & 0 
\end{array} \tag{5.7}
$$
而 $e[k]$ 的均方误差 (MSE: mean-squared error) 为：
$$
\begin{array}{rl} 
\sigma_e^2 & = E[(\epsilon - m_e)^2] \\
& = E[e^2] \\
& = \displaystyle \int_{-\Delta/2}^{\Delta/2} e^2 p(e) de \\
& = \frac{1}{\Delta} \left[ \frac{e^3}{3} \right]_{-\Delta/2}^{\Delta/2} \\
& = \frac{1}{\Delta} \left[ \frac{(\Delta^3) - (-\Delta^3)}{3(4)} \right] \\
& = \frac{\Delta^2}{12} 
\end{array} \tag{5.8}
$$
其中 $\sigma_e^2$ 即为量化噪声 (quantization noise) 的平均功率。

为了衡量量化误差导致的信号质量下降程度，使用“信号量化噪声比 (SQNR: signal-to-quantization noise ratio)”这一参数，定义为：
$$
\mathrm{SQNR} = 10 \log_{10} \left( \frac{\mathrm{signal\ power}}{\mathrm{quantization\ noise\ power}} \right) \tag{5.9}
$$
单位为分贝 (dB: decibel)。

**例 5.3**: 假设信号为正弦波 $x(t) = A \sin(2\pi ft)$，其中 $A$ 为信号幅度，使用 $m$ 比特量化器（即一个采样值由 $m$ 比特表示）。请证明：
$$
\mathrm{SQNR} \approx 1.8 + 6m \ \mathrm{(dB)}
$$
**解**: 由于信号 $x(t)$ 是周期为 $T_0$ 的周期信号，因此正弦波的平均功率可由（参考 21.4 节）计算得：
$$
\begin{array}{lll} 
P & = & \displaystyle \frac{1}{T_0} \int_0^{T_0} |A \sin(2\pi ft)|^2 dt \\
& = & \displaystyle A^2 \frac{1}{T_0} \int_0^{T_0} \{ 1 - \cos(4\pi ft) \} dt \\
& = & \displaystyle \frac{A^2}{2} 
\end{array}
$$
由于信号 $x(t)$ 的幅度范围在 $-A$ 到 $A$ 之间，若量化器使用 $L$ 个量化电平，则量化间隔为：
$$
\Delta = \frac{2A}{L}
$$
因此，量化噪声的平均功率可由公式 (5.8) 计算得：
$$
\sigma_e^2 = \frac{\Delta^2}{12} = \frac{4(A^2 / L^2)}{12} = \frac{A^2}{3L^2}
$$
于是，SQNR 为：
$$
\begin{array}{rcl} 
\operatorname{SQNR} & = & 10 \log_{10} \left( \frac{A^2 / 2}{A^2 / (3L^2)} \right) \\
& = & 10 \log_{10} \left( \frac{3L^2}{2} \right) \\
& = & 1.8 + 20 \log_{10}(L) 
\end{array}
$$
由于 $m$ 比特量化器的量化电平数 $L = 2^m$，将其代入上式得：
$$
\mathrm{SQNR} = 1.8 + 20 \log_{10}(2^m) \approx 1.8 + 6m
$$

在实际应用中，均匀量化器 (uniform quantizer) 仅在输入信号的概率密度函数呈均匀分布时才能提供较高的 SQNR。但如果输入信号具有其他概率密度函数，则量化器应在信号幅度较小（弱信号）的区域采用较小的量化间隔，并在信号幅度较大（强信号）的区域采用较大的量化间隔，这种量化间隔不等的量化器被称为**非线性量化器 (nonlinear quantizer)**。图 5.5 展示了均匀量化器和非线性量化器的工作特点。通常，非线性量化器能更有效地降低整体信号失真，且综合性能优于均匀量化器。有关量化器的更多详细信息，可参考 [9, 38]。

![](images/chapter_5/e8432d432a52be4553005e46173246af138a330c4113e3387c2c4094e012d8fe.jpg)
(a) 均匀量化器

![](images/chapter_5/4a58d4efa70e167790ff32bf68ca77362e0c78bcf70395ba7aa0278ad5031bd3.jpg)
(b) 非线性量化器
图 5.5: 量化器工作特点示例 (a) 均匀量化器 和 (b) 非线性量化器

### 编码 (Encoding)

在经过量化步骤后，每个量化采样值 $x_q[k]$ 将被进行编码，以转换为比特数据。每个采样值由 $k = \log_2(L)$ 个比特表示，其中 $L$ 是量化器中使用的量化电平数。所有这些比特数据的总称称为：

![](images/chapter_5/b90bf3612c63850a387daf99550422a865278ee3d89f57a2f2f4ea5a9d5884d8.jpg)
图 5.6: 脉冲编码调制 (PCM) 过程图

“PCM 序列 (PCM sequence)”。如果采样频率为 $f_s$ 赫兹/秒（或每秒 $f_s$ 个采样值），那么 PCM 序列的比特率 $R_b$（即数据传输率）为：
$$
R_b = \frac{1}{T_b} = k f_s \tag{5.10}
$$
单位为比特每秒 (bps)，其中 $T_b$ 为比特周期，$k$ 为每个采样值所用的比特数。图 5.6 展示了 PCM 过程的工作特点。

**例 5.4**: 在电话系统中，语音信号的采样频率为 8000 Hz，且每个采样值使用 7 比特量化。那么，电话信道中 PCM 序列的比特率是多少？
**解**: $R_b = 8000 \times 7 = 56,000$ 比特每秒。

接下来的步骤是将得到的 PCM 序列与脉冲信号进行调制，将其转换为 PCM 波形信号 (PCM waveform)。这一步骤通常被称为“线路编码 (line code)”。在实际应用中，PCM 波形有多种形式，例如：不归零码 (NRZ: non-return-to-zero)、差分不归零码 (NRZI: non-return-to-zero interleaved)、曼彻斯特编码 (Manchester) 等 [9]。每种形式都有其各自的优缺点，具体取决于所采用的应用场景。通常，选择某种 PCM 波形信号的衡量标准包括 [9]：

- 信号频谱特性：有助于了解功率谱密度和带宽。
- 比特同步能力。
- 错误检测能力。
- 对干扰和噪声的鲁棒性。
- 电路实现的成本 and 复杂度。

在硬盘驱动器的信号处理系统中，常用的波形格式是 NRZ 和 NRZI（详见 6.2.6 节）。

**例 5.5**: 将语音信号以 $R_b = 36,000$ bps 的比特率进行 PCM 传输。已知要采样的语音信号最高频率为 3200 Hz。请计算可能的采样频率、量化电平数以及每个采样值的比特数。
**解**: 根据采样定理，采样频率必须满足：
$$
f_s \geq 2 f_{\max} = 2(3200) = 6400 \ \mathrm{Hz}
$$
设每个采样值的比特数位 $k$，则有：
$$
k f_s \leq R_b = 36,000 \ \mathrm{bps}
$$
因此，实际采样频率和每个采样值的比特数可通过下式计算：
$$
k \leq \frac{R_b}{f_s} = \frac{36,000}{6,400} = 5.6
$$
假设系统采用 $k = 5$ 比特/采样值，则量化电平数 $L$ 为：
$$
L = 2^k = 2^5 = 32
$$
为了在每个采样值使用 5 比特的情况下达到此要求，采样频率应为：
$$
f_s = \frac{36,000}{5} = 7200 \ \mathrm{Hz}
$$

## 5.1.5 脉冲幅度调制

脉冲幅度调制 (PAM: pulse amplitude modulation) 是一种将数字数据与脉冲信号相结合的调制方法，其结果是一种被称为“PAM 信号 (PAM signal)”的模拟信号。其数学表达式如下：
$$
r(t) = \sum_{k=0}^{\infty} a_k g(t - kT) \tag{5.11}
$$
其中 $a_k \in \mathcal{A}$ 是属于集合 $\mathcal{A}$ 的数字数据，$\mathcal{A}$ 是所有可能数据值的集合，$g(t)$ 是用于调制的脉冲信号，$t$ 为时间，$T$ 为 $a_k$ 的周期。在硬盘驱动器的信号处理系统中，通常仅涉及二进制系统 (binary system)，因此 $|\mathcal{A}| = 2$，其中 $\mathcal{A} = \{0, 1\}$ 或 $\mathcal{A} = \{-1, 1\}$。

图 5.7 展示了脉冲幅度调制的示例。假设脉冲信号为：
$$
g(t) = A \frac{t}{T} \{ u(t) - u(t-T) \}
$$
其中 $u(t)$ 为单位阶跃函数，$A$ 为常数。若数据序列 $\{a_k\} = \{1, -1, 1, -1, -1, 1\}$，则得到的信号 $r(t)$ 形状如图 5.7 所示。在这种情况下，可以发现从波形中能够立即判断发送的是比特 -1 还是比特 1，且 $r(t)$ 没有发生失真。

![](images/chapter_5/6d6d5efeca88bb6cf8f99385e3f1a01e1e3967c2bb27b643694d7ec15eef8d9f.jpg)
图 5.7: 脉冲幅度调制示例

## 5.1.6 噪声

噪声 (noise) 是系统不需要的信号，因为它会干扰接收端电路检测和解码信息的能力。因此，如果系统中的噪声过多，接收端电路产生的错误也会随之增加。通信系统中常见的噪声有多种类型，在本节中，我们将重点讨论白噪声 (white noise) 和有色噪声 (colored noise)，这两者在硬盘驱动器的信号处理系统中非常常见。

### 白噪声

在离散时间系统 (discrete-time system) 中，白噪声是指一个互不相关 (uncorrelated) 的随机变量序列 $\{n_k\}$，其自相关函数为 [35]：
$$
R_{nn}(k) = \frac{N_0}{2} \delta[k] = \begin{cases} N_0/2, & k=0 \\ 0, & \text{else} \end{cases} \tag{5.12}
$$
其中 $N_0/2$ 是噪声的双边功率谱密度 (two-sided power spectrum density)，单位为瓦特/赫兹 (W/Hz)，$\delta[k]$ 是克罗内克 $\delta$ 函数 (Kronecker delta function)，其傅里叶变换为：
$$
G_n(e^{j\omega}) = \mathscr{F}[R_{nn}(k)] = \sum_{k=-\infty}^{\infty} R_{nn}(k) e^{-j\omega k} = \frac{N_0}{2} \tag{5.13}
$$
其中 $G_n(e^{j\omega})$ 是 $n_k$ 的功率谱密度，$\omega = 2\pi f$ 是角频率，单位为弧度 (radian)。公式 (5.13) 表明 $G_n(e^{j\omega})$ 与频率无关，即对于所有 $-\infty < f < \infty$，都有 $G_n(e^{j\omega}) = N_0/2$。这意味着白噪声会对所有频带的通信系统产生影响，且噪声 $n_k$ 的总功率为无穷大。因此，通信系统的接收端电路必须使用低通滤波器 (low-pass filter) 来使噪声功率变得有限，即不允许截止频率 (cut-off frequency) 之外的噪声进入系统。虽然白噪声在通信系统中普遍存在，但由于其统计特性确定且固定，因此较为容易处理。

由于白噪声仅由公式 (5.12) 定义，因此一个互不相关的实数高斯随机变量序列也被视为一种白噪声过程 (white noise process)，通常被称为“加性高斯白噪声 (white Gaussian noise)”，其概率密度函数遵循公式 (4.28)。白噪声的一个典型例子是热噪声 (thermal noise)。

### 有色噪声

有色噪声是指任何不具备白噪声特性的噪声。有色噪声的重要特性是其各个采样值之间存在相关性 (correlation)。若令 $w_k$ 为有色噪声，其自相关函数为：
$$
R_{ww}(k) \neq 0, \quad \text{for } k \neq 0 \tag{5.14}
$$
这种相关性具有多种用途，例如可以帮助预测未来的采样值或辅助分析系统的响应（详见 2.7.3 节）。

有色噪声在硬盘驱动器的信号处理系统中非常普遍。因为当白噪声通过任何滤波器（如均衡器）时，输出结果将变为有色噪声，且其频谱与该滤波器的频谱相似。由于有色噪声对数据检测电路的影响极大，因此研究人员提出了许多处理方法。例如，在某些硬盘驱动器接收端电路中使用了噪声预测器 (noise predictor)，这种电路被称为“噪声预测最大似然 (NPML: noise-predictive maximum-likelihood) 检测器”，详见《数字数据存储信号处理 第 2 卷：接收端设计》一书的第 6 章 [6]。

## 5.1.7 无失真传输

无失真传输 (distortionless transmission) 发生在信道的输出信号仍保持与输入信号相同的“形状 (shape)”时，但输出信号的幅度可能会发生变化或出现时间延迟 [39]。通常，通信系统（如电话系统和无线通信系统）的信道可被视为一个带限线性滤波器 (band-limited linear filter)，其冲激响应为 $g(t)$，频率响应为：
$$
G(f) = |G(f)| \angle G(f) \tag{5.15}
$$
其中 $|G(f)|$ 是 $G(f)$ 的幅度谱，$\angle G(f)$ 是 $G(f)$ 的相位谱。因此可以得出结论，该信道不产生失真的条件是信道具有恒定的幅度谱和线性相位谱，即：
$$
|G(f)| = |K| \tag{5.16}
$$
$$
\angle G(f) = -2\pi t_d f \pm m 180^\circ \tag{5.17}
$$
其中 $K$ 和 $m$ 为常数，$t_d$ 为延迟量。

通常，信号在传输过程中会遇到失真，失真可分为：
1) **线性失真 (linear distortion)**，进一步分为：
   1.1) 幅度失真 (amplitude distortion)：当 $|G(f)| \neq |K|$ 时发生。
   1.2) 相位失真 (phase distortion)：当 $\angle G(f) \neq -2\pi t_d f \pm m 180^\circ$ 时发生。
2) **非线性失真 (nonlinear distortion)**：当系统中存在非线性电子元件或部件时发生。

在实际应用中，线性失真的影响可以通过使用均衡器 (equalizer) 来消除或减轻（详见 5.6 节），而处理非线性失真则需要采用更先进的技术 [39]。

**例 5.6**: 考虑一个无失真的基带模拟传输系统，系统中存在双边功率谱密度为 $N_0/2$ 的白噪声 $n(t)$，其中 $N_0 = 10^{-9}$ 瓦特/赫兹。发送的信号是带宽为 4000 赫兹的语音信号。接收端使用一个截止频率为 8000 赫兹的低通滤波器来减少噪声。假设该低通滤波器的频率响应为：
$$
H_{LP}(\omega) = \frac{1}{1 + j(\omega/\omega_0)}
$$
![](images/chapter_5/80c24f7b2cb4f1e01e0bba629b84ebf9d05935555428117136c1d82a859ac935.jpg)
图 5.8: 低通滤波器的频率响应

当 $\omega_0 = 2\pi(8000)$ 弧度时（如图 5.8 所示），请计算该低通滤波器输出端的噪声功率。

**解**: 低通滤波器输出端的噪声功率可通过公式 (4.56) 计算，即：
$$
\begin{array}{rcl} 
P_n & = & E[n^2(t)] \\ 
& = & \displaystyle \frac{1}{2\pi} \int_{-\infty}^{\infty} \frac{N_0}{2} |H_{LP}(\omega)|^2 d\omega \\ 
& = & \displaystyle \frac{N_0}{2} \frac{1}{2\pi} \int_{-\infty}^{\infty} \frac{1}{1 + (\omega/\omega_0)^2} d\omega \\ 
& = & \displaystyle \frac{N_0}{2} \omega_0 \\ 
& = & \displaystyle \frac{10^{-9}}{2} \times 2\pi(8000) \\ 
& = & \displaystyle 25.132 \times 10^{-6} \ \mathrm{W} 
\end{array}
$$
因此，低通滤波器输出端的噪声功率为 $25.132 \times 10^{-6}$ 瓦特。

![](images/chapter_5/1dc59100fb5374c91d78d73bd83cc5d9aa248f2a56cfb2b17e6098474c384ab0.jpg)
图 5.9: 加性高斯白噪声中的数据检测通信系统模型

## 5.2 加性高斯白噪声中的数据检测

本节将介绍在仅存在加性高斯白噪声 (AWGN: additive white Gaussian noise) 的通信系统中的数据检测 (data detection) 步骤，如图 5.9 所示。其中，$a_k \in \{a_0, a_1\}$ 为比特输入数据，比特周期为 $T$，$\{a_0, a_1\}$ 的取值为 $\{0, 1\}$ 或 $\{-1, 1\}$。$g_t(t)$ 为用于调制的脉冲信号（或可视为信道的冲激响应），其有效时间范围为 $0 \le t \le T$，这意味着不会产生码间干扰 (ISI)。因此，接收端电路接收到的信号为：
$$
p(t) = r(t) + n(t) \tag{5.18}
$$
其中 $r(t) = \sum_k a_k g_t(t - kT)$ 是发送的数据脉冲信号，$n(t)$ 是均值为零且双边功率谱密度为 $N_0/2$ 的加性高斯白噪声。随后，信号 $p(t)$ 通过一个冲激响应为 $g_r(t)$ 的滤波器，并在 $t = kT$（$k$ 为整数）时刻进行采样。采样得到的数值 $y_k$ 被发送至阈值检测器 (threshold detector)，用于对数据 $a_k$ 进行译码，即求出 $\hat{a}_k$。

### 5.2.1 匹配滤波器 (Matched Filter)

匹配滤波器 (matched filter) 是一种线性接收滤波器 (receiving filter)，其设计旨在与接收到的每种波形 (waveform) 相匹配，从而使滤波器输出端的信噪比 (SNR) 最大化。考虑仅发送单个脉冲 (isolated pulse) 的情况（即该脉冲仅与单个数据比特 $a_k$ 相对应），此时信号 $r(t)$ 可以用以下数学表达式表示：
$$
r(t) = \begin{cases} r_0(t), & 0 \leq t \leq T \quad \text{for } a_k = a_0 \\ r_1(t), & 0 \leq t \leq T \quad \text{for } a_k = a_1 \end{cases} \tag{5.19}
$$
根据图 5.9 的模型，在 $t = T$ 时刻，采样电路的输出数据为：
$$
y(T) = a(T) + n_0(T) \tag{5.20}
$$
为了方便在该节中进行阐述，可将其简写为：
$$
y = a_k + n_0 \tag{5.21}
$$
其中 $a_k = a(T)$ 是所需信号的分量，$n_0 = n_0(T)$ 是噪声分量。可以证明，$n_0$ 是一个均值为零、方差为 $\sigma^2$ 的高斯随机变量，即 $n_0 \sim \mathcal{N}(0, \sigma^2)$。因此，在 $t = T$ 时刻，采样电路输出端的信噪比 (SNR) 为：
$$
\mathrm{SNR}_T = \frac{a_k^2}{\sigma^2} \tag{5.22}
$$
其中 $a_k^2$ 是所需信号 $a(t)$ 在 $t = T$ 时刻的平均功率。因此，匹配滤波器 $g_r(t) = g_0(t)$ 即为使公式 (5.22) 中的 $\mathrm{SNR}_T$ 达到最大值的滤波器。

由于在采样电路之前的所需信号分量为：
$$
a(t) = \mathcal{F}^{-1} [R(f) G_0(f)] = \int_{-\infty}^{\infty} R(f) G_0(f) e^{j 2\pi f t} df \tag{5.23}
$$
其中 $R(f)$ 是信号 $r(t)$ 的傅里叶变换，$G_0(f)$ 是匹配滤波器 $g_0(t)$ 的傅里叶变换。因此，在 $t = T$ 时刻采样得到的所需信号值为：
$$
a_k = a(T) = \int_{-\infty}^{\infty} R(f) G_0(f) e^{j 2\pi f T} df \tag{5.24}
$$
同样地，噪声 $n_0$ 的平均功率为：
$$
\sigma^2 = \int_{-\infty}^{\infty} N(f) |G_0(f)|^2 df = \frac{N_0}{2} \int_{-\infty}^{\infty} |G_0(f)|^2 df \tag{5.25}
$$
其中 $N(f) = N_0/2$ 是噪声 $n(t)$ 的傅里叶变换。将公式 (5.24) 中的 $a_k$ 和公式 (5.25) 中的 $\sigma^2$ 代入公式 (5.22)，可得：
$$
\mathrm{SNR}_T = \frac{\left| \int_{-\infty}^{\infty} R(f) G_0(f) e^{j 2\pi f T} df \right|^2}{\frac{N_0}{2} \int_{-\infty}^{\infty} |G_0(f)|^2 df} \tag{5.26}
$$
根据施瓦茨不等式 (Schwarz's inequality) [9]：
$$
\left| \int_{-\infty}^{\infty} f_1(x) f_2(x) dx \right|^2 \le \int_{-\infty}^{\infty} |f_1(x)|^2 dx \int_{-\infty}^{\infty} |f_2(x)|^2 dx \tag{5.27}
$$
其中 $f_1(x)$ 和 $f_2(x)$ 是任意函数。当且仅当
$$
f_1(x) = K f_2^*(x) \tag{5.28}
$$
时，公式 (5.27) 等号成立。其中 $K$ 为常数，$(\cdot)^*$ 表示共轭复数 (complex conjugate) 操作。若令 $f_1(x) = G_0(f)$ 且 $f_2(x) = R(f) e^{j 2\pi f T}$，则有：
$$
\left| \int_{-\infty}^{\infty} R(f) G_0(f) e^{j 2\pi f T} df \right|^2 = \int_{-\infty}^{\infty} |R(f)|^2 df \int_{-\infty}^{\infty} |G_0(f)|^2 df \tag{5.29}
$$
当且仅当
$$
G_0(f) = K R^*(f) e^{-j 2\pi f T} \tag{5.30}
$$
随后，将公式 (5.29) 代入公式 (5.26)，可得 $\mathrm{SNR}_T$ 的最大值为：
$$
\begin{array}{rcl} 
\mathrm{SNR}_{T, \max} & = & \displaystyle \frac{\int_{-\infty}^{\infty} |R(f)|^2 df \int_{-\infty}^{\infty} |G_0(f)|^2 df}{\frac{N_0}{2} \int_{-\infty}^{\infty} |G_0(f)|^2 df} \\
& = & \displaystyle \frac{2}{N_0} \int_{-\infty}^{\infty} |R(f)|^2 df \\
& = & \displaystyle \frac{2E}{N_0} 
\end{array} \tag{5.31}
$$
其中
$$
E = \int_{-\infty}^{\infty} |R(f)|^2 df = \int_{-\infty}^{\infty} |R(t)|^2 dt \tag{5.32}
$$
是信号 $r(t)$ 的能量。可见，$\mathrm{SNR}_T$ 的最大值取决于信号能量和噪声的平均功率，而与脉冲信号 $r(t)$ 的形状无关。

因此，匹配滤波器的频率响应符合公式 (5.30)，其傅里叶逆变换为：
$$
g_0(t) = \mathcal{F}^{-1} [G_0(f)] = \mathcal{F}^{-1} [K R^*(f) e^{-j 2\pi f T}] \tag{5.33}
$$
由于信号 $r(t)$ 是实函数，因此公式 (5.33) 可以写为：
$$
g_0(t) = K r(T - t) = r(T - t) \tag{5.34}
$$
在不丢失信息的情况下，可设 $K = 1$。由此可见，匹配滤波器 $g_0(t)$ 即为将脉冲信号 $r(t)$ 进行折叠 (folding) 并延迟 $T$ 秒后的信号。图 5.10 展示了在给定信号 $r(t)$ 时如何求得匹配滤波器 $g_0(t)$ 的示例。对于二进制通信系统，使用匹配滤波器的接收端电路结构如图 5.11 所示。

### 5.2.2 相关器 (Correlator)

考虑图 5.9 中的模型，接收滤波器的输出信号 $y(t)$ 可以用以下数学表达式表示：
$$
y(t) = p(t) * g_r(t) = \int_{-\infty}^{\infty} p(\tau) g_r(t - \tau) d\tau \tag{5.35}
$$
其中 $*$ 为卷积运算符 (convolution operator)。如果系统使用匹配滤波器作为接收滤波器，即 $g_r(t) = g_0(t)$，将公式 (5.34) 中的 $g_0(t) = r(T - t)$ 代入公式 (5.35)，可得：
$$
y(t) = \int_{-\infty}^{\infty} p(\tau) r(T - [t - \tau]) d\tau \tag{5.36}
$$
在 $t = T$ 时刻，可得：
$$
y(T) = \int_{-\infty}^{\infty} p(\tau) r(\tau) d\tau \tag{5.37}
$$
公式 (5.37) 通常被称为 $p(t)$ 与 $r(t)$ 之间的相关计算 (correlation)。基于公式 (5.37) 构建的接收端电路被称为“相关器 (correlator)”。对于二进制通信系统，发送数据的信号有两种，即 $r_0(t)$ 和 $r_1(t)$。因此，使用相关器的接收端电路结构如图 5.12 所示。由此可见，匹配滤波器也可以构建为相关器的形式（对比图 5.11 和图 5.12）。

![](images/chapter_5/315af3c43207b8e64ca2663b5ea08cdd5f7644ef20d47823dfe334e5faf27785.jpg)
图 5.12: 使用相关器的二进制通信系统接收端电路结构

### 5.2.3 判定规则

根据图 5.9 中的通信系统模型，当匹配滤波器 $g_0(t)$ 被用作接收滤波器时，采样电路在 $t = T$ 时刻的输出数据将符合公式 (5.21)，即：
$$
y = a_k + n_0 \tag{5.38}
$$
其中 $a_k \in \{a_0, a_1\}$ 是所需的比特数据，$n_0 \sim \mathcal{N}(0, \sigma^2)$ 是加性高斯白噪声，其概率密度函数为：
$$
p(n) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp \left\{ - \frac{n^2}{2\sigma^2} \right\} \tag{5.39}
$$
其中 $\exp\{\cdot\}$ 为指数函数。根据公式 (5.38)，在给定 $a_k$ 的条件下，$y$ 成为一个高斯随机变量，其均值为 $a_0$ 或 $a_1$，方差为 $\sigma^2$。因此，条件概率密度函数 (conditional probability density function) $p(y | r_0)$ 表示在给定符号 $r_0 = r_0(t)|_{t=T} = r_0(T)$ 被发送（对应于 $a_0$）的情况下，随机变量的概率密度函数，其值为：
$$
p(y | r_0) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp \left[ - \frac{(y - a_0)^2}{2\sigma^2} \right] \tag{5.40}
$$

同样地，$p(y | r_1)$ 表示在给定符号 $r_1 = r_1(t)|_{t=T} = r_1(T)$ 被发送（对应于 $a_1$）的情况下，随机变量的概率密度函数，其值为：
$$
p(y | r_1) = \frac{1}{\sqrt{2\pi\sigma^2}} \exp \left[ - \frac{(y - a_1)^2}{2\sigma^2} \right] \tag{5.41}
$$

若定义：
- $H_0$ 为发送符号 $r_0 = r_0(T)$ 的假设（对应于 $a_k = a_0$）
- $H_1$ 为发送符号 $r_1 = r_1(T)$ 的假设（对应于 $a_k = a_1$）

阈值检测器将对数据 $y$ 进行解码，以根据以下判定规则决定发送端发送的比特数据是 $a_0$ 还是 $a_1$：
$$
y_k \stackrel{H_1}{\gtrless} \gamma \tag{5.42}
$$
其中 $\gamma$ 为阈值电平。在设计阈值检测器时，系统设计者的目标是寻找最佳的 $\gamma$ 值，以使检测器输出端的错误概率最小化，或者寻找使给定 $y$ 时 $r_i$（$i=0$ 或 1）的条件概率密度函数
$$
p(r_i | y)
$$
最大化的 $\gamma$。因此，阈值检测器采用的判定规则为：
$$
p(r_1 | y) \stackrel{H_1}{\gtrless} p(r_0 | y) \tag{5.43}
$$
采用公式 (5.43) 判定规则的检测器被称为“MAP（最大后验概率，maximum a-posteriori probability）检测器”。

根据贝叶斯定理 (Bayes' theorem)，即 $p(a | b) = p(b | a) p(a) / p(b)$，公式 (5.43) 可以重新写为：
$$
\frac{p(y | r_1) p(r_1)}{p(y)} \stackrel{H_1}{\gtrless} \frac{p(y | r_0) p(r_0)}{p(y)} \tag{5.44}
$$
其中 $p(r_0)$ 和 $p(r_1)$ 分别是发送符号 $r_0$ 和 $r_1$ 的先验概率密度函数 (a-priori probability density function)。公式 (5.44) 可整理为：
$$
\frac{p(y | r_1)}{p(y | r_0)} \stackrel{H_1}{\gtrless} \frac{p(r_0)}{p(r_1)} \tag{5.45}
$$
公式 (5.45) 中的判定规则通常被称为“似然比测试 (likelihood ratio test)”。

在 $p(r_0) = p(r_1)$ 的情况下，即发送端发送符号 $r_0$ 或 $r_1$ 的概率相等，公式 (5.45) 可简化为：
$$
p(y | r_1) \stackrel{H_1}{\gtrless} p(y | r_0) \tag{5.46}
$$
采用公式 (5.46) 判定规则的检测器被称为“ML（最大似然，maximum likelihood）检测器”。将公式 (5.40) 中的 $p(y | r_0)$ 和公式 (5.41) 中的 $p(y | r_1)$ 代入公式 (5.46)，得：
$$
\begin{array}{rl}
\frac{1}{\sqrt{2\pi\sigma^2}} \exp \left\{ - \frac{(y - a_1)^2}{2\sigma^2} \right\} & \stackrel{H_1}{\gtrless} \frac{1}{\sqrt{2\pi\sigma^2}} \exp \left\{ - \frac{(y - a_0)^2}{2\sigma^2} \right\} \\
\exp \left\{ - \frac{(y - a_1)^2}{2\sigma^2} \right\} & \stackrel{H_1}{\gtrless} \exp \left\{ - \frac{(y - a_0)^2}{2\sigma^2} \right\}
\end{array} \tag{5.47}
$$
对公式 (5.47) 两边取自然对数 $\ln(\cdot)$，得：
$$
\begin{array}{rl}
- \frac{(y - a_1)^2}{2\sigma^2} & \stackrel{H_1}{\gtrless} - \frac{(y - a_0)^2}{2\sigma^2} \\
- \frac{y^2 - 2ya_1 + a_1^2}{2\sigma^2} & \stackrel{H_1}{\gtrless} - \frac{y^2 - 2ya_0 + a_0^2}{2\sigma^2} \\
2y(a_1 - a_0) & \stackrel{H_1}{\gtrless} a_1^2 - a_0^2 \\
y & \stackrel{H_1}{\gtrless} \frac{a_1 + a_0}{2}
\end{array} \tag{5.48}
$$

![](images/chapter_5/432a5bbd54b57e35293007c6c6b45aa1dd9f9785ed74bd94ae437d4d37d22878.jpg)

![](images/chapter_5/03cb4783ccb92b81d9984fae9d26aee18dbe6b23ddbde689d6a33ad641eb51af.jpg)
(a) $p(r_0) = p(r_1)$
(b) $p(r_0) < p(r_1)$
图 5.13: 情况 (a) $p(r_0) = p(r_1)$ 和 (b) $p(r_0) < p(r_1)$ 时的阈值 $\gamma$

因此，使检测器输出端错误概率最小的最佳阈值 $\gamma$ 为：
$$
\gamma = \frac{a_0 + a_1}{2} \tag{5.49}
$$

在 $p(r_0) \neq p(r_1)$ 的情况下，最佳阈值 $\gamma$ 根据公式 (5.45) 还取决于 $p(r_0)$ 和 $p(r_1)$。图 5.13 展示了 $p(r_0) = p(r_1)$ 和 $p(r_0) < p(r_1)$ 时的阈值示例。从图 5.13(a) 可以看出，当 $p(r_0) = p(r_1)$ 时，$\gamma$ 正好位于 $a_0$ 和 $a_1$ 的正中间。而在图 5.13(b) 中，当 $p(r_0) < p(r_1)$ 时，意味着发送端发送符号 $r_1$ 的概率高于 $r_0$。因此，$\gamma$ 距离 $a_1$ 比距离 $a_0$ 更远，从而增加了 $y(T)$ 落在 $a_1$ 区域（即 $y(T) > \gamma$）的概率，使得阈值检测器更有可能判定 $y(T)$ 为 $a_1$。然而在实践中，通常假设通信系统发送数据的概率为 $p(r_0) = p(r_1)$，使数据具有随机变量的特性，从而简化系统分析。

### 5.2.4 概率误差计算

参考图 5.13(a)，当 $p(r_0) = p(r_1)$ 时，接收端在以下情况下会发生错误：系统发送信号 $r_0(t)$，但阈值检测器判定为发送了 $a_1$（即系统内部的噪声导致 $y(T) > \gamma$）。因此：
$$
p(e | r_0) = p(H_1 | r_0) = \int_{\gamma}^{\infty} p(y | r_0) dy \tag{5.50}
$$

同样地，如果系统发送信号 $r_1(t)$，但阈值检测器判定为发送了 $a_0$（即系统噪声导致 $y(T) < \gamma$），也会发生错误。此时的错误概率为：
$$
p(e | r_1) = p(H_0 | r_1) = \int_{-\infty}^{\gamma} p(y | r_1) dy \tag{5.51}
$$

因此，整个系统（对于二进制系统）的总错误概率，或称比特误码率 (Bit Error Rate, BER)，可由下式求得：
$$
P_e = \sum_{i=0}^{1} p(e | r_i) p(r_i) = p(e | r_0) p(r_0) + p(e | r_1) p(r_1) \tag{5.52}
$$

在 $p(r_0) = p(r_1)$ 的情况下，公式 (5.52) 可简化为：
$$
P_e = \frac{1}{2} p(e | r_0) + \frac{1}{2} p(e | r_1) \tag{5.53}
$$

由于概率密度函数的对称性，$p(e | r_0) = p(e | r_1)$，因此：
$$
P_e = p(e | r_1) = p(e | r_0) = \int_{\gamma}^{\infty} p(y | r_0) dy \tag{5.54}
$$

将公式 (5.49) 中的 $\gamma$ 和公式 (5.40) 中的 $p(y | r_0)$ 代入公式 (5.54)，得：
$$
P_e = \int_{\frac{a_0 + a_1}{2}}^{\infty} \frac{1}{\sqrt{2\pi\sigma^2}} \exp \left[ - \frac{(y - a_0)^2}{2\sigma^2} \right] dy \tag{5.55}
$$

通过变量代换 $u = (y - a_0) / \sigma$，则 $dy = \sigma du$，公式 (5.55) 可整理为：
$$
\begin{array}{lll}
P_e & = & \displaystyle \int_{\frac{a_1 - a_0}{2\sigma}}^{\infty} \frac{1}{\sqrt{2\pi}} \exp \left[ - \frac{u^2}{2} \right] du \\
& = & \displaystyle Q \left( \frac{a_1 - a_0}{2\sigma} \right)
\end{array} \tag{5.56}
$$
其中 $Q$ 函数定义为 $Q(x) = \frac{1}{\sqrt{2\pi}} \int_{x}^{\infty} e^{-u^2/2} du$ [9, 36, 37]，且 $\sigma^2 = N_0 / 2$。

根据公式 (5.56)，要降低 $P_e$，需要增大 $(a_1 - a_0) / \sigma$。这可以通过设计一个匹配 $r_1(t) - r_0(t)$ 信号的接收滤波器来实现。因此，$t = T$ 时刻的信噪比 (SNR) 可以写为：
$$
\mathrm{SNR}_T = \frac{(a_1 - a_0)^2}{\sigma^2} = \frac{2 E_d}{N_0} \tag{5.57}
$$
其中 $\sigma^2 = N_0 / 2$ 是采样电路输出端噪声的平均功率，$E_d$ 是发送信号之差的能量，定义为：
$$
E_d = \int_{-\infty}^{\infty} \{ r_1(t) - r_0(t) \}^2 dt \tag{5.58}
$$

因此，公式 (5.56) 中的错误概率可以重新写为：
$$
P_e = Q \left( \frac{1}{2} \sqrt{\mathrm{SNR}_T} \right) = Q \left( \sqrt{\frac{E_d}{2N_0}} \right) \tag{5.59}
$$

公式 (5.58) 中发送信号之差的能量 $E_d$ 可以展开为：
$$
E_d = \int_0^T r_1^2(t) dt + \int_0^T r_0^2(t) dt - 2 \int_0^T r_1(t) r_0(t) dt \tag{5.60}
$$

其中，公式 (5.60) 右侧的前两项分别是信号 $r_1(t)$ 和 $r_0(t)$ 的能量（即 $E_{r1}$ 和 $E_{r0}$）。在实践中，计算通常引用“平均比特能量 (average bit energy)” $E_b$，其定义为：
$$
E_b = \frac{1}{2} \left\{ \int_0^T r_1^2(t) dt + \int_0^T r_0^2(t) dt \right\} \tag{5.61}
$$

公式 (5.60) 右侧的最后一项与互相关系数 (cross-correlation coefficient) 相关，如下所示：
$$
\rho = \frac{1}{E_b} \int_0^T r_1(t) r_0(t) dt \tag{5.62}
$$

其中 $-1 \le \rho \le 1$。将公式 (5.61) 和 (5.62) 代入公式 (5.60)，可得：
$$
E_d = 2E_b - 2E_b \rho = 2E_b(1 - \rho) \tag{5.63}
$$

![](images/chapter_5/0d69e2160ab6e8796db140c1cd586bb1fc799a7f5fc2988a7eaf2b873189cdc1.jpg)
图 5.14: 对称信号 (Antipodal signal) 的位置

因此，公式 (5.59) 可以重新写为：
$$
P_e = Q \left( \sqrt{\frac{E_b(1 - \rho)}{N_0}} \right) \tag{5.64}
$$

## 对极信号的误码率 (BER)

如果二进制信号满足 $r_0(t) = -r_1(t)$（即 $a_0 = -a_1$），这种信号形式被称为“对极信号 (antipodal signal)”，如图 5.14 所示。在这种情况下，比特能量为 $E_{r0} = E_{r1} = \sqrt{E_b}$，且互相关系数 $\rho$ 为：
$$
\rho = \frac{1}{E_b} \int_0^T r_1(t) r_0(t) dt = - \frac{1}{E_b} \int_0^T r_1^2(t) dt = -1
$$
因此，根据公式 (5.64)，使用对极信号传输数据的通信系统的 BER 为：
$$
P_e = Q \left( \sqrt{\frac{E_b(1 - (-1))}{N_0}} \right) = Q \left( \sqrt{\frac{2E_b}{N_0}} \right) \tag{5.65}
$$
由公式 (5.65) 可以看出，系统的 BER 仅取决于 $E_b/N_0$ 的值，而与发送信号 $a_0$ 和 $a_1$ 的具体波形无关。

此外，BER 也可以用数据点 $a_0$ 和 $a_1$ 之间的距离来表示。如图 5.14 所示，数据点 $a_0$ 和 $a_1$ 之间的距离为 $d_{01} = 2\sqrt{E_b}$，因此 $E_b = d_{01}^2 / 4$。

![](images/chapter_5/26581a0ec6732cd1c5e1ebc6f5b935392e63c438ea1dc93918d180acb160b75a.jpg)
图 5.15: 正交信号的位置

将此 $E_b$ 代入公式 (5.65)，得：
$$
P_e = Q \left( \sqrt{\frac{d_{01}^2}{2N_0}} \right) = Q \left( \sqrt{\frac{E_d}{2N_0}} \right) \tag{5.66}
$$
其中 $d_{01}^2 = E_d = \int_{-\infty}^{\infty} \{ r_1(t) - r_0(t) \}^2 dt$。

## 正交信号的误码率 (BER)

正交信号 (orthogonal signal) 是指满足比特能量 $E_{r0} = E_{r1} = \sqrt{E_b}$ 且互相关系数 $\rho$ 为以下值的二进制信号 $r_0(t)$ 和 $r_1(t)$：
$$
\rho = \frac{1}{E_b} \int_0^T r_1(t) r_0(t) dt = 0
$$
如图 5.15 所示，这意味着两个信号之间成 $90^\circ$ 角。在这种情况下，$d_{01} = \sqrt{2E_b}$，因此使用正交信号传输数据的通信系统的 BER 为：
$$
P_e = Q \left( \sqrt{\frac{d_{01}^2}{2N_0}} \right) = Q \left( \sqrt{\frac{E_d}{2N_0}} \right) = Q \left( \sqrt{\frac{E_b}{N_0}} \right) \tag{5.67}
$$

## BER 计算示例

**示例 5.7** 考虑一个二进制通信系统，发送的信号 $r_0(t)$ 和 $r_1(t)$ 波形如图 5.16 所示。信号 $r(t)$ 受到双边功率谱密度为 $N_0/2$ 的 AWGN 干扰，并经过匹配滤波器过滤，最后在 $t = T$ 时刻进行采样。已知 $N_0 = 10^{-12} \text{ W/Hz}$，请计算该系统的 BER。

![](images/chapter_5/dd0ff70c430d6e77d9edd177ccbe38447d0991ae718d2ac9d601acab99ae7585.jpg)
![](images/chapter_5/703aa22b629cd6d34cea1a2a861700ec0ae5e1c3297b2ca3e890bcfc856cd08f.jpg)
图 5.16: 通信系统中使用的信号 $r_0(t)$ 和 $r_1(t)$ 的波形

**解：** 从图 5.16 的信号波形可以看出，$r_0(t) = -r_1(t)$，这表明该通信系统使用了对极信号传输数据。由于对极信号的 BER 由公式 (5.65) 给出，即：
$$
P_e = Q \left( \sqrt{\frac{2E_b}{N_0}} \right)
$$
因此，在计算 $P_e$ 之前，需要先求出平均比特能量 $E_b$。首先计算信号 $r_0(t)$ 的能量：
$$
\begin{array}{lll} 
E_{r0} & = & \displaystyle \int_0^{3 \times 10^{-6}} |r_0(t)|^2 dt \\
& = & (2 \times 10^{-3})^2 (1 \times 10^{-6}) + (1 \times 10^{-3})^2 (2 \times 10^{-6}) \\
& = & 6 \times 10^{-12} \text{ Joules}
\end{array}
$$
由于 $r_0(t) = -r_1(t)$，因此信号 $r_1(t)$ 的能量与 $r_0(t)$ 相同，即 $E_{r1} = E_{r0}$。因此：
$$
E_b = \frac{E_{r0} + E_{r1}}{2} = 6 \times 10^{-12} \text{ Joules}
$$
将 $E_b$ 代入 $P_e$ 公式得：
$$
\begin{array}{lll} 
P_e & = & Q \left( \sqrt{\frac{2(6 \times 10^{-12})}{10^{-12}}} \right) \\
& = & Q(\sqrt{12}) \\
& = & 0.000266
\end{array}
$$
由此可见，系统的 BER 与信号 $r_0(t)$ 和 $r_1(t)$ 的具体波形无关。只要 $r_0(t)$ 和 $r_1(t)$ 的能量相等，无论其波形如何，系统的 BER 保持不变。

**示例 5.8** 考虑一个使用单极信号 (unipolar signaling) 的二进制通信系统，其中：
$$
\begin{array}{rcl} 
r_0(t) & = & 0, \quad 0 \le t \le T \\
r_1(t) & = & A, \quad 0 \le t \le T 
\end{array}
$$
其中 $A$ 为常数。图 5.17 展示了与数据序列 $\{1, 0, 1, 1, 0, 1, 0\}$ 相对应的信号 $r(t)$ 示例。信号 $r(t)$ 受到双边功率谱密度为 $N_0/2$ 的 AWGN 干扰，并经过匹配滤波器过滤，最后在 $t = T$ 时刻进行采样。请用 $Q$ 函数表示该系统的 BER。

![](images/chapter_5/399b99a26d5d5d6d7b2264f6f27a08a34ac3c5ca5a2f30dcd5e4b73d51a0e730.jpg)
图 5.17: 使用单极信号（或正交信号）时与数据序列 $\{1, 0, 1, 1, 0, 1, 0\}$ 相对应的信号 $r(t)$

**解：** 由于 $r_0(t)$ 和 $r_1(t)$ 满足 $\rho = \int_0^T r_1(t) r_0(t) dt = 0$，因此它们是正交信号。对于正交信号，其 BER 由公式 (5.67) 给出，即：
$$
P_e = Q \left( \sqrt{\frac{E_d}{2N_0}} \right) = Q \left( \sqrt{\frac{A^2 T}{2N_0}} \right)
$$
其中，发送信号之差的能量 $E_d$ 为：
$$
E_d = \int_0^T (A - 0)^2 dt = A^2 T
$$
同样地，BER 也可以通过平均比特能量 $E_b$ 来计算。根据公式 (5.67)：
$$
P_e = Q \left( \sqrt{\frac{E_b}{N_0}} \right) = Q \left( \sqrt{\frac{A^2 T}{2N_0}} \right)
$$
其中 $E_b = (E_{r0} + E_{r1}) / 2 = A^2 T / 2$，因为 $E_{r0} = 0$ 且 $E_{r1} = \int_0^T A^2 dt = A^2 T$。

**示例 5.9** 考虑一个使用双极信号 (bipolar signaling) 的二进制通信系统，其中：
$$
\begin{array}{rlr} 
r_0(t) & = & -A, \quad 0 \le t \le T \\
& & \\
r_1(t) & = & A, \quad 0 \le t \le T 
\end{array}
$$
其中 $A$ 为常数。图 5.18 展示了与数据序列 $\{1, 0, 1, 1, 0, 1, 0\}$ 相对应的信号 $r(t)$ 示例。信号 $r(t)$ 受到双边功率谱密度为 $N_0/2$ 的 AWGN 干扰，并经过匹配滤波器过滤，最后在 $t = T$ 时刻进行采样。请用 $Q$ 函数表示该系统的 BER。

![](images/chapter_5/1508d1b98a51c927637ee33fa3facf44442cee954637754c7729aa309a7a8d26.jpg)
图 5.18: 使用双极信号（或对极信号）时与数据序列 $\{1, 0, 1, 1, 0, 1, 0\}$ 相对应的信号 $r(t)$

**解：** 由于 $r_0(t) = -r_1(t)$，因此这两个信号是对极信号。对极信号的 BER 可由公式 (5.66) 给出，即：
$$
P_e = Q \left( \sqrt{\frac{E_d}{2N_0}} \right) = Q \left( \sqrt{\frac{2A^2 T}{N_0}} \right)
$$
其中，发送信号之差的能量 $E_d$ 为：
$$
E_d = \int_0^T [A - (-A)]^2 dt = (2A)^2 T = 4A^2 T
$$
同样地，BER 也可以通过平均比特能量 $E_b$ 来计算。根据公式 (5.65)：
$$
P_e = Q \left( \sqrt{\frac{2E_b}{N_0}} \right) = Q \left( \sqrt{\frac{2A^2 T}{N_0}} \right)
$$
其中 $E_b = (E_{r0} + E_{r1}) / 2 = A^2 T$，因为 $E_{r0} = E_{r1} = \int_0^T A^2 dt = A^2 T$。

通过示例 5.8 和 5.9 可以看出，使用双极信号的通信系统（$P_e = Q(\sqrt{2E_b/N_0})$）比使用单极信号的系统（$P_e = Q(\sqrt{E_b/N_0})$）具有更好的 BER 性能。

如图 5.19 所示，这是因为单极信号（即正交信号）在图 5.15 中的位置与双极信号（即对极信号）在图 5.14 中的位置相比，后者的比特距离更大。对极信号的比特距离大于正交信号的比特距离，这意味着检测电路做出错误判断的可能性较低，因此双极信号系统的 BER 低于单极信号系统。

![](images/chapter_5/fc717a48364fca6722481ad9589c18d98bda8b572184e056d349f6b4663ee906.jpg)
图 5.19: 使用单极信号和双极信号的二进制通信系统的 BER 性能对比

## 5.3 码间干扰

码间干扰 (ISI: intersymbol interference) 是指从发送端发送的第 $k$ 个脉冲信号对相邻脉冲信号（即第 $k-i$ 个脉冲信号，其中 $i$ 为非零整数）产生干扰或叠加的现象。要观察所使用的通信信道 (communication channel) 是否产生 ISI，可以通过向信道发送一个脉冲信号来实现。如果信道输出端的脉冲信号数量超过一个，则表明该信道产生了 ISI。

考虑图 5.20 中的离散时间信道模型。当具有比特周期 (bit period) $T$ 的输入数据序列 $a_k$ 通过由下式定义的信道 $H(D)$ 时：
$$ H(D) = \sum_{k=0}^\nu h_k D^k \tag{5.68} $$
其中 $h_k$ 是信道的第 $k$ 个系数，$\nu$ 是信道的记忆长度 (memory)（或 $\nu+1$ 为信道的抽头数 (tap)），$D$ 是 $T$ 单位的时间延迟运算符。信道的输出数据 $r_k$ 受到 AWGN $n_k$ 的干扰，其均值为零，方差为 $\sigma^2$，记作 $n_k \sim \mathcal{N}(0, \sigma^2)$。随后，检测电路将根据接收到的数据 $y_k$ 对输入数据 $a_k$ 进行估算，即求解 $\hat{a}_k$。

若规定信道 $H(D)$ 为线性时不变系统 (LTI 系统)，则信道输出 (channel output) $r_k$ 是输入数据 $a_k$ 与系统冲激响应 $h_k$ 卷积的结果，即：
$$ \begin{array}{l} r_k \\ \\ = \sum_{i=0}^\nu a_{k-i} h_i \\ = \underbrace{a_k h_0}_{\text{期望信号}} + \underbrace{a_{k-1} h_1 + \ldots + a_{k-\nu} h_\nu}_{\text{ISI}} \end{array} \tag{5.69} $$
由公式 (5.69) 可知，系统仅需要 $a_k h_0$ 项，而其他项则导致了 ISI。因此，可以说当信道的当前输出信号不仅是当前输入信号的函数，而且还是过去和未来输入信号的函数时，就会发生 ISI 现象。例如，由公式 (5.69) 可见，信道输出信号 $r_k$ 是当前输入 $a_k$ 和过去输入 $a_{k-i}$ 的函数。或者可以总结为：如果信道 $H(D)$ 没有记忆（即 $\nu = 0$），则信道输出信号将不存在 ISI。

例如，如图 5.7 所示，由于 $g(t)$ 是仅在 0 到 $T$ 时间段内有值的信道冲激响应（认为该信道没有记忆），当输入数据 $a_k$ 通过该信道时，所得信号 $r(t)$ 中不含 ISI。因此，通过观察信号 $r(t)$ 的波形，可以很容易地识别出在哪个时间段数据 $a_k$ 为比特 1 或比特 -1。但如果信道 $g(t)$ 的信号值超过了时间 $T$，则会导致产生 ISI，如图 5.21 所示。可以看出，由每个 $a_k$ 产生的脉冲信号相互重叠，使得合成信号（灰色曲线）发生畸变。因此，很难判断在哪个时间段输入数据 $a_k$ 的值是什么。

## 5.3.1 检查 ISI 的严重程度

通常，ISI 的严重程度可以通过“眼图 (eye diagram)”来观察。眼图是通过将需要显示的模拟信号在每个时间段内进行重叠绘制而成的，在硬盘驱动器领域，这被称为“比特单元 (bit cell)” $T$。如图 5.22 所示，其结果看起来像人的眼睛，因此被称为眼图。

![](images/chapter_5/08c33456330cfc32b3538829970627158dc18202e9824bbb4acfb30cb25bce2b.jpg)

![](images/chapter_5/83dab31a32d83e7d43b94975aa081eb881a867b339384466ac7213fcfa56c252.jpg)
图 5.21: 符号间干扰 (ISI) 产生示例

![](images/chapter_5/daf9da1613257e1b203849b9c26a537c0c9bd7c6b5401b2f25dcfe96cd1 la.jpg)
图 5.22: 眼图构建示例

通过眼图可以了解噪声和 ISI 的严重程度。也就是说，如果眼睛看起来很窄或闭合，则表明噪声和 ISI 非常严重；相反，如果眼睛睁得很大，则表明噪声和 ISI 较轻。

![](images/chapter_5/c7c58e772b0a48b24df4340042167a3aa2a850892ecc49f4c7de78dcf5afa6e3.jpg)
图 5.23: 眼图详解

在实际应用中，眼图可以指示最佳采样时间 (optimum sampling time)、时间误差敏感度 (sensitivity timing error)、峰值畸变 (peak distortion)、噪声裕量 (noise margin) 以及零点交叉畸变 (distortion of zero crossings)，如图 5.23 [9] 所示。可以看到，最佳采样时间位于比特单元的中心点。图 5.24 展示了信道 $H(D) = 1 - D^2$ 在不同 $\text{SNR}$ 情况下的眼图示例（在检测电路的输入端测量），其中 $\text{SNR}$ 定义为：

$$
\mathrm{SNR} = 10 \log_{10} \left( \frac{E_b}{N_0} \right) \tag{5.70}
$$

单位为分贝 (dB: decibel)，其中 $E_b$ 是每比特信号能量，$\sigma^2 = N_0/2$ 是噪声功率。可以看出，当 $\text{SNR}$ 较小时，噪声非常严重，导致眼睛几乎闭合；相反，当系统的 $\text{SNR}$ 较大时，噪声较轻，使得眼睛睁得很大。

![](images/chapter_5/f1a5c074ae9fa3c89ad73a9f3582fb166cade8341d17812fd6c632a3244a22d1.jpg)
(a) 时间

![](images/chapter_5/ef362593368a5445a5891d5b4132375bda2231338579219f14edc05c475eb734.jpg)
(b) 时间
图 5.24: 信道 $H(D) = 1 - D^2$ 在 (a) $\text{SNR} = 10 \text{ dB}$ 和 (b) $\text{SNR} = 30 \text{ dB}$ 时的眼图示例

## 5.3.2 ISI 严重程度的计算

除了利用眼图来考察 ISI 的严重程度外，信道引起的 ISI 严重程度也可以用数值计算得出。考虑图 5.20 中的通信系统模型，信道的输出数据 $r_k$ 可以通过数学方程表示，如式 (5.69) 所示，即：

$$
r_k = a_k * h_k = \sum_{i=0}^\nu a_{k-i} h_i
$$

因此，ISI 的严重程度可以通过以下公式计算：

$$
\xi = \frac{\sum_k |h_k| - \max_k |h_k|}{\max_k |h_k|} \tag{5.71}
$$

其中 $\max_k |h_k|$ 是 $h_k$ 可能的最大值。如果 $\xi = 0$，意味着信道不产生 ISI；如果 $\xi > 0$，则意味着信道会产生 ISI，且 $\xi$ 值越大，表示 ISI 的严重程度越高。

示例 5.10 请比较信道 $H_1(D) = 1 - D^2$ 和 $H_2(D) = 1 + D - D^2 - D^3$ 哪个产生的 ISI 更多。

解：根据题目给定条件，信道 $H_1(D)$ 的 $\xi_1$ 值为：

$$
\xi_1 = \frac{(|1| + |0| + |-1|) - |1|}{|1|} = 1
$$

而信道 $H_2(D)$ 的 $\xi_2$ 值为：

$$
\xi_2 = \frac{(|1| + |1| + |-1| + |-1|) - |1|}{|1|} = 3
$$

由于 $\xi_2 > \xi_1$，说明信道 $H_2(D)$ 产生的 ISI 比信道 $H_1(D)$ 更多。这可以用一个通用原理来解释：在两个信道能量相同的情况下，具有更多抽头（或记忆长度）的信道更有可能产生更多的 ISI。

## 5.3.3 ISI 对误码率的影响

在本节中，将探讨 ISI 对误码率 (BER) 的影响。考虑图 5.20 所示的通信系统模型。通常，随着系统 SNR 的增加，其在 BER 方面的整体性能会提高（即 BER 降低）。因此，假设系统 A 是一个没有 ISI 的系统，其 BER 性能遵循图 5.25 中的曲线 A。如果增加噪声强度，该系统的 BER 将变为曲线 B。这意味着，如果希望新系统的 BER 维持在与原系统相同的水平（例如 $\mathrm{BER} = 10^{-5}$），则必须增加新系统的 SNR，如图 5.25(a) 中箭头所示。然而，如果系统中存在 ISI（即 $\nu > 0$），系统的 BER 将变为曲线 C。这意味着当系统达到一定的 BER 水平时，无论如何增加 SNR，BER 也不再降低。这种现象被称为“误码平台 (error floor)”。

![](images/chapter_5/341c42cb1446dfb19a3dda8e13e7147c7bd35fc062312abc303c3cd682121fef.jpg)

![](images/chapter_5/05fece585e759108e2656f0a98d44074abdd86f0fff2a45a532221cf29f30690.jpg)  
图 5.25：(a) 仅有噪声系统和 (b) 同时具有噪声 and ISI 系统的误码率 (BER)

总之，如果系统仅受噪声干扰（没有 ISI），增加 SNR 将始终降低 BER。但如果系统中存在 ISI，随着 SNR 的增加，BER 仅降低到一定水平，之后无论如何增加 SNR，BER 也不再降低。因此，必须寻找方法尽可能地消除或减轻系统中的 ISI 影响，以提高系统在增加 SNR 时的整体效率。其中一种减轻 ISI 影响的方法是使用均衡器 (Equalizer)，这将在 5.6 节中详细讨论。

## 5.4 奈奎斯特定理

考虑图 5.26 中的实际信道模型 (realistic channel model)，其中 $a_k$ 是输入数据序列，$G_t(f)$ 是频域中的发送滤波器 (transmitting filter)，$G_c(f)$ 是频域中的信道，$G_r(f)$ 是频域中的接收滤波器 (receiving filter)，而 $n(t)$ 是噪声。定义：

$$
G(f) = G_t(f) G_c(f) G_r(f) \tag{5.72}
$$

![](images/chapter_5/929547498eca2f3653f909bc167faa76359fb859e6eb77c0ee0ca901bc15ddfb.jpg)
图 5.26: 实际信道模型

这是整个系统的总频率响应，其在时域中的傅里叶变换对为 $g(t)$，即 $g(t) \Longleftrightarrow G(f)$。于是，信号 $r(t)$ 可以表示为如下数学方程：

$$
r(t) = \sum_m a_m g(t - mT) + n(t) \tag{5.73}
$$

其中 $n(t)$ 是经过滤波的噪声，其傅里叶变换为 $N(f) = W(f) G_r(f)$，而 $W(f)$ 是 $w(t)$ 的傅里叶变换。

随后，采样电路 (sampler) 在时间 $t_k = kT$（其中 $k$ 为整数）对信号 $r(t)$ 进行采样，即：

$$
\begin{array}{lcl}
r_k = r(t)|_{t=kT} = r(kT) & = & \sum_m a_m g(kT - mT) + n(kT) \\
& = & a_k g(0) + \sum_{m \neq k} a_m g(kT - mT) + n(kT)
\end{array} \tag{5.74}
$$

其中 $n(kT)$ 是 $kT$ 时刻的噪声幅度。方程 (5.74) 右侧的第一项是系统所需的数据，而第二项则是系统产生的 ISI。在理想情况下，接收电路希望采样电路的输出信号 $r(kT)$ 等于 $a_k g(0) + n(kT)$（即没有 ISI），这样就可以使用简单的检测电路（如边沿检测电路）来对数据 $r_k$ 进行解码，从而降低检测电路的构建成本。然而，要实现 $r(kT) = a_k g(0) + n(kT)$，必须满足：

$$
g(kT) = \begin{cases} 1, & k = 0 \\ 0, & \text{else} \end{cases} \tag{5.75}
$$

因为这样可以使方程 (5.74) 右侧的第二项为零。

具有方程 (5.75) 特性的脉冲信号通常被称为“奈奎斯特脉冲 (Nyquist pulse)”。在通信系统中，比较重要的奈奎斯特脉冲可分为以下三种类型：

1) 理想奈奎斯特脉冲 (ideal Nyquist pulse)
2) RC 脉冲 (raised-cosine)
3) RRC 脉冲 (root-raised cosine)

详细内容如下。

## 5.4.1 理想奈奎斯特脉冲

理想奈奎斯特脉冲 $g_I(t)$ 定义为：

$$
g_I(t) = \operatorname{sinc}\left(\frac{t}{T}\right) = \frac{\sin(\pi t / T)}{\pi t / T} \tag{5.76}
$$

其中 $\operatorname{sinc}(t)$ 是 sinc 函数，其信号形状如图 5.27(左) 所示。可以看出，理想奈奎斯特脉冲 $g_I(t)$ 符合方程 (5.75) 的要求，即当 $k=0$ 时 $g_I(kT) = 1$，且当 $k$ 为任何不等于零的整数时 $g_I(kT) = 0$。如果使用连续时间傅里叶变换将信号 $g_I(t)$ 转换为频域信号，结果为：

$$
G_I(f) = T \Pi(fT) \tag{5.77}
$$

![](images/chapter_5/da5031a681327a46695a5532fb9cdcac463a575e31211cb0c36984043d05fecd.jpg)
图 5.27: 理想奈奎斯特脉冲的傅里叶变换对

其中 $\Pi(fT)$ 是频域中的矩形脉冲，定义为：

$$
\Pi(fT) = \begin{cases} 1, & -\frac{1}{2T} \le f \le \frac{1}{2T} \\ 0, & \text{else} \end{cases} \tag{5.78}
$$

如图 5.27(右) 所示。

理想奈奎斯特脉冲在“模拟信号重建 (analog signal reconstruction)”中具有重要意义。例如，考虑图 5.28 中的三个模拟信号 A、B 和 C，其中 $T$ 为比特周期。如果在 $t = kT$ ($k = 1, 2, 3, 4$) 时对这三个模拟信号进行采样，将得到相同的 4 比特采样数据 $\{1, 1, -1, 1\}$（见图 5.28）。然而，如果尝试根据采样数据 $\{1, 1, -1, 1\}$ 重建模拟信号，则只有一种模拟信号能够被原样重建，这符合采样定理：[9, 38] “只有当采样频率大于或等于模拟信号最高频率的两倍时，采样得到的数据才与原模拟信号等效”。（详情见 5.5 节）。在实际操作中，可以通过将采样数据送入理想低通滤波器来重建模拟信号，这相当于将采样数据与 sinc 函数（理想奈奎斯特脉冲）进行卷积。图 5.29 展示了由采样数据 $\{1, 1, -1, 1\}$ 重建的模拟信号。可以看出，只要系统中不存在时间抖动 (timing jitter)，相邻比特产生的脉冲信号就不会在采样点处干扰所需比特的信号。

![](images/chapter_5/a21d42c471af79cc7c964c4184a2a7449fabea71277a73e507eeba9672f1.jpg)
图 5.28: 三个在 $t = kT$ 采样后均得到采样数据 $\{1, 1, -1, 1\}$ 的模拟信号

![](images/chapter_5/be868a7b8032b0061e9a9f7ea2b61f9914496303980f352dd5c11597f21e4569.jpg)
图 5.29: 多个相隔一个比特单元的理想奈奎斯特脉冲之和

## 5.4.2 理论最小带宽

信号的带宽 (bandwidth) 是指幅度谱不为零的正频率范围，单位为赫兹 (Hz: hertz)。例如，根据图 5.30 可知，基带信号 (baseband signal) 的带宽为 $W = f_{\text{max}}$，而带通信号 (bandpass signal) 的带宽为 $W = 2 f_{\text{max}}$。此外，带宽有多种定义方式，具体取决于给定的条件，例如零点到零点带宽 (null-to-null bandwidth)、3 dB 带宽 (3-dB bandwidth) 或半功率带宽 (half-power bandwidth) 等。因此，在确定信号带宽之前，必须明确所需的带宽定义类型，因为不同类型的带宽数值有所不同。

![](images/chapter_5/b80fc6ef78084a975e4ed6b82f380d14e35657676bd5e6328561a7cab64788f3.jpg)
图 5.30: (左) 基带信号 和 (右) 带通信号 的带宽

本书仅考虑零点到零点带宽。考虑用于通信系统的脉冲信号（如图 5.27 所示），在理论上 [9]，以符号率 $R_s$ (symbols per second) 发送数据且无 ISI 时，所需的最小带宽 (minimum bandwidth) $W_0$ 为：

$$
W_0 = \frac{R_s}{2} \quad (\text{Hz}) \tag{5.79}
$$

其中 $R_s = 1/T$，$T$ 为符号周期 (symbol period)。此外，可以通过“带宽效率 (bandwidth efficiency)” $\eta$ 来衡量系统的带宽利用率，定义为：

$$
\eta = \frac{R_s}{W_0} \tag{5.80}
$$

单位为比特每秒每赫兹 (bits/second/hertz)。也就是说，$\eta$ 值越大，表明带宽利用率越高。例如，理想奈奎斯特脉冲的最小带宽为：

$$
W_0 = \frac{1}{2T} = \frac{R_s}{2} \quad (\text{Hz})
$$

其带宽效率为：

$$
\eta = \frac{R_s}{R_s/2} = 2 \quad (\text{bits/second/Hz})
$$




