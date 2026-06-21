
## 6.1 引言

如今，各种电子设备，如计算机、手机、便携式音乐播放器和数字相机等，对数据存储空间的需求日益增长。数字磁记录（digital magnetic recording）技术被认为是各种应用（application）中存储数据的主要方法，包括硬盘驱动器（hard disk drive）、软盘（floppy disk）和磁带（magnetic tape）。然而，所有这些应用都基于相同的基本工作原理，涉及读写头（read head）、写头（write head）和磁存储介质（magnetic media），如图 6.1 所示。其中，电感式读写头（inductive head）由具有低矫顽力（coercivity）和高磁导率（permeability）的磁性材料制成 [1]，周围绕有线圈；而存储介质通常由具有高矫顽力的磁性材料制成。

![](images/chapter_6/567a922e6b00b84186e82f21962f5ccf040a0c0a39b8795ab2b_b1ccf246c6fbbb.jpg)

本书将重点讲解两种记录技术：纵向记录（longitudinal recording）和垂直记录（perpendicular recording）。纵向记录是过去硬盘驱动器所采用的技术，其存储介质的磁化方向与磁盘平面平行，如图 6.1 所示。而垂直记录技术已开始在目前的硬盘驱动器中采用，其存储介质的磁化方向与磁盘平面垂直。目前，垂直记录技术的研究进展迅速，因为与纵向记录技术相比，它可以将硬盘驱动器的存储容量提高数十倍 [19]。

硬盘驱动器中的数字数据存储系统（digital data storage system）可以用一个通用框图来模拟，如图 6.2 所示。信息比特（message bits）首先由“纠错码编码器（error-correction code (ECC) encoder）”进行编码，目前硬盘驱动器中常用的纠错码是 RS 码（Reed-Solomon code）[42, 43]。随后，编码后的数据再次通过“调制编码器（modulation encoder）”进行编码，以调整数据的特性使其适应硬盘驱动器的信道，例如使数据序列符合特定格式或消除直流分量（d.c. component）等。调制编码器中常用的编码方式是 RLL 码（run-length limited code）[44]。调制编码器的输出数据被视为将要写入存储介质的数据，称为“记录比特（recorded bit）”。之后，记录比特被发送至“调制器（modulator）”，将其转换为写电流波形（write current waveform），然后由写头将该波形写入存储介质中。

在读取数据阶段，当读写头移动到磁化方向发生变化的区域时（见图 6.1），读写头将从存储介质中读取数据，输出一个电压波形信号，称为“回读信号（read-back signal）”。关于写入和读取过程的详细说明将在 6.2 和 6.3 节中分别讨论。随后，回读信号被送入读取信道（read channel）进行处理，读取信道包含以下组件：低通滤波器（LPF: low-pass filter）、采样电路（sampler 或 analog-to-digital converter）、均衡器（equalizer）和检测器（detector）等。最终的输出数据由调制解码器（modulation decoder）和纠错码解码器（ECC decoder）进行解码，以恢复所需的原始信息比特。

![](images/chapter_6/904a57667172c09a96c1cc7d183127516e3b5607e40bd397dcf5d0d2b83e4a92.jpg)  
图 6.2: 硬盘驱动器数字数据存储系统的通用模型
