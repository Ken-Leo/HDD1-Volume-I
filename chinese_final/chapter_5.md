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












